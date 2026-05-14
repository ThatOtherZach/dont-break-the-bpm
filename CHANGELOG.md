# Changelog

All notable changes to BreakBPM will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [0.4.0] - 2026-05-14
### Added
- Full Windows 98 retro UI theme (gray 3D windows, navy title bars, classic fonts)
- Simplified ball system using `(X)` text notation only
- Smart ball selector showing only legal/available balls
- Green terminal-style ball return readout showing sunk balls in order
- Major UI overhaul while keeping all core functionality

### Changed
- Ball representation changed from emojis/colors to simple `(1)(3)(8)` format
- Ball return moved to prominent terminal-style input field

## [0.3.0] - 2026-05-14
### Added
- Prominent Ball Return visual (L-inspired design)
- Balls append in chronological order with roll-in animation
- Improved player scores section

## [0.2.0] - 2026-05-14
### Added
- Team assignment (Solids vs Stripes) for 8-ball
- Ball selector modal with legal balls only
- 4-digit short code generator + improved sharing
- Proper 8-ball and 9-ball win rules (group clearance before 8-ball)

## [0.1.0] - 2026-05-14
### Added
- Initial release
- Basic scoring, BPM tracking, timer, shareable URL state
- 8-ball / 9-ball / practice modes
- Multiplayer via link (async state sharing)
- Shot logging and undo

[0.4.0]: https://github.com/ThatOtherZach/dont-break-the-bpm/compare/v0.3.0...v0.4.0
[0.3.0]: https://github.com/ThatOtherZach/dont-break-the-bpm/compare/v0.2.0...v0.3.0
[0.2.0]: https://github.com/ThatOtherZach/dont-break-the-bpm/compare/v0.1.0...v0.2.0
[0.1.0]: https://github.com/ThatOtherZach/dont-break-the-bpm/releases/tag/v0.1.0