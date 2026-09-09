# StageDesk - Connexion directe aux consoles / Direct console networking

## Français

StageDesk Desktop communique directement sur le LAN, sans DMT ni Mixing Station.
La connexion, la détection, la lecture et l'envoi sont toujours des actions explicites.
Ces connecteurs ont des tests logiciels sur de vraies sockets TCP/UDP locales ;
aucune console physique n'a été validée pour cette livraison. Faites une recette
hors antenne sur votre modèle et votre firmware avant utilisation en production.

### Compatibilité réseau

| Famille | Port par défaut | Lecture et écriture des entrées |
|---|---|---|
| Yamaha DM7 / RIVAGE PM | TCP 49280 | Labels, couleurs, icônes, DCA, HPF, mute et fader ; relecture |
| Yamaha CL / QL | TCP 49280 | Labels, couleurs, icônes, DCA, mute et fader ; relecture ; pas de HPF |
| Yamaha TF / DM3 | TCP 49280 | Labels, couleurs, icônes, mute et fader ; relecture ; pas de DCA/HPF |
| Allen & Heath dLive / Avantis | TCP 51325 | Lecture labels/couleurs ; écriture labels/couleurs relues ; DCA/mute/fader envoyés sans relecture ; HPF dLive seulement, sans relecture |
| Behringer X32 / Midas M32 | UDP 10023 | Labels, couleurs, icônes, DCA, HPF, mute et fader ; relecture ; 32 entrées |
| Behringer WING | UDP 2223 | Labels, couleurs, icônes, mute et fader ; relecture ; 40 canaux + 8 aux ; pas de DCA/HPF |

La capacité du modèle choisi s'applique. dLive reste limité à 128 entrées et
Avantis à 64, même en dPack. Le canal MIDI de base A&H doit correspondre à celui
de la console : 1 à 12, défaut 12. Les labels sont limités à 8 caractères ASCII
sur dLive/Avantis/TF/DM3, 12 sur X32/M32, 16 sur WING ; CL/QL autorise 8 octets UTF-8.
Les valeurs non prises en charge restent décochées à l'import. Un résultat
« envoyé sans relecture » ne signifie pas « vérifié ».

### Connexion et transfert

1. Choisissez la famille, le modèle exact et le mode **Réseau** en source ou destination.
2. Utilisez l'IP de contrôle de la console, pas celle de sa carte Dante. En
   Simulation, aucune socket n'est ouverte. Décochez Simulation pour communiquer.
3. Saisissez l'IP/hôte ou cliquez **Détecter**. Choisissez votre interface puis
   démarrez explicitement la recherche. Elle est limitée au port et à la famille
   choisis, à un bloc local /24 au maximum (253 autres hôtes), sans scan automatique.
   Utilisez une IP manuelle pour un autre bloc, VLAN ou une interface /31-/32.
4. **Tester** demande une réponse au protocole. Ce n'est ni une authentification
   ni une certification de modèle/firmware ; A&H ne fournit ici aucune identité fiable.
5. **Lire Current** importe l'état courant. En destination, contrôlez **Inclure**
   et les cases sous **Détails**, puis **Envoyer**. Une relecture immédiate prépare
   les différences ; les champs relus sont sauvegardés avant la confirmation finale.
6. Vérifiez le rapport et la console. **Arrêter** cesse les commandes suivantes,
   mais n'annule pas celles déjà envoyées. Une erreur peut laisser un envoi partiel.

WING : modifier l'apparence d'un canal lié à sa source (`clink`) détache ce lien
cosmétique en préservant les champs visibles non cochés. Le routage est inchangé.
Les lectures/écritures ne sont pas atomiques : aucun autre opérateur ou logiciel
ne doit modifier les mêmes paramètres pendant le transfert.

### Scènes et snapshots

L'envoi normal agit sur **Current**, jamais implicitement sur une scène sauvegardée.
Yamaha, dLive, Avantis et WING utilisent leurs fichiers natifs pour les snapshots
sauvegardés, ou une mémorisation effectuée depuis la console après contrôle.

X32/M32 propose deux actions distinctes, hors Simulation :

- **Importer une scène** liste les emplacements 000-099 sans rappel. Après choix,
  sauvegarde des champs relisibles de Current et confirmation spécifique, la scène
  est rappelée puis Current relu. Cela peut changer tout le mix, gains, routage,
  effets, mutes et niveaux. Les Safes s'appliquent. Aucun retour automatique à
  l'état précédent ; pas de lecture invisible d'une scène enregistrée.
