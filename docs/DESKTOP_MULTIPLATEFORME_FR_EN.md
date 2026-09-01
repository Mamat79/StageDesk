# StageDesk v2026 — Windows x64 / macOS Intel / macOS Apple Silicon

**Save My Time**

[Français](#français) · [English](#english)

## Français

La version actuelle de StageDesk v2026 est publiée pour Windows x64,
macOS Intel et macOS Apple Silicon :

**1. Récupérer → 2. Convertir → 3. Transférer**

Le tableau universel, les projets `.smtshow` et `.stageflow`, les fonctions de
modification et les règles de compatibilité sont disponibles sous Windows.
Changer de
source, de destination, de langue ou de thème ne vide pas le tableau courant.

### Paquets disponibles

Le paquet officiel est publié sur la
[dernière release StageDesk v2026](https://github.com/Mamat79/StageDesk/releases/latest) :

- Windows x64 ;
- macOS Intel (`osx-x64`) ;
- macOS Apple Silicon (`osx-arm64`).

Chaque archive est autonome et ne demande pas l’installation séparée du runtime
.NET. Téléchargez uniquement depuis la release officielle et contrôlez le
fichier SHA-256 associé lorsqu’il est fourni. Aucune signature de plateforme ni
notarisation n’est revendiquée par cette documentation.

### Interface

- interface française ou anglaise ;
- thèmes Système, Clair et Sombre dans le menu **Affichage** ;
- grille dimensionnée par le projet importé ;
- case d’inclusion du canal visible par défaut ;
- réglages d’application par paramètre accessibles avec **Détails** ;
- copier-coller, sélection par colonne et recopie intelligente ;
- menus Fichier, Édition, Outils, Affichage et À propos ;
- lien vers Dante Config Editor et licence StageDesk disponibles depuis
  l’application.

### Modèles embarqués et prérequis locaux

StageDesk embarque certains modèles vierges sélectionnés, assainis et
contrôlés par SHA-256. Le manifeste prouve l’intégrité, pas les droits de
redistribution. Ils permettent de créer un projet sans installer
l’éditeur correspondant et sont toujours copiés avant écriture. Aucun projet
utilisateur ni show de production n’est inclus. Les formats qui exigent encore
une bibliothèque constructeur ou un modèle privé restent conditionnels :

- **SSL Live / SOLSA** : les opérations locales `.show` nécessitent les
  bibliothèques SOLSA installées sous Windows ; elles ne sont pas annoncées sur
  macOS quand ces bibliothèques sont absentes.
- **DM3, DM7 et Yamaha TF** : import des projets natifs uniquement ; aucun
  parcours de destination n’est publié pour ces familles.
- **Midas HD96** : import show natif et import/export du classeur Excel
  constructeur ; aucune destination show native n’est publiée.
- **Qu classique** : import des shows et scènes Qu-16/24/32/Pac/SB uniquement ;
  aucune destination Qu n’est affichée tant qu’une sortie StageDesk n’a pas été
  rouverte dans un éditeur ou sur la console correspondante.
- **Harrison LiveTrax/Mixbus** : les modèles assainis de capacité 128/512 sont
  embarqués ; la sortie contient exactement les canaux inclus et aucun éditeur
  Harrison n’est requis pour Nouveau projet.
- **Nuendo** : l’échange `.dawproject` fonctionne sans Nuendo installé. Dans
  Nuendo : **Fichier > Importer > DAWproject**, jamais **Ouvrir le projet** qui
  attend un `.npr` ; StageDesk ne lit ni n’écrit directement `.npr`.
- **Sequoia** : le modèle `.VIP` assaini de 128 pistes est embarqué ; le
  connecteur reste limité à Current, labels et mutes.
- **VENUE S6L** : les six profils E6L/E6LX 112/128/144/176/192/256 ont été
  chargés dans VENUE Offline 8.2 avec relecture des labels MicLine transférés.
- **Ableton Live 12** : le Nouveau projet audio-only exact de deux pistes a été
  ouvert, fermé puis rouvert dans Live 12.4.
- **DCE** : création et remplacement XML ont été relus ; les Rx sont modifiés
  tandis que le bloc Tx est préservé à l’identique.

La disponibilité exacte par modèle est détaillée dans la
[matrice des connecteurs](CONNECTORS_STATUS_v2026.md).

### Fichiers et sécurité

StageDesk écrit une nouvelle copie par défaut. Si l’utilisateur choisit explicitement
de remplacer une destination existante, StageDesk crée auparavant dans le même
dossier un backup sans horodatage, préfixé `Bckp_` (`Bckp2_`, puis `Bckp3_`
si nécessaire), et en vérifie l’identité par SHA-256. Seuls les modèles vierges
sélectionnés et listés dans le manifeste d’intégrité peuvent être inclus ; aucun projet
utilisateur ni show de production n’est embarqué.

Une relecture StageDesk confirme que la sortie correspond au format décodé par StageDesk ;
elle ne remplace pas une réouverture dans l’éditeur constructeur. Avant une
utilisation en direct, contrôlez aussi le projet sur la machine physique.

### Licence et liens

- [Licence utilisateur StageDesk v2026](EULA_FR_EN.md)
- [Télécharger StageDesk v2026](https://github.com/Mamat79/StageDesk/releases/latest)
- [Télécharger Dante Config Editor (DCE)](https://github.com/Mamat79/Dante-Config-Editor/releases/latest)
- [Acheter une licence StageDesk - 29 € TTC](https://smt-license.mamat79-dce.workers.dev/buy)

**SiLeMI/O by Mamat** — `----[]--`

---

## English

The current StageDesk v2026 release is available for Windows x64, macOS Intel,
and macOS Apple Silicon:

**1. Retrieve → 2. Convert → 3. Transfer**

The universal table, `.smtshow` and `.stageflow` projects, editing tools and
compatibility rules are available on Windows. Changing the source, destination, language or
theme does not clear the current table.

### Available packages

The official package is published on the
[latest StageDesk v2026 release](https://github.com/Mamat79/StageDesk/releases/latest):

- Windows x64;
- macOS Intel (`osx-x64`);
- macOS Apple Silicon (`osx-arm64`).

Each archive is self-contained and does not require a separate .NET runtime.
Download only from the official release and verify the accompanying SHA-256
file when supplied. This documentation makes no platform-signing or
notarisation claim.

### Interface

- English or French interface;
- System, Light and Dark themes in the **View** menu;
- grid sized from the imported project;
- channel Include checkbox visible by default;
- per-parameter application controls available under **Details**;
- copy/paste, whole-column selection and smart fill;
- File, Edit, Tools, View and About menus;
- Dante Config Editor and StageDesk licensing links available in the
  application.

### Bundled templates and local prerequisites

StageDesk bundles selected blank templates that are sanitised
and SHA-256 pinned. The manifest proves integrity, not redistribution rights.
They allow New Project to work without the matching editor
and are always copied before writing. No user project or production show is
included. Formats that still require a vendor library or a private template
remain conditional:

- **SSL Live / SOLSA**: local `.show` operations require SOLSA libraries on
  Windows and are not advertised on macOS when those libraries are unavailable.
- **DM3, DM7, and Yamaha TF**: native project/scene import, existing-copy write,
  and New Project from the exact model template. Every DM3/DM7/TF profile was
  loaded, saved, and reread in its editor.
- **Midas HD96**: native-show import, existing/new scene write in a protected
  copy, and manufacturer Excel workbook import/export. Final HD96 Editor loading
  remains pending.
- **classic Qu**: Qu-16/24/32/Pac/SB show/scene import, Current/scene label
  write, and scene creation in a copy. Both classic layouts pass StageDesk reread;
  final validation requires a Qu console.
- **Harrison LiveTrax/Mixbus**: the sanitised 128/512-track capacity templates
  are bundled; the output contains exactly the included channels and Harrison
  software is not required for New Project.
- **Nuendo**: `.dawproject` exchange works without Nuendo installed. In Nuendo,
  use **File > Import > DAWproject**, never **Open Project**, which expects an
  `.npr`; StageDesk does not directly read or write `.npr`.
- **Sequoia**: the sanitised 128-track `.VIP` template is bundled; the connector
  remains limited to Current, labels and mutes.
- **VENUE S6L**: all six E6L/E6LX 112/128/144/176/192/256 profiles loaded in
  VENUE Offline 8.2 with Current MicLine label readback.
- **Ableton Live 12**: the exact two-track audio-only New Project opened,
  closed, and reopened in Live 12.4.
- **DCE**: XML creation and replacement were read back; Rx changed while the
  Tx block remained byte-identical.

Exact model availability is listed in the
[connector matrix](CONNECTORS_STATUS_v2026.md).

### Files and safety

StageDesk writes a new copy by default. If the user explicitly chooses to replace an
existing destination, StageDesk first creates a backup in the same folder, with a
name prefixed `Bckp_` (`Bckp2_`, then `Bckp3_` when needed), without a
timestamp, and verifies its identity by SHA-256. Only selected blank templates
listed in the integrity manifest may be included; no user project or production
show is bundled.

StageDesk readback confirms that an output matches the format decoded by StageDesk; it does
not replace reopening the result in the vendor editor. Before live use, also
check the project on the physical target.

### Licence and links

- [StageDesk v2026 End-User Licence](EULA_FR_EN.md)
- [Download StageDesk v2026](https://github.com/Mamat79/StageDesk/releases/latest)
- [Download Dante Config Editor (DCE)](https://github.com/Mamat79/Dante-Config-Editor/releases/latest)
- [Buy a StageDesk license - €29 including tax](https://smt-license.mamat79-dce.workers.dev/buy)

**SiLeMI/O by Mamat** — `----[]--`
