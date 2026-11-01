# StageDesk Windows 2027.1.10 — vérifications et limites / checks and limits

## Français

La livraison Windows x64 a été construite localement avec la recette officielle `packaging/build-desktop.ps1`, puis installée en remplacement de la version précédente après sauvegardes récupérables sur deux disques. L'installation native affiche 2027.1.10 ; les 171 fichiers du programme correspondent au paquet vérifié. Les réglages, modèles, préparations, récupérations et données de licence existants ont été préservés. Aucune activation commerciale nouvelle n'a été effectuée.

Sur l'application installée, le contrôle visuel automatisé a terminé normalement avec le code 0 : 41 rendus, dont 24 du parcours de conversion, couvrent français/anglais, clair/sombre et deux tailles de fenêtre. Ces sélections synthétiques vérifient l'interface ; les écritures de fichiers ont été testées séparément.

Le 1er novembre 2026, les trois intentions ont été exécutées dans l'interface installée sur des fichiers CL3 synthétiques privés : création d'un projet et de sa première scène ; ajout d'une scène ; insertion dans une scène existante. La relecture des fichiers confirme les labels et noms attendus, la conservation des autres scènes et les sauvegardes avant remplacement. L'ajout de scène actualise Current avant de le dupliquer ; l'insertion dans une scène existante conserve Current. Les deux fichiers de remplacement correspondent intégralement aux témoins attendus.

Le retour depuis l'aperçu ne crée aucun résultat. L'annulation de la confirmation de remplacement conserve la cible. Un label trop long exige une confirmation explicite d'adaptation ; l'annuler conserve le fichier, sans troncature silencieuse. Pour CL3, l'aperçu distingue 64 canaux transférables des 32 lignes de préparation hors capacité, conservées dans le tableau. L'application QA s'est fermée naturellement avec le code 0. Les 707 fichiers personnels inventoriés avant ces essais sont restés identiques.

Les contrôles source restent distincts : reprise ciblée finale 212/212, sécurité/capacités 104/104, précision Current 11/11 et dernier garde d'aperçu 14/14. Ces groupes se recoupent et ne constituent pas un total additionnable. Le rapport complet initial conserve ses 12 échecs sur 931 cas ; leurs noms figurent dans les réussites de la reprise ciblée après correction. Il n'est pas présenté comme une nouvelle exécution complète réussie.

Limites : aucune console physique, connexion réseau ou recette audio ; aucune nouvelle ouverture de ces trois fichiers dans Yamaha CL/QL Editor. Les trois conversions visibles utilisent le français et le thème sombre ; les autres combinaisons sont couvertes par le contrôle visuel automatisé distinct. Les refus de profil inconnu/scène indisponible ne sont pas de nouveaux essais manuels de cette session. Les données de licence ont été conservées comme données opaques. Ces contrôles Windows ne qualifient pas macOS : les paquets Mac publics restent en 2027.1.8 jusqu'à une livraison distincte vérifiée.

Installateur : `StageDesk-Setup-v2027.1.10.exe` — 57 831 349 octets. SHA-256 :

```text
9249d58f8dfa38a60e0a6550ad9d398d501812eadae6c98c5bfac688fc1f4a1a
```

Archive Windows x64 : `StageDesk-v2027.1.10-win-x64.zip` — 82 251 055 octets. SHA-256 :

```text
278c8368cfd1772c61fe765450c57fc71ea9bd8fba965b71a9b5fe5830e20741
```

## English

Windows x64 was built locally using the official `packaging/build-desktop.ps1` recipe, then installed over the previous version after recoverable backups on two drives. Native Windows registration reports 2027.1.10; all 171 program files match the verified package. Existing settings, templates, preparations, recovery files and opaque licence data were preserved. No new commercial activation was performed.

The installed application completed its separate visual smoke naturally with exit code 0: 41 renders, including 24 conversion-workflow views, cover French/English, light/dark and two window sizes. Synthetic UI selections verify the interface; file writes were exercised separately.

On 1 November 2026, all three intentions were executed through the installed interface using private synthetic CL3 fixtures: new project and first scene, additional scene, and insertion into an existing scene. Readback confirms expected labels and names, preservation of other scenes and verified pre-replacement backups. Adding a scene updates Current before cloning it; existing-scene insertion leaves Current unchanged. Both replacement outputs match their expected reference files byte for byte.

Returning from the preview creates no output. Cancelling replacement preserves the target. Overlong labels require explicit adaptation approval; cancelling preserves the file without silent truncation. For CL3, the preview distinguishes 64 transferable channels from 32 out-of-capacity preparation rows retained in the table. The QA application exited naturally with code 0. All 707 personal files inventoried before these tests remained identical.

Source checks are separate: final targeted rerun 212/212, safety/capacity checks 104/104, Current disclosure 11/11 and final preview guard 14/14. These overlapping groups must not be added into a single total. The initial full report retains 12 failures out of 931 cases; all affected case names passed in the targeted rerun after correction. This is not represented as a fresh successful full-suite run.

Limits: no physical console, network or audio acceptance, and no fresh Yamaha CL/QL Editor import of these three outputs. Visible file conversions used French/dark; the other UI combinations belong to the separate automated visual smoke. Unknown-profile/unavailable-scene refusals were not newly exercised manually in this session. Licence data remained opaque. Windows qualification does not qualify macOS; public Mac packages remain at 2027.1.8 pending a separately verified delivery. Installer and ZIP hashes above identify the exact Windows files.


Actualisation / Update — 1 November 2026: la mention Mac 1.8 ci-dessus décrit l’état à la qualification Windows. Une livraison Mac 2027.1.10 séparée est maintenant vérifiée : [qualification Mac et limites / Mac checks and limits](QUALIFICATION-MAC-2027.1.10.md). Windows evidence remains distinct.
