# StageDesk Lawo native files and Ember+ labels

## Français

Ce complément décrit les parcours Lawo de StageDesk 2027.1.4. Il ne constitue
pas une certification sur console physique. Les preuves viennent de
sauvegardes et relectures dans mxGUI, de
transferts Ember+ sur des simulateurs isolés et des tests de StageDesk.

| Profil testé | Production native `.lpn` | Réseau Ember+ |
|---|---|---|
| mc²66 MKII, mxGUI 5.14.2.6 | Lecture et labels ASCII, 8 octets | Non exposé |
| mc²36 MKII 32 faders, mxGUI 12.4.0.0 | Lecture et labels longs UTF-8, 63 octets | Labels Current, port explicite |
| mc²56 MKIII, mxGUI 12.4.0.0 | Lecture et labels longs UTF-8, 63 octets | Labels Current, port explicite |
| mc²96, mxGUI 12.4.0.0 | Lecture et labels longs UTF-8, 63 octets | Labels Current, port explicite |

Les autres variantes, générations et firmwares ne sont pas qualifiés. Les
structures DSP stockées dans un fichier ne prouvent pas la capacité ou les
licences du matériel. Le numéro de canal correspond à l'identité DSP native,
jamais à l'ordre des faders. Aucun gain, mute, fader, routage, couleur ou icône
n'est modifié par ce connecteur.

### Travailler sur des fichiers

Choisissez Lawo, le profil exact puis **Fichier projet**. Ouvrez une production
`.lpn` et sélectionnez Current ou un snapshot enregistré. Après import, modifiez
les labels dans le tableau. En destination, sélectionnez explicitement Current,
un snapshot existant ou l'option de nouvelle copie d'un snapshot. Le nom d'un
nouveau snapshot accepte 1 à 8 lettres ASCII, chiffres, tirets ou underscores.

**Nouveau projet** requiert l'enregistrement de votre propre seed natif dans le
stockage privé local de StageDesk. Ce fichier doit contenir un snapshot
duplicable. Ce n'est pas une remise à zéro : la nouvelle production conserve
les données héritées du seed. Aucun projet personnel ni modèle usine Lawo
vierge n'est redistribué. La génération binaire est contrôlée ; vérifiez le
modèle exact dans mxGUI, car les trois profils modernes partagent la même
révision de format. Le seed est copié, haché et revalidé avant création.

Les noms courts modernes restent inchangés lors des exports du tableau. Sur
le format ancien, les miroirs de labels doivent être complets et cohérents :
une entrée ambiguë ou non qualifiée est refusée, sans écriture partielle de
fichier. Une protection `.protected_files` non vide, une révision inconnue,
des générations mélangées ou des structures invalides empêchent l'export.
Les productions et données décompressées sont limitées à 128 Mio.

Un projet existant n'est remplacé qu'après confirmation du chemin exact et
sauvegarde `Bckp_` vérifiée. Conservez cette sauvegarde et votre production
constructeur complète. Rouvrez chaque sortie dans la bonne version de mxGUI
avant transfert vers le matériel.

### Se connecter en réseau

Sur l'un des trois profils modernes, choisissez **Réseau**. Saisissez une
adresse IPv4 unicast et le port Ember+ réellement configuré. Le champ de port
commence à zéro pour vous obliger à le préciser ; le port 9000 utilisé dans
la recette des VM n'est pas un défaut universel. **Détecter** recherche sur
l'interface locale choisie et ce port uniquement, avec une réponse typée
qualifiée requise. Une simple ouverture de port ne suffit pas.

**Tester** contrôle le produit et la version ; **Lire Current** découvre les
entrées DSP et leurs labels. Pour envoyer, cochez les labels souhaités, quittez
la Simulation, puis contrôlez la prévisualisation et la confirmation. StageDesk
effectue une prélecture, sauvegarde les valeurs relisibles et refuse tout
changement du modèle, de l'inventaire ou d'une entrée sélectionnée depuis la
prévisualisation. Après envoi, deux relectures fraîches contrôlent l'application,
dont une sur une nouvelle connexion. Les noms courts restent préservés.

