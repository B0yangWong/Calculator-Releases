# Calculator

[中文](README.md)

An offline scientific calculator for Apple Silicon Macs, with editable powers and fractions, scientific notation, Chinese and English interfaces, and local calculation history.

This repository publishes downloads, documentation, and issue reports only. The application source code is not public. Calculator is not an official Desmos product and does not embed the Desmos website or proprietary code.

![Calculator English interface](docs/screenshots/calculator-en.png)

## Download and install

- [Latest release](https://github.com/B0yangWong/Calculator-Releases/releases/latest)
- [Download v1.0.0: Calculator-1.0.0-macOS-arm64.zip](https://github.com/B0yangWong/Calculator-Releases/releases/download/v1.0.0/Calculator-1.0.0-macOS-arm64.zip)
- [v1.0.0 release notes and checksum files](https://github.com/B0yangWong/Calculator-Releases/releases/tag/v1.0.0)

Requires an Apple Silicon Mac and macOS 14 or later. This build was tested on macOS 27, not on a physical Mac running macOS 14. No Intel build is provided.

Unzip the download, move `Calculator.app` to Applications, and open it. No account, internet connection, or additional runtime is needed. GitHub's automatically generated `Source code (zip)` and `Source code (tar.gz)` contain only this repository's release documentation, not the application source or an installer. Download the versioned app ZIP linked above.

This release is ad-hoc signed, not Developer ID signed or Apple notarized. macOS may block the first launch. Only if you trust the source and the file is unchanged: attempt to open it, then use System Settings → Privacy & Security → Open Anyway and confirm. Availability depends on your Mac and its management policy. See [Apple's instructions](https://support.apple.com/en-us/102445). Stop if macOS says the app will damage your computer or is damaged; report the issue instead of disabling system protection.

## Type expressions directly

| Input | Meaning |
| --- | --- |
| `2^3` | Editable exponent; result: 8 |
| `(2+3)/2` | Editable stacked fraction; result: 2.5 |
| `e-25` | 10 to the power of −25 |
| `1.6e-25` | 1.6 × 10 to the power of −25 |
| `10*e*3` | e is Euler's constant; result: approximately 81.5484548537714 |
| `(e)-25` | Euler's constant minus 25 |

Press the right arrow after an exponent or denominator to return to the main expression. Space also exits an exponent. Operators following a scientific-notation exponent return to the main expression automatically. Enter saves a row. A light gray result is a live preview; saved results appear darker.

The default angle mode is degrees. Check Degrees / Radians before using trigonometric functions. Choose 中文 or English in Settings → Language; the interface changes immediately and remembers your choice.

## Features

- Arithmetic, powers, roots, absolute values, percentages, factorials, π, e, and ans.
- Trigonometric, inverse trigonometric, hyperbolic, inverse hyperbolic, and logarithmic functions.
- Combinations, permutations, rounding, gcd, lcm, modulo, and related functions.
- Variables such as `a=5` and single-parameter functions such as `f(x)=x^2+1`.
- Lists, element-wise operations, and statistics including mean, median, sum, standard deviation, and variance.
- Optional complex-number mode and common matrix operations.
- Editable calculation history with dependent results recalculated, undo, redo, copy, paste, and history export. Clear All removes both history and the unsubmitted expression and can be undone during the current session.
- Local autosave, light / dark themes, adjustable text size, and Chinese / English interface and app menus.

## Limits

- General calculations use floating-point arithmetic and display 15 significant digits. This is not an arbitrary-precision calculator. Purely numeric rational expressions have an exact-fraction path; fraction / decimal result switching is limited to these expressions.
- Percent means division by 100, not the context-dependent percentage behavior of some commercial calculators.
- History is limited to 250 rows, lists to 1024 items, factorials to 170, and matrices to 32 × 32.
- List ranges, list indexing, multi-parameter custom functions, and recursive functions are not implemented.
- Graphing, derivatives, and integration are not available yet. Full behavioral parity with Desmos is not promised.
- Tests do not cover every input. Independently check important calculations, including units, angle mode, and precision.

## Privacy, updates, and feedback

Calculations work offline. The app has no account, telemetry upload, or cloud sync. History and settings are stored locally without application-level encryption; see [Privacy](PRIVACY.md). Updates require a manual download.

Use [bug reports](https://github.com/B0yangWong/Calculator-Releases/issues/new/choose) to provide a reproducible expression, actual and expected results, angle mode, app version, and macOS version. Remove private details from screenshots and history before posting. Feature requests are welcome in [Issues](https://github.com/B0yangWong/Calculator-Releases/issues).

See [Changelog](CHANGELOG.md) for version changes. Third-party license notices accompany the download. This repository does not provide an open-source license for the Calculator application's source code.
