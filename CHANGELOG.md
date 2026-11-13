# 版本升级记录 · Changelog

每条先中文、后英文，两段一一对应，条目数相同。

Each release lists the same items twice — Chinese first, then English. The two lists map one to one.

---

## 1.8.4 · 2026-11-13

**中文**

- 只有一个格子处于激活态：其余格子里当前标签显示为灰色，四格标签不再一起高亮
- 新建标签排在最后，路径取**本格当前激活的那个标签**（视图、排序、预览状态也跟着它）
- 标签图标跟着文件夹走：给文件夹换过图标（`desktop.ini` 里的 `IconResource`）的，标签上直接显示那个图标；没换过的仍然用主题色的小文件夹
- 复制/移动的进度卡片新增「取消」按钮，可以中途停下；已经写进去的半截文件自动删掉
- 小图标视图直接显示缩略图，不用先切到缩略图再切回来；只对有缩略图的类型批量取图
- 详细列表的列顺序改为 名称 / 大小 / 修改日期 / 类型，去掉那个没有意义的空占位列
- 放大某一格后，被压小的格子合并成**同一条**竖条，压几个就在条内纵向分几块（原来是并排几条细竖条）
- 修 AI 提示词读错：提示词优化 / 翻译类节点（✨提示词优化 等）原来显示的是它加工后的英文译文，现在优先取人写的原文；纯展示节点（easy showAnything 等）的缓存文本不再被当成提示词
- 内存占用大改：全尺寸图缓存从「每格 4 张」改成全程共用一份、按字节封顶；原图预解码从「选中就解」改成停住 400ms 才解、全局串行、换选中立刻取消；缩略图缓存从「满 4000 条清空」改成按字节淘汰；预览栏取图从 520 DIP 降到 300 DIP（显示区只有 268 DIP，肉眼看不出差别）；16 位 PNG 不再按 8 字节/像素解码
- 实测（60 张 6000×4000 照片，四格分别翻 25 / 10 / 10 / 10 张）：峰值从 1052 MB 降到 476 MB，稳定占用从 775 MB 降到 390 MB
- 发布包改名带上版本与架构：`QuadCut-1.8.4-win-x64.exe` / `-portable.zip` / `-lite.zip`，32 位系统的用户一眼就知道下不了，不用白下 70 MB
- 配置文件解析失败时先留一份 `config.broken-时间戳.json` 再重置，不再静默覆盖掉用户那份
- 版本号升到 1.8.4

**English**

- Only one pane is active now: in the other panes the current tab turns grey, instead of every tab strip lighting up at once
- New tabs are appended at the end and take the path of the **currently active tab** in that pane (view, sorting and preview state follow it too)
- Tab icons follow the folder: if a folder has a custom icon (`IconResource` in `desktop.ini`), the tab shows that icon; folders without one keep the small theme-coloured folder
- The copy/move progress card has a Cancel button: a transfer can be stopped midway and the partially written file is removed
- Small-icon view shows thumbnails right away, no need to switch to thumbnail view and back; images are fetched in a batch, only for types that have thumbnails
- Details view column order is now Name / Size / Date modified / Type, and the meaningless empty placeholder column is gone
- When one pane is maximized, the compressed panes now share a **single** vertical strip, split into one block per pane (previously they were several thin side-by-side strips)
- Fixed wrong AI prompts: prompt expander / translator nodes (✨ Prompt Optimize and the like) used to show their translated English output; now the original text you typed is preferred, and cached text from display-only nodes (easy showAnything etc.) is no longer taken as the prompt
- Memory rework: the full-size image cache is now one shared pool with a byte budget instead of 4 images per pane; pre-decoding waits 400 ms and runs one at a time globally, cancelled as soon as the selection changes; the thumbnail cache evicts by bytes instead of "clear at 4000 entries"; preview thumbnails are fetched at 300 DIP instead of 520 (the visible area is only 268 DIP, so no difference to the eye); 16-bit PNGs are no longer decoded at 8 bytes per pixel
- Measured (60 photos of 6000×4000, arrowing 25 / 10 / 10 / 10 through four panes): peak down from 1052 MB to 476 MB, steady state down from 775 MB to 390 MB
- Release assets now carry version and architecture: `QuadCut-1.8.4-win-x64.exe` / `-portable.zip` / `-lite.zip`, so 32-bit users can tell at a glance and do not waste a 70 MB download
- When the config file fails to parse, a `config.broken-<timestamp>.json` copy is kept before resetting, instead of silently overwriting the user's settings
- Version bumped to 1.8.4

---

## 1.8.3 · 2026-11-07

**中文**

- 修好部分 PNG 的 AI 图读不出参数：ComfyUI 的 tEXt / zTXt / iTXt 文本块全部读取，prompt 里的 `NaN` / `Infinity` 不再让整份解析失败，没有采样器的工作流回退到 workflow 节点
- 支持 A1111 的 `parameters` 文本块
- 格子右上角小圆点放大 / 还原，其余格子收成图标竖条；修好拖动分隔条后缩放窗口露出黑区的问题
- README 出七种语言版本（简体 / 繁體 / 英 / 日 / 韩 / 法 / 德），标题与「致敬 Q-Dir」使用金色 SVG

**English**

- Fixed AI parameters failing to read on some PNG files: all ComfyUI tEXt / zTXt / iTXt chunks are read, `NaN` / `Infinity` inside the prompt no longer break parsing, and workflows without a sampler fall back to the workflow node
- Added support for the A1111 `parameters` text block
- The dot at a pane's top-right corner maximizes / restores it and squeezes the other panes into icon strips; fixed black areas appearing when resizing the window after dragging a splitter
- README published in seven languages (Simplified Chinese, Traditional Chinese, English, Japanese, Korean, French, German), with gold SVG headings

---

## 1.8.2 · 2026-11-07

**中文**

- 方向键续选、TXT / PDF / PPTX 预览、切回窗口自动刷新
- 删除后选中落在补位上来的那一项；同目录粘贴生成「副本」
- 快捷栏可以整条贴到窗口右侧
- 状态栏显示当前磁盘剩余空间
- 快捷方式去掉 `.lnk` 后缀与系统箭头；100% 查看原图定名「焦点快查」

**English**

- Arrow-key continued selection, TXT / PDF / PPTX previews, auto-refresh when switching back to the window
- After a delete, selection lands on the item that slid up into place; pasting in the same folder creates a "copy"
- The shortcut bar can be docked to the right edge of the window
- Status bar shows the free space of the current drive
- Shortcuts drop the `.lnk` extension and get the system arrow; the 100% view is named "Quick focus check"
