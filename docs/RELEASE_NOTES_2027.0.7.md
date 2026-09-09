# StageDesk 2027.0.7 - Connexions réseau / Console networking

## Français

- Connexion LAN directe : IP/hôte manuel, port configurable et détection volontaire
  sur l'interface choisie. Aucun scan ni reconnexion automatique.
- Lecture de Current et envoi des champs cochés pour Yamaha DM7, RIVAGE PM,
  CL/QL, TF, DM3, Allen & Heath dLive/Avantis, Behringer X32/Midas M32 et WING.
- Canal MIDI A&H configurable ; réponses MIDI temps réel intercalées tolérées.
- X32/M32 : liste des scènes, import après rappel explicite confirmé, mémorisation
  de tout Current dans un emplacement vide revérifié. Aucun écrasement volontaire
  d'un slot occupé ni répétition automatique d'un rappel/stockage incertain.
- Sauvegarde des champs relus en `.smt` + SHA-256 avant envoi ou rappel de scène ;
  Simulation sans socket, annulation et arrêt au premier échec de vérification.
- Paramètres et limites propres à chaque famille, y compris préservation de
  l'apparence visible WING lors du détachement du lien cosmétique `clink`.
- Panneaux réseau utilisables sur petit et grand écran, en français/anglais,
  clair/sombre ; notices professionnelles et démarrages rapides actualisés.

**Limites importantes :** les tests utilisent de vraies sockets TCP/UDP locales,
pas des consoles physiques. La recette matérielle hors antenne reste à faire.
A&H ne relit que labels/couleurs ; les autres champs acceptés sont envoyés sans
relecture. Les transferts ne sont pas atomiques : aucun autre contrôleur ne doit
modifier les mêmes paramètres ou mémoriser dans le même slot en parallèle.
La sauvegarde StageDesk n'est pas un show complet ni un rollback.
Un rappel X32/M32 peut changer tout le mix et laisse la console dans l'état rappelé.
Les scènes sauvegardées des autres familles passent par leurs fichiers natifs.

Voir les [procédures réseau détaillées](NETWORK_CONSOLES.md) et les guides PDF.
Les projets, activations, identifiants et formats historiques restent compatibles.

## English

- Direct LAN connection with manual IP/host, configurable port and explicit
  discovery on the chosen interface. No automatic scanning or reconnection.
- Current import and checked-field sending for Yamaha DM7, RIVAGE PM, CL/QL,
  TF, DM3, Allen & Heath dLive/Avantis, Behringer X32/Midas M32 and WING.
- Configurable A&H base MIDI channel and interleaved real-time MIDI handling.
- X32/M32 scene listing, separately confirmed recall/import and storage of the
  entire Current mix into a freshly checked empty slot. Occupied slots refused;
  uncertain recall/store commands are never retried automatically.
- Readable-field `.smt` + SHA-256 backup before sending or recalling; zero-socket
  Simulation, cancellation and stop on the first verification failure.
- Family-specific limits, WING linked-appearance preservation, responsive network
  panels and updated French/English professional and quick-start PDF guides.

**Limits:** real local TCP/UDP socket tests are not physical console qualification.
Off-air hardware validation remains required. A&H reads back labels/colours only;
other supported writes are sent without readback. Transfers are non-atomic:
avoid concurrent controllers editing the same fields or storing into the same
slot. Backups are not full shows or automatic rollback. X32/M32 recall may change
the entire mix and leaves the console in that state. Other saved scenes use
native files. See the [network procedures](NETWORK_CONSOLES.md).

macOS DMGs use ad-hoc integrity signing, without Apple Developer ID/notarization.
The native Apple Silicon smoke test does not qualify execution on Intel hardware.
