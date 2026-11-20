# Native Redux Plugin

A full in-game cheat & tweak menu for the Skate 2 (PC rewrite), a drop-in plugin. No launcher,
no patcher — two files go next to the game and the menu opens with `TAB` (keyboard) · `D-pad Left + R3` (controller).

> The plugin never touches the official `skate2-pc.exe`.

| | |
|---|---|
| **For game version** | Official Skate 2 (PC rewrite) |
| **Open the menu** | `TAB` (keyboard) · `D-pad Left + R3` (controller) |
| **Install** | Drop 2 files next to `skate2-pc.exe` |
| **Online** | Works — to the server and other players it behaves like the normal game |

---

## Download

Download **[`Native Redux Plugin.rar`](Native%20Redux%20Plugin.rar)** — it contains the two files
you need:

| File | What it is |
|---|---|
| `NativeReduxPlugin.asi` | The plugin (the Native Redux menu + the game it runs). |
| `version.dll` | [Ultimate ASI Loader](https://github.com/ThirteenAG/Ultimate-ASI-Loader) v10.0.2 (x64), unchanged, by ThirteenAG — the loader that starts the plugin. |

<details>
<summary><b>This release — checksums</b></summary>

```
NativeReduxPlugin.asi
version.dll
```
</details>

---

## Install

1. Copy `version.dll` and `NativeReduxPlugin.asi` into the folder that holds the official
   `skate2-pc.exe` (v0.3.5).
2. Start the game the normal way. Press `TAB` (or `D-pad Left + R3`) to open the menu.

**Uninstall:** delete `version.dll`, `NativeReduxPlugin.asi` and `NativeReduxPlugin.log`. The
game is back to normal.

---

## What's in the menu

Everything is organized into tabs. Move rows with Left/Right; a switch flips, a number steps
(hold to repeat), and `Y` lets you type a value directly.

- **Skating** — Walk/Running Speed, Ollie Height, Footplant, Body Rotation/Flip Speed, Board
  Size, No Speed Cap, No Fall Damage, score multiplier, and more.
- **Player** — Jump Height, Back To Marker Speed.
- **World** — Gravity (and ragdoll / hippy-jump gravity), Disable All Props, No Online Boundary,
  spawn-out-of-bounds.
- **Timers** — ragdoll / Hall of Meat / settle timers, No In-Air Timer.
- **Visual** — brightness, contrast, saturation, bloom, lighting, cameraman controls, 3D mode.
- **Control** — camera smoothness and feel.
- **Game Settings → Cheats**
  - *Swaytic's Cheats* — Big Head, Big Black Physics, Unpatch Pop Shuvit, Unpatch Moonwalk, …
  - *Skate 3 Cheats* — Hoverboards, Mini Skaters, Zombie Pedestrians, Streetsweeper, …
  - 3D Mode, Change Player Name, Game Mode / Freeze Game / Game Speed (offline only).
- **Skater Editor** — full appearance control: Colorable Items (per-piece colour overrides),
  Gloss per clothing piece, Play Style (pro skaters' animation styles), Skate 2 Gestures /
  Skate 3 Posture cross-overs, Hair Under Hats, Chain On Any Top, Clean Textures, hide any
  part / Missing Texture.
- **Profiles** — save and load your whole set of toggles and values.
- **Credits**

---

## Online play

The plugin plays online on the same server as the official game, using the nickname and server
from the game folder's `online-config.json`.

- To the server and to the other players, your game behaves like the stock official v0.3.5 —
  nothing tells them the menu is there.
- Other players see your skater and whatever it displays: your clothing, colours, hidden parts,
  Big Head / Mini size, Hoverboards, and your movement. Looks only this menu draws (Gloss, Board
  Size, a swap onto a part the base game doesn't colour) are client-side — only you see them.
- A few things can't apply online because every player shares the lobby's clock and rules: Game
  Mode, Freeze Game, Game Speed are greyed out in an online game.

**Please play fair.** The cheats change your client; be considerate on a shared server.

---

## Compatibility & game updates

- This build runs only on the official v0.3.5 `skate2-pc.exe`. On startup the plugin checks the
  exe's SHA-256; if it's any other version the plugin does nothing and the game runs normally.
  The reason is written to `NativeReduxPlugin.log` next to the exe.
- When the official game updates to a new version, the game will run without the menu until a
  plugin built for that version is released. While the plugin is active the game's own update
  check does not run, and the plugin never updates itself.

---

## How it works

The official `skate2-pc.exe` is not patched on disk or in memory (apart from one jump at its
entry point). When the game starts, the loader (`version.dll`) loads the plugin; the plugin
confirms the exe is official v0.3.5 and then runs the Native Redux build of the game in place of
the exe's own code. On any other exe the plugin stands aside and the game runs stock.

---

## Troubleshooting

- **Menu won't open / game runs like stock** — check `NativeReduxPlugin.log` next to the exe; it
  says whether the plugin started and, if not, why (usually the exe isn't official v0.3.5).
- **A console window flashes on launch** — expected; the plugin closes it.
- **Profiles** are stored in `Native Redux Plugin Profiles` next to the exe.

---

## Credits

- **Swaytic** — Made the Native Redux Plugin · The ideas and direction for it all · Swaytic's Cheats · All the play testing
- **Wispp** — Skate 2 Rust Port · S2 Native Menu · S3 Native Menu
- **Matt (LAVA)** — LAVA's Skate 2 Cheat Table V1.1.0 · The menu's tabs, rows and order
- **Claude and Codex (AI)** — Wrote the plugin's code · Tested every build
- **SunJay** — Attrib (Vault) reader · Vault (Names, Addresses, Values)
- **Ulfednyer** — Skate 3 X360 RTM Tool · Footplant Forever's landing value
- **S4M** — Pop shuvit bounce write-up · Used for Unpatch Pop Shuvit

---

## License

- **Ultimate ASI Loader** (`version.dll`): https://github.com/ThirteenAG/Ultimate-ASI-Loader/blob/master/license
- **GPL-3.0**: https://www.gnu.org/licenses/gpl-3.0.html

---
