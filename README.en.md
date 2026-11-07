<p align="center">
  <a href="README.md">简体中文</a> ·
  <a href="README.zh-Hant.md">繁體中文</a> ·
  <a href="README.en.md"><b>English</b></a> ·
  <a href="README.ja.md">日本語</a> ·
  <a href="README.ko.md">한국어</a> ·
  <a href="README.fr.md">Français</a> ·
  <a href="README.de.md">Deutsch</a>
</p>

<p align="center">
  <img src="docs/docs-hero.png" width="176" alt="QuadCut" />
</p>

<p align="center"><img src="docs/gold-qdir-en.svg" width="351" height="51" alt="In tribute to Q-Dir" /></p>

<h1 align="center">QuadCut</h1>

<p align="center"><strong>Quad-pane file manager · Windows 1.8.3</strong></p>

Anyone who has sorted photos with Windows Explorer knows the back-and-forth: copy in one window, paste in another, and a few minutes later you can no longer tell which is which. Picking the one sharp frame out of dozens of burst shots means double-clicking each one, zooming in, and closing it again.

QuadCut lays it all out on a single screen: four panes open at once, pick on the left, drop on the right; up to 6 tabs per pane; and hold one key to see any detail at 100%. It is also friendly to photos and AI art — select a file and it tells you shutter speed, ISO and aperture, and reads the model and prompt out of AI images too.

---

## Four panes, one screen

Switch between four, three or two panes at any time, and each pane can hold multiple tabs. Pick on the left, drop on the right — `Ctrl+X` / `Ctrl+V` between panes moves files, so you never bounce between two Explorer windows. Tabs can be dragged to reorder, dragged into another pane, or dragged into the sidebar to become a bookmark.

## Themes that ease eye strain

![The light green eye-care theme](docs/1.png)

Staring at the same pale grey all day is the most tiring part. Three palettes — light, dark and eye-care green — let you match the light in the room and your mood, so long culling and sorting sessions are easier on the eyes. Switching is instant, and the choice survives a restart.

## Quick focus check: hold Ctrl for 100%

![Hold Ctrl for a 100% view, with the photo's EXIF beside it](docs/2.png)

Checking focus across 30 burst shots? No need to suffer. Hold `Ctrl` over the preview and it snaps to 100% actual pixels; middle-click pins it so it stays after you let go. It is the most direct way to tell whether a shot is sharp.

No viewer needed: select a photo and the right side lists dimensions, camera body and lens, while the status bar shows shutter, ISO and aperture. RAW is supported; sort by capture time, show images only, and rotate JPEGs in place (tags only, no re-compression) all live in the menu.

## AI at a glance

![Model, sampler, steps and prompt of an AI image](docs/ai.png)

No need to open your AI app to check AI parameters: the model, sampler, steps, CFG and positive prompt that ComfyUI and A1111 / SD.Next write into PNG files appear the moment you select the file, with a button beside them to copy the whole thing. Looking for "how was that image made?" now takes a second; even a pure upscaling workflow tells you which upscaler it used.

---

## Batch rename

![Batch rename dialog](docs/4.png)

Select a few files and press `F2`; put `work###` in the template and you get `work001`, `work002`… You see a preview of the result first, and nothing happens until you confirm. Either all of them succeed, or none are touched.

## One click to enlarge

![Click the small dot in the top-right corner to maximise a pane](docs/6.png)

Suddenly need to concentrate on a single folder? Click to maximise and you get the room. Every pane carries a very subtle dot in its top-right corner: click it and that pane fills the whole work area while the others collapse into narrow strips showing just an icon; click the dot again, or click any strip, and everything returns exactly as it was before. When you are grinding through one folder among many, no layout changes and no remembering where you last dragged things.

## Bookmarks you can add or remove at will

![Sidebar entries can be added and removed freely](docs/8.png)

Pin the places you use to the sidebar and reach them in one click; hide the ones you don't need (Music, Videos, a particular drive) from the right-click menu, and bring them back with a single "show all" — hiding only affects the sidebar, never a folder on disk. The whole bar can also move to the right side of the window, taking its width, bookmarks and hidden items along.

## UI scaling that follows your monitor

![Automatic (4K at 120%) plus 100/120/150% options](docs/5.png)

New monitor, changed scaling, plugged into a projector — no digging through settings: the default "Auto" computes the right ratio for the current screen, and fixed 100% / 120% / 150% steps are there if you prefer. Text and icons stay crisp, and never shrink to a squint.

---

## Change the logo whenever

![Eight icon colour schemes](docs/31.png)

Tired of the same logo? Swap it to match your mood — from crisp Guanlan blue and pure black-and-white to red-blue, black-gold, purple-gold and rose. Eight colour schemes, and it is the program icon that changes, together with the title bar and taskbar.

## Seven interface languages

![Language menu](docs/7.png)

简体中文, 繁體中文, English, 日本語, 한국어, Français, Deutsch. The first run follows your system language; switch any time from the menu.

## Other conveniences

- **Bookmarks and right-click send**: right-click a place or bookmark → "Open in pane" and pick top-left / bottom-right, no dragging
- **Search** (`Ctrl+F`): the current folder plus all subfolders, with `*` `?` wildcards
- **Type-ahead**: type the first letters to jump to a file in the list
- **The address bar is a run box**: type `cmd` or `notepad` to launch it; a shortcut pointing at a folder opens in the pane on double-click
- **Peek at documents**: TXT (including GBK), the first page of a PDF, embedded thumbnails of PPTX / Word — without opening Office first
- **Refresh on return**: files copied in from elsewhere are there when you come back, saving an `F5`; after deleting a file, the arrow keys continue from where the selection is instead of jumping back to the top
- **Eject removable drives**: a button right next to USB sticks and external drives, no tray hunting
- **Single instance**: launching again brings the open window to the front instead of opening another one

---

## Download (1.8.3)

| Build | Size | Recommended system |
| --- | --- | --- |
| `quadCut.exe` (full) | ~70 MB | Windows 7 and above, no runtime install needed |
| `quadCut-portable.zip` (full) | ~68 MB | Same, just unzip and run |
| `quadCut-lite.zip` (lite) | ~7.6 MB | Windows 10 and above (.NET 6+ desktop runtime required) |

Direct download: [full quadCut.exe](https://github.com/dungeonlee/QuadCut-win/releases/latest/download/quadCut.exe) · [portable zip](https://github.com/dungeonlee/QuadCut-win/releases/latest/download/quadCut-portable.zip) · [lite zip](https://github.com/dungeonlee/QuadCut-win/releases/latest/download/quadCut-lite.zip)
If Windows shows "Windows protected your PC" on first launch, click "More info → Run anyway".

---

## License

Copyright © 2026 Michael. All rights reserved.

Free to use, including demos and everyday use in commercial projects.

Free to redistribute unmodified, but not for a fee, and not as a product for sale.

No modification, decompilation or reverse engineering, and no redistribution of modified versions.

Provided "as is", without warranty; the author is not liable for damage caused by use.

Full terms in the in-app LICENSE (the `LICENSE` / `LICENSE.txt` in the release package).

---

## Another platform

**macOS version** → https://github.com/dungeonlee/QuadCut

Windows project home → https://github.com/dungeonlee/QuadCut-win
