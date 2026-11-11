# Companion Living Style

A Ragnarok Offline add-on by DaggerHashimoto. It gives recruited companions, ambient AI and AI vendors varied costume looks across the whole world:

- complete outfits (upper, middle, lower and garment worn together), reshuffled for each play session
- town-themed looks in 34 major towns, with a Costume Guide in each town to switch the theme off or on
- townsfolk who sit to rest and show the odd emote
- optional Cold Bolt use for companions that already know the skill

It's cosmetic only: no items, stats, jobs or shop inventories change. Costumes really equipped on companions always take priority.

## Install

In Ragnarok Offline 1.8.3 or newer, find **Companion Living Style** in **Find Mods**. Or download `companion-living-style-<version>.zip` from [Releases](../../releases) and install it with **Install from ZIP**. Turn on Population Engine, enable the add-on, then use **Apply & restart**. It works on Renewal and pre-renewal.

If you update by hand, replace the whole `companion-living-style` folder. Leftover NPC files from an older version run a second styling script and make outfits flip.

## Layout

- `companion-living-style/`: the mod, exactly as installed. `npc/living-style-v*.txt` and `ROPD-OUTFITS-v*.json` are generated; edit `tools/living-style.template.txt` instead.
- `tools/`: the catalog inputs, the generator and the checks. See [tools/README.md](tools/README.md).
- `.github/workflows/release.yml`: on a `v*` tag, it runs the checks, zips `companion-living-style/` and publishes the release with that version's changelog.

## Releasing

1. Bump the version: the versioned file names, `mod.json`, the changelogs and the check expectations.
2. Run `node tools/build.cjs`, `node tools/check.cjs` and `node tools/check-refresh.cjs`.
3. Commit, then push a tag that matches `mod.json` (for example `v1.7.2`). The workflow builds and publishes the release, and the app offers it as an update.

## Credits and licence

GPL-3.0-or-later (see [LICENSE](LICENSE)). Costume definitions come from rAthena (GPL-3.0-or-later). Outfit combinations come from the public appearance data on iromarket.net's ROPD pages. Companion Party Overhaul is a separate mod by Always.

☕ [Buy me a coffee](https://buymeacoffee.com/miisteryap)
