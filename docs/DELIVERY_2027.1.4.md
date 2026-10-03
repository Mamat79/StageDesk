# StageDesk 2027.1.4 — livraison vérifiée / verified delivery

## Français

Livraison stable du 3 octobre 2026 :
[release GitHub publique](https://github.com/Mamat79/StageDesk/releases/tag/v2027.1.4),
[fiche StageDesk](https://silemio.com/logiciels/stagedesk).

Les sources restent dans `Mamat79/StageDesk-Source`. Le tag privé `v2027.1.4`
désigne le commit compilé `6ba0a3681ddf30274f37410c68bbd7b231f97e15` ;
590 fichiers de source, tests, dépendances et packaging concordent avec le
checkout testé. La branche de travail et l'index existants sont conservés.
Le tag public désigne le commit de documentation sans code source
`3dfb3ceffcd42c01cead1667f5763661e6a7d83b`. Aucun asset précédent n'est remplacé.

### Vérifications

- Windows Release : Core 1153/1153 sur deux passages complets, Desktop 850/850,
  WPF 68/68 ; aucun test ignoré dans ces suites.
- Smoke du paquet Windows et de la copie installée : 17 captures chacun,
  français/anglais, clair/sombre, six commandes de suite vérifiées et fichiers
  d'entrée inchangés. Profil de recette séparé du profil utilisateur.
- Installateur isolé : installation et désinstallation réussies, 166 fichiers
  comparés sans modification de l'installation, de l'activation ou des raccourcis.
- Remplacement réel par l'installateur publié : version 2027.1.4 enregistrée,
  166 fichiers conformes, 373 fichiers utilisateur inchangés ; un seul raccourci
  Bureau nommé `StageDesk v2027`. Sauvegarde préalable vérifiée : 548 fichiers,
  plus l'enregistrement de désinstallation, conservés localement.
- Mac : [Codemagic build 18 sur Mac mini M2](https://codemagic.io/app/6a9ebd96b4b9452bca44fee1/build/6ac077107394575b200a9d0b),
  tag exact v2027.1.4, commit exact ci-dessus ; Core 1153/1153, Desktop 850/850,
  deux architectures vérifiées et smoke natif arm64 de 17 captures. Les DMG
  téléchargés depuis Codemagic sont identiques aux assets GitHub.
- GitHub Latest stable : 14 assets, tous téléchargés sans authentification,
  avec concordance SHA-256 des fichiers, des digests GitHub et des sidecars.
- Site SiLeMI/O : version 170, source
  `d563a7d506f75b59b9a47c72aee6ef6bb186ed7e`, publication réussie. Pages FR/EN
  relues ; six redirections de téléchargement vérifiées après la redirection
  canonique du domaine vers `www`, avec la bonne version et clé SHA-256.
  Les releases des autres logiciels et les PDF précédemment approuvés sont inchangés.

### Empreintes des paquets

| Fichier | SHA-256 |
|---|---|
| StageDesk-Setup-v2027.1.4.exe | `8c7626e9c8b4a4c0a94f284550da0796f3b57fabb25950398214d7baa1e6e3fc` |
| StageDesk-v2027.1.4-win-x64.zip | `ec448a4411f09bca4e77e4c23fa245dce284acb1e0414ed71198036ecc70eb96` |
| StageDesk-v2027.1.4-osx-arm64.dmg | `ac6cc874775ff1dd8d7e0138463dc26c31b418c1008d1b67dc6b5568c4724480` |
| StageDesk-v2027.1.4-osx-x64.dmg | `cec41b9fbb10d800ba81d4507cf1fb6140fd0d5c41c63f74275d3504f1f515a7` |

L'exécutable Windows installé et celui du paquet ont le même SHA-256 :
`97c0a9d19136e4589477f6b6d90100d773515fe7aa0a5734ef296834028d769e`.

### Périmètre et limites

Lawo mc²66 MKII 5.14.2.6 : fichiers natifs seulement. Lawo mc²36 MKII 32 faders,
mc²56 MKIII et mc²96 12.4.0.0 : fichiers natifs et labels Current par Ember+.
Les nouvelles productions partent du seed privé de l'utilisateur, pas d'un
modèle usine redistribué ni d'une conversion entre générations. Aucun gain,
mute, fader, routage, couleur, icône ou rappel/store réseau n'est envoyé.
Les originaux Lawo, 664 fichiers, sont conservés sans changement ; les clones
de recette sont arrêtés et leurs interfaces réseau désactivées.

Les chargements/sauvegardes mxGUI et les simulateurs isolés ne constituent pas
une qualification sur console physique. L'exécution native Intel, une installation
interactive sur Mac Intel et la signature/notarisation Apple ne sont pas revendiquées.
La recette physique hors antenne reste nécessaire avant utilisation en exploitation.
La notice [Lawo fichiers et réseau](LAWO_NATIVE_AND_NETWORK.md) et les
[notes de version bilingues](RELEASE_NOTES_2027.1.4.md) décrivent les limites.

## English

StageDesk 2027.1.4 is the verified stable Windows/Apple Silicon/Intel release.
The Windows installation was replaced with the published installer; all 166
payload files match, 373 user-profile files remain unchanged, and the desktop
keeps one `StageDesk v2027` shortcut. A verified 548-file rollback backup is
retained locally. Licensing and the v2027 commercial generation are preserved.

The exact private source tag and public source-free distribution commit are
listed above. Windows passed 1153 Core, 850 Desktop and 68 WPF tests. The tagged
M2 build passed 1153 Core and 850 Desktop tests, both package architecture checks,
and a native arm64 17-capture smoke. The installed Windows smoke also passed.
All 14 public assets were downloaded and their full-file SHA-256 verified.
The bilingual website and all six installer redirects were checked after publication.

The package hashes above are authoritative. The new bilingual Lawo supplement
accompanies the existing approved PDF guides. Lawo modern Ember+ transfers
Current labels only, with explicit IP/port, confirmation, backup and independent
readback; legacy 5.14 remains file-only. Native mxGUI tests are not physical-console
certification. Native Mac Intel execution and Apple notarisation remain unverified.
