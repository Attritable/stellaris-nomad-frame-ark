# Nomad Frame Ark — design note (potato)

**Working title:** Nomad Frame Ark  
**Owner:** Heimerdinger (eng lead) via CloudAgent  
**Bar:** p-stack potato — ship cloneable structure; Thomas load-tests in-game  
**Repo:** https://github.com/Attritable/stellaris-nomad-frame-ark  
**Keys:** see `KEYS.md` (sourced from local Stellaris 4.4 + Giga 3.39.4 slices)

## Intent

Frame World playstyle (single expanding “home” that eats the galaxy’s pops/economy) but as a **nomad ark**: mobile capital, not a black-hole frame planet. Visuals later — reuse standard Giga/Frame / vanilla arkship gfx for now.

## Target lock (Thomas 2026-09-20)

- **Game:** Vanilla Stellaris **4.4**
- **Nomads meaning:** vanilla 4.4 **Nomadic** (`is_nomadic` / Nomads DLC) — **not** a Workshop Nomads patch
- **Hard dependency:** Gigastructural Engineering & More only
- **Optional later:** UI Overhaul Dynamic (+ Giga UIOD) only if Frame Fix UI path is required

## Dependencies

1. **Gigastructural Engineering & More (4.4)** — required  
   Local install: `version=3.39.4`, `remote_file_id=1121692237`, `name="Gigastructural Engineering & More (4.4)"` (`giga/descriptor.mod`)
2. **Nomads DLC** — required for playable gate (`has_nomads_dlc` → `host_has_dlc = "Nomads"`)
3. **UI Overhaul Dynamic** (+ Giga UIOD) — only if a later Frame Fix path needs it; not potato-required
4. Optional reference: `[4.4] XHK Frameworld 4.4 Fix` (Steam `3615040887`) — structural inspiration only; not a hard dep

## Key facts from refs (2026-09-20)

- Vanilla Nomadic origins (`origin_default_nomads` etc.) use `possible = { is_nomadic = yes }` and `playable = { has_nomads_dlc = yes }`.
- `is_nomadic` is a **hardcoded** special requirement / country check — not defined as a scripted trigger in `09_scripted_triggers_nomads.txt`.
- Giga `origin_frameworld` is **disabled** in the 4.4 Giga line (`always = no`, "Disabled for 4.0"). Capital would be `pc_giga_frameworld` via `giga_frameworld_system`.
- This mod ships **`origin_nomad_frame_ark`** as a **separate** Nomadic origin — it does **not** re-enable or impersonate `origin_frameworld`.

## Potato deliverable (shipped)

Cloneable Stellaris mod folder (this repo root = mod folder):

- `descriptor.mod` / `stellaris-nomad-frame-ark.mod` — `supported_version` `v4.4.*`, Giga dependency exact name
- `common/governments/civics/00_nomad_frame_ark_origins.txt` — `origin_nomad_frame_ark` with real `is_nomadic` / `has_nomads_dlc`
- `common/scripted_triggers/nomad_frame_ark_triggers.txt` — thin wrappers
- Stub events/flags: `nomad_frame_ark_empire`, `has_ark_capital`, planet `ark_capital` / `nomad_frame_ark_capital`
- `localisation/english/nomad_frame_ark_l_english.yml`
- `KEYS.md`, `README.md`, `QUESTIONS.md`

**Out of potato:** custom 3D, balance pass, full Frame district/outpost parity, Workshop publish, `change_pc` to Frame planet, firing Giga Frame events.

## Constraint

**No Stellaris game files redistributed.** Keys extracted from local install **slices** under `/workspace/stellaris-refs/` (not full game upload). Do **not** invent Giga/vanilla keys.

## Non-goals

Diverting TTRPG craft bots; inventing Giga APIs; claiming to be `origin_frameworld` while it stays disabled upstream.
