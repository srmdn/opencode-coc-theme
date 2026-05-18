# opencode-coc-theme

Supercell Store inspired themes for [OpenCode](https://opencode.ai).

- `clash-of-clans.json`: soft off-white store palette, even in dark terminal mode
- `clash-of-clans-dark.json`: darker store palette

Both are closer to `https://store.supercell.com/clashofclans` than to the old fantasy CoC palette.

## Install

```bash
mkdir -p ~/.config/opencode/themes
cp themes/clash-of-clans.json ~/.config/opencode/themes/
cp themes/clash-of-clans-dark.json ~/.config/opencode/themes/
```

Or symlink for updates:

```bash
ln -s "$(pwd)/themes/clash-of-clans.json" ~/.config/opencode/themes/
ln -s "$(pwd)/themes/clash-of-clans-dark.json" ~/.config/opencode/themes/
```

Activate in OpenCode:

```text
/theme clash-of-clans
```

Or darker version:

```text
/theme clash-of-clans-dark
```

Or set it in `~/.config/opencode/tui.json`:

```json
{
  "$schema": "https://opencode.ai/tui.json",
  "theme": "clash-of-clans"
}
```

## Palette

| Role | Token | Hex |
|---|---|---|
| Page base | `storeBeige` | `#D8C4AD` |
| Soft highlight | `storeBeigeLight` | `#F5E3C7` |
| Main text | `storeText` | `#191919` |
| Muted text | `storeTextMuted` | `#666666` |
| Card / surface | `storeWhite` | `#FFFFFF` |
| CTA blue | `storeBlue` | `#2D85F3` |
| Bright blue | `storeBlueBright` | `#4A9EFF` |
| Gold accent | `storeGold` | `#F2CD4A` |
| Gold shadow | `storeGoldDark` | `#BC8C1C` |
| Success | `storeGreen` | `#46DFAE` |
| Error | `storeRed` | `#F94343` |
| Dark background | `storeInk` | `#15161E` |
| Dark panel | `storeInkPanel` | `#1B1B22` |
| Dark elevated | `storeInkElevated` | `#21222C` |
| Dark border | `storeBorderDark` | `#313345` |

## Notes

- Main goal: mimic store UI feel, not game art.
- Use `background`, `text`, and `primary` tokens first.
- Keep syntax colors restrained. Blue, gold, green, and red are enough.
