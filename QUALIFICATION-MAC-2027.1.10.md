# StageDesk macOS 2027.1.10 — vérifications et limites / checks and limits

## Français

Les nouveaux paquets Apple Silicon et Intel, leurs deux fichiers SHA-256 et quatre guides Mac ont été construits avec Codemagic, puis qualifiés séparément de Windows. Ils complètent la release 2027.1.10 existante ; les fichiers Windows et les anciennes versions sont conservés. Les guides Mac ont des noms distincts des guides Windows et correspondent aux documents embarqués.

La nouvelle exécution des tests sur Mac compte **2 193 réussites : 1 259 Core et 934 Desktop**, aucun échec ni test ignoré. Ce total décrit cette exécution ; les contrôles Windows et les anciens résultats Mac ne lui sont pas substitués.

Sur Apple Silicon, l'application a été lancée depuis le **DMG monté en lecture seule**, avec un profil et une présence QA isolés. Elle s'est fermée normalement avec le code 0 en 46,672 secondes, avant la borne de 180 secondes, puis le volume a été détaché. La version 2027.1.10 a été rapprochée dans les métadonnées des deux paquets, le résultat du smoke et le parcours de conversion.

Le smoke de l'application montée produit **41 rendus de composants Avalonia**, dont 24 vues du parcours de conversion couvrant français/anglais, clair/sombre et deux tailles de fenêtre. Huit échantillons ont été examinés. Il vérifie les trois intentions, le retour depuis l'aperçu sans écriture et la conservation de la préparation sur des sélections synthétiques. Ces images sont des rendus de composants, pas des captures intégrales du bureau ni une recette humaine complète des dialogues natifs.

Les limites suivantes s'appliquent :

- **Intel : compilation et contrôle statique uniquement**, sans exécution sur un Mac Intel physique.
- **macOS 14 minimum déclaré** dans les métadonnées ; aucune matrice d'essais des versions de macOS n'est revendiquée. Runtime .NET 10.0.12 autonome.
- Signature ad hoc contrôlée sur le runner ; **pas de Developer ID ni de notarisation**.
- Aucun essai sur console physique, réseau, audio ou projecteur ; aucune installation ou migration sur un profil personnel Mac.
- Le smoke synthétique ne prouve pas des conversions réelles de fichiers, écritures d'adaptateurs ou sauvegardes par l'interface Mac. Les trois cas CL3 exécutés sous Windows restent une preuve Windows distincte. Les annulations en milieu d'écriture et les modifications externes de fichiers pendant un aperçu ne sont pas qualifiées par ce smoke. Les contrôles source couvrent des protections distinctes et ne remplacent pas ces essais natifs.
- Des tests à fixtures privées facultatives peuvent ne pas exercer leur témoin si la fixture manque ; le total CI ne prouve pas leur exécution. Les témoins synthétiques obligatoires et les modèles embarqués sont distincts.
- **Une nouvelle activation permanente sur Mac n'est pas prise en charge.** Le parcours actuel dépend de Windows DPAPI. L'utilisation gratuite reste disponible avec **Continuer avec StageDesk**, y compris hors ligne ; prix et droits existants restent inchangés.

L'ancienne tentative interrompue ne qualifie aucun paquet livré. La présente qualification se rapporte exclusivement à la nouvelle construction vérifiée. Les huit fichiers publics ont été téléchargés intégralement sans authentification et leurs tailles/SHA-256 comparés aux fichiers qualifiés avant la mise à jour des liens Mac courants.

## English

The new Apple Silicon and Intel packages, two SHA-256 sidecars and four Mac guides were built with Codemagic and qualified separately from Windows. They extend the existing 2027.1.10 release while preserving its Windows files and all earlier versions. Mac guides use distinct names and match the embedded documents.

The new Mac test execution reports **2,193 passed: 1,259 Core and 934 Desktop**, zero failures and skips. Windows checks and historical Mac results are separate evidence.

On Apple Silicon, the application launched from the **read-only mounted DMG**, using isolated QA profile/presence directories. It exited naturally with code 0 in 46.672 seconds, within 180 seconds, and the volume was detached. Version 2027.1.10 was explicitly checked across both packages' metadata, the smoke result and the conversion-workflow result.

The mounted smoke produced **41 Avalonia component renders**, including 24 conversion views across French/English, light/dark and two window sizes. Eight samples were reviewed. Synthetic selections exercise the three intentions, returning from the preview without writing and preserving the preparation. These are component renders, not full desktop screenshots or complete human acceptance of native dialogs.

Limits: **Intel is cross-built and statically inspected only**, without physical Intel execution. **macOS 14 is a metadata minimum**, without an OS-version test matrix; runtime .NET 10.0.12 is self-contained. Signing is ad hoc, without Developer ID or notarization. No real console, network, audio, projector, personal installation or personal-profile migration was tested.

The synthetic Mac smoke does not prove real adapter file conversion/write/backup through the Mac interface. The three actual Windows CL3 cases remain Windows evidence. Mid-write cancellation and external file changes during a preview are not qualified by this smoke; source tests cover separate protections. Optional private fixtures may return early when absent, so the CI total does not assert that every optional witness ran.

**New permanent activation on Mac is unsupported by the current Windows/DPAPI activation path.** Free use remains available through **Continue with StageDesk**, including offline; existing pricing and rights are unchanged.

The earlier interrupted attempt does not qualify these packages. This qualification refers only to the new verified build. All eight new public files were fully downloaded anonymously and compared against expected sizes/SHA-256 before updating current Mac links.

## DMG SHA-256

Apple Silicon — `StageDesk-v2027.1.10-osx-arm64.dmg` — 86 399 280 bytes:

```text
fba24cece330ccd0e6f0c64eb09e4190bd1aeaaeb5cd45bd1bfdad7b25f1585c
```

Intel — `StageDesk-v2027.1.10-osx-x64.dmg` — 88 529 470 bytes:

```text
53a62f7ada5373d6c6c1eae1ff655b2f6a6e53a6f633e3bb23a055d7d28a0adb
```
