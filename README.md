# Nomad Frame Ark (Potato)

Stellaris 4.4 origin stub: **Frame World playstyle as a nomadic ark capital** — mobile home, not a black-hole frame planet.

**Bar:** valid mod structure Thomas can enable in the launcher. TODOs where Gigastructures / Frame keys are unknown. No balance, no custom 3D, no Workshop publish yet.

## Load order

1. **Gigastructural Engineering & More** (Steam Workshop historically `1121692237`)
2. **UI Overhaul Dynamic** (+ Giga UIOD patch) — only if you also run Frame Fix / UI-dependent Frame content
3. Optional reference: **[4.4] XHK Frameworld 4.4 Fix** (`3615040887`) — structural inspiration; **not** a hard dependency of this potato
4. **This mod** (`Nomad Frame Ark`)

No Stellaris game files are redistributed here. Clone, copy the folder into your Stellaris `mod/` directory (or symlink), and point the launcher `.mod` `path=` at it.

## Install (local)

1. Copy `/workspace/stellaris-nomad-frame-ark` (or this repo) into  
   `~/.local/share/Paradox Interactive/Stellaris/mod/stellaris-nomad-frame-ark/`  
   (Windows: `Documents\\Paradox Interactive\\Stellaris\\mod\\...`).
2. Copy `stellaris-nomad-frame-ark.mod` into the parent `mod/` folder and fix `path=` to match.
3. Enable in launcher after Giga (and UIOD if needed).

## Dependencies

Declared in `descriptor.mod` / `.mod`:

- `Gigastructural Engineering & More` (display name; workshop id `1121692237` historically)

Exact Giga origin / planet / flag keys for Frame World are **not** wired yet — see `QUESTIONS.md` and TODOs in scripts.

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
