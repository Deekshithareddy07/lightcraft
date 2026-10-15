# LightCraft app icon

The Lightscape app icon and logo, formatted and sized for all supported desktop platforms (macOS,
Windows, and Linux).

## Geometry

macOS files (`.icns`, `lightcraft-macos-512.png`) use Apple's icon grid: a centered logo (~80% scale, 412x412)
with a transparent margin on a 512x512 canvas.
Windows and Linux files use full-bleed / standard square bounds across 16-512 px.

## Provenance

Original Lightscape logo artwork provided by the project owner. Rendered to PNG and packed into multi-resolution
icon formats. Licence: `LICENSE.txt` (MIT OR Apache-2.0, like the repo).

## Files

| File | What |
|---|---|
| `lightcraft.svg` | vector icon |
| `lightcraft-small.svg` | lighter vector icon |
| `lightcraft-1024.png` | 1024 px render (store listings, docs) |
| `lightcraft-macos-512.png` | runtime window/Dock icon on macOS (embedded by `apps/lightcraft/src/main.rs`; scaled to ~80% with transparent margin) |
| `lightcraft.icns` | macOS bundle icon (`CFBundleIconFile`) |
| `lightcraft.ico` | Windows icon, 16-256 px, embedded in `lightcraft.exe` by `apps/lightcraft/build.rs` |
| `hicolor/<n>x<n>/apps/ai.storyteller.lightcraft.png` | Linux icon theme, 16-512 px; the 256 px one is also the runtime window icon on Windows and Linux |
| `hicolor/scalable/apps/ai.storyteller.lightcraft.svg` | Linux scalable icon |

The app id is `ai.storyteller.lightcraft`: the Wayland app id, the `.desktop` file
(`packaging/linux/ai.storyteller.lightcraft.desktop`, `Icon=ai.storyteller.lightcraft`) and the hicolor icon
name. To install on Linux, copy `hicolor/` into `/usr/share/icons/hicolor/` (or `~/.local/share/icons/hicolor/`)
and the `.desktop` file into `applications/`.

## Regenerate

From the source image (`lightscape.png`), generate PNGs for each resolution using Python (PIL/Pillow),
and pack the Windows icon with `cargo xtask ico`. Every output is committed.
