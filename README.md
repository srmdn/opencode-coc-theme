# opencode-coc-theme

Clash of Clans inspired theme for [OpenCode](https://opencode.ai) — gold, elixir, and dark elixir palette. Built for the TUI.

![preview](https://img.shields.io/badge/theme-clash--of--clans-gold)

## Overview

| Component | What |
|---|---|
| **[Option A](themes/clash-of-clans.json)** | CoC color theme JSON + Monocraft font → shippable **now** |
| **[Option B](docs/option-b.md)** | Monospaced CoC font build pipeline → **backup plan** |

Option A gives you the full CoC aesthetic via colors + a game-themed monospaced font. Option B would create a true monospaced "CocCraft" font from scratch.

## Quick Start (Option A)

### 1. Install Monocraft font

[Monocraft](https://github.com/IdreesInc/Monocraft) is a Minecraft-inspired monospaced programming font — thematically adjacent to Clash of Clans.

```bash
# macOS (Homebrew)
brew install --cask font-monocraft

# Or download from: https://github.com/IdreesInc/Monocraft/releases
```

### 2. Set Monocraft as your terminal font

**iTerm2**: Preferences → Profiles → Text → Font → Monocraft
**Terminal.app**: Settings → Profiles → Text → Font → Monocraft
**Kitty**: `font_family Monocraft` in `kitty.conf`
**Alacritty**: `family: Monocraft` in `alacritty.yml`

### 3. Install the theme

```bash
# Global install (all projects)
mkdir -p ~/.config/opencode/themes
cp themes/clash-of-clans.json ~/.config/opencode/themes/

# Or symlink for updates
ln -s "$(pwd)/themes/clash-of-clans.json" ~/.config/opencode/themes/
```

### 4. Activate

```
# In OpenCode TUI:
/theme clash-of-clans
```

Or set permanently in `~/.config/opencode/tui.json`:
```json
{
  "$schema": "https://opencode.ai/tui.json",
  "theme": "clash-of-clans"
}
```

## Theme Palette

| Token | CoC Source | Hex | Preview |
|---|---|---|---|
| Gold | Resources / logo | `#F8B133` | 🟡 |
| Elixir Pink | Elixir resource | `#D44A8C` | 🩷 |
| Dark Elixir Purple | Dark elixir | `#7B4FBF` | 🟣 |
| Green Gem | Gems | `#4CAF50` | 🟢 |
| Damage Red | HP bar / attacks | `#E53935` | 🔴 |
| Builder Orange | Builder base | `#FF9800` | 🟠 |
| Elixir Glow | Elixir glow effect | `#CE6BB8` | 💜 |
| Parchment | UI text | `#F5E0B8` | 📜 |
| Deep Dark | Night village | `#1A0D14` | ⬛ |
| Stone Walls | Walls / panels | `#2E1D26` | 🟫 |

### Syntax Highlighting

```
keywords    → gold       🟡  import, function, return, if
functions   → elixir     🩷  myFunction(), handleClick()
strings     → green gem  🟢  "hello world"
numbers     → purple     🟣  42, 3.14
types       → glow       💜  string, number, interface
operators   → orange     🟠  =>, ==, +
comments    → muted      📜  // this is a comment
```

## Rollback

Everything is reversible:

| What | How | Time |
|---|---|---|
| Terminal font | Terminal settings → pick old font | 5s |
| OpenCode theme | `/theme opencode` (pick default) | Instant |
| Remove theme files | `rm ~/.config/opencode/themes/clash-of-clans.json` | Instant |
| Remove Monocraft | Font Book → right-click → Remove | 10s |

Nothing touches system files. Nothing overrides defaults permanently.

## Project Structure

```
opencode-coc-theme/
├── themes/
│   └── clash-of-clans.json   ← The theme
├── docs/
│   └── option-b.md           ← Backup plan: monospaced CoC font
└── README.md
```

## License

MIT — do whatever you want with the theme JSON.
Font: Monocraft is [OFL-1.1](https://github.com/IdreesInc/Monocraft/blob/main/LICENSE).
