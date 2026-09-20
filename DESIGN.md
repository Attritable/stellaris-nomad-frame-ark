# Nomad Frame Ark — design note (potato)

**Working title:** Nomad Frame Ark  
**Owner:** Heimerdinger (eng lead) via CloudAgent  
**Bar:** p-stack potato — ship cloneable structure; Thomas load-tests in-game  
**Repo:** https://github.com/Attritable/stellaris-nomad-frame-ark

## Intent

Frame World playstyle (single expanding “home” that eats the galaxy’s pops/economy) but as a **nomad ark**: mobile capital, not a black-hole frame planet. Visuals later — reuse standard Giga/Frame ark / habitat ship gfx for now.

## Dependencies (assumed; confirm in QUESTIONS)

1. Gigastructural Engineering & More (4.4 workshop line; historically Steam `1121692237`)
2. Likely UI Overhaul Dynamic + Giga UIOD patch if we lean on XHK Frameworld Fix patterns
3. **Nomads** — vanilla 4.4 Nomadic (`is_nomadic` country trigger / government restriction) compatible origin. Potato does **not** hard-require a third-party “Nomads patch”.
4. Optional reference: `[4.4] XHK Frameworld 4.4 Fix` (Steam `3615040887`) as structural inspiration — do **not** require players to run XHK unless we explicitly depend.

## Potato deliverable (shipped)

Cloneable Stellaris mod folder (this repo root = mod folder):

- `descriptor.mod` / `stellaris-nomad-frame-ark.mod` — name, `supported_version` `v4.4.*`, Giga dependency
- `common/governments/civics/00_nomad_frame_ark_origins.txt` — `origin_nomad_frame_ark`
- Stub events/flags: `nomad_frame_ark_empire`, `has_ark_capital`, planet `ark_capital` / `nomad_frame_ark_capital`
- `localisation/english/nomad_frame_ark_l_english.yml`
- `README.md` with load order + no game redistribution
- `QUESTIONS.md` kept in sync with eng-briefs copy intent

**Out of potato:** custom 3D, balance pass, full Frame district parity, Workshop publish.

## Constraint

**No Stellaris game files.** May download **mod packages** (SteamCMD workshop, mirrors) and public docs only. Potato spike could not run SteamCMD on this box (32-bit loader missing) — scaffolded from public docs only; Giga/XHK script keys remain TODO.

## Non-goals

Diverting TTRPG craft bots; inventing Giga APIs not present in downloaded mods.
