<h1 align="center">Calculator</h1>

<p align="center"><img src="docs/app-icon.png" width="96" alt="Calculator 黑洞主题图标"></p>

<p align="center"><strong>为 macOS 制作的科学计算器，让你始终可以修改原来的算式。</strong></p>

<p align="center">乘方、分数、科学计数法，都在正在输入的原式里完成。</p>

<p align="center">
  <a href="https://github.com/B0yangWong/Calculator-Releases/releases/latest">下载</a> |
  <a href="#功能">功能</a> |
  <a href="PRIVACY.md">隐私说明</a> |
  <a href="README.md">English</a>
</p>

---

输入 `^` 就写乘方，输入 `/` 就写上下分数，输入 `1.6e-25` 就写科学计数法。继续在原式中编辑，随时看预览结果，按 Enter 保存一行。以前的算式也能修改；更改变量或前面的计算，后续相关结果会重新计算。

本仓库只公开应用下载、使用说明和示例截图，不公开应用源码。Calculator 是独立应用，不是 Desmos 官方产品，也没有嵌入其网站或专有代码。

**v1.0.0：**需要 Apple Silicon Mac 和 macOS 14 或更高版本。在 macOS 27 上验证过，未在 macOS 14 实机验证，不提供 Intel 包。本版采用本机临时签名，没有 Apple Developer ID 签名，也未经过 Apple 公证，首次打开可能被系统拦截。下载前请阅读[安装与打开](#安装与打开)。

## 功能

| 功能 | 可以做什么 |
| --- | --- |
| 直接编辑公式 | 输入乘方、根式和上下分数，从上标或分母返回后接着编辑原式。 |
| 科学计数法与自然常数 | `e-25` 表示 10⁻²⁵，`1.6e-25` 表示 1.6 × 10⁻²⁵，`10*e*3` 中的 e 表示自然常数。 |
| 科学函数 | 四则运算、绝对值、百分数、阶乘、π、ans、三角及反三角、双曲及反双曲、对数、组合、排列、取整、最大公约数、最小公倍数和余数。 |
| 变量与自定义函数 | 定义 `a=5` 或单参数函数 `f(x)=x^2+1`，在后续算式中重复使用。 |
| 列表与统计 | 逐元素运算，以及平均数、中位数、总和、标准差、方差等统计函数。 |
| 复数与矩阵 | 按需开启复数模式，使用常用矩阵运算。 |
| 可以继续修改的计算记录 | 编辑历史、重算相关结果、撤销、重做、复制、粘贴和导出。 |
| 中英文界面 | 在设置中切换界面和菜单语言、主题与字号。正常重开后保留设置和未提交输入。 |
| 离线使用 | 不需要账号，没有遥测上传、云同步或自动更新检查。 |

## 界面预览

截图来自实际应用，使用隔离的示例算式，不包含私人历史。

<p align="center"><img src="docs/screenshots/calculator-zh.png" width="1080" alt="Calculator 中文界面的分数、科学计数法和实时预览结果"></p>

<details>
<summary>英文界面</summary>

<p align="center"><img src="docs/screenshots/calculator-en.png" width="1080" alt="Calculator 英文界面"></p>

</details>

## 直接输入公式

| 输入 | 含义 |
| --- | --- |
| `2^3` | 输入可编辑上标，结果为 8 |
| `(2+3)/2` | 输入可编辑上下分数，结果为 2.5 |
| `e-25` | 10 的 −25 次方 |
| `1.6e-25` | 1.6 × 10 的 −25 次方 |
| `10*e*3` | e 为自然常数，结果约为 81.5484548537714 |
| `(e)-25` | 自然常数 e 减去 25 |

浅色结果是按 Enter 前的预览，保存后颜色加深。上标或分母输入完后按右箭头回到原式；上标也可以按空格退出。科学计数法指数后的加减乘除会自动回到原式。

默认使用角度制，计算三角函数前请确认“角度 / 弧度”。百分号表示除以 100，不采用部分商用计算器根据上下文计算百分比的规则。

## 安装与打开

1. 从 [v1.0.0 发布页](https://github.com/B0yangWong/Calculator-Releases/releases/tag/v1.0.0) 下载 [Calculator-1.0.0-macOS-arm64.zip](https://github.com/B0yangWong/Calculator-Releases/releases/download/v1.0.0/Calculator-1.0.0-macOS-arm64.zip)。新版本可在[最新发布页](https://github.com/B0yangWong/Calculator-Releases/releases/latest)查看。
2. 解压后把 `Calculator.app` 拖入“应用程序”。替换旧版本前先正常退出，不需要安装 Xcode、登录账号或另装运行环境。
3. 打开应用。若被 macOS 拦截，只在信任下载来源、确认文件未被篡改并愿意承担风险时继续。先尝试打开，再进入“系统设置 → 隐私与安全性”，选择“仍要打开”并确认，具体见 [Apple 官方说明](https://support.apple.com/en-us/102445)。受管理的设备可能没有这一选项。若系统提示文件已损坏或会损害电脑，请停止打开并反馈，不要关闭系统安全保护。
4. 用 `Command + ,` 打开设置，选择中文或 English、主题与字号，计算前检查角度模式。

发布页附带 `SHA256SUMS.txt`，可与下载 ZIP 的校验值比较，检查文件是否在下载中损坏。校验值一致不等于确认发布者身份、证明应用安全或得到 Apple 认可。

GitHub 自动提供的 `Source code (zip)` 和 `Source code (tar.gz)` 只有本仓库的公开文档、示例图片和第三方说明，不含应用源码，也不是安装包。请下载带版本号的应用 ZIP。

## 常用操作

| 操作 | 快捷键或方式 |
| --- | --- |
| 保存当前计算 | `Enter` |
| 离开上标或分母 | 右箭头；上标也可按空格退出 |
| 回到输入行 | `Command + N` |
| 撤销 / 重做 | `Command + Z` / `Command + Shift + Z` |
| 复制 / 粘贴 | `Command + C` / `Command + V` |
| 导出历史 | `Command + Shift + E` |
| 清除历史及未提交输入 | `Command + Shift + Delete` 或“清除全部”；当前会话中可以撤销 |
| 打开设置 | `Command + ,` 或设置按钮 |
| 打开输入说明 | `Command + /` 或帮助按钮 |

历史和未提交输入会保存在本机。普通运行有单实例保护，防止不同应用进程同时写同一份历史；强制退出或断电不等同于正常退出。

## 隐私与当前限制

历史及设置保存在 `~/Library/Application Support/FormulaDesk/state.json`，保留的目录名不影响应用名称。记录并未由应用加密。复制、粘贴和导出由用户触发，系统备份和诊断服务另受 macOS 设置控制。保存和删除细节见[隐私说明](PRIVACY.md)。

- 一般计算使用浮点数，显示 15 位有效数字，不是任意精度计算器。纯数字有理数算式有精确分数路径；结果的分数 / 小数切换也仅适用于这类算式。
- 最多保存 250 行历史；列表最多 1024 项；阶乘最大为 170；矩阵最大为 32 × 32。
- 列表范围写法、列表索引、多参数自定义函数和递归函数未实现。
- 绘图、求导和积分尚未实现，也不保证与 Desmos 的所有行为一致。
- 测试无法覆盖所有算式和全部 Mac。较旧的支持系统与全新 Mac 的首次打开仍需实机验证。重要计算请独立核对，特别是单位、角度模式和精度。

更新需手动下载。正常退出后替换应用，不要删除其 Application Support 数据目录；版本变化见[更新记录](CHANGELOG.md)。

[反馈问题](https://github.com/B0yangWong/Calculator-Releases/issues/new/choose)时，请提供算式、实际和期望结果、角度模式、应用版本及系统版本。[功能建议](https://github.com/B0yangWong/Calculator-Releases/issues)也可以提交。内容会公开，不要上传私人历史或敏感截图。

## 第三方组件

MathLive 提供公式编辑，mathjs 及其依赖支持计算。第三方说明及许可证随下载包附带，仓库中也提供[第三方说明](THIRD_PARTY_NOTICES.txt)及 [ThirdPartyLicenses](ThirdPartyLicenses/) 副本。本下载仓库不为 Calculator 应用或图标授予开源许可。
