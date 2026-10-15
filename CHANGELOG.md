# 更新记录 / Changelog

## v1.1.3

修复显示、点击响应和物理数值边界，下载包为 1.1.3 / build 13。包含此前仅在本机使用的 1.1.1 和 1.1.2 修复；上一个公开版本 v1.1.0 继续保留。仍只公开下载包和文档，不公开应用源码。

- 修复正常计算结果在重复计算、增加输入位数时被误用错误样式的问题；结果与算式同字号，未提交的预览保留浅色。
- “使用结果”明确插入当前草稿，避免编辑器焦点延迟时插入错误位置或看似没有响应。
- 修复保存后撤销恢复非空草稿时，重做误走文本编辑路径的问题；覆盖科学 / 物理模式、公式表添加及后续文字编辑。
- 科学 / 物理模式保留各自已加载的历史编辑器，不再每次切换都重建；键盘保留，并拒绝旧编辑器迟到的焦点事件。首次加载长历史仍有成本。
- 原生窗口允许后台第一次点击传给按钮；可信后台鼠标事件与原生首击策略分开验证，未把它们当作完整的人手点击与自动激活认证。
- 构建时把旧版应用备份为 ZIP，而不是在构建目录保留额外的可启动应用。
- 修复支持范围内的分数阶根反向求解漏负根，以及接近重根时误判解数的问题；不以残差容差合并可区分的根。
- 输入转为可编辑数学排版时保留原始数字文本，避免粘贴后先丢失小数末位而绕过精度检查；覆盖实际编辑器的输入往返。
- 输入舍入、极端下溢和多项式系数消去等无法可靠认证的情况明确拒绝，避免把它们报告为零、精确单根或无解。通常显示 15 位有效数字，必要时以最多 17 位区分近根，不等于任意精度。

2026-10-15 的最终构建通过 202 项计算、回归、构建与许可测试，114 项真实 WebKit 检查，24 项原生交互，31 项扩展验收，13 项原生窗口、8 项物理布局、5 项公式表 / 原生剪贴板及 7 项本机保存检查。202 项中包含 50 项独立物理标准算例和 42 项物理边界 / 输入往返回归；128 项物理 / 公式定向测试是其中子集，不额外相加。包完整性、签名完整性、版本与 arm64 架构已核对。

满历史仍有明显停顿。250 行时，到下一次渲染机会的记录为首次物理加载约 1.17 秒、热切换科学约 0.19–0.34 秒、物理约 0.52–0.77 秒；不是人手点击到画面完成的测量，不能承诺瞬时切换。方法见[验证说明](VALIDATION.md)。物理模式不是任意方程或联立方程求解器，量纲一致不证明物理正确，多解需自行选择。测试主机是 arm64、macOS 27.0；macOS 14 只是最低构建目标。未经过 Apple Developer ID 签名或公证，独立全新 Mac 首次安装仍待验证。

### English

Maintenance release 1.1.3 / build 13 fixes display, click response, and physics numerical boundaries. It includes the fixes previously used locally in 1.1.1 and 1.1.2; the previous public v1.1.0 release remains available. Only downloads and documentation are published, not application source.

- Fixes a numeric result incorrectly receiving the error style after recomputation or additional input. Results retain the expression's text size; unsubmitted previews stay pale.
- Makes Use result explicitly insert into the current draft, avoiding delayed-focus insertion into the wrong editor or an apparently ignored click.
- Fixes Redo taking the text-edit path after Undo restores a nonempty draft from a committed calculation; covers both modes, formula-library additions, and later text edits.
- Retains each mode's loaded history editors instead of rebuilding them on every switch, keeps the keyboard in place, and rejects stale editor-focus events. The initial load of a long history still has a cost.
- Allows the first background click to reach native-window buttons. Trusted background-pointer delivery and the native first-mouse policy were checked separately, not as a complete human click-and-activation certification.
- Stores build-time app backups as ZIP archives instead of leaving additional launchable app bundles in build folders.
- Fixes missing negative roots in supported fractional-root inversions and incorrect near-repeated-root classification. Distinguishable roots are not merged using a residual tolerance.
- Preserves original numeric text through editable-math conversion so a pasted decimal is not shortened before precision checks; regressions include editor input round trips.
- Rejects unreliable cases involving input rounding, extreme underflow, or lost polynomial coefficients instead of certifying zero, an exact root, or no solution. Results normally display 15 significant digits; up to 17 digits may distinguish nearby roots, not provide arbitrary precision.

The final build passed checks on 2026-10-15: 202 calculation, regression, build, and license tests; 114 real WebKit checks; 24 native interactions; 31 extended acceptance checks; 13 native-window checks; 8 physics-layout checks; 5 formula-library / native-clipboard checks; and 7 local-persistence checks. The 202 tests include 50 independent physics examples and 42 physics-boundary / input-round-trip regressions. The 128-test physics / formula subset is not an additional total. Package integrity, signature integrity, version, and arm64 architecture were checked.

Full histories still pause noticeably. At 250 rows, times to a later frame opportunity were about 1.17 seconds for the first Physics load, 0.19–0.34 seconds for warm Scientific switches, and 0.52–0.77 seconds for warm Physics switches. These are not physical click-to-paint measurements or a promise of instant switching. See [Validation Scope](VALIDATION.md) for methods. Physics solving is not arbitrary or simultaneous equation solving; dimensions do not prove physical validity, and root selection remains the user's responsibility. The test host is arm64 with macOS 27.0; macOS 14 is a minimum build target. The app is not Developer ID signed or Apple notarized. A separate clean-Mac first install remains unverified.

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
