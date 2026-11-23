# StageDesk - Connexion directe aux consoles / Direct console networking

## Français

StageDesk Desktop communique directement sur le LAN, sans DMT ni Mixing Station.
La connexion, la détection, la lecture et l'envoi sont toujours des actions explicites.
Ces connecteurs ont des tests logiciels sur de vraies sockets TCP/UDP locales ;
aucune console physique n'a été validée pour cette livraison. Faites une recette
hors antenne sur votre modèle et votre firmware avant utilisation en production.

### Compatibilité réseau

| Famille | Protocole et port par défaut | Lecture et écriture des entrées |
|---|---|---|
| Yamaha DM5 / DM5 Compact | Yamaha RCP sur TCP 49280 | 60 ou 48 entrées selon modèle ; labels UTF-8, couleurs, icônes, DCA, coupe-bas, mute et fader avec relecture |
| Yamaha DM7 / RIVAGE PM | Yamaha RCP sur TCP 49280 | Labels, couleurs, icônes, DCA, HPF, mute et fader ; relecture |
| Yamaha CL / QL | Yamaha RCP sur TCP 49280 | Labels, couleurs, icônes, DCA, mute et fader ; relecture ; pas de HPF |
| Yamaha TF / DM3 | Yamaha RCP sur TCP 49280 | Labels, couleurs, icônes, mute et fader ; relecture ; pas de DCA/HPF |
| Allen & Heath dLive | MIDI sur TCP 51325 | Labels, couleurs, mute et fader lus et relus. DCA et HPF envoyés sans relecture. |
| Allen & Heath Avantis | MIDI sur TCP 51325 | Labels et couleurs lus et relus. DCA, mute et fader envoyés sans relecture. |
| Allen & Heath SQ-5 / SQ-6 / SQ-7 / SQ-Rack, firmware 1.6 | MIDI sur TCP 51325 | Mutes d’entrée Current, avec relecture. Vue LR en lecture seule : affectation, panoramique et code de niveau de l’entrée choisie. IP saisie manuellement. |
| Behringer X32 / Midas M32 | OSC sur UDP 10023 | Labels, couleurs, icônes, DCA, HPF, mute et fader ; relecture ; 32 entrées |
| Behringer WING | OSC sur UDP 2223 | Labels, couleurs, icônes, mute et fader ; relecture ; 40 canaux + 8 aux ; pas de DCA/HPF |
| Lawo mc²36 MKII 32 / mc²56 MKIII / mc²96, mxGUI 12.4.0.0 | Port Ember+ configuré explicitement, aucun défaut | Labels DSP Current uniquement, 63 octets UTF-8, noms courts conservés ; deux relectures fraîches ; pas de rappel/stockage de snapshot |

Le [complément Lawo](LAWO_NATIVE_AND_NETWORK.md) précise les profils, le seed
natif privé et les limites de ce connecteur. Le mc²66 MKII 5.14 reste sur fichier.

