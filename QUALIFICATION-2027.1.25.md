# StageDesk 2027.1.25

- Windows · `dfb705171772eb8556f830d3cae8cae5af94f52e`
- macOS · `be345354471c18c98072ad1905f3d4fd3f595cbd`

Les révisions ont le même code et les mêmes guides. Seule la liste des empreintes utilisée pour empaqueter les guides Mac diffère.

Both revisions use the same application code and guides. Only the checksum list used to package the Mac guides differs.

## Windows

- Windows x64. Installateur Setup et archive portable.
- 79 tests moteur ciblés et 197 tests de l’application ont réussi sur le Dell pendant la qualification. Les libellés d’aide actualisés ont fait l’objet de 55 tests ciblés.
- Les 171 fichiers extraits de l’installateur ont été comparés au paquet portable.
- L’atelier a vérifié l’installation et la désinstallation dans un environnement isolé. Le Setup Windows est non signé.
- Les guides SiLeMI/O FR et EN intégrés à l’aide correspondent à l’édition 2027.7 approuvée.

- Windows x64. Setup installer and portable archive.
- 79 focused engine tests and 197 application tests passed on the Dell during qualification. The updated Help text was covered by 55 focused tests.
- All 171 files extracted from Setup were compared with the portable package.
- Installation and removal passed in an isolated environment. Windows Setup is unsigned.
- The French and English SiLeMI/O guides in Help match the approved 2027.7 edition.

## macOS

- macOS 14 ou ultérieur. Deux DMG distincts, Apple Silicon et Intel.
- 1 850 tests moteur et 1 044 tests de l’application ont réussi sur Codemagic. Trois groupes de tests utilisant des projets Allen & Heath locaux ont été ignorés faute de fichiers témoins sur le Mac mini. Les tests correspondants ont été exécutés dans la recette Windows.
- Le DMG Apple Silicon a été monté en lecture seule et l’application a démarré sur le Mac mini M2. Le paquet Intel a été contrôlé pour l’architecture x86_64. Un essai sur Mac Intel physique reste à faire.
- Le parcours gratuit reste accessible sur Mac. L’activation d’un nouveau code de licence permanente est disponible sous Windows.

- macOS 14 or later. Separate Apple Silicon and Intel DMGs.
- 1,850 engine tests and 1,044 application tests passed on Codemagic. Three test groups requiring local Allen & Heath projects were skipped because their files were unavailable on the Mac mini. The corresponding tests ran during Windows qualification.
- The read-only mounted Apple Silicon DMG launched on the Mac mini M2. The Intel package passed x86_64 architecture verification. Runtime testing on physical Intel hardware remains pending.
- Free use remains available on Mac. Activation of a new permanent license code is available on Windows.

## Consoles / Consoles

La notice professionnelle documente les protocoles et les paramètres accessibles en direct par famille. Les conversions sur fichier et les connexions directes dépendent du modèle, de la version et du réglage. Le rapport de conversion recense les points à contrôler ou à reprendre dans la destination.

The professional guide documents direct connection protocols and supported operations by family. File conversion and direct access depend on the model, version and setting. The conversion report lists details to review or complete on the destination.
