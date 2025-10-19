# ArkhamHorrorR20Sheet

Custom Roll20 character sheet for Arkham Horror — The Roleplaying Game.

## Repository Structure
- `sheet.html`: Roll20 sheet markup scaffold with defined attribute names, dice pool summaries, and tabbed layout sections.
- `sheet.css`: Base stylesheet for layout scaffolding, dice/horror panels, and responsive tab controls.
- `sheet.json`: Roll20 metadata configuration.
- `translations/translation.json`: Initial localization file.
- `docs/`: Documentation resources, including the [attribute reference](docs/attributes.md) and [repeating section planning guide](docs/repeating-sections.md).
- `assets/`: Asset directory (currently contains a `.gitkeep` placeholder).

Recent updates added system-aware skill roll buttons, action-economy trackers, and combat roll tooling (including weapon-level attack/reaction buttons that respect advantage, disadvantage, cover, and engagement flags). The status tab now includes trauma management tied to Table 2–2, insight mitigation reminders, and an expanded injury log with natural healing timers and unique injury toggles. Horror and insight workflows automate limit adjustments, trauma rolls when horror dice show 1s, Introspection/Counseling recovery, and the full suite of insight spends (bonus successes, advantage, clues, narrative edits, and cheat-death limit reductions).

Latest Sheet Worker scripts now manage dice pool refills, damage application, and the strain workflow (including auto-creating an injury reminder). They also toggle combat flags, increment per-turn/per-scene action counters, recalculate social-scene success totals, stamp vehicle condition changes, and prefill injury entries from Table 2–1 rolls. Future work will continue fleshing out automation and deeper Arkham Horror rules integration.
