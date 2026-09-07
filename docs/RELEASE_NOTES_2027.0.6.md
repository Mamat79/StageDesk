# StageDesk v2027

Version Windows : 2027.0.6.

## Français

- Les tableaux indiquent désormais clairement les cellules modifiables et les
  champs en lecture seule, sans changer les droits ni les règles métier.
- Les colonnes dotées d'un éditeur intégré (libellé, couleur et icône) sont
  correctement signalées comme modifiables.
- Les contrastes des actions, états et textes secondaires ont été renforcés en
  thèmes clair et sombre, en français comme en anglais.
- Les alertes LIVE locales de StageFlow sont lues séparément de la connexion au
  projet : elles restent disponibles sur le même ordinateur même sans session
  réseau jointe.
- L'acquittement est local à chaque destinataire. Mettre la réception locale en
  pause ou suspendre l'émission globale écarte le retard accumulé au lieu de le
  rejouer lors de la reprise.
- Les fichiers LIVE sont contrôlés avant lecture (session, projet, schéma,
  taille et cohérence) et ne modifient pas le document du projet.

Les identifiants nécessaires à la compatibilité restent inchangés : projets
`.smt` et `.smtshow`, domaine `smt/smt.json`, identifiant d'application, alias
de mise à jour et canal historique. Le nom public reste exclusivement
**StageDesk**. Les profils, licences et données utilisateur existants sont
conservés.

Cette livraison ne modifie ni ne republie les artefacts macOS.

[Télécharger pour votre système](https://www.silemio.com/logiciels/stagedesk)

## English

- Tables now clearly distinguish editable cells from read-only fields without
  changing permissions or business rules.
- Columns with embedded editors (label, colour and icon) are correctly marked
  as editable.
- Action, status and secondary-text contrast has been strengthened in light and
  dark themes, in both French and English.
- Local StageFlow LIVE alerts are read independently from project connection:
  they remain available on the same computer without a joined network session.
- Acknowledgement is local to each recipient. Pausing local reception or global
  emission discards accumulated backlog instead of replaying it after resume.
- LIVE files are checked before use (session, project, schema, size and
  consistency) and never modify the project document.

Compatibility identifiers remain unchanged: `.smt` and `.smtshow` projects,
the `smt/smt.json` domain, application identifier, update alias and historical
channel. The public product name remains exclusively **StageDesk**. Existing
profiles, licences and user data are preserved.

This release neither changes nor republishes macOS assets.

[Download for your system](https://www.silemio.com/en/software/stagedesk)
