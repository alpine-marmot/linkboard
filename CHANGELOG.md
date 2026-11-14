# Changelog

English · [Deutsch](CHANGELOG.de.md)

All notable changes to Linkboard are listed here. The format follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/), and the version numbers follow [Semantic Versioning](https://semver.org/).

## [Unreleased]

## [1.3.0] - 2026-11-14

### Added
- **Saving to a file** (Chrome and Edge only): Linkboard can store your data in a file you choose, for example in a cloud folder (OneDrive, iCloud Drive, Dropbox, Google Drive), and keep two devices in sync. Every change is written to the file. After a restart one click on **Allow access** is needed. If the file is newer than the data in the browser, Linkboard asks which version to use. If the file is invalid, it is never overwritten.
- **First-start message** that explains the choice and states clearly that saving to a file only works in Chrome and Edge, and not in Firefox, Safari, Brave (without a flag) and all browsers on iPhone and iPad. Existing users see the message once; their data is copied into the new file. On a second device an existing file can be opened.
- **Storage status in the settings:** shows whether Linkboard saves to a file or to the browser storage, the file name and the time of the last save. A bar at the top appears when access to the file is needed or saving failed.

### Changed
- **The backup moved to the settings** (section *Backup*): **Download a backup** and **Load a backup (JSON)**. In the header, the **Import** button became **Bookmarks** and only imports bookmark files (HTML).

### Documentation
- README (English and German): new section *Storage and synchronization* with a browser table, notes on file storage in the privacy section (new storage keys, IndexedDB reference to the file, cloud folder).

## [1.2.0] - 2026-11-12

### Added
- **Two languages:** the whole interface can be switched between German and English with the new square **DE/EN** button next to the light/dark switch. The first start follows the browser language. Your own block, column and link names are never translated. The sample content is created in the language of the first start.
- **Bookmark import:** **Import** now also reads bookmark files (HTML) exported from Chrome, Edge, Firefox and Safari. A selection window shows all folders and links with checkboxes, search and "All / None / Only new". Layout: keep the folder structure (folder becomes block, subfolder becomes column, large folders are split into columns of at most 20 links) or flat in columns "Import 1, 2, 3 …". Color: alternating per column or one color, from any of the four palettes. Links that already exist, duplicates in the file and addresses that cannot be opened (`chrome://`, `file://`) are shown but deselected. The link check for imported links is off by default.

### Changed
- **The coffee break is now optional and off by default.** If you used it before, turn it on once in the settings under *Features*. The settings for times, sound and preview only appear once the box is ticked.
- **More link types:** addresses without `//` such as `spotify:…`, `facetime:…`, `maps:…`, `geo:…` now stay unchanged (before, `https://` was wrongly put in front). `javascript:`, `data:`, `vbscript:` and `blob:` are no longer accepted. The bookmark import now also takes app links and other address types (not `file:`, `chrome:`, `about:` and similar). Favicon requests to Google are only made for web links (`http`, `https`).

### Documentation
- README: screenshots added; new *Link types* section with examples and limits; privacy section reworked ("At a glance" overview, notes on third-party cookies, no integrity check for SortableJS, personal data in `mailto:`/`tel:` tiles, weather request with Bern as the default location).

## [1.1.0] - 2026-11-08

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

[Unreleased]: https://github.com/alpine-marmot/linkboard/compare/v1.3.0...HEAD
[1.3.0]: https://github.com/alpine-marmot/linkboard/compare/v1.2.0...v1.3.0
[1.2.0]: https://github.com/alpine-marmot/linkboard/compare/v1.1.0...v1.2.0
[1.1.0]: https://github.com/alpine-marmot/linkboard/compare/v1.0.0...v1.1.0
[1.0.0]: https://github.com/alpine-marmot/linkboard/releases/tag/v1.0.0
