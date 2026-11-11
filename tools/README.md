# Companion Living Style catalog tools

These files are maintainer inputs. They don't ship inside the installed mod.

- `observed-outfits.json`: outfit combinations as shown on iromarket.net's public ROPD pages (https://www.iromarket.net/ropd/), collected November 10, 2026. Each outfit has only four integer View fields (upper, middle, lower, garment). There are no names, character or account IDs, or anything else personal.
- `costume-reference.json`: matching rAthena costume definitions (GPL-3.0-or-later), limited to observed views that have entries in the app 1.8.3 bundled HatTable/RobeTable. This is a conservative allowlist, not a complete client asset scan.
- `living-style.template.txt`: the runtime source template, with a single generated catalog marker.
- `build.cjs`: validates and deduplicates complete tuples, then writes the runtime arrays and the installed catalog. It rejects malformed or extra outfit fields, and an unknown occupied slot excludes the whole combination.
- `check.cjs`: catalog provenance, strict input validation, generated output, a replay of the actual registration block, and settings-bridge checks.
- `check-refresh.cjs`: client timing and cancellation, bounded server scans, and the in-view restyle.

Run from the repository root:
```
node tools/build.cjs
node tools/check.cjs
node tools/check-refresh.cjs
```

The catalog keeps only 431 of the 1,487 collected combinations. A missing bundled table entry doesn't prove the player's GRFs lack the sprite. Expand the allowlist only after verifying mappings and sprites. Keep zero slots and the observed tuple, and never fill missing pieces with guesses.

For a new release, raise the version deliberately (the versioned file names, `mod.json`, and the expectations in the checks). Never commit raw authenticated HTML or session data. Neither the generator nor the installed mod uses the network.
