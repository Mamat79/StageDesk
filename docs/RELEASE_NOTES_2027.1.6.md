# StageDesk 2027.1.6 — maintenance

Livraison du 10 octobre 2026, qualifiée sur Windows x64 et macOS Apple Silicon.
Les paquets et leurs empreintes sont publiés ; l'installation sur chaque poste
reste une étape distincte.

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

## Qualification et provenance / Qualification and provenance

Source produit : 96dcd0a11b5244f582c5b3a578ebc96c4148cf42, tag v2027.1.6.
Les paquets Windows qualifiés et les deux DMG proviennent de cette même source.
Le dépôt public conserve uniquement la distribution et la documentation.

Les DMG publics sont les fichiers du véritable job Codemagic tagué
6aca20edbe310044f98dfe89, et non ceux du build de branche privé. Tests de ce
job : 1153 Core et 866 Desktop, zéro échec ; lancement natif arm64 réussi,
17 exports FR/EN clair/sombre. Les cinq exports relus par l'atelier et les
douze restants relus avant publication couvrent les 17 fichiers, uniquement
dans les régions capturées. Les tests conditionnels Windows-only ne prouvent
pas les permissions Windows sur Mac.

Le job tagué reste en statut failed : seule l'étape de publication a échoué
à la lecture de la release existante, sans cause d'authentification précise
exposée. Le téléversement a été réparé avec l'accès GitHub opérationnel, sans
rebuild, sans nouveau tag, sans écrasement et sans transfert de secret. Les
24 assets publics et leurs 12 sidecars ont été contrôlés ; les quatre fichiers
Mac ont été retéléchargés anonymement et comparés aux artefacts de ce job.

- Apple Silicon : 85 922 985 octets, SHA-256
  `443df41e3599dda167064c9cee3a8fac0186408719afe1ec2f058b4b03807282`.
- Intel x64 : 88 103 833 octets, SHA-256
  `0637baf97964a691157a65d16b396bd3016559a225462dfe62c9c68e64f945f4`.
- Installateur Windows : SHA-256
  `e27f43e899a32fbf1e5ea82dc3d4a8e2e6438c424065243396ca43aaed20ba9a`.
- ZIP Windows : SHA-256
  `843e564bfd5f7743fb81f45e44badc77b4e159aec4377fa26e64052e3f611bee`.

Le seuil macOS 14+ de la recette privée est accepté par correspondance
historique documentée : Xcode 26.6 (17F113), image documentée macOS 26.5.1.
Ce recoupement n'est pas une mesure directe sw_vers du runner.

Limites : pas de mise à jour de profil Mac utilisateur, pas d'exécution native
Intel, pas de signature Developer ID/notarisation, pas d'activation physique ni
de nouvelle recette sur console réelle. Signature Mac d'intégrité ad hoc,
installateur Windows non signé. Le smoke lance le bundle de staging, pas
l'application depuis le DMG monté. Les exports visuels sont des rendus de
l'application, pas une recette réseau sur du matériel. Le contrôle de toutes
les vues défilantes et transitions DPI n'est pas déclaré effectué.

L'asset `RELEASE_NOTES_2027.1.6.md` et son checksum joints à la release sont
conservés sans écrasement comme instantané du staging initial. Le présent
document du dépôt et le texte de la release décrivent la livraison finale.
Aucune installation utilisateur ni mise à jour du site n'est déclarée par
ce reçu de publication.

Public Mac DMGs are the exact artifacts from the genuine tagged Codemagic
job above. Tests, both packages and the native arm64 smoke passed; the job's
overall failed status is retained because its release-read/upload step failed.
GitHub upload was repaired without rebuilding or overwriting. Native Intel,
Mac user-profile upgrade, Developer ID/notarization and physical-console or
activation qualification remain unperformed. macOS 14+ is required. The
attached release-notes asset is the immutable initial staging snapshot;
this repository document and the release body supersede its staging status.
