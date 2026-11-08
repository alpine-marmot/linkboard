# Changelog

English · [Deutsch](CHANGELOG.de.md)

All notable changes to Linkboard are listed here. The format follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/), and the version numbers follow [Semantic Versioning](https://semver.org/).

## [Unreleased]

## [1.1.0] 2026-11-08

### Added
- **Link check:** an optional green or red dot on each tile shows whether the link's server responds. If the first request fails, a second attempt with a different request type follows. Results are cached for 15 minutes. A gray dot means "not checked" (still checking, offline, or not checkable from the page, for example `http://` links and local addresses on a page served over https). The check can be switched off per link.
- **Statistics:** a new button next to the color dots opens a chart view with the 10 most clicked links and the click history per day (14 days), week (12 weeks) or month (12 months), for all links or a single one.
- **Settings dialog** (gear icon, top right; the clock opens it too): clock format (24 h or 12 h AM/PM), break times, break reminder only visual or with a short chime, link check on/off, statistics on/off.
- **Break reminder with sound** (optional): a short two-tone chime at the start of the coffee break. Browsers only allow it after you have clicked the page once.
- **Fourth color palette:** grayscale.
- **Open all:** a button in every column header opens all links of that column in new tabs with one click (each counts as a click).
- The page asks the browser not to send a referrer with any request.

### Changed
- Clock and break settings moved from the clock dialog into the central settings. Existing values are migrated automatically (`startseite-v1-clock` becomes `startseite-v1-settings`).
- With statistics switched off, no daily click history is recorded. The simple click counter per link keeps running, because the "Top links" tile and the sort option "most clicks" use it.
- The header is more compact, so weather, clock and buttons stay in one row from about 1366 px window width, also in edit mode.

### Documentation
- README (English and German): where the data is stored in Chrome, Edge, Firefox and Safari, which external services are contacted, notes for IT environments, Swiss data protection law (FADP/DSG) and the Safari note about the 7-day storage limit, including the recommendation to use the local file in Safari.

### Compatibility
- Exports from 1.0.0 can be imported. New fields (tile shape, link check, click history) are optional.

## [1.0.0] - 2026-11-04

First public release.

### Added
- Link tiles with name, URL and color, wide or square, opened in a new tab.
- Blocks, columns and tiles with editable titles and drag and drop.
- Sorting per column (A–Z, color, most clicks), color filter and live search.
- "Top links" tile (Top 5 or Top 10).
- Weather with outside temperature (Open-Meteo), digital clock with coffee break animation at 09:30 and 15:00.
- Three color palettes, dark and light theme, responsive layout.
- Export and import as a JSON file.
- English and German README, MIT license.

[Unreleased]: https://github.com/alpine-marmot/linkboard/compare/v1.1.0...HEAD
[1.1.0]: https://github.com/alpine-marmot/linkboard/compare/v1.0.0...v1.1.0

