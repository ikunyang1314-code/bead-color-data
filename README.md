# Fuse Bead Color Data

Structured color codes for 9 fuse bead (a.k.a. perler beads / ironing beads / Hama beads)
brands, plus a universal palette. Each record contains the **brand color code**, a
**color name**, and **HEX / RGB** values — the same data used by the color-matching
engine at [beiyapd.com](https://beiyapd.com/en/bead-tools).

Color names are kept in their original (mostly Chinese) brand naming.

## Files

| File | Brand | Colors |
|---|---|---|
| `perler.csv` | Perler (5 mm) | 117 |
| `hama.csv` | Hama (Midi) | 89 |
| `artkal.csv` | Artkal (S-5mm) | 176 |
| `artkal-c.csv` | Artkal C Mini (2.6 mm) | 174 |
| `artkal-hard.csv` | Artkal Hard | 176 |
| `artkal-soft.csv` | Artkal Soft | 176 |
| `nabbi.csv` | Nabbi | 30 |
| `mard.csv` | MARD | 221 |
| `ikea.csv` | IKEA Pyssla | 18 |
| `universal.csv` | Universal palette | 72 |

**Total: 1,249 color cards across 10 palettes** (988 unique color codes across the
9 brand palettes after de-duplication).

Machine-readable manifest: [`index.json`](index.json).

## Format

CSV with header:

```
code,name,hex,r,g,b
P01,银白,#F1F1F1,241,241,241
```

- `code` — the brand's own color code (e.g. `P01` for Perler, `H01`/`H101` for Hama,
  `A1`…`M15` for MARD, `I01` for IKEA).
- `name` — original color name as published by the brand/supplier.
- `hex` / `r,g,b` — sRGB values used for color matching (CIEDE2000 against uploaded
  photos in the BeiYa generator).

## Usage

Free to use for personal and commercial projects. Attribution appreciated:

> Color data from [beiyapd.com/color-data](https://beiyapd.com/color-data/)
> (BeiYa bead pattern generator).

## Maintenance

- Source of truth: `src/data/beads/*.json` in the [beiya-pd](https://github.com/ikunyang1314-code/beiya-pd) project.
- Last synced: 2026-10-07.
- Found an error? Open an issue with the brand, color code and the corrected HEX/RGB.

## Disclaimer

Values are compiled for photo-to-pattern color matching. For craft-critical work
(e.g. ordering beads to fill a large project), verify against the manufacturer's
official color chart.
