# Open questions — Nomad Frame Ark (Stellaris)

Running list for Thomas. Do not block potato spike on these — defaults noted.

## RESOLVED (Thomas 2026-09-20)

1. **Target game version?** **LOCKED:** Stellaris **Vanilla 4.4** (`supported_version = "v4.4.*"`) + current Giga workshop line.
2. **What is “Nomads”?** **LOCKED:** **vanilla 4.4 Nomadic** (empire Nomadic toggle / `is_nomadic` country trigger + government restriction from DD #424). **NOT** a separate Steam Workshop “Nomads patch.” Public Voidfarers origin key: `origin_default_nomads`. No third-party Nomads pack in the dependency list.
3. **Required mods?** **LOCKED hard dep:** **Gigastructural Engineering & More** only. **UI Overhaul Dynamic** (+ Giga UIOD patch) only if a later Frame Fix path requires it — not required for potato. XHK Frameworld Fix remains optional reference, not a hard dep.

## Still open (non-blocking defaults)

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
| Exact Giga Frame World origin key (disabled in main Giga for 4.0+) | UNKNOWN — Frame restored via XHK Fix; do not invent |
| Exact Nomads DLC `host_has_dlc` string | UNKNOWN — playable gate commented out; Nomadic is vanilla 4.4 + Nomads DLC content |
| Exact `possible` government/`is_nomadic` special-requirement syntax | DD #424 documents government restriction + country trigger; potato comments document intent; hard `is_nomadic = yes` block left commented until game files confirm |

## Blockers that would stop a real in-game prove

- No game install on agent box — structural/syntax potato only until Thomas load-tests.
- Mod packages must be downloaded from Steam Workshop / mirrors without redistributing game files.
