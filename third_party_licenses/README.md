# Corpus de licences du paquet desktop StageDesk v2026

Ce dossier accompagne les paquets publics Windows `win-x64` et macOS
`osx-x64` / `osx-arm64`. L'inventaire a été recoupé avec trois publications
non découpées et non rognées de `SMT.Desktop` pour ces RID. Les dépendances de
build ou de test absentes des sorties publiées ne sont pas revendiquées comme
des composants distribués.

Les fichiers sont des copies intégrales, non réécrites :

| Groupe distribué | Version(s) | Source exacte du texte |
|---|---:|---|
| Avalonia UI | 12.0.3 | `Avalonia-LICENSE.md` et `Avalonia-NOTICE.md`, dépôt `AvaloniaUI/Avalonia`, commit `21e816874efa142bf9903b51fd323d1f35e56ab3` |
| Avalonia Controls DataGrid | 12.0.0 | `Avalonia.Controls.DataGrid-LICENSE.md`, dépôt `AvaloniaUI/Avalonia.Controls.DataGrid`, commit `3d2cf024d6f15d4e770f655246185ad417f93f51` |
| ANGLE Windows natif | 2.1.25547.20250602 | `Avalonia.ANGLE-LICENSE`, fichier `LICENSE` du paquet NuGet exact |
| Police Inter embarquée par Avalonia | 3.019, `git-0a5106e0b` | `Inter-OFL-LICENSE.txt`, dépôt `rsms/inter`, commit `0a5106e0b`; version et licence recoupées avec la table `name` du TTF distribué |
| ClosedXML | 0.105.0 | `ClosedXML-LICENSE`, dépôt `ClosedXML/ClosedXML`, commit `d15f6690886801980c0d83b7eb1d1b5d2171ad31` |
| ClosedXML.Parser | 2.0.0 | `ClosedXML.Parser-LICENSE.txt`, dépôt `ClosedXML/ClosedXML.Parser`, commit `658973aeedc2fe289e0ccba2bb9959f67692ded5` |
| Open XML SDK | 3.1.1 | `OpenXML-SDK-LICENSE` et `OpenXML-SDK-NOTICE`, dépôt `dotnet/Open-XML-SDK`, commit `f9e6ad7524e22b6b1f932deabc9055201b7870c0` |
| ExcelNumberFormat | 1.1.0 | `ExcelNumberFormat-LICENSE`, dépôt `andersnm/ExcelNumberFormat`, tag/commit `v1.1.0` / `38c6a71919ad3895e3ba61d7a888012670d26303` |
| SkiaSharp et HarfBuzzSharp | 3.119.4-preview.1.1 et 8.3.1.3 | `SkiaSharp-HarfBuzzSharp-LICENSE.txt` et `SkiaSharp-HarfBuzzSharp-THIRD-PARTY-NOTICES.txt`, fichiers des paquets NuGet exacts; les notices Win32 et macOS ont le même SHA-256 |
| MicroCom.Runtime | 0.11.4 | `MicroCom.Runtime-LICENSE`, dépôt `kekekeks/MicroCom`, commit `28850f85fb586488828ab7267ed4a87e8c970b51` |
| RBush.Signed | 4.0.0 | `RBush-LICENSE`, dépôt `viceroypenguin/RBush`, commit `b8690322abac35d835baa2fdca4a3918ed77a910` |
| SharpZipLib | 1.4.2 | `SharpZipLib-LICENSE.txt`, dépôt `icsharpcode/SharpZipLib`, commit `33f64eb0f28cdd2b084cb822fcc224c7c5aba553` |
| SixLabors.Fonts | 1.0.0 | `SixLabors.Fonts-LICENSE`, dépôt `SixLabors/Fonts`, commit `32bef42997adb10268369ca149777f00e4241ce9` |
| System.IO.Packaging | 8.0.1 | `System.IO.Packaging-LICENSE.txt` et `System.IO.Packaging-THIRD-PARTY-NOTICES.txt`, fichiers du paquet NuGet exact |
| System.IO.Pipelines | 8.0.0 | `System.IO.Pipelines-LICENSE.txt` et `System.IO.Pipelines-THIRD-PARTY-NOTICES.txt`, fichiers du paquet NuGet exact |
| Tmds.DBus.Protocol | 0.92.0 | `Tmds.DBus-COPYING`, dépôt `tmds/Tmds.DBus`, commit `282acebca8d4e4e3ba211646ac650911ee94edfd` |
| .NET Runtime auto-contenu | 8.0.30 | licences et notices exactes des packs NuGet `Microsoft.NETCore.App.Runtime.win-x64`, `osx-x64` et `osx-arm64`; les deux packs macOS ont des fichiers identiques |
| dLive MIDI Tools, référence adaptée | 2.14.0 | `dlive-midi-tools-LICENSE.txt`, commit `7f31ddf9bca294f8280f0f510464abcd6afea56e` |

Ces textes ne placent pas StageDesk lui-même sous les licences des composants tiers.
Ils satisfont les obligations de conservation applicables aux composants
nommés et n'accordent aucune licence sur les marques ou formats propriétaires.

---

# StageDesk v2026 desktop third-party licence corpus

This directory ships with the public Windows `win-x64` and macOS `osx-x64` /
`osx-arm64` packages. The inventory was cross-checked against untrimmed,
non-single-file publishes for all three RIDs. Every legal file is an unmodified
copy from the exact NuGet package or the upstream repository revision recorded
in the table above. Build-only and test-only dependencies absent from the
published output are not represented as distributed runtime components.

These texts apply only to the named third-party components. They do not license
StageDesk itself, any vendor trademark, or any proprietary project format.
