# Open questions — Nomad Frame Ark (Stellaris)

Running list for Thomas. Do not block potato spike on these — defaults noted.

## RESOLVED (Thomas + local refs 2026-09-20)

1. **Target game version?** **LOCKED:** Stellaris **Vanilla 4.4** (`supported_version = "v4.4.*"`) + Giga workshop line `3.39.4` / `remote_file_id=1121692237`.
2. **What is “Nomads”?** **LOCKED:** vanilla 4.4 Nomadic. Evidence: `origin_default_nomads` etc. in `00_origins.txt` with `possible = { is_nomadic = yes }`; `has_nomads_dlc = { host_has_dlc = "Nomads" }` in `09_scripted_triggers_nomads.txt`. **NOT** a Workshop Nomads patch.
3. **Required mods?** **LOCKED hard dep:** Gigastructural Engineering & More only (`name="Gigastructural Engineering & More (4.4)"`). UIOD optional later. XHK Fix optional reference.
4. **Exact Nomads DLC `host_has_dlc` string?** **ANSWERED:** `"Nomads"` via `has_nomads_dlc` (`09_scripted_triggers_nomads.txt`). Wired as `playable = { has_nomads_dlc = yes }`.
5. **Exact `possible` / `is_nomadic` syntax?** **ANSWERED:** `possible = { is_nomadic = yes }` (same as Voidfarers). `is_nomadic` is hardcoded special requirement — not a scripted-trigger definition in the nomads triggers file.
6. **Frame World origin / planet keys?** **ANSWERED from Giga slices:**
   - Origin: `origin_frameworld` — **disabled** (`always = no`, "Disabled for 4.0") in `frameworld_origins.txt`
   - Planet: `pc_giga_frameworld`; initializer `giga_frameworld_system`
   - Triggers: `giga_has_frameworld_origin` (= `has_origin = origin_frameworld`), `giga_is_frame_world` (= planet class check)
   - Potato uses a **separate** origin; does not re-enable Frame World.

## Still open (product — not key archaeology)

7. **Scope of ark playstyle:** one arkship capital (vanilla Nomadic) with Frame-*inspired* economy later, OR also Frame-style planetary strip-to-outpost loop (`pc_giga_frameworld_outpost_*`, `giga_frameworld_outpost` flag)? Default potato: flags + confirm event only; no megastructure/outpost spawn.
8. **Should day-1 ever `change_pc` / adopt Frame capital?** Default **no** — conflicts with mobile ark. Leave Frame planet for optional later hybrid if Thomas wants stationary+mobile mix.
9. **Origin display name?** Default shipped: `Nomad Frame Ark` / `origin_nomad_frame_ark`.
10. **Multiplayer / AI?** Default: player-only (`random_weight = { base = 0 }`, `ai_playable = { always = no }`).
11. **Steam Workshop publish later?** Default: private GitHub cloneable potato first.
12. **Dependency on XHK Frameworld Fix?** Default: **no**. Giga upstream has Frame disabled; if Thomas wants stock Frame systems, decide whether to soft-depend on a Fix mod or reimplement selectively.

## Closed gaps (were “missing workshop packages”)

Local slices now present under `/workspace/stellaris-refs/`. See `KEYS.md` for the full wired/unwired table.

## Blockers for in-game prove

- No full game install on agent box — structural/syntax potato until Thomas load-tests.
- Do not redistribute Stellaris or Giga binaries via this repo.
