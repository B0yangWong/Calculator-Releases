# 更新记录 / Changelog

## v1.1.0

新增物理计算和离线公式表，下载包为 1.1.0 / build 10。仍只公开应用下载和文档，源码不公开。

- 去掉原来的大标题栏，保留紧凑的模式选择与设置入口；科学键盘可按需展开，窗口缩放时调整布局。
- 物理模式支持输入等式、代入已知量的数值和单位，在支持范围内求一个未知实数标量，并检查量纲和换算兼容单位。
- 大写 $E$ 与自然常数 $e$ 分开；$c$ 默认为真空光速，$h$、$\alpha$ 等常数均允许修改。
- 内置 100 条物理公式：经典力学 28、分析力学 22、量子力学 24、热力学 26；中英文搜索，按分类查找。
- 公式采用数学排版，鼠标悬停或键盘聚焦显示“复制”和“添加到计算”。添加新建一行，不覆盖当前草稿或已有变量定义。
- 每条公式附变量含义、推荐单位、适用条件和来源；来源仅在用户点击时由外部浏览器打开。
- 科学与物理记录分开保存；物理变量在工作区内共享，修改后重算相关物理记录。正常重开保留模式、参数、单位和公式表关联。
- 修复含下标的变量在公式编辑后被拆成多个量的问题，以及对话框焦点与键盘操作问题。

本次验证通过 77 项计算、构建与许可测试，114 项实际 WebKit 界面检查，13 项原生窗口检查，8 项物理布局检查，5 项公式表与原生剪贴板检查，以及 7 项本机保存检查。测试环境是 Apple Silicon Mac、macOS 27；macOS 14 实机、Intel 和独立全新 Mac 首次打开未验证。

77 条标量关系可在现有单未知量求解范围内代入；23 条含微积分、向量、算符或不等式的公式只作参考，不自动求解。并非每个变量都能反求，物理条件与多解选择需自行判断。温度目前仅支持开尔文，不提供摄氏或华氏偏移换算。下载包仍只有 arm64，未经过 Developer ID 签名或 Apple 公证。具体见[使用说明](README.zh-CN.md)。

### English

Adds physics calculations and an offline formula library in version 1.1.0 / build 10. Only app downloads and documentation are public; application source remains private.

- Removes the large header, keeps compact mode and settings controls, and makes the scientific keyboard collapsible. Layout adapts as the window is resized.
- Physics mode accepts equations with known values and units, solves supported single-unknown real-scalar equations, checks dimensions, and converts compatible units.
- Preserves uppercase $E$ separately from Euler's constant $e$. The default $c$ is the speed of light in vacuum; constants including $h$ and $\alpha$ can be overridden.
- Includes 100 formulas: 28 classical mechanics, 22 analytical mechanics, 24 quantum mechanics, and 26 thermodynamics, with English / Chinese search and category browsing.
- Typeset formula cards reveal Copy and Add to calculation on hover or keyboard focus. Adding creates a new row without replacing the current draft or existing variable definitions.
- Entries include variable meanings, suggested units, applicability notes, and sources. Source pages open in an external browser only on request.
- Keeps scientific and physics records separate; shared physics variable edits recalculate relevant physics history. Mode, parameters, units, and formula-library associations survive a normal relaunch.
- Fixes splitting of subscripted variables after formula editing, and improves dialog focus and keyboard operation.

Checks pass: 77 calculation, build, and license tests; 114 real WebKit UI checks; 13 native-window checks; 8 physics-layout checks; 5 formula-library and native-clipboard checks; and 7 local-persistence checks. Tested on an Apple Silicon Mac with macOS 27; physical macOS 14 devices, Intel, and a separate clean-Mac first launch remain unverified.

77 scalar relations support substitution within the current single-unknown solver's limits; 23 calculus, vector, operator, or inequality entries are reference-only and not solved automatically. Not every variable can be solved for; applicability and root selection remain the user's responsibility. Temperature currently supports kelvin only, without Celsius / Fahrenheit offset conversion. The download remains arm64 only, without Developer ID signing or Apple notarization. See [documentation](README.md).

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

本版仅有 arm64 下载包；未经过 Apple Developer ID 签名或公证。一般计算为浮点数、显示 15 位有效数字。绘图、求导和积分尚未实现。具体限制见 [使用说明](README.zh-CN.md#隐私与当前限制)。

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

This release is arm64 only and is not Developer ID signed or Apple notarized. General calculations use floating point and display 15 significant digits. Graphing, derivatives, and integration are not implemented. See [limitations](README.md#privacy-and-limits).
