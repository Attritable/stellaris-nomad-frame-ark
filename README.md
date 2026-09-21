# Nomad Frame Ark (Potato)

Stellaris **Vanilla 4.4** origin stub: **Frame-inspired playstyle as a nomadic ark capital** — mobile home, not Giga’s black-hole `pc_giga_frameworld`.

Requires **vanilla Nomadic** (`is_nomadic` + Nomads DLC) and **Gigastructural Engineering & More (4.4)**. Not a Workshop “Nomads patch” dependency.

**Bar:** valid mod structure Thomas can enable in the launcher. Real keys from local install slices — see `KEYS.md`. No balance, no custom 3D, no Workshop publish yet.

## Load order

1. **Gigastructural Engineering & More (4.4)** (Steam `1121692237`, local version `3.39.4`)
2. **This mod** (`Nomad Frame Ark`)
3. **UI Overhaul Dynamic** (+ Giga UIOD patch) — only if you later need Frame Fix / UI-dependent Frame content
4. Optional reference: **[4.4] XHK Frameworld 4.4 Fix** (`3615040887`) — not a hard dependency

Enable **Nomadic** empire mode when testing. Giga’s `origin_frameworld` is **disabled** upstream; this origin is a separate path.

No Stellaris game files are redistributed here.

## Install (local)

1. Copy this folder into  
   `~/.local/share/Paradox Interactive/Stellaris/mod/stellaris-nomad-frame-ark/`  
   (Windows: `Documents\Paradox Interactive\Stellaris\mod\...`).
2. Copy `stellaris-nomad-frame-ark.mod` into the parent `mod/` folder and fix `path=` to match.
3. Enable in launcher after Giga.

## Dependencies

Declared in `descriptor.mod` / `.mod`:

- `Gigastructural Engineering & More (4.4)` (exact `name=` from local Giga `descriptor.mod`)

Playable gate (in origin): `has_nomads_dlc` → `host_has_dlc = "Nomads"`.

## Potato contents

| Path | Role |
|------|------|
| `KEYS.md` | Every confirmed upstream key + what we wired |
| `descriptor.mod` | In-folder metadata |
| `stellaris-nomad-frame-ark.mod` | Launcher pointer |
| `common/governments/civics/00_nomad_frame_ark_origins.txt` | `origin_nomad_frame_ark` |
| `common/scripted_triggers/nomad_frame_ark_triggers.txt` | Thin triggers |
| `common/on_actions/nomad_frame_ark_on_actions.txt` | Game-start hook |
| `events/nomad_frame_ark_events.txt` | Ark capital flags + confirm event |
| `localisation/english/nomad_frame_ark_l_english.yml` | EN loc |
| `DESIGN.md` / `QUESTIONS.md` | Design + open questions |

## License / redistribution

- **Do not** redistribute Stellaris or Gigastructures game/mod binaries via this repo.
- Scripts and docs here are original potato stubs for private clone/load-test.
