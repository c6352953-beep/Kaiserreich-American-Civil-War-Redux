# American content inventory and compatibility map

This is an initial repository-level inventory based on the public source trees inspected on 2026-11-11. It is a discovery document, not permission to copy source files or assets.

## Source repositories

- Kaiserredux: https://github.com/JoeBidenWhatAreYouHiding/kx (default branch: master)
- Kaiserreich: https://github.com/Kaiserreich/Kaiserreich-HOI4 (default branch: master)
- Target: https://github.com/c6352953-beep/Kaiserreich-American-Civil-War-Redux (branch: main)

The Kaiserreich README identifies the current source release as HOI4 1.19.4. The mod descriptor therefore targets the 1.19 series pending a local launch test.

## Initial KX American country set

The KX `history/countries` directory contains these clearly American entries:

| KX tag | KX country file | Displayed country |
|---|---|---|
| AML | `AML - American Legion.txt` | American Legion |
| BDN | `BDN - Biden's America.txt` | Biden's America |
| CAL | `CAL - Pacific States of America.txt` | Pacific States of America |
| COR | `COR - Constitutional States of America.txt` | Constitutional States of America |
| CSA | `CSA - Combined Syndicates of America.txt` | Combined Syndicates of America |
| FSA | `FSA - Federate States of America.txt` | Federate States of America |
| NEE | `NEE - New England.txt` | New England |
| TEX | `TEX - American Union State.txt` | American Union State |
| TXS | `TXS - Texas.txt` | Texas |
| USA | `USA - United States of America.txt` | United States of America |

Additional American content appears under the shared civil-war event, decision, idea, scripted-effect, trigger, and localisation files listed below. The KX country roster should be rechecked against the complete tree before treating it as exhaustive.

## KX content files identified

### Focus trees
- `common/national_focus/United_States_of_America.txt`
- `common/national_focus/Combined_Syndicates_of_America.txt`
- `common/national_focus/American_Union_State.txt`
- `common/national_focus/Pacific_States_of_America.txt`
- `common/national_focus/Constitutional_States_of_America.txt`
- `common/national_focus/New_England.txt`
- `common/national_focus/Texas.txt`
- `common/national_focus/America_FP_Shared.txt`

### Characters and country setup
- `common/characters/KX_USA.txt`
- `common/characters/KX_CSA.txt`
- `common/characters/KX_AUS.txt`
- `common/characters/KX_CAL.txt`
- `common/characters/KX_NEE.txt`
- `common/characters/KX_TEX.txt`
- `history/countries/USA - United States of America.txt`
- `history/countries/CSA - Combined Syndicates of America.txt`
- `history/countries/TEX - American Union State.txt`
- `history/countries/CAL - Pacific States of America.txt`
- `history/countries/COR - Constitutional States of America.txt`
- `history/countries/NEE - New England.txt`
- `history/countries/TXS - Texas.txt`

### Decisions, ideas, events, and mechanics
- `common/decisions/American_Civil_War_decisions.txt`
- `common/decisions/United_States_of_America_decisions.txt`
- `common/decisions/Combined_Syndicates_of_America_decisions.txt`
- `common/decisions/American_Union_State_decisions.txt`
- `common/decisions/Constitutional_American_Republic_decisions.txt`
- `common/decisions/New_England_decisions.txt`
- `common/decisions/Texas_decisions.txt`
- `common/ideas/United_States_of_America_ideas.txt`
- `common/ideas/Combined_Syndicates_of_America_ideas.txt`
- `common/ideas/American_Union_State_ideas.txt`
- `common/ideas/Pacific_States_of_America_ideas.txt`
- `common/ideas/Constitutional_States_of_America_ideas.txt`
- `common/ideas/New_England_ideas.txt`
- `common/ideas/Texas_Ideas.txt`
- `common/scripted_effects/American_Civil_War_scripted_effects.txt`
- `common/scripted_triggers/American_Civil_War_scripted_triggers.txt`
- `common/on_actions/on_actions_United_States_of_America.txt`
- `events/American_Civil_War.txt`
- `events/United_States_of_America.txt`
- `events/Combined_Syndicates_of_America.txt`
- `events/American_Union_State.txt`
- `events/Constitutional_States_of_America.txt`
- `events/Pacific_States_of_America.txt`
- `events/New_England.txt`
- `events/Texas.txt`
- `common/scripted_localisation/American_Civil_War_scripted_localisation.txt`

This list is a verified starting subset, not the complete dependency inventory. The next pass must enumerate localisation, map/state history, OOBs, AI, decisions categories, country tags, flags, portraits, GUI, and every referenced scripted trigger/effect.

## KR compatibility observations

The current KR tree already contains its own American Civil War implementation, including:
- Focus trees: `USA focus (United States).txt`, `NEE focus (New England).txt`, `ACC focus (American Constitutional Coalition).txt`, `APG focus (American Peoples Government).txt`, and `WCA focus (Workers Congress of America).txt`.
- Events: `01 American Civil War events.txt`, `USA events (United States).txt`, `NEE events (New England).txt`, `ACC events (American Constitutional Coalition).txt`, `APG events (American Peoples Government).txt`, and `WCA events (Workers Congress of America).txt`.
- Shared mechanics: `01_American Civil War effects.txt`, `01 American Civil War decisions.txt`, `03 American Civil War ideas.txt`, and `01 - American_Civil_War_scripted_localisation.txt`.

KR's current tag set is not a one-to-one match for KX. For example, KR uses ACC, APG, and WCA where KX has separate COR, AML, and CSA content, while both have USA and NEE. This means the port must be a deliberate compatibility merge, not a blind file copy. Existing KR American systems must be preserved and extended where appropriate.

## Licensing and attribution gate

The inspected KX root contains `Readme.txt`, which points to an interface credits file, but no root `LICENSE` file was found at the expected path. The inspected KR root likewise had no root `LICENSE` file at the expected path. A missing license does not grant redistribution rights.

Before copying or adapting third-party code, portraits, flags, focus icons, event art, or other assets into this public submod, verify the applicable permissions and attribution requirements with the respective project maintainers/contributors. Until then, implementation should be limited to original code and original assets, or to content whose reuse permission is explicitly documented.

## Implementation order

1. Finish the exhaustive source and KR dependency inventories.
2. Map KX American tags and mechanics onto KR's current tags and civil-war setup.
3. Implement a small, isolated shared-mechanics layer with original code.
4. Port/adapt one faction at a time, starting with USA and its civil-war setup.
5. Add the remaining factions, events, decisions, characters, localisation, and assets only after dependency and permission checks.
6. Run HOI4/KR validation and test the American Civil War start, faction splits, reunification, and post-war paths.
