# StageDesk v2027

Version 2027.0.0 - Windows x64, macOS Intel et Apple Silicon.

## Français

- Centre StageFlow LIVE accessible en haut à droite : découverte réseau,
  adresse manuelle, projet et hôte identifiés, association volontaire et déconnexion.
- Collage des codes à six chiffres avec espaces ou tirets et conservation des
  zéros initiaux. Les sessions redémarrées et les codes incorrects sont distingués.
- Déconnexion immédiate côté application : une réponse réseau tardive ne peut
  pas rétablir une session quittée. Le tableau reste ouvert, sans reconnexion automatique.
- Installateur Windows EXE et DMG distincts pour Mac Intel et Apple Silicon.
- La recherche de mises à jour compare la version complète installée et choisit
  l'installateur correspondant au système.
- Nom public StageDesk, icône officielle transparente, notices FR/EN harmonisées.

Les projets `.smt`, `.smtshow` et `.stageflow`, les connecteurs existants et les
licences restent compatibles. Aucun export console ou DAW n'est déclenché par LIVE.

Les DMG utilisent une signature d'intégrité ad hoc. Ils ne sont pas signés avec
Developer ID ni notarisés par Apple ; macOS peut donc afficher un avertissement.
Les SHA-256 sont fournis avec chaque téléchargement officiel.

## English

- Top-right StageFlow LIVE connection center: network discovery, manual address,
  identified project and host, voluntary association and disconnection.
- Six-digit codes accept pasted spaces or hyphens and preserve leading zeros.
  Restarted sessions and incorrect codes have distinct messages.
- Immediate local disconnection: late network responses cannot restore a session
  that has been left. The table stays open without automatic reconnection.
- Windows EXE installer and separate Intel / Apple Silicon DMGs.
- Update checks compare the complete installed version and select the installer
  matching the operating system and architecture.
- StageDesk public name, official transparent icon and consistent FR/EN guides.

Existing `.smt`, `.smtshow` and `.stageflow` projects, connectors and licenses remain
compatible. LIVE never triggers a console or DAW export.

DMGs use ad-hoc integrity signing, not Apple Developer ID signing or notarization;
macOS may therefore display a warning. SHA-256 files accompany official downloads.
