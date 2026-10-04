# StageDesk 2027.1.5 — qualification Windows/macOS / Windows/macOS qualification

## Français

Cette version réduit à 5 secondes le rappel au démarrage après les 30 jours
d'essai inchangés. Une licence valide conserve zéro attente. Le rappel ne bloque
aucune fonction après le décompte et n'interrompt jamais une session en cours.
Les projets, réglages et activations sont conservés.

Paquets Windows x64, macOS Apple Silicon (arm64) et macOS Intel (x64), avec
empreintes SHA-256. Ils proviennent du même commit source privé qualifié :
`562742c183e165f4f5a62f4c80a4080929573216`.
Le tag public désigne uniquement la documentation et la distribution sans source.

Vérifications Windows : 1153 tests du moteur, 856 tests Desktop, 68 contrats WPF,
et 27 tests ciblés de licence. Le test du dialogue attend effectivement environ
5 secondes dans les deux langues. Installation standard vérifiée sur Windows ;
les 166 fichiers du paquet concordent.

Vérifications Mac : build Codemagic `6ac2857b6c3f58a525bef88f` sur Mac mini M2,
1153 tests du moteur et 856 tests Desktop réussis. Les deux paquets et leurs
architectures sont vérifiés. Le démarrage natif Apple Silicon est contrôlé avec
17 captures automatisées FR/EN, clair/sombre. Les quatre notices StageDesk
extraites indépendamment de chaque DMG concordent avec les notices Windows.

### Limites de qualification

- Pas d'exécution native ni de recette d'installation sur Mac Intel.
- Pas de recette native Mac dédiée au décompte après expiration de l'essai ;
  la validation Mac couvre les tests automatisés partagés et le démarrage arm64.
- Pas de signature Developer ID ni de notarisation Apple revendiquées.
- Les captures automatisées ne sont pas une recette manuelle en exploitation.
  Huit images d'alertes utilisent des composants synthétiques, pas des alertes
  d'un réseau réel.
- Aucun nouveau test sur console physique ni aucune recette terrain.
  Le comportement et les limites Lawo, CL/QL et des autres connecteurs de
  la version 2027.1.4 restent inchangés.

Les notices, licences et anciennes releases sont conservées. Les fichiers de
récupération ne sont pas supprimés par le remplacement du programme.

## English

This release reduces the startup reminder to 5 seconds after the unchanged
30-day trial. Valid licences retain zero wait. The countdown never disables
features afterwards or interrupts an active session. Projects, settings and
activations are preserved.

Windows x64, macOS Apple Silicon (arm64) and macOS Intel (x64) packages include
SHA-256 checksums. All are built from the same qualified private source commit:
`562742c183e165f4f5a62f4c80a4080929573216`.
The public tag identifies only the source-free documentation/distribution.

Windows checks: 1153 Core tests, 856 Desktop tests, 68 WPF contracts and 27
targeted licensing tests passed. The dialog test actually awaits approximately
five seconds in both languages. The standard Windows installation was verified
with all 166 package files matching.

Mac checks: Codemagic build `6ac2857b6c3f58a525bef88f` on a Mac mini M2 passed
1153 Core and 856 Desktop tests. Both packages and their architectures were
verified. Native Apple Silicon startup was checked with 17 automated captures,
FR/EN and light/dark. All four StageDesk manuals independently extracted from
each DMG match the Windows manuals.

### Qualification limits

- No native execution or installation acceptance on an Intel Mac.
- No dedicated native Mac acceptance of the expired-trial countdown; Mac
  evidence covers shared automated tests and native arm64 startup.
- No Developer ID signing or Apple notarization is claimed.
- Automated captures are not manual production acceptance. Eight alert images
  exercise synthetic components, not real network alerts.
- No new physical-console testing or field acceptance. Lawo, CL/QL and other
  connector behavior and qualification limits from 2027.1.4 remain unchanged.

Manuals, licences and earlier releases are retained. Program replacement does
not delete recovery copies.
