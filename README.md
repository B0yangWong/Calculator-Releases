<h1 align="center">Calculator</h1>

<p align="center"><img src="docs/app-icon.png" width="96" alt="Calculator black-hole app icon"></p>

<p align="center"><strong>A native macOS scientific calculator that keeps your original expression editable.</strong></p>

<p align="center">Powers, fractions, and scientific notation, without leaving the expression you started.</p>

<p align="center">
  <a href="https://github.com/B0yangWong/Calculator-Releases/releases/latest">Download</a> |
  <a href="#features">Features</a> |
  <a href="PRIVACY.md">Privacy</a> |
  <a href="README.zh-CN.md">中文说明</a>
</p>

---

Type `^` to build a power, `/` to build a stacked fraction, or `1.6e-25` for scientific notation. Keep working in the same expression, see a live result, and press Enter to save it. Earlier rows remain editable, so changing a variable or calculation updates the results that follow.

This repository contains downloads, documentation, and demo images. Application source is not published here. Calculator is an independent app, not a Desmos product, and does not embed its website or proprietary code.

**v1.0.0:** Apple Silicon Macs, macOS 14 or later. Tested on macOS 27, not on a physical macOS 14 device. No Intel build. The app is ad-hoc signed, without Developer ID signing or Apple notarization; macOS may block the first launch. See [Install and Open](#install-and-open) before proceeding.

## Features

| Feature | What you can do |
| --- | --- |
| Editable mathematical input | Type powers, roots, and fractions directly; return from an exponent or denominator to continue the original expression. |
| Scientific notation and natural e | Use `e-25` for 10⁻²⁵, `1.6e-25` for 1.6 × 10⁻²⁵, and `10*e*3` for Euler's constant. |
| Scientific functions | Arithmetic, absolute values, percentages, factorials, π, ans, trigonometric and hyperbolic functions and their inverses, logarithms, combinations, permutations, rounding, gcd, lcm, and modulo. |
| Variables and functions | Define `a=5` or a single-parameter function such as `f(x)=x^2+1`, then reuse it in later rows. |
| Lists and statistics | Use element-wise operations, mean, median, sum, standard deviation, variance, and related functions. |
| Complex numbers and matrices | Enable complex-number mode when needed and use common matrix operations. |
| A reusable worksheet | Edit earlier rows, recalculate dependent results, undo and redo, copy and paste, or export history. |
| English and Chinese | Change interface and menu language, theme, and text size in Settings. Preferences and unfinished input survive a normal relaunch. |
| Offline operation | No account, telemetry upload, cloud sync, or automatic update check. |

## Preview

These screenshots show the actual app with isolated example calculations, not personal history.

<p align="center"><img src="docs/screenshots/calculator-en.png" width="1080" alt="Calculator with editable fractions, scientific notation, and a live result preview"></p>

<details>
<summary>Chinese interface</summary>

<p align="center"><img src="docs/screenshots/calculator-zh.png" width="1080" alt="Calculator in Simplified Chinese"></p>

</details>

## Type Expressions Directly

| Input | Meaning |
| --- | --- |
| `2^3` | Editable exponent; result: 8 |
| `(2+3)/2` | Editable stacked fraction; result: 2.5 |
| `e-25` | 10 to the power of −25 |
| `1.6e-25` | 1.6 × 10 to the power of −25 |
| `10*e*3` | e is Euler's constant; result: approximately 81.5484548537714 |
| `(e)-25` | Euler's constant minus 25 |

A pale result is the live preview before Enter; saved results appear darker. After entering an exponent or denominator, use the right arrow to continue the main expression. Space also exits an exponent. Operators after a scientific-notation exponent return to the main expression automatically.

The default angle mode is degrees. Check Degrees / Radians before using trigonometric functions. Percent means division by 100, not the context-dependent percentage behavior of some commercial calculators.

## Install and Open

1. Download [Calculator-1.0.0-macOS-arm64.zip](https://github.com/B0yangWong/Calculator-Releases/releases/download/v1.0.0/Calculator-1.0.0-macOS-arm64.zip) from the [v1.0.0 release](https://github.com/B0yangWong/Calculator-Releases/releases/tag/v1.0.0), or find a newer build in [Latest Release](https://github.com/B0yangWong/Calculator-Releases/releases/latest).
2. Extract the archive and move `Calculator.app` into Applications. Quit an older copy normally before replacing it. No Xcode, account, or additional runtime is required.
3. Open the app. If macOS blocks it, only proceed if you trust the download and are confident it has not been altered. After the first attempt, use System Settings → Privacy & Security → Open Anyway and confirm, following [Apple's instructions](https://support.apple.com/en-us/102445). This option may not be available on a managed Mac. If macOS says the app is damaged or will harm your computer, stop and report it. Do not disable system security checks.
4. Open Settings with `Command + ,` to choose 中文 or English, a theme, and text size. Check the angle mode before calculating.

The release includes `SHA256SUMS.txt`. Compare its value with the downloaded ZIP to check for download corruption. A matching checksum does not verify publisher identity, prove the app is safe, or indicate Apple approval.

GitHub's `Source code (zip)` and `Source code (tar.gz)` contain this repository's public documentation, demo images, and notices. They are not app installers and do not contain the Calculator application source.

## Everyday Controls

| Action | Shortcut or interaction |
| --- | --- |
| Save the current calculation | `Enter` |
| Leave an exponent or denominator | Right arrow; Space also exits an exponent |
| Focus the input row | `Command + N` |
| Undo / redo | `Command + Z` / `Command + Shift + Z` |
| Copy / paste | `Command + C` / `Command + V` |
| Export history | `Command + Shift + E` |
| Clear history and unfinished input | `Command + Shift + Delete`, or Clear All; can be undone during the current session |
| Open Settings | `Command + ,` or the settings button |
| Open the input guide | `Command + /` or the help button |

The app saves history and unfinished input locally. Normal operation uses a single-instance guard to prevent separate app processes from writing to the same history. Force quitting or losing power is not equivalent to a normal quit.

## Privacy and Limits

History and settings stay in `~/Library/Application Support/FormulaDesk/state.json`; the retained directory name does not affect the app's display name. These records are not encrypted by the app. Copy, paste, and export are user-triggered. macOS backups and diagnostic services are separate. See [Privacy](PRIVACY.md) for details, including deletion.

- General calculations use floating-point arithmetic and display 15 significant digits. This is not an arbitrary-precision calculator. Purely numeric rational expressions have an exact-fraction path; fraction / decimal result switching is limited to those expressions.
- History: up to 250 rows. Lists: up to 1024 items. Factorials: up to 170. Matrices: up to 32 × 32.
- List ranges, list indexing, multi-parameter custom functions, and recursive functions are not implemented.
- Graphing, derivatives, and integration are not available yet. Full behavioral parity with Desmos is not promised.
- Tests cannot cover every expression or every supported Mac. Older supported macOS versions and a clean-Mac first launch still need hands-on validation. Independently check important calculations, including units, angle mode, and precision.

Updates are manual: download a newer version, quit normally, and replace the app without deleting its Application Support folder. See [Changelog](CHANGELOG.md) for version changes.

For [bug reports](https://github.com/B0yangWong/Calculator-Releases/issues/new/choose), include the expression, actual and expected results, angle mode, app version, and macOS version. [Feature requests](https://github.com/B0yangWong/Calculator-Releases/issues) are also welcome. Reports are public; do not upload private history or sensitive screenshots.

## Credits

MathLive provides formula editing; mathjs and its dependencies support evaluation. Third-party notices and licenses accompany the download and are also available in [Third-Party Notices](THIRD_PARTY_NOTICES.txt) and [ThirdPartyLicenses](ThirdPartyLicenses/). This download repository does not grant an open-source license to the Calculator application or icon artwork.
