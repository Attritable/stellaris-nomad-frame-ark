# Nomad Frame Ark (Potato)

Stellaris **Vanilla 4.4** origin stub: **Frame World playstyle as a nomadic ark capital** — mobile home, not a black-hole frame planet.

Designed for **vanilla 4.4 Nomadic** empires (Arkships / `is_nomadic`) plus **Gigastructural Engineering**. Not a Workshop “Nomads patch” dependency.

**Bar:** valid mod structure Thomas can enable in the launcher. TODOs where Gigastructures / Frame keys are unknown. No balance, no custom 3D, no Workshop publish yet.

## Load order

1. **Gigastructural Engineering & More** (Steam Workshop historically `1121692237`)
2. **This mod** (`Nomad Frame Ark`)
3. **UI Overhaul Dynamic** (+ Giga UIOD patch) — **only if** you later need Frame Fix / UI-dependent Frame content (not required for potato)
4. Optional reference: **[4.4] XHK Frameworld 4.4 Fix** (`3615040887`) — structural inspiration; **not** a hard dependency

Enable **vanilla Nomadic** in empire creation when testing this origin’s intended playstyle.

No Stellaris game files are redistributed here. Clone, copy the folder into your Stellaris `mod/` directory (or symlink), and point the launcher `.mod` `path=` at it.

## Install (local)

1. Copy `/workspace/stellaris-nomad-frame-ark` (or this repo) into  
   `~/.local/share/Paradox Interactive/Stellaris/mod/stellaris-nomad-frame-ark/`  
   (Windows: `Documents\Paradox Interactive\Stellaris\mod\...`).
2. Copy `stellaris-nomad-frame-ark.mod` into the parent `mod/` folder and fix `path=` to match.
3. Enable in launcher after Giga (UIOD only if needed for a later Frame Fix path).

## Dependencies

Declared in `descriptor.mod` / `.mod`:

- `Gigastructural Engineering & More` (display name; workshop id `1121692237` historically)

**Not** declared: any third-party Nomads workshop pack — Nomadic is vanilla 4.4.

Exact Giga origin / planet / flag keys for Frame World are **not** wired yet — see `QUESTIONS.md` and TODOs in scripts. Do not invent Giga frame keys.

## Potato contents

| Path | Role |
|------|------|
| `descriptor.mod` | In-folder metadata |
| `stellaris-nomad-frame-ark.mod` | Launcher pointer (`path=mod/stellaris-nomad-frame-ark`) |
| `common/governments/civics/00_nomad_frame_ark_origins.txt` | `origin_nomad_frame_ark` |
| `common/on_actions/nomad_frame_ark_on_actions.txt` | Game-start hook |
| `events/nomad_frame_ark_events.txt` | Ark capital flags + confirm event |
| `localisation/english/nomad_frame_ark_l_english.yml` | EN loc |
| `DESIGN.md` / `QUESTIONS.md` | Design + open questions |

## License / redistribution

- **Do not** redistribute Stellaris or Gigastructures game/mod binaries via this repo.
- Scripts and docs here are original potato stubs for private clone/load-test.
