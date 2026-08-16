# Sofle Keyboard Layout Upgrade Guide

This guide describes the enhanced keymap prepared in [`config/sofle_enhanced.keymap`](file:///Users/dhruvcharan/code/zmk-config-sofle2encoder/config/sofle_enhanced.keymap).

---

## 🚀 How to Apply When You Connect Your Keyboard

When you are ready to flash your keyboard:

1. Replace `sofle.keymap` with the enhanced version:
   ```bash
   cp config/sofle_enhanced.keymap config/sofle.keymap
   ```
2. Commit and push the changes:
   ```bash
   git add config/sofle.keymap
   git commit -m "feat(keymap): add trackpad encoder gestures, symbol cluster, and LALT HRM"
   git push origin master
   ```
3. Download the firmware `.uf2` files from your GitHub Actions build artifacts, double-tap the reset button on each half of your Sofle to enter the bootloader, and copy the `.uf2` file to each side.

---

## 🎛️ Encoder & Click Functionality Reference

| Layer | Left Knob (Turn / Click) | Right Knob (Turn / Click) |
| :--- | :--- | :--- |
| **BASE** (No thumbs held) | `Volume Up/Dn`<br>**Click (Tap-Dance)**: 1-tap `Play/Pause`, 2-tap `Next Track`, Hold `Mute` | `Line-by-Line Code Scrobble (Up/Down)`<br>**Click**: `Raycast / Spotlight` (`Cmd+Space`) |
| **LOWER** (Hold Left Thumb) | `Volume Up/Dn`<br>**Click**: `App Exposé` (`Ctrl+Down`) | `Swipe Desktops/Spaces` (`Ctrl+Left / Ctrl+Right`)<br>**Click**: `Mission Control` (`Ctrl+Up`) |
| **RAISE** (Hold Right Thumb) | `Zoom In / Out` (`Cmd+Plus / Cmd+Minus`)<br>**Click**: `Reset Zoom 100%` (`Cmd+0`) | `Page Up / Down Scrub`<br>**Click**: `Hard Browser Refresh` (`Cmd+Shift+R`) |
| **ADJUST** (Hold Both Thumbs) | `Ghostty Split Nav` (`Cmd+Alt+Left/Right`) | `Neovim Jump List` (`Ctrl+O / Ctrl+I`) |

---

## ⌨️ Layer Summary

* **Layer 0 (BASE)**:
  * Uses `LALT` on both `S` (Left hand) and `L` (Right hand) to ensure Ghostty / Zellij shortcuts (`Alt+s`, `Alt+h/j/k/l`) never produce macOS accent characters (`ß`).
* **Layer 1 (LOWER - Navigation & Browser)**:
  * Right hand: `HJKL` arrows, word jumps (`Option + Left/Right`), line start/end (`Cmd + Left/Right`).
  * Left hand: Browser shortcuts for Vimium (`Cmd+W` close tab, `Cmd+L` address bar, `Cmd+Shift+T` reopen tab, `Cmd+F` search).
* **Layer 2 (RAISE - Symbols & Numpad)**:
  * Left hand: Programming brackets `{ } [ ] ( ) < > = ! & | ~ \` without shift strain.
  * Right hand: Full 3x3 numeric keypad (`7-8-9`, `4-5-6`, `1-2-3`, `0`).
