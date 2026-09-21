# Confirmed keys (local Stellaris 4.4 + Giga install slices)

Sourced from `/workspace/stellaris-refs/` on 2026-09-20. **Do not invent** keys beyond this list.

## Giga descriptor (`giga/descriptor.mod`)

| Field | Value |
|-------|-------|
| `name` | `Gigastructural Engineering & More (4.4)` |
| `version` | `3.39.4` |
| `supported_version` | `v4.4.*` |
| `remote_file_id` | `1121692237` |

Mod `descriptor.mod` / `.mod` dependency string uses this exact `name`.

## Nomadic — vanilla

| Key | Kind | Source | Notes |
|-----|------|--------|-------|
| `is_nomadic` | Hardcoded special requirement / country check | Used in `vanilla/00_origins.txt` `possible = { is_nomadic = yes }`; used throughout `vanilla/09_scripted_triggers_nomads.txt` | **Not** defined as a scripted trigger in that file |
| `has_nomads_dlc` | Scripted trigger | `vanilla/09_scripted_triggers_nomads.txt` | `host_has_dlc = "Nomads"` |
| `origin_default_nomads` | Origin (Voidfarers) | `vanilla/00_origins.txt` | Reference Nomadic origin |
| `origin_sacred_path` | Origin | same | Nomadic; spiritualist |
| `origin_heirs_of_the_khan` | Origin | same | Nomadic; militarist + olig/dict/imp |
| `origin_forever_cruise` | Origin | same | Nomadic |
| `black_hole_nomad_init` (+ siblings) | System initializer | `vanilla/00_nomad_custom_initializers.txt` | `usage = nomad_init` |
| `civilian_arkship_megastructure` | Megastructure | `vanilla/29_nomad_arkships.txt` | + `science_` / `military_` |
| `civilian_arkship` / `science_arkship` / `military_arkship` | Ship size (mega inline) | same | Used as `SHIP_SIZE` |
| `civilian_arkship_tier_1` … `_3` | Ship / starbase size | `vanilla/09_scripted_triggers_nomads.txt` (`is_arkship_ship`) | Also science_/military_; `military_arkship_champions_forge` |
| `is_arkship_ship` / `is_arkship_fleet` / `is_capital_arkship_starbase` | Scripted triggers | same | Capital ark detection |
| `create_arkship_effect` | Scripted effect | `vanilla/nomads_effects.txt` | `$TYPE$` = civilian/science/military_arkship |
| `tech_civilian_arkship` / `tech_science_arkship` / `tech_military_arkship` | Tech | `vanilla/29_nomad_arkships.txt` | |
| `district_ark_*` / `arkship_mining_array` | Districts / modules | `vanilla/nomads_effects.txt` | Advanced empire ark capital districts |

## Frame World — Giga

| Key | Kind | Source | Notes |
|-----|------|--------|-------|
| `origin_frameworld` | Origin | `giga/frameworld_origins.txt` | **`possible = { always = no }` — "Disabled for 4.0"** |
| `pc_giga_frameworld` | Planet class | same (`starting_colony`); `giga/giga_origin_frameworld.txt` | Stationary Frame capital |
| `giga_frameworld_system` | Initializer | `giga/giga_origin_frameworld.txt` | Black hole + `pc_giga_frameworld` home |
| `giga_has_frameworld_origin` | Scripted trigger | `giga/giga_frameworld_triggers.txt` | `has_origin = origin_frameworld` (**trigger, not a flag**) |
| `giga_is_frame_world` | Scripted trigger | same | `is_planet_class = pc_giga_frameworld` |
| `pc_giga_frameworld_outpost_planet` / `_artificial` / `_ringworld` | Planet classes | same (`is_frameworld_outpost_planet`) | Outpost strip loop |
| `giga_frameworld_outpost` | Planet flag | same (`has_frameworld_outpost`) | |
| `giga_frameworld_origin.000` etc. | Events | `giga/frameworld_on_actions.txt` | Setup / monthly / yearly Frame logic |

Commented in Giga origin (disabled block): `# is_nomadic = no` — upstream intended Frame World **incompatible** with Nomadic.

## Wired into this potato

| Our key / usage | Real upstream key used |
|-----------------|------------------------|
| `origin_nomad_frame_ark` `possible` | `is_nomadic = yes` |
| `origin_nomad_frame_ark` `playable` | `has_nomads_dlc = yes` |
| icon / picture | `origins_default_nomads.dds` / `GFX_origin_nomad_default` |
| dependency string | `Gigastructural Engineering & More (4.4)` + workshop id documented `1121692237` |
| `is_nomad_frame_ark_empire` | `has_origin = origin_nomad_frame_ark` (ours) |
| Day-1 flags | `nomad_frame_ark_empire`, `has_ark_capital`, planet `ark_capital` / `nomad_frame_ark_capital` |

## Explicitly NOT wired (product / safety)

- `change_pc = pc_giga_frameworld` — would make stationary Frame capital; conflicts with Nomadic ark playstyle
- Claiming `has_origin = origin_frameworld` or firing `giga_frameworld_origin.*` — origin disabled; events assume Frame planet
- Setting `giga_has_frameworld_origin` as a country flag — it is a trigger, not a flag
- Custom ark megastructure spawn — `create_arkship_effect` exists in vanilla effects; product decision pending (QUESTIONS.md)
