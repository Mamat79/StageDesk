# Références et composants tiers

## Yamaha RCP — module Bitfocus

Le projet `bitfocus/companion-module-yamaha-rcp` a été étudié comme référence d’interopérabilité :

- dépôt : <https://github.com/bitfocus/companion-module-yamaha-rcp> ;
- licence déclarée par le dépôt : MIT ;
- usage dans StageDesk : vérification du port, des familles, des adresses et des limites de paramètres.

Aucun fichier source JavaScript du module n’est distribué dans StageDesk.

## dLive MIDI Tools — Tobias Grupe

Le connecteur réseau Allen & Heath MIDI/TCP adapte les constantes, le framing
SysEx et la table de couleurs publiés dans `dlive-midi-tools` (DMT) :

- dépôt d'origine : <https://github.com/togrupe/dlive-midi-tools> ;
- version/révision étudiée : v2.14.0,
  `7f31ddf9bca294f8280f0f510464abcd6afea56e` ;
- copie de référence locale : `.tools/dlive-midi-tools` ;
- auteur et copyright : Tobias Grupe, 2023 ;
- licence : MIT ;
- éléments adaptés : port TCP 51325, en-tête SysEx Allen & Heath, commandes de
  lecture/écriture des noms et couleurs, limites réseau dLive/Avantis et codes
  couleur 0 à 7.

Le texte de la licence MIT de DMT est distribué dans
`third_party_licenses/dlive-midi-tools-LICENSE.txt`. DMT est une référence
tierce, non officielle Allen & Heath. StageDesk ne revendique aucune validation sur
console physique ni support constructeur à partir de cette seule référence.

## Bibliothèques distribuées

L'inventaire a été recoupé avec des publications non rognées du client desktop
pour `win-x64`, `osx-x64` et `osx-arm64`. Le paquet distribue notamment :

- Avalonia UI 12.0.3 et Avalonia Controls DataGrid 12.0.0, ainsi que la police
  Inter embarquée et ANGLE sur Windows ;
- ClosedXML 0.105.0, ClosedXML.Parser 2.0.0, Open XML SDK 3.1.1 et
  ExcelNumberFormat 1.1.0 ;
- SkiaSharp 3.119.4-preview.1.1, HarfBuzzSharp 8.3.1.3,
  MicroCom.Runtime 0.11.4, RBush.Signed 4.0.0, SharpZipLib 1.4.2,
  SixLabors.Fonts 1.0.0 et Tmds.DBus.Protocol 0.92.0 ;
- System.IO.Packaging 8.0.1, System.IO.Pipelines 8.0.0 et le runtime .NET
  auto-contenu 8.0.30 propre à chaque architecture publiée.

Les textes intégraux de licence et de notice sont distribués sous
`third_party_licenses/`. Leur provenance, la version et le commit exacts sont
inventoriés dans `third_party_licenses/README.md`. Ces fichiers sont des copies
non réécrites des paquets NuGet ou des dépôts amont indiqués. Les dépendances de
build et de test absentes du paquet desktop ne sont pas présentées comme des
composants runtime.

## Projets de compatibilité

Le dépôt et les paquets desktop peuvent contenir des modèles vierges de
compatibilité sous `assets/project-templates/`. Les chemins et empreintes sont
recensés dans `assets/project-templates/ALLOWLIST.sha256` ; ce manifeste prouve
l’intégrité des fichiers, pas les droits de redistribution. L’inclusion d’un
modèle ne doit pas être interprétée comme une licence accordée par son éditeur
ou son constructeur. L’éligibilité de chaque fichier à une distribution
publique doit être vérifiée séparément selon les licences et autorisations
applicables.

StageDesk valide le modèle sélectionné et travaille uniquement sur une copie. Aucun
projet utilisateur, show de production, média, firmware ni donnée personnelle
ne doit être ajouté aux paquets. Les formats qui exigent un modèle privé ou un
éditeur installé restent résolus localement.

Les noms de produits et marques cités appartiennent à leurs détenteurs
respectifs. StageDesk est un outil indépendant, sans affiliation ni validation des
constructeurs. La compatibilité annoncée décrit uniquement les formats et
parcours effectivement testés dans StageDesk ; elle ne remplace pas une validation
dans l’éditeur officiel et sur la machine physique.

---

# Third-party references and components

StageDesk studied the MIT-licensed Bitfocus Yamaha RCP module and Tobias Grupe's
MIT-licensed `dlive-midi-tools` v2.14.0 as interoperability references. No
Bitfocus JavaScript source is distributed. The DMT licence text is included in
`third_party_licenses/dlive-midi-tools-LICENSE.txt`.

The published desktop application includes Avalonia UI 12.0.3, Avalonia
Controls DataGrid 12.0.0, the embedded Inter font, ClosedXML 0.105.0 and its
Open XML stack, SkiaSharp, HarfBuzzSharp, SharpZipLib, SixLabors.Fonts and the
self-contained .NET 8.0.30 runtime, together with the other runtime components
listed in `third_party_licenses/README.md`.

Full unmodified licence and notice texts ship under `third_party_licenses/`.
That directory records the exact package version, upstream revision and source
for every grouped text. The inventory was checked against untrimmed publishes
for Windows x64, macOS Intel and macOS Apple Silicon; build-only and test-only
dependencies absent from the desktop package are excluded from the runtime
inventory.

The repository and desktop packages may contain blank compatibility templates
under `assets/project-templates/`. Their paths and hashes are listed in
`assets/project-templates/ALLOWLIST.sha256`; this manifest proves file
integrity, not redistribution rights. Including a template must not be read as
a licence granted by its publisher or manufacturer. Eligibility for public
distribution must be checked separately under the applicable licences and
permissions.

StageDesk validates the selected template and edits only a copy. No user project,
production show, media, firmware or personal data may be added to the packages.
Formats that require a private template or an installed editor continue to be
resolved locally.

All product names and trademarks belong to their respective owners. StageDesk is an
independent tool and is neither affiliated with nor endorsed by those vendors.
Compatibility statements describe only the formats and workflows actually
tested by StageDesk; official-editor and physical-device validation remain necessary.
