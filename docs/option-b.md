# Option B: Monospaced Clash of Clans Font Pipeline

**Status**: Backup plan — pursue only if Option A (Monocraft + CoC theme) isn't satisfying enough.

## Goal

Create a fully monospaced programming font based on the Clash of Clans visual style, equivalent to what [Monocraft](https://github.com/IdreesInc/Monocraft) did for Minecraft.

## The Legal Hurdle

Supercell-Magic / You Blockhead is proprietary (Comicraft, licensed to Supercell). You cannot legally modify and redistribute the actual font file.

### Solution: Build an open-source replica

Create a **new** font from scratch that captures the CoC visual style, using only original glyph designs. This is what Monocraft did — it's not Mojang's font, it's a replica built from scratch.

This means:
- ✅ Legal to distribute under OFL or MIT
- ✅ Can be published on GitHub, npm, Homebrew
- ✅ Can be modified freely
- ❌ Cannot extract glyphs from Supercell-Magic.ttf directly

## Technical Pipeline

### Phase 1: Glyph Design

Create original glyphs in the CoC style:

```
Source material (reference only):
  ├── Clash of Clans UI screenshots
  ├── Fan art / community recreations
  └── Supercell-Magic.ttf (visual reference, NOT extraction)

Output:
  └── FontForge source files (.sfd)
      ├── Uppercase A-Z
      ├── Lowercase a-z
      ├── Digits 0-9
      ├── Programming symbols: {} [] () <> _ # @ $ % ^ & * ~ ` |
      ├── Punctuation: . , ; : " ' ! ? - – — / \
      ├── Math: + - × ÷ = ≠ ≈ < > ≤ ≥
      ├── Arrows: → ← ↑ ↓ ↔ (ligature candidates)
      └── Ligatures: => != === !== >= <= |> ||> -> <- |>
```

### Phase 2: Monospacing

Make every glyph occupy exactly the same advance width:

- **Narrow chars** (`i`, `l`, `1`, `t`, `f`, `j`, `r`): Add serifs, tails, or wider strokes
- **Wide chars** (`W`, `M`, `m`, `w`, `@`, `#`): Condense or adjust proportions
- **Moderate chars** (most letters): Ensure consistent spacing and visual weight

Tools: FontForge Python API, similar to Monocraft's `build/` scripts.

### Phase 3: Ligatures

Add programming ligatures matching Monocraft's set:

```
→  ->   =>   ==   !=   !==   ===   <=   >=   ::   |>   ||>
→  |>   <|   >>   <<   ++   --   **   //   /*   */   .=   .-
→  &&   ||   |>|  <|>  <$>  </>  <!--  ~>   -<   >-   <->
```

### Phase 4: Delivery

Generate font files and publish:

```
dist/
├── CocCraft.ttc          # TrueType Collection (macOS)
├── CocCraft.ttf          # TrueType (cross-platform)
├── CocCraft.woff2        # Web
└── CocCraft-Regular.otf  # OpenType
```

## Estimated Effort

| Phase | Work | Time (estimate) |
|---|---|---|
| Glyph design | ~200 unique glyphs, vector design | 2-4 weeks |
| Monospacing | Adjust advance widths, refine | 1-2 weeks |
| Kerning & metrics | Spacing pairs, line height | 3-5 days |
| Ligatures | ~30 programming ligatures | 3-5 days |
| Testing | Terminal rendering, edge cases | 1 week |
| Packaging | Brew cask, npm, documentation | 2-3 days |
| **Total** | | **~6-8 weeks** |

This assumes part-time work. Full-time effort could compress to ~2-3 weeks.

## Reference Projects

- [Monocraft](https://github.com/IdreesInc/Monocraft) — Minecraft → monospaced font (223 commits, FontForge + Python)
- [Miracode](https://github.com/IdreesInc/Miracode) — Vectorized Monocraft variant
- [Minecraft-Font](https://github.com/IdreesInc/Minecraft-Font) — Non-monospaced Minecraft font replica

## Decision Gate

Pursue Option B if and only if:
1. Option A (Monocraft + CoC theme) feels inauthentic after daily use
2. Someone is willing to commit ~6 weeks to glyph design
3. The legal path (from-scratch replica) is clearly understood

Otherwise: Option A ships now and works today.
