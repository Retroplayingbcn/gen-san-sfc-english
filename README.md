# Ganbare! Daiku no Gen-san (SFC, JP) – English Translation

English translation patch for **Ganbare! Daiku no Gen-san** (Irem, 1993) for the Super Famicom, a Japan-only release.

Translated using AI (Claude Pro) by [RetroPlayingBCN](https://www.retroplayingbcn.es).

**[⬇ Download the latest release](https://github.com/Retroplayingbcn/gen-san-sfc-english/releases/latest)**

## Which patch do I need?

Use the patch that matches your ROM (1 MB, no copier header). Apply it with Floating IPS, Rom Patcher JS or any IPS patcher. Both results are 2 MB (HiROM) with a valid internal header checksum.

| Patch | Base ROM MD5 | Result MD5 | Result CRC32 |
|---|---|---|---|
| `Ganbare_Daiku_no_Gen-san_EN_standard.ips` (standard ROM, most common) | `9866b522bec493784b124ca70ce69919` | `c2ed10bb294789f36098fb5c51fc17ec` | `1299babb` |
| `Ganbare_Daiku_no_Gen-san_EN.ips` ("FastROM"-patched ROM) | `f21c97e9943cb29592eaada932b6271b` | `a35d2c33adf4916697d14ed825556a59` | `579ba3de` |

The two base ROMs differ in only 4 bytes; the translation is identical.

## What's translated

- Storybook pages (5) and all 9 boss conversations (35 pages)
- Chapter title cards on the map (Prologue, 1-1 … Finale)
- Ending (7 pages), scrolling epilogue and staff credits (roles + names in romaji)
- Kanna's cheer lines
- HUD: SCORE / LIFE / STG + area name (TOWN, FOREST, VALLEY, HIDEOUT, FINAL) and FOE in boss fights
- Title screen speech bubble: "IF YOU NEED ME, PRESS START!" / "LET'S GO!"

## Technical changes

- New 8×16 dialogue font (original design), packed two letters per 16×16 cell.
- Glyph drawing routines (`C2:0F10` and its copy at `C0:95EF`) rewritten for half-width characters; cursor advance changed from 2 tiles to 1 in both typewriter routines.
- ROM expanded to 2 MB; new text placed in bank `D0`, 24-bit pointers redirected.
- Bank for chapter titles, Kanna's cheers and the epilogue redirected (`LDY` immediates).
- Title bubble: hook in the BG3 buffer DMA routine (`C0:8355` → `DF:8000`).
- Life bar end caps redrawn (they used to look like the kana "ku" in たいりょく).

## Testing (snes9x emulator)

- Boot, title, intro, storybook, chapter cards, HUD in normal and boss stages.
- All 50 dialogue pages rendered one by one in-game.
- 6 stages played for ~6000 frames each: behaviour identical to the original ROM.
- Standard ROM build: boot, title, story, map, HUD, boss and final stages checked.
- The epilogue and credits were checked against the engine's table/format, but have not been seen on screen yet (requires finishing the game).

## Not translated (graphics, not text)

- Wooden title logo (the original Japanese logo is kept).
- "てやんでい!" exclamation sprite and some background signs.

## Notes

No ROMs are provided here. You must supply your own dump.

Feedback and bug reports are welcome at [retroplayingbcn.es](https://www.retroplayingbcn.es) or in this repository's Issues.