La capacité du modèle choisi s’applique. dLive prend en charge 128 entrées.
Choisissez **Avantis** ou **Avantis Solo** pour 64 entrées, ou la variante **dPack**
correspondante pour 96 entrées avec le firmware V2 et dPack actif. Le test du
profil dPack vérifie la réponse de l’entrée 96. Le canal MIDI de base doit
correspondre à celui de la console (1 à 12, 12 par défaut). Les labels sont limités à 8 caractères ASCII
sur dLive/Avantis/TF/DM3, 12 sur X32/M32, 16 sur WING ; CL/QL autorise 8 octets UTF-8.
Pour SQ 1.6, renseignez l’adresse de contrôle du modèle sélectionné et son canal
MIDI de 1 à 16. Cliquez sur « Afficher le routage » pour lire l’affectation de
l’entrée choisie au LR, son panoramique et son code de niveau. La loi de fader
configurée sur la console détermine l’équivalence en dB. Les labels et les
scènes enregistrées passent par le fichier de show. [Protocole Allen & Heath](https://support.allen-heath.com/hc/en-gb/articles/47793519540497-SQ-MIDI-Protocol-Firmware-V1-6)

Les valeurs non prises en charge restent décochées à l'import. Un résultat
« envoyé sans relecture » ne signifie pas « vérifié ».

### Connexion et transfert

#### dLive Director et Avantis Director

- Sur Windows ou Mac, ouvrez votre show dans Director. Dans StageDesk,
  sélectionnez dLive ou Avantis et le mode **Réseau**, puis cliquez sur
  **Director sur ce PC**. StageDesk teste le port MIDI/TCP local `127.0.0.1:51325`
  en lecture et renseigne le canal MIDI de base. Cette adresse est indépendante
  du réseau Wi-Fi. Fermez l’autre Director si les deux éditeurs sont ouverts.
- Pour joindre directement la console, saisissez son IP de contrôle ou cliquez
  sur **Détecter sur le réseau…** et choisissez l’interface appropriée. Pour dLive
  et Avantis, choisissez un résultat pour remplir l’adresse et le canal MIDI. En
  saisie manuelle, indiquez le canal de base du système distant. Si Director est
  relié à une console, vérifiez son état avant d’envoyer des changements.
- Le transfert réseau porte sur **Current**. Pour lire une scène, rappelez-la
  dans Director ou sur la console, puis cliquez sur **Lire Current**. Pour
  conserver un envoi dans une scène, vérifiez le résultat et enregistrez la
  scène dans Director ou sur la console. **Show enregistré…** ouvre le fichier
  du show pour choisir la scène et effectuer un transfert sans rappel sur le système.
- Avant chaque transfert réseau, la fenêtre **Paramètres à envoyer** permet
  d’écarter en une fois un type de donnée pour tous les canaux inclus. Elle
  respecte les cases de chaque ligne et les capacités du profil choisi.

Le raccourci local reprend le principe documenté par
[dLive MIDI Tools](https://github.com/togrupe/dlive-midi-tools/blob/main/doc/usage.md#console-selection--connection-settings).
Sous Windows, dLive Director 2.12 a fourni les 128 entrées en lecture.
Avantis Director 2.02, en mode hors ligne Avantis puis Avantis Solo sur le
show usine FOH dPack, a fourni les 96 entrées. Les noms et couleurs des
entrées 65 et 96 ont été envoyés, relus puis rétablis dans les deux modes.
Les connexions à Director sous macOS et aux consoles physiques restent à vérifier.

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

Pour dLive ou Avantis, enregistrez la préparation StageDesk pour retrouver
l’adresse, le port et le canal MIDI. L’aperçu liste les paramètres cochés à
modifier, avec la valeur avant envoi si elle a été lue. Pour le fader, il affiche
le palier MIDI qui sera envoyé. Un palier reçu inconnu est signalé. Les champs
identiques déjà relus sont écartés. Une nouvelle lecture des valeurs connues
et sélectionnées précède la première commande et annule l’envoi si l’une a
changé. Pour adapter la sélection, fermez l’aperçu et ajustez les cases dans
**Détails**. Vérifiez manuellement les champs dont la relecture est indisponible.

WING : modifier l'apparence d'un canal lié à sa source (`clink`) détache ce lien
cosmétique en préservant les champs visibles non cochés. Le routage est inchangé.
Les lectures/écritures ne sont pas atomiques : aucun autre opérateur ou logiciel
ne doit modifier les mêmes paramètres pendant le transfert.

Sur WING, **Voir le routage Current…** propose une entrée, un bus ou un
Main, en source ou destination. Une entrée affiche ses sources et ses
16 départs bus. Un bus ou Main affiche ses 8 départs vers les matrices.
La fenêtre présente l’activation, le niveau et le point de prélèvement.
Les valeurs de Current sont lues successivement.

Sur X32/M32, le même bouton affiche l’indice de source d’une tranche,
son lien stéréo et ses 16 départs bus. La vue indique le niveau,
l’activation et le lien des bus. Le type commun à chaque paire apparaît
sous forme de code OSC. L’indice d’entrée ne détaille pas le patch physique.

Sur dLive, sélectionnez une tranche puis un auxiliaire mono ou stéréo
déjà configuré sur le MixRack. StageDesk lit l’activation du départ et
son niveau brut MIDI avec le protocole dLive v2.0. Le point pré/post,
le patch physique et la configuration du bus ne font pas partie de cette lecture.

Pour convertir les départs d’une scène X32/M32 v4.0 vers WING, ouvrez
la scène dans **Récupérer**, choisissez **Réseau** pour la WING de
destination, puis **Convertir les départs X32/M32…**. Associez une tranche
source à une tranche mono WING, un bus à un bus, ou un Main à un Main.
Cochez les départs voulus dans l’aperçu. Les départs pré-fader d’une
tranche exigent le point PFL standard. Pour un bus ou un Main, les
matrices sont associées par numéro. Les matrices 7 et 8 de la WING
restent en place.
L’envoi sauvegarde les valeurs relues dans `NetworkBackups`, vérifie à
nouveau Current, applique les changements approuvés et relit le routage
de la source, y compris le patch de la tranche et les départs hors sélection.

Dans l’autre sens, choisissez une source **WING → Réseau** et une scène
X32/M32 v4.0 de destination. **Convertir les départs WING…** lit une
tranche Current, affiche ses départs et crée une copie de la scène pour
la tranche X32/M32 choisie. Le plan et la relecture accompagnent la copie.
Le patch X32/M32 provient de la scène de destination.

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

### dLive Director and Avantis Director

Open the show in Director. Select dLive or Avantis in **Network** mode and click
**Director on this computer** on Windows or Mac. StageDesk checks local MIDI/TCP
at `127.0.0.1:51325` with read requests and fills in the base MIDI channel. Close
the other editor if both Directors are running. For a direct console connection,
enter the control IP and base MIDI channel or use **Discover on network…**.
Selecting a discovery result fills in both values.

The network workflow exchanges **Current**. Recall a scene in Director or on the
console and then use **Read Current**. After sending checked changes, store the
desired scene in Director or on the console. **Saved show…** opens the show file
for selecting and transferring a stored scene without recalling it on the system.
The **Settings to send** window filters the prepared fields for the transfer.
The filters apply to the included channels and follow the selected network profile.
On Windows, offline dLive Director 2.12 exposed all 128 inputs for reading.
Offline Avantis Director 2.02 exposed all 96 inputs in both Avantis and
Avantis Solo modes with the FOH dPack factory show. Input names and colours
were sent, read back and restored on inputs 65 and 96 in both modes.
Director connectivity on macOS and physical console verification are pending.

StageDesk Desktop connects directly over the LAN, without DMT or Mixing Station.
The table above lists the supported fields and default ports. Software tests use
real local TCP/UDP sockets; **no physical console was validated for this release**.
Test off-air on your model and firmware before production use.

The [Lawo supplement](LAWO_NATIVE_AND_NETWORK.md) covers the connector's native
profiles and Ember+ workflow: mc²36 MKII 32, mc²56 MKIII and mc²96 on mxGUI
12.4.0.0 only, explicit configured port, DSP Current labels, 63-byte UTF-8,
short names preserved and two fresh readbacks. No network snapshot recall/store;
mc²66 MKII 5.14 stays file-only. Physical-console qualification remains pending.

For SQ classic firmware 1.6, enter the control IP and the MIDI channel (1–16).
Current input mutes support confirmed writes and readback. The routing view
shows the chosen input’s LR assignment, pan and native level code. The console’s
fader law determines dB. Use the show file for names and saved scenes.
[Allen & Heath protocol](https://support.allen-heath.com/hc/en-gb/articles/47793519540497-SQ-MIDI-Protocol-Firmware-V1-6)

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

Yamaha and OSC writes use readback. dLive reads and verifies labels, colours,
input mute and supported fader steps. Avantis reads and verifies labels and colours.
DCA and dLive-only HPF use send only, as do Avantis mute and fader. Check those
fields manually. The base MIDI channel must match (1-12, default 12). dLive supports
128 inputs. Select **Avantis** or **Avantis Solo** for 64 inputs, or the matching
**dPack** model for 96 inputs with firmware V2 and dPack active. Testing the dPack
profile checks the response from input 96. WING uses 40 channels + 8 aux;
editing linked appearance detaches `clink` while preserving visible unchecked
fields and routing. TF/DM3/WING omit network DCA/HPF; CL/QL omits HPF.

Save a StageDesk preparation to reopen its address, port and MIDI channel.
The dLive and Avantis preview lists checked changes next to the value read from
the mixer when available. It displays the fader step that will be sent and
flags unknown steps received from the console. Matching values already read
from the mixer are skipped. StageDesk rereads known selected values before the
first write and cancels the send if one changed. To revise the selection, close
the preview and adjust the boxes under **Details**.

On WING, **View Current routing…** lets you choose an input, bus or Main
on a source or destination console. An input shows its patch and 16 bus
sends. A bus or Main shows its eight matrix sends. Current values are read
one at a time, including enabled state, level and tap point.

On X32/M32, the same button shows one input’s source index and stereo
link status, its 16 bus sends, and each bus pair’s link status. The
shared tap is displayed as an OSC code. The input index leaves the
physical patch unresolved.

On dLive, choose an input and an existing mono or stereo auxiliary bus
on the MixRack. StageDesk reads the send assignment and raw MIDI level
using the dLive v2.0 protocol. The tap, physical patch and bus configuration
are outside this read operation.

To convert sends from an X32/M32 v4.0 scene to WING, open the scene as the
source, choose a WING network destination, and select **Convert X32/M32
sends…**. Match one input to a mono WING input, a bus to a bus, or a Main
to a Main. Select the sends in the preview. Input pre-fader sends require
the standard PFL tap. Matrix sends match by number. WING matrices 7 and 8
keep their existing values.
StageDesk saves the initial routing values, checks Current again, applies
the approved changes, and reads back the source, its other sends and
its input patch when applicable.

For the reverse direction, use a WING network source and an existing
X32/M32 v4.0 destination scene. **Convert WING sends…** captures one
Current input and previews its bus sends before creating a scene copy
with the destination patch. The plan and readback are saved with the copy.

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

Le connecteur MIDI/TCP existant conserve les adaptations et l’avis MIT de
`dlive-midi-tools` v2.14.0. Les nouvelles lectures dLive suivent les requêtes
documentées par Allen & Heath en V1.9 et V2.0. Pour étendre le catalogue à terme,
Mixing Station Desktop documente REST, WebSocket et OSC. Un connecteur optionnel
pourrait réutiliser le contrat `IConsoleAdapter` avec une matrice de champs
qualifiée par modèle. Ce candidat utilise les adaptateurs StageDesk directs.
[Attributions tierces](../THIRD_PARTY_NOTICES.md)

The existing MIDI/TCP adapter keeps the adaptations and MIT notice for
`dlive-midi-tools` v2.14.0. The new dLive reads follow Allen & Heath V1.9 and
V2.0 documentation. Mixing Station Desktop documents REST, WebSocket and OSC.
A future optional connector could use `IConsoleAdapter` with a verified field
list per model. This candidate uses the direct StageDesk adapters.
[Third-party notices](../THIRD_PARTY_NOTICES.md)

- [Allen & Heath - external TCP/IP control](https://support.allen-heath.com/hc/en-gb/articles/37282561723537-External-Control-integrating-A-H-systems-in-TCP-IP-environments)
- [Allen & Heath - dLive MIDI over TCP V1.9](https://www.allen-heath.com/content/uploads/2023/05/dLive-MIDI-Over-TCP-Protocol-V1.9.pdf)
- [Yamaha RCP - Bitfocus protocol integration and parameter lists](https://github.com/bitfocus/companion-module-yamaha-rcp)
- [Patrick-Gilles Maillot - X32 OSC documentation](https://sites.google.com/site/patrickmaillot/x32)
- [Allen & Heath - dLive MIDI Over TCP/IP Protocol V2.0](https://www.allen-heath.com/content/uploads/2024/06/dLive-MIDI-Over-TCP-Protocol-V2.0.pdf)
- [Allen & Heath - Avantis MIDI TCP/IP Protocol](https://support.allen-heath.com/hc/en-gb/articles/45146889174801-Avantis-MIDI-TCP-IP-Protocol)
- [dlive-midi-tools - préparation et transport MIDI/REST, licence MIT](https://github.com/togrupe/dlive-midi-tools)
- [Mixing Station - API REST, WebSocket et OSC](https://mixingstation.app/docs/use-cases/apis/)
- [Patrick-Gilles Maillot - WING remote documentation](https://sites.google.com/site/patrickmaillot/wing)

Ces références ne constituent ni une certification ni un partenariat constructeur.
These references do not constitute vendor certification or a partnership.