- **Mémoriser Current** enregistre tout le mix de la console, pas seulement le
  tableau StageDesk, dans un emplacement vide nommé (ASCII, 1 à 16 caractères).
  Envoyez d'abord vos modifications. Les slots occupés sont refusés et revérifiés
  juste avant l'envoi. Le protocole ne permet pas de réservation atomique : aucun
  autre opérateur ne doit mémoriser dans ce slot simultanément. Une réponse perdue
  ne déclenche jamais de répétition automatique du rappel ou de la mémorisation.

### Sauvegarde et sécurité

Gardez d'abord un **show constructeur complet**. La sauvegarde `.smt` + `.sha256`
contient seulement les champs effectivement lus : ce n'est ni un show complet
ni un rollback. Son chemin figure dans la confirmation ; elle se rouvre en Simulation.

- Windows : `%LOCALAPPDATA%/SMT/NetworkBackups`.
- macOS : `~/Library/Application Support/SMT/NetworkBackups`.

Isolez le réseau de contrôle : ces protocoles ne sont ni chiffrés ni authentifiés.
N'exposez pas leurs ports à Internet. Les autres familles conservent les parcours
fichier ; un port ouvert ou un éditeur hors ligne ne prouve pas un transfert réseau.

## English

StageDesk Desktop connects directly over the LAN, without DMT or Mixing Station.
The table above lists the supported fields and default ports. Software tests use
real local TCP/UDP sockets; **no physical console was validated for this release**.
Test off-air on your model and firmware before production use.

Select the exact family/model and Network. Use the console control IP, not the
Dante card IP. Simulation opens no socket. Discover requires an interface and an
explicit start; it checks only the selected family/port on at most the local /24
block (253 other hosts). Other blocks, VLANs and /31-/32 interfaces need manual IP.
Test requires a protocol response, not just an open port. Protocol replies are
not authentication; A&H does not provide reliable model identity here.

Read Current imports the live state. Check Include and each field under Details
before Send. StageDesk rereads Current, calculates supported differences, backs
up readable fields, then requests live-write confirmation. Stop cancels future
commands only; already sent changes remain. Read/write operations are not atomic:
no other operator or application should change the same parameters during transfer.

Yamaha and OSC writes use readback. A&H reads labels/colours only; DCA, mute,
fader and dLive-only HPF writes are sent **without readback**. Sent is not verified.
Its base MIDI channel must match (1-12, default 12); network capacity is limited
to 128 dLive / 64 Avantis inputs, including dPack. WING uses 40 channels + 8 aux;
editing linked appearance detaches `clink` while preserving visible unchecked
fields and routing. TF/DM3/WING omit network DCA/HPF; CL/QL omits HPF.

Ordinary sending changes Current, not stored snapshots. Yamaha, dLive, Avantis
and WING saved snapshots use native files or storage from the console itself.
X32/M32 additionally lists slots 000-099 without recall. Import scene requires a
separate whole-mix recall confirmation and a backup of readable fields, then
reads Current; safes apply and the console stays in that state. Store Current
saves the console's entire mix into a freshly checked empty slot (1-16 ASCII
character name). Occupied slots are refused, but the protocol has no atomic slot
reservation: never store to the same slot from another controller simultaneously.
Recall/store is sent once; a lost reply is never retried automatically.

Keep a complete vendor show before writing. The `.smt` + SHA-256 backup includes
only fields actually read, not routing, gains, phantom power, processing or
scenes. It reopens in Simulation and is not an automatic rollback. Paths are
listed above and in the confirmation. Isolate the unauthenticated, unencrypted
control network; never expose console control ports to the Internet.

## Références d'interopérabilité / Interoperability references

- [Allen & Heath - external TCP/IP control](https://support.allen-heath.com/hc/en-gb/articles/37282561723537-External-Control-integrating-A-H-systems-in-TCP-IP-environments)
- [Allen & Heath - dLive MIDI over TCP V1.9](https://www.allen-heath.com/content/uploads/2023/05/dLive-MIDI-Over-TCP-Protocol-V1.9.pdf)
- [Yamaha RCP - Bitfocus protocol integration and parameter lists](https://github.com/bitfocus/companion-module-yamaha-rcp)
- [Patrick-Gilles Maillot - X32 OSC documentation](https://sites.google.com/site/patrickmaillot/x32)
- [Patrick-Gilles Maillot - WING remote documentation](https://sites.google.com/site/patrickmaillot/wing)

Ces références ne constituent ni une certification ni un partenariat constructeur.
These references do not constitute vendor certification or a partnership.
