# 隐私说明 / Privacy

适用版本 / Applies to: Calculator v1.1.0

## 中文

Calculator 的计算和公式编辑在本机完成。应用不要求登录，不包含广告、分析追踪、遥测上传或云同步，也没有自动更新检查。

### 本机数据

应用会自动保存科学和物理模式的计算历史、尚未提交的输入、模式选择及设置，以便重新打开后恢复。物理模式还会保存变量数值、单位、常数修改、结果显示单位，以及从公式表添加的条目关联。这些信息只保存在本机，不会上传。主要数据文件位于：

`~/Library/Application Support/FormulaDesk/state.json`

`FormulaDesk` 是保留的数据目录名，不影响应用显示名称。语言选择还会在 macOS 的应用偏好设置中缓存。保存文件是明文，应用不单独加密；能够访问该账户文件的人或程序可能读取它。系统备份也可能包含这些文件。

“清除全部”清除当前模式的计算历史及未提交输入；当前会话中仍可撤销这一操作。它不表示删除另一模式的记录、清空物理变量定义，或抹除系统备份、已导出文件和已有剪贴板内容。要删除全部本机数据，先退出应用，再删除上述数据目录；应用偏好设置中的语言缓存是独立的。删除前请自行备份需要的记录。

### 剪贴板与导出

复制、剪切、粘贴和导出由用户操作触发，公式表中的“复制”也遵循这一规则。“添加到计算”只把公式加入本机计算记录，不上传数据。应用不会持续监视剪贴板；复制内容会进入 macOS 剪贴板，导出内容会保存到用户选择的位置。其他程序、系统通用剪贴板或备份工具可能处理这些内容，取决于你的系统设置。

### 公式来源链接

内置公式、搜索、参数代入和单位换算都在本机完成。公式来源不会自动下载或后台访问。只有用户点击来源链接时，应用才把 HTTPS 网页交给外部浏览器打开；不会把算式、变量数值、单位或历史作为参数发送给来源网站。浏览器及网站可能按各自政策处理访问记录、IP 地址或 Cookie，应用的离线计算不等于这些外部访问也离线。

### 系统服务与诊断

应用没有开发者运营的数据接收服务器，也不会主动上传计算记录。异常发生时，应用可能把错误描述、资源路径或技术诊断写入 macOS 系统日志；不要在算式或错误报告中输入秘密。macOS 自身的安全检查、崩溃报告、诊断共享或备份可能由系统设置控制，不能把应用离线运行理解为整个操作系统完全不联网。

GitHub 下载、浏览仓库及提交 Issues 是独立的在线行为，由 GitHub 自身的隐私政策管理。问题反馈会公开显示，请不要提交私人历史、个人资料或未经处理的敏感截图。

## English

Calculator evaluates and edits expressions locally. It requires no account and includes no ads, analytics tracking, telemetry upload, cloud sync, or automatic update check.

### Local data

The app autosaves scientific and physics history, unsubmitted expressions, mode choice, and settings for restoration on launch. Physics mode also stores variable values, units, constant overrides, result-display units, and associations with added formula-library entries. These records stay locally and are not uploaded. The main file is:

`~/Library/Application Support/FormulaDesk/state.json`

`FormulaDesk` is the retained data-directory name. The language preference is also cached in macOS application preferences. These files have no application-level encryption. Anyone or any program able to access your account's files may read them. System backups may contain copies.

Clear All removes the current mode's history and unsubmitted expression; this can still be undone during the current session. It does not delete the other mode's history, reset physics variable definitions, or erase system backups, exported files, or existing clipboard contents. To remove all local data, quit the app and delete the directory above. The cached language preference is separate. Back up any history you want to keep first.

### Clipboard and export

Copy, cut, paste, and export are user-triggered, including Copy in the formula library. Add to calculation only inserts a formula into the local worksheet; it does not upload data. The app does not continuously monitor the clipboard. Copied data enters the macOS clipboard; exported data goes to the location you choose. Other apps, Universal Clipboard, or backup tools may handle it according to your system settings.

### Formula-source links

Built-in formulas, search, parameter substitution, and unit conversion run locally. Sources are not downloaded or visited in the background. Only clicking a source link opens its HTTPS page in an external browser; the app does not attach your equation, variable values, units, or history to that request. Your browser and the website may handle access records, IP addresses, or cookies under their own policies. Offline calculation does not make those external visits offline.

### System services and diagnostics

The developer operates no data-collection server for this app, and the app does not actively upload calculation history. Errors may write descriptions, resource paths, or technical diagnostics to macOS system logs. Do not place secrets in expressions or bug reports. macOS security checks, crash reporting, diagnostic sharing, and backups are separate system-controlled activities. An offline app does not imply an entirely offline operating system.

GitHub downloads, repository browsing, and issue reports are separate online activities governed by GitHub's privacy policy. Issues are public: do not submit private history, personal information, or unredacted sensitive screenshots.
