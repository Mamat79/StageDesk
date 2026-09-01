# StageDesk v2026.9 — notes de version / release notes

[Français](#français) · [English](#english) ·
[Télécharger / Download](https://github.com/Mamat79/StageDesk/releases/latest)

Nom public / public name: **StageDesk** · édition / edition: `2026.9.0` ·
tag de mise à jour / update tag: `v2026.9`

## Français

StageDesk inaugure un flux unifié pour récupérer, convertir et transférer les
labels et réglages essentiels issus de projets audio entre consoles, logiciels
et tableaux de préparation.

### LIVE réseau StageFlow et espace de travail allégé - 2026.8

- connexion volontaire à une session StageFlow du réseau local par code à six
  chiffres, sans mémoriser ce code et sans rendre StageFlow obligatoire ;
- suivi automatique des snapshots réseau : les changements valides apparaissent
  dans le tableau sans recharger manuellement le snapshot ;
- publication limitée à `patch.json`, `smt/smt.json` et aux assets StageDesk,
  avec contrôle des chemins, tailles, empreintes et conflits optimistes ;
- alertes de labels émises une seule fois par StageFlow lors de l'enregistrement,
  avec acquittement par poste ;
- gestion des PatchSets, échanges Excel/StageFlow et informations techniques
  regroupés dans des zones repliables, fermées par défaut ;
- projet `.smtshow`, projet `.stageflow`, classeur StageFlow V3 et tous les
  connecteurs historiques restent utilisables de façon autonome.

### Interface plus lisible - 2026.7

- les choix et actions nécessaires au transfert restent directement visibles ;
- la gestion avancée des PatchSets et les informations techniques sont regroupées
  dans des sections repliables, fermées par défaut ;
- le statut et le suivi StageFlow LIVE restent visibles en permanence.

### StageFlow LIVE - 2026.7

- StageDesk détecte en lecture seule une session StageFlow LIVE V1 existante pour le
  projet `.stageflow` ouvert ; il ne crée, ne renouvelle et ne supprime jamais
  le bail LIVE ;
- le bandeau affiche **LIVE connecté**, **LIVE disponible · suivi désactivé**,
  **Autonome** ou **Conflit LIVE** ;
- la préférence **Suivre les sessions StageFlow LIVE**, activée par défaut,
  reste locale et peut être désactivée à tout moment ;
- en LIVE, chaque patch externe valide est fusionné immédiatement dans le
  tableau, sans rappel de snapshot ; une fusion à trois voies conserve les
  modifications disjointes et garde la valeur locale lors d'un conflit sur le
  même champ, tout en appliquant les autres changements ;
- sans session LIVE valide, StageDesk reste entièrement manuel et autonome ;
- les verrous, empreintes, sauvegardes, écritures atomiques, 800 canaux et tous
  les connecteurs console/DAW historiques restent inchangés.

### Projet autonome, classeur V3 et console de suite - 2026.7

- **Nouveau/Ouvrir un projet StageDesk** crée et reprend directement un
  fichier `.smtshow` autonome ; StageFlow n'est jamais requis ;
- **Nouveau/Ouvrir un projet StageFlow** reste un second parcours complet ;
- l'enregistrement partagé acquiert les verrous `patch`, `project`, puis `smt`
  et fusionne les changements disjoints avant l'écriture atomique ;
- le classeur portable StageFlow V3 gère 1 à 800 paires et 1 à 50 groupes,
  conserve les UUID, les surcharges et les exclusions, et a été relu dans les
  deux sens avec le service de classeur StageFlow ;
- la console StageFlow peut détecter StageDesk et lui ouvrir le projet dans
  l'instance existante ; un projet modifié conserve les choix Enregistrer,
  Ignorer et Annuler ;
- les liens de la suite emploient les noms publics exacts StageFlow, StageMark
  et StageMon.

### SiLeMIO Visual System v1 - 2026.7

- thème sombre **Studio Graphite** et thème clair **Atelier hybride** ;
- menus Fichier, Édition, Affichage, Outils et Aide dans l’ordre commun ;
- sélecteurs Clair/Sombre et FR/EN toujours accessibles en haut à droite ;
- navigation latérale, inspecteur contextuel et barre d’état commune signée
  `SiLeMI/O by Mamat — ----[]--` ;
- densité opérationnelle réservée au grand tableau, sans retrait d’une fonction
  métier ni changement du format StageFlow.

### Projet StageFlow natif - 2026.6

- deux parcours natifs sont disponibles : projet StageDesk autonome `.smtshow` et
  projet partagé `.stageflow`, sans nécessiter l'installation de StageFlow ;
- création, ouverture, enregistrement et Enregistrer sous fonctionnent dans les
  deux parcours ; le parcours partagé couvre le patch commun et `smt/smt.json` ;
- les anciens `.smt` restent importables ;
- le watcher fusionne les changements LIVE valides sans rappel du snapshot et
  signale les conflits de même champ sans écrasement silencieux ;
- verrous de domaines, empreintes de session, rebase du manifeste, sauvegardes
  vérifiées, écriture atomique et relecture finale protègent le projet ;
- les domaines Dante, StageMark et CAD sont validés puis conservés octet par
  octet ; les UUID communs relient les objets sans dépendance au nom affiché ;
- le menu Aide et la fenêtre À propos présentent discrètement StageFlow, gratuit
  et optionnel, Dante Config Editor et StageMark ;
- ouvrir un projet ne lance aucune connexion console, réseau ou DAW.
- la correction 2026.6.2 ouvre une préparation neuve sans faux état modifié,
  n'enregistre pas les lignes de réserve vides et garde les erreurs longues
  dans une fenêtre redimensionnable avec défilement ; le nettoyage de l'état
  initial intervient après les liaisons visuelles Avalonia.

### Parcours principal

- **Récupérer** un projet, une scène, un snapshot, une session, un tableau ou un
  état Current pris en charge.
- **Convertir** les données dans un tableau universel conservé quand la source
  ou la destination change.
- **Transférer** vers le modèle exact, dans un nouveau projet, un projet
  existant protégé par backup ou une scène cible lorsque le connecteur le
  permet.

### Nouveautés de l’interface v2026

- interface française et anglaise ;
- thèmes Système, Clair et Sombre ;
- grille dont le nombre de lignes suit le projet importé ;
- en-têtes centrés et organisés par mots complets ;
- carte de destination sans chevauchement entre capacité et aide ;
- seule la case d’inclusion du canal est visible au départ ; les contrôles
  d’application détaillés, cochés par défaut, sont regroupés sous **Détails** ;
- détection automatique du modèle natif correspondant lorsque le mode
  **Nouveau projet** est sélectionné ;
- copier-coller façon tableur, actions par colonne et exclusions rapides ;
- enchaînement immédiat de plusieurs exports : les aides d’ouverture Nuendo
  et Harrison sont désormais non bloquantes et le verrou d’export est libéré
  avant leur affichage ;
- recopie intelligente des suites numériques et stéréo, notamment
  `FX1L, FX1R, FX2L, FX2R` ;
- remplacement global des valeurs incompatibles avec possibilité de mémoriser
  et d’administrer les correspondances ;
- menus Fichier, Édition, Outils, Affichage et Aide, avec version, lien vers
  Dante Config Editor et gestion de la licence StageDesk.

### Projets et sécurité

- création native d’un projet uniquement lorsqu’une méthode sûre est disponible ;
- choix de la scène ou du snapshot source et cible quand le format le permet ;
- création d’une nouvelle scène nommée pour les connecteurs compatibles ;
- remplacement d’un projet existant uniquement après confirmation explicite ;
- avertissement et backup vérifié par SHA-256, créé dans le même dossier avec
  un nom commençant par `Bckp_` (`Bckp2_`, puis `Bckp3_` si nécessaire), sans
  horodatage, avant tout remplacement explicite d’une destination existante ;
- les modèles vierges embarqués sont sélectionnés, assainis et
  verrouillés par SHA-256 ; aucun projet utilisateur ni show de production
  n’est inclus.

### Ableton, Harrison, Nuendo, Sequoia et X32/M32

- **Ableton Live 12** : lecture/mise à jour `.als` avec backup et Nouveau projet depuis un seed
  audio-only de deux pistes dérivé du `DefaultLiveSet.als`, sans piste MIDI ou
  retour, clip, device, média, chemin, automation, send ni groove. La structure
  et les valeurs sont relues par StageDesk. La sortie exacte de deux pistes a été
  ouverte, fermée puis rouverte dans Live 12.4 ; `SMT KICK` et `SMT VOX` y ont
  été relus nativement.
- **Harrison LiveTrax 3 et Mixbus 10** : lecture et mise à jour avec backup de snapshots frères
  `.ardour`, puis création de sessions sans média à partir de modèles de
  capacité 128/512 pistes. La session publiée est réduite exactement au nombre
  de canaux inclus. Une sortie LiveTrax exacte de 7 pistes a été ouverte dans
  LiveTrax 3 avec ses noms et couleurs visibles ; les sorties Mixbus exact-N
  sont relues structurellement par StageDesk. Mixbus conserve son export Lua ;
  bus, médias, plug-ins, icônes et automation sont exclus.
- **Steinberg Nuendo 14** : import, Nouveau projet et mise à jour avec backup en
  DAWproject 1.0 avec noms, couleurs, mutes et faders. Une sortie StageDesk a été
  importée dans Nuendo 14.0.20 par **Fichier > Importer > DAWproject**,
  contrôlée puis enregistrée en `.npr`. **Ouvrir le projet** attend un `.npr` ;
  StageDesk ne lit ni n’écrit directement ce format propriétaire.
- **MAGIX Sequoia Pro 17** : lecture et mise à jour `.VIP` avec backup de l’état Current, puis
  Nouveau projet depuis un modèle assaini de 128 pistes. Le connecteur transfère
  uniquement les labels et mutes. Une sortie StageDesk et le modèle vierge ont été
  rouverts dans Sequoia Pro 17.
- **Behringer X32** : lecture, mise à jour avec backup et génération d’une scène `.scn` v4
  minimale couvrant 32 entrées et les champs pris en charge. Une sortie StageDesk a
  été chargée dans X32-Edit 4.4 avec labels, couleurs, mute et fader visibles.
- **Dante Config Editor (DCE)** : import d’un preset XML natif avec choix de la
  machine et récupération exclusive de ses Rx ; création d’un nouveau projet
  depuis la banque embarquée ou mise à jour/ajout d’une machine dans un projet
  existant. Les preuves de création et de remplacement ont été relues dans
  DCE : les labels Rx sont modifiés et le bloc Tx reste identique. DCE n’est
  pas requis sur le poste StageDesk ; l’application propose son téléchargement
  officiel pour ouvrir le résultat.

### Modèles de projet contrôlés

StageDesk peut embarquer un modèle vierge uniquement lorsqu’il a été sélectionné,
assaini et inscrit avec son SHA-256 dans le manifeste d’intégrité. Ce manifeste
prouve l’intégrité du fichier, pas les droits de redistribution. Chaque export
travaille sur une copie. Les formats qui nécessitent encore un runtime
constructeur ou un modèle privé appartenant à l’utilisateur restent
conditionnels ; aucun projet de production n’est utilisé comme modèle neutre.

Cette version étend les parcours natifs contrôlés :

- **DiGiCo SD / Quantum V2242** : les treize modèles SD5, SD5CS, SD8, SD9,
  SD10, SD11, SD12 et Quantum 1/2/3/5/7/8 sont sélectionnables avec leur
  allocation propre. StageDesk importe Current ou un snapshot nommé, écrit les
  labels ASCII dans un snapshot existant avec backup `Bckp_`, et crée un
  nouveau `.ses` depuis le seed usine exact du modèle. La duplication d’un
  snapshot reste limitée aux topologies reconnues ;
- **DM3 / DM7 / Yamaha TF** : import et écriture de Current ou des scènes
  reconnues, mise à jour d'une copie et Nouveau projet depuis le modèle natif
  exact. Les sorties DM3/DM3 Standard, DM7/DM7 Compact et TF1/TF3/TF5/TF-RACK
  ont été chargées, affichées, enregistrées puis relues dans leur éditeur ;
- **Yamaha RIVAGE PM** : treize configurations PM10/PM7/PM5/PM3 reposent sur
  quatre profils natifs stricts DSP-R10/144, CSD-R7/144, DSP-RX/120 et
  DSP-RX-EX/288. Les quatre sorties StageDesk ont été chargées sous leur profil exact
  dans RIVAGE PM Editor v7.1.0 et la scène `SMT NATIVE` y a été affichée ; le
  mode projet sait lire/écrire Current ou une scène strictement indexée et créer
  une scène dans une copie ;
- **Yamaha CL/QL** : lecture/écriture label-couleur-icône et Nouveau projet
  depuis cinq modèles embarqués avec scène 1 obligatoire ; le checksum MEMAPI,
  Current, la scène et les index sont relus structurellement. Des sorties CL5
  et QL1 avec scène 1 ont été ouvertes deux fois dans CL/QL Editor 5.8.1, puis
  rouvertes après une commande de sauvegarde sans erreur ;
- **dLive** : lecture des shows, écriture label/couleur dans Current ou un
  snapshot, création d’un snapshot nommé et Nouveau projet pour les quatorze
  variantes proposées. Le moteur commun de 128 entrées ne stocke pas l'identité
  de la surface ou du MixRack ; un show StageDesk et son nouveau snapshot ont été
  indexés puis rappelés dans dLive Director 2.12 ;
- **Avantis** : lecture et écriture de Current ou d'un snapshot, création d'un
  snapshot et Nouveau projet pour Avantis, Avantis dPack, Solo et Solo dPack à
  partir du modèle standard ou dPack contrôlé ; toutes les sorties sont relues
  par StageDesk avant publication, le réseau restant masqué ;
- **Qu classique** : import des shows et scènes Qu-16/24/32/Pac/SB, écriture
  des labels dans Current ou une scène et création d'une scène dans une copie.
  StageDesk reconnaît les deux dispositions classiques, recalcule le CRC et relit la
  sortie ; la console Qu reste nécessaire pour la validation finale et les
  Qu-5/6/7 utilisent un autre format ;
- **VENUE S6L** : lecture et écriture des labels MicLine de Current dans une
  copie `.dsh`, plus Nouveau projet pour les six moteurs E6L/E6LX 112, 128,
  144, 176, 192 et 256 depuis leurs modèles embarqués. Les six sorties ont été
  chargées dans VENUE Offline 8.2 ; `SMT KICK` et `SMT LAST` ont été relus ;
- **HD96** : import des shows natifs HD96-16/24/AIR, écriture dans une scène
  existante ou nouvelle d'une copie protégée, et import/export du classeur
  Excel constructeur. La copie et la scène sont relues par StageDesk ; leur chargement
  final dans HD96 Editor et le matériel restent à confirmer.

Ces nouvelles sorties passent la relecture structurelle StageDesk. Les six shows S6L
ont été chargés dans VENUE Offline 8.2 ; le
  show dLive et son nouveau snapshot ont aussi passé la réouverture native
  décrite ci-dessus. Les sorties CL5/QL1 et les quatre profils RIVAGE ont passé
  les contrôles éditeur décrits ci-dessus.

### Bonnes pratiques

- choisissez toujours dans StageDesk le modèle exact de la destination ;
- conservez le backup `Bckp_` et le dernier show validé avant un remplacement ;
- rouvrez le fichier produit dans l’éditeur constructeur avant une utilisation
  en direct ;
- vérifiez sur la console cible les canaux représentatifs de votre préparation.

Consultez la [liste des consoles et logiciels](../README_FR.md) puis rouvrez
chaque fichier généré dans le logiciel constructeur avant une utilisation en
direct.

### Licence

StageDesk est un logiciel propriétaire. Les exécutables officiels sont régis par la
[licence utilisateur v2026](EULA_FR_EN.md) ; le code source privé reste
propriétaire et confidentiel.

- 30 jours sans rappel, puis rappel refermable après 10 secondes ;
- aucune fonction ni aucun projet n’est bloqué après l’essai ;
- licence permanente à 29 € TTC, accessible depuis la page d’achat officielle ;
- 3 installations par défaut, avec compteur utilisé/autorisé ;
- bouton **Désactiver cet ordinateur** ;
- activation initiale en ligne puis validation locale hors ligne.

La mention d’un constructeur ou
d’un produit n’implique ni certification, ni partenariat, ni approbation.

**SiLeMI/O by Mamat** — `----[]--`

---

## English

StageDesk provides one consistent workflow for retrieving, converting and
transferring labels and essential settings from audio projects between
consoles, production software and preparation tables.

### StageFlow Network LIVE and a cleaner workspace - 2026.8

- explicit connection to a local-network StageFlow session with a six-digit
  code that is never stored, while StageFlow remains optional;
- automatic network snapshot following: valid changes appear in the table
  without a manual snapshot reload;
- publication is limited to `patch.json`, `smt/smt.json` and StageDesk-owned
  assets, with path, size, hash and optimistic-concurrency checks;
- StageFlow emits each saved label alert once, with per-client acknowledgement;
- PatchSet management, Excel/StageFlow exchanges and technical information are
  grouped in collapsible sections that start closed;
- `.smtshow`, `.stageflow`, the StageFlow V3 workbook and all existing
  connectors remain available in standalone workflows.

### Clearer interface - 2026.7

- transfer choices and primary actions remain directly visible;
- advanced PatchSet management and technical explanations are grouped in
  collapsible sections that start closed;
- StageFlow LIVE status and following controls remain permanently visible.

### StageFlow LIVE - 2026.7

- StageDesk read-only detects an existing StageFlow LIVE V1 session for the open
  `.stageflow` project; it never creates, renews, or removes the LIVE lease;
- the toolbar shows **LIVE connected**, **LIVE available · following disabled**,
  **Standalone**, or **LIVE conflict**;
- **Follow StageFlow LIVE sessions** is enabled by default, remains local, and
  can be disabled at any time;
- during LIVE, every valid external patch is immediately merged into the table
  without recalling the snapshot; a three-way merge preserves disjoint edits,
  keeps the local value on same-field conflicts, and still applies all other
  changes;
- without a valid LIVE session, StageDesk stays fully manual and standalone;
- locks, hashes, backups, atomic writes, the 800-channel capacity, and every
  existing console/DAW connector remain unchanged.

### Standalone project, V3 workbook and suite console - 2026.7

- **New/Open a StageDesk project** directly creates and resumes a standalone
  `.smtshow` file; StageFlow is never required;
- **New/Open a StageFlow project** remains a second complete workflow;
- shared saves acquire `patch`, `project`, then `smt` locks and merge disjoint
  changes before the atomic write;
- the portable StageFlow V3 workbook supports 1 to 800 pairs and 1 to 50 groups,
  preserves UUIDs, overrides and exclusions, and was read both ways with the
  StageFlow workbook service;
- the StageFlow console can detect StageDesk and open the project in its
  existing instance; a dirty project retains Save, Discard and Cancel choices;
- suite links use the exact public names StageFlow, StageMark and StageMon.

### SiLeMIO Visual System v1 - 2026.7

- **Studio Graphite** dark theme and **Atelier hybride** light theme;
- File, Edit, View, Tools and Help menus in the shared order;
- Light/Dark and FR/EN selectors remain available at the top right;
- shared side navigation, contextual inspector and status bar signed
  `SiLeMI/O by Mamat — ----[]--`;
- operational density is limited to the large table, with no removed business
  feature and no StageFlow format change.

### Native StageFlow project - 2026.6

- two native workflows are available: standalone StageDesk `.smtshow` projects and
  shared `.stageflow` projects, without requiring StageFlow to be installed;
- create, open, save, and Save As work in both workflows; the shared workflow
  covers the common patch and `smt/smt.json`;
- existing `.smt` files remain importable;
- the watcher merges valid LIVE changes without recalling the snapshot and
  flags same-field conflicts without a silent overwrite;
- domain locks, session hashes, manifest rebase, verified backups, atomic
  writes, and final readback protect the project;
- Dante, StageMark, and CAD domains are validated and preserved byte for byte;
  shared UUIDs link objects without relying on display names;
- Help and About discreetly present free, optional StageFlow, Dante Config
  Editor, and StageMark;
- opening a project starts no console, network, or DAW connection.
- the 2026.6.2 corrective build opens a new preparation in a clean state,
  omits empty reserve rows from the project, and keeps long errors inside a
  resizable, scrollable window; initial state cleanup now runs after Avalonia's
  visual bindings.

### Main workflow

- **Retrieve** a supported project, scene, snapshot, session, table or Current
  state.
- **Convert** its data in a universal working table that remains available when
  the source or destination changes.
- **Transfer** to the exact model as a new project, an existing project
  protected by an automatic backup, or a selected scene when the connector
  supports it.

### v2026 interface highlights

- English and French interface;
- System, Light and Dark themes;
- grid row count derived from the imported project;
- centred headers wrapped on complete words;
- destination card keeps capacity and guidance on separate, readable rows;
- only channel inclusion is visible initially; per-parameter controls remain
  selected by default and are grouped under **Details**;
- automatic discovery of the matching native template when **New
  Project** is selected;
- spreadsheet-style copy/paste, column actions and fast exclusion;
- immediate consecutive exports: Nuendo and Harrison opening guidance is now
  modeless and the export lock is released before it is displayed;
- smart numerical and stereo fill, including `FX1L, FX1R, FX2L, FX2R`;
- global replacement of incompatible values, with editable remembered mappings;
- File, Edit, Tools, View and About menus with version, a Dante Config Editor
  (DCE) link, licence and support.

### Projects and safety

- native project creation only when a safe method is available;
- source and target scene/snapshot selection when supported by the format;
- named scene creation for compatible connectors;
- replacement of an existing project only after explicit confirmation;
- warning and SHA-256-verified backup in the same folder, prefixed `Bckp_`
  (`Bckp2_`, then `Bckp3_` when needed) without a timestamp, before an
  explicit destination replacement;
- bundled blank templates are selected, sanitised and SHA-256
  pinned; no user project or production show is included.

### Ableton, Harrison, Nuendo, Sequoia and X32/M32

- **Ableton Live 12**: `.als` read/update with backup and New Project from a two-track
  audio-only seed derived from `DefaultLiveSet.als`, with no MIDI/return track,
  clip, device, media, path, automation, send or groove. StageDesk rereads the
  structure and values. The exact two-track output opened, closed and reopened
  in Live 12.4; `SMT KICK` and `SMT VOX` were read back natively.
- **Harrison LiveTrax 3 and Mixbus 10**: read and update sibling `.ardour`
  snapshots with backup, then create no-media sessions from 128/512-track capacity
  templates. The published session is pruned exactly to the number of included
  channels. An exact seven-track output opened in LiveTrax 3 with its names and
  colours visible; exact-N Mixbus outputs pass structural StageDesk reread. Mixbus
  keeps its Lua export; buses, media, plug-ins, icons and automation are
  excluded.
- **Steinberg Nuendo 14**: import, New Project and existing-project update with backup through
  DAWproject 1.0 with names, colours, mutes and faders. A StageDesk output was
  imported into Nuendo 14.0.20 through **File > Import > DAWproject**, checked
  and saved as `.npr`. **Open Project** expects an `.npr`; StageDesk does not directly
  read or write that proprietary format.
- **MAGIX Sequoia Pro 17**: read and update `.VIP` Current state with backup, plus New Project
  from a sanitised 128-track template. Only labels and mutes are transferred.
  A StageDesk output and the blank template reopened in Sequoia Pro 17.
- **Behringer X32**: read, update with backup and generation of a minimal `.scn` v4 scene for
  32 inputs and the supported fields. A StageDesk output loaded in X32-Edit 4.4 with
  labels, colours, mute and fader visible.
- **Dante Config Editor (DCE)**: native XML preset import with device choice and
  Rx-only retrieval; create a new project from the bundled bank, or update/add
  a device in an existing project. Creation and replacement evidence was read
  back in DCE: Rx labels change while the Tx block remains identical. DCE is
  not required on the StageDesk computer; the app offers its official download for
  opening the result.

### Controlled project templates

StageDesk bundles a blank template only when it is selected, sanitised and listed
with its SHA-256 in the integrity manifest. The manifest proves file integrity,
not redistribution rights. Every export works on a copy. Formats
that still need a vendor runtime or a private user-owned template remain
conditional; a production project is never accepted as a neutral template.

This release extends the controlled native workflows:

- **DiGiCo SD / Quantum V2242**: all thirteen SD5, SD5CS, SD8, SD9, SD10,
  SD11, SD12 and Quantum 1/2/3/5/7/8 models are selectable with their own
  allocation. StageDesk imports Current or a named snapshot, writes ASCII labels to
  an existing snapshot with a `Bckp_` backup, and creates a new `.ses` from the
  model's exact factory seed. Snapshot duplication remains limited to
  recognised topologies;
- **DM3 / DM7 / Yamaha TF**: native Current/scene import and write, existing-copy
  update and New Project from the exact native template. DM3/DM3 Standard,
  DM7/DM7 Compact and TF1/TF3/TF5/TF-RACK outputs were loaded, displayed, saved
  and reread in their editor;
- **Yamaha RIVAGE PM**: thirteen PM10/PM7/PM5/PM3 configurations use four
  strict native profiles, DSP-R10/144, CSD-R7/144, DSP-RX/120 and
  DSP-RX-EX/288. All four StageDesk outputs loaded under their exact profile in
  RIVAGE PM Editor v7.1.0 and displayed the `SMT NATIVE` scene; project mode can
  read/write Current or a strictly indexed scene and create a scene in a copy;
- **Yamaha CL/QL**: label/colour/icon read/write and New Project from five
  bundled templates with mandatory scene 1 creation; StageDesk recalculates the MEMAPI
  checksum and structurally rereads Current, the scene and every index. CL5 and
  QL1 scene-1 outputs opened twice in CL/QL Editor 5.8.1 and reopened after an
  error-free save command;
- **dLive**: show read, Current or snapshot label/colour write, named snapshot
  creation and New Project for all fourteen proposed variants. The common
  128-input engine does not store a surface or MixRack identity; a StageDesk show and
  its new snapshot were indexed and recalled in dLive Director 2.12;
- **Avantis**: Current or snapshot read/write, snapshot creation and New Project
  for Avantis, Avantis dPack, Solo and Solo dPack from the controlled standard
  or dPack template. StageDesk rereads every output before publication; networking
  remains hidden;
- **classic Qu**: Qu-16/24/32/Pac/SB show/scene import, Current or scene label
  write and scene creation in a copy. StageDesk recognises both classic layouts,
  recalculates the CRC and rereads the output; final validation still requires
  a Qu console and Qu-5/6/7 use a different format;
- **VENUE S6L**: Current MicLine label read/write in a `.dsh` copy, plus New
  Project for the six 112, 128, 144, 176, 192 and 256-channel E6L/E6LX engines.
  All six outputs loaded in VENUE Offline 8.2; `SMT KICK` and `SMT LAST` were
  read back;
- **HD96**: native-show import for HD96-16/24/AIR, write to an existing or new
  scene in a protected copy, and manufacturer Excel workbook import/export.
  StageDesk rereads the copy and scene; final HD96 Editor and hardware loading remain
  to be confirmed.

These new outputs pass structural StageDesk readback. All six S6L shows loaded in
VENUE Offline 8.2; the dLive show and new
dLive snapshot also passed the native reopen described above. CL5/QL1 outputs
and all four RIVAGE profiles passed the editor checks described above.

### Good practice

- always choose the exact destination model in StageDesk;
- keep the `Bckp_` backup and the latest approved show before replacement;
- reopen the generated file in the vendor editor before live use;
- check representative channels on the target console.

Review the [console and software list](../README.md), then reopen every generated
file in the matching vendor application before live use.

### Licence

StageDesk is proprietary software. Official executables are governed by the
[v2026 End-User Licence](EULA_FR_EN.md); the private source code remains
proprietary and confidential.

- 30 reminder-free days, then a reminder that can be closed after 10 seconds;
- no feature or project is locked after the trial;
- €29 including tax permanent license, available from the official purchase page;
- 3 installations by default, with used/allowed counts;
- **Deactivate this computer** button;
- initial online activation followed by local offline validation.

Naming a vendor or product does not
imply certification, partnership or endorsement.

**SiLeMI/O by Mamat** — `----[]--`
