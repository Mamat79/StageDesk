# StageDesk v2026 — état réel des connecteurs / actual connector status

**Save My Time**

[Français](#français) · [English](#english)

## Français

Cette matrice décrit les parcours réellement exposés par StageDesk v2026. Le mot
**natif** signifie que StageDesk traite le format de projet, de session ou de scène de
la destination ; il ne signifie ni compatibilité totale, ni certification du
constructeur. Les champs transférés varient selon le connecteur.

### Lecture des statuts

- **Oui** : parcours implémenté et résultat contrôlé ou relu par StageDesk.
- **Partiel** : lecture seule, sous-ensemble de paramètres, modèle précis ou
  condition locale indiquée dans la ligne.
- **Non** : mode masqué ou désactivé ; aucun CSV générique n’est présenté comme
  un projet constructeur.
- **Réouvert** : un témoin StageDesk a été ouvert dans le logiciel indiqué. Cela ne
  remplace pas un essai sur le matériel physique.
- **À valider** : contrôle interne acquis, mais preuve externe encore absente.

StageDesk peut inclure des modèles vierges sélectionnés, assainis et
contrôlés par SHA-256. Ils sont copiés avant toute écriture. Les formats qui
exigent encore un runtime constructeur ou un modèle appartenant à l’utilisateur
restent indiqués comme conditionnels. Aucun projet utilisateur ni show de
production n’est inclus. Le manifeste SHA-256 prouve l’intégrité des fichiers,
pas les droits de redistribution, qui restent régis par leurs titulaires.

### Consoles

| Système, ordre alphabétique | Lecture native | Écriture native | Nouveau projet | Projet existant / scène | Réseau | Validation externe actuelle |
|---|---|---|---|---|---|---|
| Allen & Heath Avantis / Solo | Oui : les quatre modèles, shows Bridge-3/4/5 et snapshots | Label/couleur dans Current ou un snapshot ; création de snapshot | Oui : modèle standard ou dPack partagé par Avantis/Solo correspondant | Current, snapshot existant ou nouveau snapshot dans une copie | Non revendiqué sans preuve réseau séparée | Nouveau projet standard/dPack et nouveau snapshot standard rappelés dans Avantis Director 2.00 ; les autres variantes passent la relecture StageDesk |
| Allen & Heath dLive | Oui : snapshots Director | Label et couleur du Current ou d’un snapshot | Oui : modèle moteur commun de 128 entrées pour les 14 variantes proposées | Current, snapshot existant ou nouveau snapshot nommé pour tout show reconnu possédant un slot vide | Non exposé | Un nouveau show et un nouveau snapshot ont été rappelés dans dLive Director 2.12 ; le fichier ne stocke pas l'identité surface/MixRack |
| Allen & Heath GLD-80 / 112 | Oui : `.tar.bz2` et scènes | Labels et couleurs des 48 entrées | Oui : modèle embarqué | Scène existante ou nouvelle | Non | Une sortie avec nouvelle scène a été ouverte dans GLD-80 Editor 1.61 et son label contrôlé ; GLD-112 et matériel à valider |
| Allen & Heath Qu classique | Oui : `SHOW####` / `SCENE###.DAT` des Qu-16/24/32/Pac/SB | Label dans Current ou une scène ; CRC recalculé | Non | Current, scène existante ou nouvelle scène dans une copie | Non | Les deux dispositions classiques passent écriture et relecture StageDesk ; validation finale sur console Qu requise ; Qu-5/5D/6/6D/7/7D utilisent un autre format |
| Allen & Heath SQ classique | Oui : Current et scènes V1.6 | Label et couleur, CRC recalculé | Oui : modèle embarqué SQ-5/6/7/Rack | Current, scène existante ou nouvelle | Non | SQ-5 et scène StageDesk rappelés dans SQ MixPad 1.6.1 ; SQ+ V2 non revendiqué |
| Avid VENUE S6L | Oui : `.dsh`, moteur/capacité, Current MicLine | Labels MicLine de Current | Oui : six seeds E6L/E6LX embarqués | Current uniquement | Non | Les six sorties 112–256 ont été transférées et chargées dans VENUE Offline 8.2 ; `SMT KICK` relu après redémarrage et `SMT LAST` identifié sur Ch 256 ; snapshots sauvegardés et matériel non validés |
| Behringer WING | Oui : `.snap` `snapshot.11` | Label, couleur, icône, mute, fader | Oui : modèle embarqué | Snapshot unique | Non | Témoin rouvert dans WING Edit 3.3.3 ; multi-snapshots et matériel à valider |
| Behringer X32 / Midas M32 | Oui : scène `.scn` | Label, couleur, icône, DCA, HPF, mute, fader | Oui : scène v4 minimale partielle | Scène unique copiée | Non | Un Nouveau projet StageDesk a été chargé dans X32-Edit 4.4 avec labels/couleurs visibles ; M32-Edit, `.shw`, OSC et matériel non validés |
| DiGiCo SD / Quantum V2242 | Oui : Current et snapshots nommés d’une session `.ses` ; 13 modèles, 32 à 108 entrées | Labels ASCII | Oui : seed exact par modèle | Snapshot existant ; nouveau snapshot lorsque la topologie est reconnue ; remplacement après confirmation et backup `Bckp_` | Non | Treize seeds/sorties contrôlés et relus par StageDesk ; écritures SD9 existante (`DCBD8058…`) et nouveau snapshot (`2CE27E77…`) rappelées dans SD9 Offline V2242 |
| Midas HD96 | Oui : scènes `.show` et classeur constructeur 144 entrées | Scène existante ou nouvelle dans une copie ; classeur Excel | Non exposé pour les shows natifs | Scène existante ou nouvelle ; import/export Excel | Non | Show officiel copié, écrit et relu par StageDesk avec source préservée ; chargement final HD96 Editor et matériel à confirmer |
| Soundcraft Vi | Oui : Start Snapshot et snapshots hérités | Label long et couleur | Oui : huit modèles embarqués | Start Snapshot ou snapshot hérité ; CueList moderne non modifiée | Non | Vi600 rouverte ; autres modèles et matériel à valider |
| SSL Live / SOLSA et System T | Oui : cues `.show` via SOLSA Windows | Label, couleur, mute, fader | Oui : runtime et modèle SOLSA installés | Cue existant ; pas de création de cue | Non | L500 `.show` sérialisé avec les DLL SOLSA et relu par StageDesk ; SOLSA 6.2.14 ne détecte aucun écran sur le bureau isolé (`Detected 0 Screens`), donc réouverture UI et matériel non validés |
| Yamaha CL / QL | Oui : Current et scènes `.CLF` | Label, couleur, icône avec checksum recalculé | Oui : cinq choix de modèle depuis trois empreintes natives embarquées ; scène 1 obligatoire depuis Initial Data | Current, scène existante ou nouvelle scène | Non exposé | Sorties CL5 et QL1 avec scène 1 ouvertes deux fois dans CL/QL Editor 5.8.1, puis rouvertes après une commande de sauvegarde sans erreur ; index/checksums relus ; matériel à valider |
| Yamaha DM3 / DM3 Standard | Oui : Current et scènes A/B `.dm3f` | Labels/couleurs/icônes dans Current ou une scène | Oui : modèle natif exact | Current ou scène d'une copie | Non | Les deux variantes chargées, enregistrées puis relues dans DM3 Editor |
| Yamaha DM7 / DM7 Compact | Oui : Current et scènes `.dm7f` | Labels/couleurs/icônes dans Current ou une scène | Oui : modèle natif exact | Current ou scène d'une copie | Non exposé | DM7 Full et Compact chargées, enregistrées puis relues dans DM7 Editor ; Compact bornée à 72 entrées |
| Yamaha RIVAGE PM | Current et scènes à double index concordant sur quatre profils 120/144/288 | Label, couleur, icône de Current ou d’une scène dans une copie | Oui : quatre profils embarqués pour treize variantes exactes | Current, scène existante ou nouvelle scène dans le premier slot libre | Non exposé | Les quatre sorties StageDesk DSP-R10, CSD-R7, DSP-RX et DSP-RX-EX ont été chargées par leur profil exact dans RIVAGE PM Editor 7.1.0 ; la scène `SMT NATIVE` est affichée ; sauvegarde native et matériel à valider |
| Yamaha TF1 / 3 / 5 / Rack | Oui : Current et scènes A/B `.TFF` | Labels/couleurs/icônes dans Current ou une scène | Oui : modèle natif exact | Current ou scène d'une copie | Non | Les quatre profils chargés, enregistrés puis relus dans TF Editor |

### Logiciels et échanges

| Système, ordre alphabétique | Lecture native | Écriture native | Nouveau projet | Projet existant / snapshot | Réseau | Validation externe actuelle |
|---|---|---|---|---|---|---|
| Ableton Live | Oui : `.als` | Noms, couleurs, mute, fader dans une copie ou un Nouveau projet audio-only 2 pistes | Seed Live 12 embarqué, neutralité stricte et relecture StageDesk | Current enregistré uniquement | Non | Sortie exacte 2 pistes ouverte, fermée puis rouverte dans Live 12.4 ; `SMT KICK` et `SMT VOX` relus nativement |
| Dante Config Editor — DCE | Oui : preset XML natif, choix d’une machine et import de ses Rx uniquement | Labels Rx d’une machine ; tous les Tx sont préservés | Oui : modèle choisi dans la banque de machines embarquée | Machine existante ou nouvelle machine ajoutée depuis la banque ; backup avant remplacement | Non | Création et remplacement XML relus dans DCE : Rx modifiés, bloc Tx conservé à l’identique ; DCE reste téléchargeable depuis StageDesk |
| Harrison — LiveTrax 3 / Mixbus 10 | Oui : snapshots `.ardour` pour les deux produits | Copie non destructive ; Mixbus propose aussi Lua | Oui : modèles de capacité 128/512, sortie réduite exactement aux canaux inclus | Snapshot frère dans la session | Non | Sortie exact-7 chargée dans LiveTrax 3 avec 7 noms/couleurs visibles ; la sortie Mixbus exact-7 est relue par StageDesk mais Mixbus 10 plante dans `libstdc++-6.dll` (`0x40000015`) avant ouverture, donc pas de preuve native Mixbus |
| MAGIX Sequoia Pro 17 | Oui : `.VIP`, Current | Labels et mute dans une copie | Oui : modèle assaini embarqué de 128 pistes | Current uniquement | Non | Une sortie StageDesk et le modèle vierge ont été rouverts dans Sequoia Pro 17 |
| REAPER | Oui : `.rpp` | Nom, couleur, image, mute, fader | Oui | État enregistré uniquement | Non | Réouverture REAPER à valider |
| Steinberg Nuendo 14 | Oui : `.dawproject` | Nom, couleur, mute, fader dans une copie | Oui : `.dawproject` | Current DAWproject uniquement | Non | Importer avec **Fichier > Importer > DAWproject**, pas **Ouvrir le projet** qui attend un `.npr` ; sortie StageDesk validée dans Nuendo 14 puis enregistrée en `.npr` |
| Tableau StageDesk — Excel / CSV | Oui | Oui | Nouveau tableau | Réimport/export | Non | Listes Excel contrôlées ; CSV sans présentation |

### Preuve native DiGiCo SD9 V2242

La source SD9 à deux snapshots
`artifacts/native-validation/digico-reverse-20260828/SD9_V2242_native_2snap_session001.ses`
fait 906 989 octets et porte le SHA-256
`6F7DCDB7F7EA6BD96A0C0D56F7289DACAEAD116C4F44C0D2D6C1588FC8286941`.
Deux sorties StageDesk ont été rappelées dans SD9 Offline V2242 :

- snapshot existant :
  `artifacts/native-validation/digico-sd9-existing-snapshot-current-writer-20260828/SMT_SD9_EXISTING_SNAPSHOT_CANDIDATE_VOX.ses`,
  906 989 octets, SHA-256
  `DCBD8058454CA2689365D5919136DED3A459024D0058EAF230E8EAD8D53F6057` ;
- nouveau snapshot `SMT_C` avec `VOX` au canal 1 :
  `artifacts/native-validation/digico-sd9-native-three-snapshot-20260828/SMT_SD9_GENERATED_SMT_C_VOX.ses`,
  940 492 octets, SHA-256
  `2CE27E77C1098C763D1A3B7161E48B7005E2711F8B7E72DEC3F440AAEF7787B5`.

Le rappel a montré `SMT_A`, `SMT_B` et `SMT_C` ; Current, `SMT_A` et `SMT_B`
sont restés à `KICK1`. Cette preuve vaut uniquement pour SD9 48 entrées,
format 456, V2242 et pour des snapshots nommés. Elle ne valide aucun autre
modèle DiGiCo, Current, Nouveau projet, le réseau ou une console physique.

### Quantum : preuve de chargement et correction Q2

Les copies isolées Quantum 1/2/3/5/7/8 ont toutes chargé, réécrit puis rechargé
les candidats Current sur deux cycles sans erreur de session. Sur Quantum 2,
une paire nativement créée
A/B→A/B/B2 a permis de borner le format, mais la première sortie StageDesk
`0CA9BCB7…` a été rejetée : l’éditeur a présenté une liste de snapshots vide et
est revenu à 589 027 octets sans aucun label témoin. Le champ de longueur
complète Q2 à `0x170`, oublié par cette sortie, est maintenant corrigé dans le
writer expérimental. Quantum 2 a chargé puis réécrit la sortie corrigée
`88FB346D…` à la même longueur en conservant `SMT_Q2` et `Q2_WRITER_CH1`, sans
erreur de parsing. La fenêtre n’a toutefois pas pu être ciblée : aucun rappel
visuel du snapshot ni du label n’est acquis. La v2026.3 expose désormais les
six Quantum avec leur profil exact, l’import Current/snapshots nommés,
l’écriture d’un snapshot existant et Nouveau projet depuis le seed officiel
exact. La création d’un snapshot supplémentaire reste limitée aux topologies
formellement reconnues. Preuves :
`artifacts/native-validation/digico-quantum-20260828/`.

## English

This matrix lists the workflows actually exposed by StageDesk v2026. **Native** means
that StageDesk handles the destination project, session or scene format; it does not
mean complete fidelity or vendor certification. Transferred fields vary by
connector.

### Status key

- **Yes**: implemented and checked or reread by StageDesk.
- **Partial**: read-only, restricted parameters/models, or a stated local
  prerequisite.
- **No**: hidden or disabled; a generic CSV is never presented as a vendor
  project.
- **Reopened**: a StageDesk witness was opened in the named application. This is not
  a physical-hardware test.
- **Pending**: internal checks exist, but external evidence is still missing.

StageDesk may include selected blank templates that are sanitised and SHA-256 pinned.
Each template is copied before writing. Formats
that still need an installed vendor runtime or a user-owned template are marked
as conditional. No user project or production show is included. The SHA-256
manifest proves file integrity, not redistribution rights, which remain with
their respective owners.

### Consoles

| System, alphabetically | Native read | Native write | New project | Existing project / scene | Network | Current external evidence |
|---|---|---|---|---|---|---|
| Allen & Heath Avantis / Solo | All four models; Bridge-3/4/5 shows and snapshots | Current/snapshot label and colour; snapshot creation | Yes: standard or dPack template shared by the matching Avantis/Solo variant | Current, existing or new snapshot in a copy | Not claimed without separate network evidence | Standard/dPack New Project and standard new snapshot recalled in Avantis Director 2.00; other variants pass StageDesk reread |
| Allen & Heath dLive | Director snapshots | Current or snapshot label and colour | Yes: common 128-input engine template for all 14 proposed variants | Current, existing snapshot or named new snapshot for any recognised show with an empty slot | Not exposed | A new show and snapshot were recalled in dLive Director 2.12; the file stores no surface/MixRack identity |
| Allen & Heath GLD-80 / 112 | `.tar.bz2` show and scenes | 48 input labels and colours | Yes: bundled template | Existing or new scene | No | An output with a new scene opened in GLD-80 Editor 1.61 and its label was checked; GLD-112/hardware pending |
| Allen & Heath classic Qu | Qu-16/24/32/Pac/SB `SHOW####` / `SCENE###.DAT` | Current/scene label with recalculated CRC | No | Current, existing scene or new scene in a copy | No | Both classic layouts pass StageDesk write/readback; final Qu-console validation is required; Qu-5/5D/6/6D/7/7D use another format |
| Allen & Heath classic SQ | V1.6 Current and scenes | Label and colour, recalculated CRC | Yes: bundled SQ-5/6/7/Rack template | Current, existing or new scene | No | SQ-5 and StageDesk scene recalled in SQ MixPad 1.6.1; SQ+ V2 not claimed |
| Avid VENUE S6L | `.dsh`, engine/capacity, Current MicLine | Current MicLine labels | Yes: six bundled E6L/E6LX seeds | Current only | No | All six 112–256 outputs were transferred and loaded in VENUE Offline 8.2; `SMT KICK` was reread after restart and `SMT LAST` identified on Ch 256; stored snapshots/hardware pending |
| Behringer WING | `snapshot.11` `.snap` | Label, colour, icon, mute, fader | Yes: bundled template | Single snapshot | No | Reopened in WING Edit 3.3.3; multi-snapshot shows/hardware pending |
| Behringer X32 / Midas M32 | Text `.scn` scene | Label, colour, icon, DCA, HPF, mute, fader | Yes: minimal partial v4 scene | Single copied scene | No | One StageDesk New Project loaded in X32-Edit 4.4 with visible labels/colours; M32-Edit, `.shw`, OSC and hardware remain unvalidated |
| DiGiCo SD / Quantum V2242 | Current and named snapshots from `.ses` sessions; 13 models, 32 to 108 inputs | ASCII labels | Yes: exact seed per model | Existing snapshot; new snapshot when topology is recognised; replacement after confirmation and `Bckp_` backup | No | Thirteen seeds/outputs checked and reread by StageDesk; SD9 existing write (`DCBD8058…`) and new snapshot (`2CE27E77…`) recalled in SD9 Offline V2242 |
| Midas HD96 | `.show` scenes and the 144-input manufacturer workbook | Existing/new scene in a copy; manufacturer Excel workbook | Not exposed for native shows | Existing or new scene; Excel import/export | No | Official show copied, written and reread by StageDesk with the source preserved; final HD96 Editor/hardware loading pending |
| Soundcraft Vi | Start and legacy numbered snapshots | Long label and colour | Yes: eight bundled templates | Start or legacy snapshot; modern CueList is not modified | No | Vi600 reopened; other models/hardware pending |
| SSL Live / SOLSA and System T | `.show` cues through Windows SOLSA | Label, colour, mute, fader | Yes: installed SOLSA runtime/template | Existing cue; no cue creation | No | An L500 `.show` was serialized with SOLSA DLLs and reread by StageDesk; SOLSA 6.2.14 reports `Detected 0 Screens` on the isolated desktop, so UI reopen and hardware remain pending |
| Yamaha CL / QL | Current and `.CLF` scenes | Label, colour and icon with recalculated checksum | Yes: five model choices from three bundled native fingerprints; scene 1 is mandatory from Initial Data | Current, existing scene or new scene | Not exposed | CL5 and QL1 scene-1 outputs opened twice in CL/QL Editor 5.8.1 and reopened after an error-free save command; index/checksums pass readback; hardware remains pending |
| Yamaha DM3 / DM3 Standard | `.dm3f` Current and A/B scenes | Current/scene label, colour and icon | Yes: exact native template | Current or scene in a copy | No | Both variants loaded, saved and reread in DM3 Editor |
| Yamaha DM7 / DM7 Compact | `.dm7f` Current and scenes | Current/scene label, colour and icon | Yes: exact native template | Current or scene in a copy | Not exposed | Full and Compact loaded, saved and reread in DM7 Editor; Compact capped at 72 inputs |
| Yamaha RIVAGE PM | Current and dual-index-consistent scenes on four 120/144/288 profiles | Current or scene label, colour and icon in a copy | Yes: four bundled profiles for thirteen exact variants | Current, existing scene or new scene in the first free slot | Not exposed | All four DSP-R10, CSD-R7, DSP-RX and DSP-RX-EX StageDesk outputs loaded under their exact RIVAGE PM Editor 7.1.0 profile and displayed `SMT NATIVE`; native save and hardware remain pending |
| Yamaha TF1 / 3 / 5 / Rack | `.TFF` Current and A/B scenes | Current/scene label, colour and icon | Yes: exact native template | Current or scene in a copy | No | All four profiles loaded, saved and reread in TF Editor |

### Software and exchange formats

| System, alphabetically | Native read | Native write | New project | Existing project / snapshot | Network | Current external evidence |
|---|---|---|---|---|---|---|
| Ableton Live | `.als` | Names, colours, mute and fader in a copy or a two-track audio-only New Project | Bundled Live 12 seed, strict neutrality and StageDesk reread | Saved Current only | No | Exact two-track output opened, closed and reopened in Live 12.4; `SMT KICK` and `SMT VOX` were read back natively |
| Dante Config Editor — DCE | Native XML preset, device selection, and Rx-only import | Rx labels for one device; every Tx is preserved | Yes: choose a model from the bundled machine bank | Existing device or a new bank device added to the project; backup before replacement | No | XML creation and replacement were reread in DCE: Rx changed and the Tx block remained byte-identical; DCE is downloadable from StageDesk |
| Harrison — LiveTrax 3 / Mixbus 10 | `.ardour` snapshots for both products | Non-destructive copy; Mixbus also offers Lua | Yes: 128/512-track capacity templates, output pruned exactly to included channels | Sibling session snapshot | No | The exact-7 output loaded in LiveTrax 3 with all seven names/colours visible; the exact-7 Mixbus output passes StageDesk reread but Mixbus 10 crashes in `libstdc++-6.dll` (`0x40000015`) before opening it |
| MAGIX Sequoia Pro 17 | `.VIP` Current | Labels and mute in a copy | Yes: bundled sanitised 128-track template | Current only | No | A StageDesk output and the blank template reopened in Sequoia Pro 17 |
| REAPER | `.rpp` | Name, colour, track image, mute, fader | Yes | Saved state only | No | REAPER reopen pending |
| StageDesk table — Excel / CSV | Yes | Yes | New table | Universal-table reimport/export | No | Excel lists checked; CSV has no presentation |
| Steinberg Nuendo 14 | `.dawproject` | Name, colour, mute, fader in a copy | Yes: `.dawproject` | DAWproject Current only | No | Import with **File > Import > DAWproject**, not **Open Project**, which expects an `.npr`; StageDesk output validated in Nuendo 14 and saved as `.npr` |

### DiGiCo SD9 V2242 native evidence

The two-snapshot source is
`artifacts/native-validation/digico-reverse-20260828/SD9_V2242_native_2snap_session001.ses`,
906,989 bytes, SHA-256
`6F7DCDB7F7EA6BD96A0C0D56F7289DACAEAD116C4F44C0D2D6C1588FC8286941`.
Two StageDesk outputs were recalled in SD9 Offline V2242: the existing-snapshot
output `SMT_SD9_EXISTING_SNAPSHOT_CANDIDATE_VOX.ses` (SHA-256
`DCBD8058454CA2689365D5919136DED3A459024D0058EAF230E8EAD8D53F6057`)
and the new `SMT_C` snapshot output `SMT_SD9_GENERATED_SMT_C_VOX.ses`
(SHA-256
`2CE27E77C1098C763D1A3B7161E48B7005E2711F8B7E72DEC3F440AAEF7787B5`).
`SMT_C` recalled CH1=`VOX`, while Current, `SMT_A` and `SMT_B` kept
CH1=`KICK1`. This evidence applies only to 48-input SD9, format 456, V2242
named snapshots; it does not validate any other DiGiCo model, Current, New
Project, networking or physical hardware.

### Quantum load evidence and Q2 correction

Isolated Quantum 1/2/3/5/7/8 copies all loaded, rewrote and reloaded the
Current research candidates over two cycles without a session error. On
Quantum 2, a native A/B to
A/B/B2 pair bounded the model-specific structure, but the first StageDesk output
`0CA9BCB7…` was rejected: the editor showed an empty snapshot list and fell
back to a 589,027-byte state with none of the witness labels. The missing Q2
complete-length field at `0x170` is now fixed in the experimental writer, but
Quantum 2 loaded and rewrote the corrected `88FB346D…` output at the same
length while retaining `SMT_Q2` and `Q2_WRITER_CH1`, with no parse error. The
window could not be targeted, so neither the snapshot nor the label was
visually recalled. v2026.3 now exposes all six Quantum profiles with exact
model selection, Current/named-snapshot import, existing-snapshot writing and
New Project from the exact official seed. Creating an additional named
snapshot remains limited to formally recognised topologies. Evidence:
`artifacts/native-validation/digico-quantum-20260828/`.

## Limite commune / common boundary

Every generated file should be reopened in the matching vendor application and
checked on the target hardware before live use. Automated readback proves that
StageDesk produced the structure it expects; it cannot prove firmware compatibility,
licensing, cabling, clocking or behaviour of a physical console.

Chaque fichier généré doit être rouvert dans l’application constructeur puis
contrôlé sur le matériel cible avant une utilisation en direct. La relecture
automatique prouve la structure attendue par StageDesk ; elle ne prouve ni le
firmware, ni les licences, ni le câblage, ni l’horloge, ni le comportement de la
console physique.
