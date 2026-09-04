# StageDesk v2027 - Windows et macOS

## Français

StageDesk prépare et transfère les labels et réglages essentiels entre consoles
et logiciels audio, dans une interface commune en français ou en anglais.

### Installer

Téléchargez uniquement depuis la
[release officielle StageDesk](https://github.com/Mamat79/StageDesk/releases/latest).

- **Windows x64** : lancez `StageDesk-Setup-v2027.0.0.exe`. L'assistant installe
  `StageDesk.exe` pour votre compte, crée le raccourci **StageDesk v2027** et
  propose une désinstallation standard dans les applications Windows.
- **Mac Intel** : ouvrez `StageDesk-v2027.0.0-osx-x64.dmg`.
- **Mac Apple Silicon** : ouvrez `StageDesk-v2027.0.0-osx-arm64.dmg`.
- **Sur Mac**, glissez **StageDesk.app** dans **Applications**, puis lancez-le.
  Si une version est déjà présente, enregistrez et fermez vos projets avant remplacement.

Les paquets incluent le runtime .NET : aucune installation séparée n'est nécessaire.
Les fichiers SHA-256 accompagnent les installateurs. Les DMG utilisent une signature
d'intégrité ad hoc, sans signature Developer ID ni notarisation Apple ; macOS peut
afficher un avertissement. Ne considérez pas cette signature comme une certification Apple.

### Trois façons de travailler

1. **Projet StageDesk** : créer, ouvrir et enregistrer son fichier autonome
   `.smtshow`. Les anciens fichiers `.smt` restent importables.
2. **Projet StageFlow local** : créer, ouvrir et enregistrer directement un dossier
   `.stageflow` sans devoir installer StageFlow.
3. **Session StageFlow LIVE** : cliquer sur **LIVE** en haut à droite. Le centre
   recherche les sessions du LAN et permet une adresse IPv4 privée manuelle.
   Choisir le projet et l'ordinateur hôte, puis saisir ou coller le code à six
   chiffres affiché par StageFlow. Les espaces et tirets sont acceptés et les
   zéros initiaux sont conservés.

L'association est volontaire. Aucun code ni jeton n'est enregistré, et aucune
reconnexion n'est automatique. Une déconnexion conserve le tableau ouvert.
Les changements valides du patch LIVE apparaissent sans rappeler le snapshot ;
les conflits conservent la valeur locale et restent signalés. Les alertes de
labels sont reçues par défaut et restent visibles jusqu'à acquittement local.

### Interface et travail audio

Le tableau conserve ses données lorsque la source, la destination, le thème ou
la langue change. Les flèches permettent de replier les panneaux gauche, haut et
droite ; **Affichage > Mode tableau agrandi** donne la place au tableau.
**Détails** ouvre les réglages par paramètre à la demande.

Les imports et exports métier restent disponibles indépendamment de StageFlow.
Un clic explicite sur **Exporter** reste nécessaire : LIVE ne commande jamais
une console ou un logiciel audio. Choisissez le profil exact et le mode proposé.
La [matrice des connecteurs](CONNECTORS_STATUS_v2026.md) précise les parcours,
formats et prérequis constructeur, notamment les bibliothèques SSL sous Windows.

### Données, mises à jour et licence

Un remplacement explicitement choisi crée d'abord un backup voisin vérifié
`Bckp_`, sans sous-dossier. Les projets utilisateur, réglages et activations
ne sont pas effacés par une mise à jour ou une désinstallation standard.
La recherche de mises à jour compare la version complète et vérifie le SHA-256
du paquet correspondant au système avant de le présenter.

Consultez la [licence utilisateur](EULA_FR_EN.md) et la
[notice de licence](LICENSING_STAGEDESK_FR_EN.md). StageFlow est gratuit et optionnel.

## English

StageDesk prepares and transfers labels and essential settings between audio
consoles and software through one French or English interface.

### Install

Download only from the
[official StageDesk release](https://github.com/Mamat79/StageDesk/releases/latest).

- **Windows x64**: run `StageDesk-Setup-v2027.0.0.exe`. The wizard installs
  `StageDesk.exe` for your account, creates the **StageDesk v2027** shortcut,
  and registers standard uninstallation in Windows Apps.
- **Intel Mac**: open `StageDesk-v2027.0.0-osx-x64.dmg`.
- **Apple Silicon Mac**: open `StageDesk-v2027.0.0-osx-arm64.dmg`.
- **On Mac**, drag **StageDesk.app** into **Applications**, then launch it.
  Save and close projects before replacing an existing version.

Packages include .NET; no separate runtime installation is required.
SHA-256 files accompany the installers. DMGs use ad-hoc integrity signing, not
Apple Developer ID signing or notarization, so macOS may display a warning.
This signature is not Apple certification.

### Three workflows

1. **StageDesk project**: create, open and save a standalone `.smtshow` file.
   Legacy `.smt` files remain importable.
2. **Local StageFlow project**: create, open and save a `.stageflow` folder
   directly without installing StageFlow.
3. **StageFlow LIVE session**: click **LIVE** at the top right. The connection
   center discovers LAN sessions and offers manual private IPv4 entry. Select
   the project and host, then type or paste the host's six-digit code. Spaces
   and hyphens are accepted, and leading zeros are preserved.

Association is voluntary. Codes and tokens are never saved; reconnection is
never automatic. Disconnecting keeps the table open. Valid LIVE patch changes
appear without recalling a snapshot. Conflicts keep the local value and remain
flagged. Label alerts are enabled by default and stay visible until acknowledged
on this computer.

### Interface and audio work

Changing the source, target, theme or language preserves the table. Arrows
collapse the left, upper and right panels; **View > Expanded table mode** expands the
table. **Details** exposes per-parameter controls when needed.

Audio imports and exports work independently of StageFlow. **Export** remains
an explicit action; LIVE never commands a console or audio application.
Choose the exact profile and offered mode. The
[connector matrix](CONNECTORS_STATUS_v2026.md) describes workflows, formats and
vendor prerequisites, including SSL libraries on Windows.

### Data, updates and licensing

An explicitly selected replacement first creates a verified neighbouring
`Bckp_` backup without a subfolder. Updates and standard uninstallation do not
erase user projects, settings or activation. The update check compares the full
installed version and verifies the matching package's SHA-256 before presenting it.

See the [user licence](EULA_FR_EN.md) and
[licensing guide](LICENSING_STAGEDESK_FR_EN.md). StageFlow is free and optional.
