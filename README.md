Ganbare! Daiku no Gen-san (SFC, JP) - English Translation
=========================================================

Translated using AI (Claude Pro). Visit our website: https://www.retroplayingbcn.es
==================================================================================

Files
  Ganbare_Daiku_no_Gen-san_EN.ips  IPS patch (apply to the original Japanese ROM)

Required base ROM
  MD5  f21c97e9943cb29592eaada932b6271b  (1 MB, no copier header)
Patched result
  MD5  a35d2c33adf4916697d14ed825556a59   CRC32 579ba3de
  Size 2 MB (HiROM/FastROM). Internal header checksum fixed (valid).

What's translated
  - Storybook pages (5) and all 9 boss conversations (35 pages)
  - Chapter title cards on the map (Prologue, 1-1 ... Finale)
  - Ending (7 pages), scrolling epilogue and staff credits (roles + names in romaji)
  - Kanna's cheer lines
  - HUD: SCORE / LIFE / STG + area name (TOWN, FOREST, VALLEY, HIDEOUT, FINAL) and FOE in boss fights
  - Title screen speech bubble: "IF YOU NEED ME, PRESS START!" / "LET'S GO!"

Technical changes
  - New 8x16 dialogue font (original design), packed two letters per 16x16 cell.
  - Glyph drawing routines (C2:0F10 and its copy at C0:95EF) rewritten for half-width
    characters; cursor advance changed from 2 tiles to 1 in both typewriter routines.
  - ROM expanded to 2 MB; new text placed in bank D0, 24-bit pointers redirected.
  - Bank for chapter titles, Kanna's cheers and the epilogue redirected (LDY immediates).
  - Title bubble: hook in the BG3 buffer DMA routine (C0:8355 -> DF:8000).
  - Life bar end caps redrawn (they used to look like the kana "ku" in たいりょく).

Testing (snes9x emulator)
  - Boot, title, intro, storybook, chapter cards, HUD in normal and boss stages.
  - All 50 dialogue pages rendered one by one in-game.
  - 6 stages played for ~6000 frames each: behaviour identical to the original ROM.
  - The epilogue and credits were checked against the engine's table/format, but
    have not been seen on screen yet (requires finishing the game).

Not translated (graphics, not text)
  - Wooden title logo (the original Japanese logo is kept).
  - "てやんでい!" exclamation sprite and some background signs.

Feedback and bug reports are welcome at https://www.retroplayingbcn.es
