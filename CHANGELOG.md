# 更新记录 / Changelog

## v1.0.0

首次公开下载版，仅发布应用下载包和文档，源码不公开。

- Apple Silicon Mac 离线科学计算器，支持可编辑上标、分数与科学计数法。
- 兼顾 `e-25` 科学计数法与 `10*e*3` 中的自然常数。
- 三角、对数、统计、变量、单参数函数、可选复数和矩阵计算。
- 可修改计算历史、联动重算、撤销、重做、复制粘贴、导出与本机自动保存。
- 中英文界面和菜单、主题与字号设置。
- 黑洞主题图标；输入中的结果用浅色预览，保存后加深显示。
- 修复长公式保存后重新打开时的恢复问题。
- 普通运行采用单实例保护，避免多个窗口进程同时写入同一份历史。

本版仅有 arm64 下载包；未经过 Apple Developer ID 签名或公证。一般计算为浮点数、显示 15 位有效数字。绘图、求导和积分尚未实现。具体限制见 [使用说明](README.md#当前边界)。

### English

First public download release. Only app downloads and documentation are published; the source code is not public.

- Offline scientific calculator for Apple Silicon, with editable exponents, fractions, and scientific notation.
- Distinguishes `e-25` notation from Euler's constant in `10*e*3`.
- Trigonometry, logarithms, statistics, variables, single-parameter functions, optional complex numbers, and matrices.
- Editable history, dependent-result recalculation, undo, redo, copy, paste, export, and local autosave.
- Chinese / English interface and menus, themes, and text-size settings.
- Black-hole icon; pale live-preview results become darker when saved.
- Fixes restoration of saved long expressions after relaunch.
- Single-instance protection during normal operation prevents separate app processes from writing to the same history simultaneously.

This release is arm64 only and is not Developer ID signed or Apple notarized. General calculations use floating point and display 15 significant digits. Graphing, derivatives, and integration are not implemented. See [limitations](README.en.md#limits).
