# StageDesk 2027.1.6 — maintenance

Candidate de livraison préparée le 10 octobre 2026. La publication et
l'installation restent soumises à la recette croisée Windows/macOS.

## Français

- Les copies de récupération illisibles sont signalées avec leur emplacement
  et conservées. Un dossier de copies différées inaccessible n'empêche plus
  de proposer les copies lisibles. Les sauvegardes suivantes ne remplacent
  pas silencieusement une copie reconnue illisible.
- Migration vers .NET 10 LTS, runtime auto-contenu 10.0.12 : aucun SDK requis
  pour l'utilisateur des paquets distribués. Nouvelle candidate Mac : macOS 14
  ou ultérieur ; vérifier ce prérequis avant remplacement d'une version antérieure.
- Aucune nouvelle fonction de console, modification des formats de projets,
  contrats LIVE, droits/signatures de licence ou remise à zéro de l'essai.
  Le rappel de fin d'essai conserve ses 5 secondes ; une licence valide n'attend pas.
- Les essais logiciels ne constituent pas une validation sur console physique.
  Les limites matérielles, Intel natif, signature et notarisation restent celles
  des recettes documentées ; ne pas les déduire d'une compilation réussie.

## English

- Unreadable recovery copies are retained and reported with their location.
  An inaccessible deferred-copy directory no longer hides readable copies.
  Later autosaves do not silently replace a copy identified as unreadable.
- Migration to .NET 10 LTS, self-contained runtime 10.0.12. Distributed packages
  do not require a user-installed SDK. New Mac candidate requires macOS 14 or later.
- No new console feature or change to project formats, LIVE contracts, licence
  rights/signatures or trial lifetime. Expired-trial reminder stays at five seconds;
  valid licences retain zero wait.
- Software tests are not physical-console qualification. Native Intel execution,
  signing and notarization remain separate, explicitly recorded acceptance steps.

## État du staging / Staging status

Cette prérelease n'est pas la version stable ni la dernière version recommandée.
Les paquets Windows sont présents ; les assets macOS seront ajoutés par le
pipeline tagué après son préflight d'accès et de budget. Aucune installation
utilisateur n'est déclarée réalisée. Le site et la release stable précédente
ne sont pas remplacés par ce staging.

Recette privée croisée : Windows x64 et macOS arm64 natif réussis sur la même
source 96dcd0a11b5244f582c5b3a578ebc96c4148cf42. Tests Mac : 1153 Core et
866 Desktop, zéro échec. Les deux architectures Mac et leurs DMG sont vérifiés.
Le job Mac relève Xcode 26.6 (17F113), recoupé avec la fiche officielle historique
de l'image macOS 26.5.1 ; ce n'est pas une mesure directe sw_vers du runner.

Limites : pas de mise à jour de profil Mac utilisateur, pas d'exécution native
Intel, pas de signature Developer ID/notarisation, pas d'activation physique ni
de nouvelle recette sur console réelle. Les exports visuels de smoke sont des
rendus de l'application, pas une recette réseau sur du matériel.

This is a staging prerelease, not the stable/latest release. Windows assets
are available; macOS assets await the tagged pipeline and its access/budget
preflight. No user installation is claimed. Native Intel execution, Mac user
profile upgrade, Developer ID/notarization and physical-console/activation
qualification remain unperformed.