Le réseau ne rappelle et ne mémorise aucun snapshot. Pour un snapshot
enregistré, utilisez le parcours fichier ou une action explicite de la console
après contrôle. La sauvegarde réseau contient les champs du tableau relus,
pas une production complète ni un mécanisme de retour arrière.

Une annulation ne retire pas les commandes déjà émises. Une erreur ou un
délai dépassé peut laisser un résultat partiel ou incertain ; contrôlez l'état
dans mxGUI ou sur la console et relisez une nouvelle prévisualisation avant
tout autre essai. StageDesk ne réessaie et ne reconnecte pas automatiquement.
Ember+ n'est pas traité comme une authentification : utilisez un réseau de
contrôle isolé, jamais un port exposé à Internet, et faites une recette hors
antenne sur le modèle et le firmware physiques avant production.

## English

This supplement describes the Lawo workflows in StageDesk 2027.1.4.
It is not physical-console certification. Evidence
comes from native mxGUI save/readback, Ember+ transfers to isolated simulators
and StageDesk tests.

The qualified native profiles are mc²66 MKII with mxGUI 5.14.2.6 (eight-byte
ASCII labels), and mc²36 MKII 32 faders, mc²56 MKIII and mc²96 with mxGUI
12.4.0.0 (63-byte UTF-8 long labels). Only the three modern profiles expose
Ember+ Current label transfers. Other variants, generations and firmware are
not qualified. Stored DSP counts are not physical capacity or licence evidence.
Channel numbers follow stable DSP identity, not fader order. The connector
never writes gains, mutes, faders, routing, colours or icons.

### Native production files

Choose the exact Lawo profile and **Project file**, open a native `.lpn`, then
select Current or a stored snapshot. Import and edit labels in the table. The
destination can be Current, a selected existing snapshot or a new duplicate
of an existing snapshot. New snapshot names accept 1–8 ASCII letters, digits,
hyphens or underscores.

**New project** requires your own native seed registered in StageDesk's private
local storage, with a duplicable snapshot. It is not a factory reset: inherited
seed data remain in the new production. No personal production or Lawo factory
blank is bundled. The binary generation is checked, but you must verify the
exact model in mxGUI because the three modern profiles share the same format
revision. Seeds are copied, hashed and revalidated before creation.

Modern short names are preserved. Legacy mirrors must be complete and coherent;
unsupported or ambiguous inputs are refused without a partial output-file
write. Non-empty `.protected_files` manifests, unknown or mixed revisions and
invalid structures block export. Productions and decompressed data are bounded
to 128 MiB. Existing project replacement requires exact-path confirmation and
a verified `Bckp_` backup. Keep it and your full vendor production, and reopen
every output in the matching mxGUI before loading physical hardware.

### Direct networking

Choose **Network** for a qualified modern profile. Enter an explicit unicast
IPv4 address and the configured Ember+ port. The initial zero port deliberately
requires a choice; port 9000 used on the QA VMs is not a universal default.
**Discover** probes only the selected local interface and port, requiring a
qualified typed reply rather than an open TCP port.

**Test** checks product/version. **Read Current** discovers DSP inputs and
their labels. Select labels, leave Simulation, review the preview and confirm.
StageDesk rereads the provider and backs up readable table values before
confirmation. A changed identity, inventory or selected input rejects the
whole request before sending. After sending, two fresh readbacks verify the
result, including a separate connection. Short names are preserved.

There is no network snapshot recall or store. Use native files for stored
snapshots, or an explicit console action after checking Current. The network
backup is not a full production or rollback. Cancellation cannot undo emitted
commands; errors and timeouts may leave a partial or uncertain outcome. Check
the provider and refresh the preview before another attempt. No automatic
retry or reconnect occurs. Ember+ is not authentication: isolate the control
LAN, do not expose its ports to the Internet, and qualify physical hardware
and firmware off-air before production use.
