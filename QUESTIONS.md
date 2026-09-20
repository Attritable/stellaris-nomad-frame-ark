# Open questions — Nomad Frame Ark (Stellaris)

Running list for Thomas. Do not block potato spike on these — defaults noted.

## Must-ask eventually (non-blocking defaults)

1. **Target game version?** Default assume Stellaris 4.4 + current Giga workshop line (`supported_version = "v4.4.*"`).
2. **Required mods / load order?** Default: Gigastructural Engineering → UI Overhaul Dynamic (if Frame Fix needs it) → XHK Frameworld Fix (reference only) → **this mod**. See README.
3. **What is “Nomads patch” exactly?** Workshop name/id? Default: treat as vanilla 4.4 Nomadic (`is_nomadic`); no third-party Nomads pack required for potato.
4. **Scope of ark playstyle:** start with one ark megastructure/ship as capital like Frame World (mobile habitat economy on a ship), OR also Frame-style planetary strip-to-outpost loop? Default potato: flags only + confirm event; no megastructure spawn yet.
5. **Origin name / civic?** Default: `Nomad Frame Ark` / `origin_nomad_frame_ark` (shipped).
6. **Multiplayer / AI?** Default: player-only (`random_weight = { base = 0 }`).
7. **Steam Workshop publish later?** Default: private GitHub cloneable potato first.

## Gaps from missing workshop packages (this spike)

SteamCMD was attempted on the agent box but **failed** (`linux32/steamcmd`: no 32-bit dynamic linker `/lib/i386-linux-gnu/ld-linux.so.2`). **No Gigastructures or XHK Frameworld Fix workshop zips were downloaded.**

Until packages are inspected locally by Thomas (or SteamCMD works elsewhere), these keys stay TODO — do **not** invent:

| Suspected key (public rumor / Fix pages) | Status |
|------------------------------------------|--------|
| `pc_giga_frameworld` | UNCONFIRMED — not used in potato scripts |
| `giga_has_frameworld_origin` | UNCONFIRMED |
| `frameworld_upgrade` / other `frameworld_*` flags | Mentioned on XHK Fix page; not wired |
| Exact Giga Frame World origin key (disabled in main Giga for 4.0+) | UNKNOWN — Frame restored via XHK Fix |
| Exact Nomads DLC `host_has_dlc` string | UNKNOWN — playable gate commented out |
| `is_nomadic` civic/origin restriction syntax | Documented as existing in DD #424; exact special-requirement block not copied into potato `possible = {}` |

## Blockers that would stop a real in-game prove

- No game install on agent box — structural/syntax potato only until Thomas load-tests.
- Mod packages must be downloaded from Steam Workshop / mirrors without redistributing game files.
