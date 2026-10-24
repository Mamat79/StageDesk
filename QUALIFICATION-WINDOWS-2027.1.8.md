# StageDesk 2027.1.8 — qualification Windows / Windows qualification

Cette livraison concerne **Windows x64**. L’installeur a remplacé l’application précédente sur le Dell de construction ; un démarrage normal avec le profil Windows personnel existant et sa fermeture normale ont été vérifiés. **macOS reste en 2027.1.7**, avec ses paquets et ses limites de vérification propres.

## Identités

| Élément | Identité |
| --- | --- |
| Dépôt source privé | Mamat79/StageDesk-Source |
| Branche de construction et intégration | main |
| Commit exact de construction | 3abd2e53823b9f4f6d4cff37277e39c35365b02e |
| Définition du code applicatif conservée | 5ca087973c9d4f2be0207afc6f3a36e4820def82 |
| Commit des contrôles ciblés | 5ac4c722d0d6164286b3966b9c1e1c2c45d6f7f2 |
| Installeur | StageDesk-Setup-v2027.1.8.exe — 57 703 089 octets |
| SHA-256 installeur | 6f21f360bd93ec33e326968bb9648fef032183fdce129713f2d929877a53da69 |
| Archive | StageDesk-v2027.1.8-win-x64.zip — 81 832 259 octets |
| SHA-256 archive | 9a0f48381d5689fffef141e143cac1490570032dd4ec7e747d08de1ac301d715 |
| SHA-256 programme installé | ddb8dca4e201d200b5da8b2f240ae424beddfbf0e511db8667757a1feb92988f |

L’identité de construction est attestée par les manifestes externes et les octets qualifiés. La fenêtre À propos affiche 2027.1.8 / Windows x64 ; elle n’embarque pas de SHA source. Les documents approuvés ont été intégrés au commit final sans changement supplémentaire du comportement applicatif validé.

## Contrôles effectués

- **172 contrôles ciblés réussis**, sans échec ni test ignoré : 171 contrôles du parcours de licence et un contrôle des métadonnées WPF. Les nouveaux contrôles attendent réellement la fin des opérations asynchrones de l’interface.
- Publication .NET et compilation Inno locales, puis qualification indépendante du paquet : **170 fichiers de payload identiques** entre l’archive ZIP, le contenu extrait du Setup et le dossier de distribution qualifié. Versions et ressources de l’EXE et du Setup relues. Les erreurs/refus initiaux de supervision restent archivés séparément ; ils n’ont pas été renommés en succès.
- Quatre guides FR/EN générés et relus : **62 pages** au total, textes de licence, liens et limites de page vérifiés, rendu visuel inspecté. Les mêmes quatre PDF sont intégrés au paquet et joints à la Release. Les guides Suite restent inchangés.
- Recettes visuelles de licence en français/anglais, clair/sombre, essai neuf/expiré, avec acceptation indépendante et limites natives explicites ci-dessous. Le parcours gratuit sans code et les messages de licence permanente facultative ont été relus.
- Sauvegardes indépendantes sur deux volumes/disques, répétition de restauration isolée et comparaison des sources personnelles : 755 fichiers dans la vue Codex et 48 fichiers complémentaires dans le contexte Windows, par jeu de sauvegarde. Les deux vues contiennent des objets communs et des objets différents ; elles ont été qualifiées séparément par identités de fichiers.
- Installeur standard exécuté une fois jusqu’à sa sortie normale zéro, cible installée vérifiée et lancement automatique décoché. Les 170 fichiers du payload, 18 anciennes notes conservées et deux fichiers du désinstalleur sont présents : 190 fichiers installés. L’ancienne installation 2027.1.1 reste préservée. Le registre Windows et les raccourcis utiles correspondent à 2027.1.8.
- Démarrage personnel du **véritable programme installé**, sans argument ni substitution de profil : interface en français, thème sombre, préparation vierge et À propos 2027.1.8 / Windows x64. Fermeture normale avec code natif zéro ; tous les processus observés sont terminés. Aucun projet ouvert ou enregistré, aucun code saisi, aucune activation, préférence ou décision de récupération modifiée.
- Après fermeture : **967 entrées Codex strictement inchangées**. Dans la vue Windows, 79 entrées inchangées et trois deltas expliqués : licence et dates des dossiers parents. Toutes les valeurs de licence préexistantes sont conservées ; seule la date de dernière utilisation avance normalement. Réglages et **24 règles complètes** inchangés, sans réécriture. La référence au modèle Excel est conservée, même si le fichier référencé est absent. La présence temporaire de la seule instance démarrée a été identifiée puis retirée normalement ; aucune présence étrangère modifiée. Inventaires des fichiers installés identiques avant/après.

Les comparaisons privées ne divulguent ni code, token, clé, reçu d’activation ni valeur personnelle. Aucune restauration n’a été effectuée pour fabriquer une égalité.

## Limites des vérifications

Le clic natif sur Quitter **avant** la fin du décompte, le chronométrage natif exact des cinq secondes et l’atteinte de la taille minimale 680 × 560 DIP ne sont pas qualifiés par ces parcours. Les contrôles logiciels couvrent la règle d’attente ; ils ne remplacent pas ces observations natives manquantes.

Le réseau n’a pas été physiquement coupé pendant le démarrage personnel. Les contrôles de service utilisent notamment des transports simulés ; aucune nouvelle activation payée ou offerte n’a été réalisée. Aucun matériel audio, console, échange réseau réel, import de projet utilisateur ou conduite sur site n’est qualifié par cette livraison.

Les contrôles macOS historiques conservent leurs propres limites. Aucun paquet, version, signature, identifiant d’asset ni empreinte Mac n’est changé ; aucune compilation Mac ou GitHub Actions Windows n’a été lancée pour cette livraison. Les paquets Mac existants restent sur leur Release 2027.1.7.

## English

This release is for **Windows x64**. It was built locally from private source commit `3abd2e53823b9f4f6d4cff37277e39c35365b02e`, qualified, installed over the previous application and started once using the existing real Windows profile. About displayed 2027.1.8 / Windows x64. The ordinary process exited normally with native code zero; no activation, code entry, project or settings change was performed.

The targeted test run passed **172 checks with no failure or skip**. All **170 payload files** match between ZIP, extracted Setup and qualified distribution. The four approved bilingual guides contain **62 pages**. The standard installer exited zero and its automatic application launch was unchecked. Independent backup and restore rehearsals preceded replacement.

After the personal launch, all **967 Codex entries** stayed strictly unchanged. In the separate Windows view, **79 entries** stayed unchanged and only three individually explained file/directory metadata deltas remained. All preexisting licence values were preserved except the normal bounded last-seen date. Settings and all **24 complete replacement rules** stayed unchanged. The actual instance presence was observed and removed by normal disposal; installed file inventories stayed identical.

Early native Quit, exact native five-second timing and the minimum 680 × 560 DIP size remain unqualified. The actual personal launch did not disconnect networking; software tests with simulated transport do not prove a new real permanent-code activation or live console/network operation. No physical audio equipment or user project import was tested. Initial failed/refused supervisor runs remain recorded separately.

**macOS remains at 2027.1.7** with original assets, hashes and its historical verification limits. No Mac package/job or Windows GitHub Actions build was added. This report contains no personal licence values or private machine paths.
