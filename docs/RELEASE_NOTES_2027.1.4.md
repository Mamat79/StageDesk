# StageDesk 2027.1.4

## Français

Cette version ajoute les échanges de labels Lawo dans StageDesk, sur fichiers
natifs et, pour les profils modernes testés, directement sur le réseau local.

- Productions `.lpn` : import de Current ou d'un snapshot, transfert des labels
  vers un état existant, ou création d'un snapshot par duplication.
- Profils testés : mc²66 MKII sous mxGUI 5.14.2.6 ; mc²36 MKII 32 faders,
  mc²56 MKIII et mc²96 sous mxGUI 12.4.0.0.
- Nouvelle production depuis votre seed natif privé. Les données héritées sont
  conservées : ce n'est pas un modèle usine vierge ni une conversion entre
  générations. Aucun projet personnel n'est distribué.
- Ember+ moderne : IPv4 manuelle ou détection volontaire sur l'interface
  choisie, port configuré explicitement, identification typée du produit et du
  firmware, puis lecture et envoi des labels Current.
- Identités DSP stables, sans correspondance fondée sur l'ordre des faders.
  Le nom court moderne est conservé lors de l'envoi depuis le tableau.
- Prélecture, confirmation et sauvegarde avant envoi ; nouvelle lecture côté
  fournisseur puis contrôle indépendant avant annonce de réussite. Un échec
  ou une annulation n'entraîne aucune nouvelle tentative automatique.
- Labels uniquement : aucun gain, mute, fader, routage, couleur, icône, rappel
  ou mémorisation de snapshot n'est envoyé par le connecteur Lawo.
- Le profil ancien 5.14 reste limité aux fichiers. Les révisions inconnues,
  protections non qualifiées et miroirs legacy incomplets sont refusés.

Les productions ont été chargées, sauvegardées et relues dans mxGUI ; les
échanges Ember+ ont été vérifiés sur des simulateurs isolés. Ces preuves ne
constituent pas une qualification sur console physique. Le nombre de
structures DSP stockées ne prouve pas les capacités ou licences du matériel.
Consultez le [complément Lawo](LAWO_NATIVE_AND_NETWORK.md) pour les limites de
noms, les sauvegardes et la procédure de préparation hors antenne.

La génération commerciale v2027, les licences et les corrections 2027.1.3
restent conservées. Les guides PDF existants sont accompagnés du complément
Lawo bilingue. Windows x64, macOS Apple Silicon et Intel utilisent le même
connecteur ; l'exécution native Mac Intel et la notarisation Apple ne sont pas
revendiquées.

## English

This version adds Lawo label exchange in StageDesk through native files and,
for the tested modern profiles, directly over the local network.

- `.lpn` productions: import Current or a snapshot, transfer labels to an
  existing state, or create a snapshot by duplication.
- Tested profiles: mc²66 MKII with mxGUI 5.14.2.6; mc²36 MKII 32 faders,
  mc²56 MKIII and mc²96 with mxGUI 12.4.0.0.
- New production from your private native seed. Inherited data are retained;
  this is not a blank factory template or cross-generation conversion. No
  personal production is distributed.
- Modern Ember+: manual IPv4 or explicit discovery on the selected interface,
  an explicitly configured port, typed product/firmware identification, then
  Current-label read and transfer.
- Stable DSP identities, never fader-order matching. Modern short names are
  preserved when sending from the StageDesk table.
- Safety read, confirmation and backup before sending; fresh provider values
  and an independent readback are required before reporting success. Failure
  or cancellation never triggers an automatic retry.
- Labels only: the Lawo connector sends no gain, mute, fader, routing, colour,
  icon, snapshot recall or snapshot-store commands.
- The legacy 5.14 profile remains file-only. Unknown revisions, unqualified
  protections and incomplete legacy mirrors are refused.

Productions were loaded, saved and reread in mxGUI, and Ember+ transfers were
verified on isolated simulators. This is not physical-console qualification.
Stored DSP structures do not prove hardware capacity or licences. Read the
[Lawo supplement](LAWO_NATIVE_AND_NETWORK.md) for naming limits, backups and
off-air preparation guidance.

The v2027 commercial generation, licensing and 2027.1.3 fixes are retained.
Existing PDF guides are accompanied by the bilingual Lawo supplement. Windows
x64, macOS Apple Silicon and Intel use the same connector; native Mac Intel
execution and Apple notarisation are not claimed.
