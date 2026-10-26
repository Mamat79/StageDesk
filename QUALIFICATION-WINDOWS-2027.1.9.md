# StageDesk 2027.1.9 — qualification Windows

**Cette livraison concerne Windows 2027.1.9. Les paquets et notices macOS restent en 2027.1.8.** Les nouveaux paquets Mac seront publiés après leur propre qualification. Les anciennes releases sont conservées.

**This release delivers Windows 2027.1.9. macOS packages and specific manuals remain at 2027.1.8.** New Mac packages will be published after their separate qualification. Previous releases are preserved.

## Français

Produit et recette Windows `3a02d75463f0254dfbf6c6f031453e617f360d85`,
branche `refonte-direction-b-20261026`, construction locale avec
`packaging/build-desktop.ps1`, SDK .NET10.0.401 et Inno Setup6.4.3.
Setup Windows x64 autonome non signé ; aucun build Windows GitHub Actions.

La route Récupérer → Modifier → Envoyer, les colonnes Inclure/numéro/labels
original et préparé, l'inspecteur de canal et les thèmes suivent la refonte.
Les valeurs originales, les choix Appliquer, la validation facultative et les
confirmations de transfert gardent leurs fonctions existantes.

Le propriétaire du code a exécuté les suites et contrôles source : première
suite avec914 réussites et4 attentes devenues obsolètes, puis39 tests ciblés
réussis après leur correction. Le bilan couvre919 identifiants stables validés,
sans prétendre à une seconde exécution intégrale. Le contrôle WPF de métadonnées
a réussi. Les12 rendus source sans écran FR/EN clair/sombre, à trois tailles,
restent distincts des essais du programme réellement livré.

Le véritable installeur a été extrait et ses170 fichiers correspondent à la
sortie qualifiée. Son programme a exécuté la recette native officielle avec
profil et présence de suite isolés : fenêtre visible,17 PNG au total dont8
rendus de composants d'alerte synthétiques, clair/sombre et français/anglais,
tableau agrandi et6 commandes du parcours console. Les fichiers d'essai sont
inchangés ; la fermeture du mode de contrôle a terminé avec le code0. Les
images d'alertes n'exercent aucun réseau physique.

La mise à jour personnelle existante a réussi après deux sauvegardes privées
vérifiées C/D de730 fichiers,406328966 octets par copie. Un fichier a été
restauré dans un dossier d'essai, sans restaurer de licence ou le profil réel.
Les170 fichiers installés correspondent au paquet ;557 fichiers personnels
comparés sont inchangés. Version, inscription dans le registre Windows réel et
raccourci unique StageDesk v2027 ont été vérifiés. Le programme installé a
ensuite passé la même recette native avec un profil isolé, puis quitté0.
Les quatre PDF produit et les deux guides communs approuvés sont réutilisés
sans régénération ; les notes de livraison décrivent la nouvelle disposition.

Limites : pas de console audio réelle, transfert de production, appareil MIDI,
téléphone ou réseau interpostes validé. Les changements de DPI Windows n'ont
pas fait l'objet d'une matrice humaine complète. Les contrôles synthétiques et
rendus internes ne certifient pas toutes les opérations par souris/clavier.
La qualification et les SHA macOS sont séparés ; cette recette ne prétend pas
valider un paquet Mac ni ses limites d'activation.

## English

Locally built self-contained Windows x64 release from product/recipe
`3a02d75463f0254dfbf6c6f031453e617f360d85`, official PowerShell packaging,
.NET SDK10.0.401 and Inno Setup6.4.3. Unsigned Setup; no Windows Actions build.

Source-owner checks began with914 passes and4 obsolete expectations, followed
by39 passing targeted tests after correction. The result covers919 stable test
IDs, not a claimed second full suite. WPF metadata and12 headless source layout
renders passed; these are separate from actual packaged-app checks.

All170 files extracted from the real Setup matched the qualified output. The
packaged application ran the official native smoke with isolated profile and
suite presence: visible window,17 PNGs including8 synthetic alert component
renders, both themes/languages, table expansion and6 suite workflow commands.
Fixture bytes were unchanged and shutdown returned0. Synthetic alerts exercise
no physical network.

The existing Windows installation was upgraded after independently verified
private C/D backups. Installed payload, actual Windows registry, version and
unique shortcut passed; all557 compared personal files remained unchanged.
The installed app then passed the isolated native smoke and exited0. Approved
product PDFs and shared guides are reused, with new release notes describing
the layout. A backup sample was restored into a test directory only.

No physical console/audio/MIDI, production transfer, phone or intercomputer
network acceptance; no exhaustive human keyboard/mouse/OS-DPI matrix. macOS
package identity and activation limits require their own qualification.

## SHA-256

```text
765f7e02107fa5a3291fdb3e05de5704e55dc23101f4d825a78734cc95beea78  StageDesk-Setup-v2027.1.9.exe
7b3d8120ce66bf0fe6301adaab3fbaa7b1448878a99c5b738ad785d6478d3df1  StageDesk-v2027.1.9-win-x64.zip
```
