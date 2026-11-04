# Linkboard

[Deutsch](README.de.md) · English

A single-file browser start page: your links as colored tiles, grouped into blocks and columns, with weather, a clock and a search bar. No build step, no framework, no account. Everything is stored in your browser.

<img width="1384" height="678" alt="Bildschirmfoto 2026-11-04 um 08 59 09" src="https://github.com/user-attachments/assets/fdaab89a-ad26-41a0-8cfb-505b6af49a88" />

## Features

- **Link tiles** with name, URL and color (3 color palettes plus a free color picker), opened in a new tab
- **Two tile shapes**: wide buttons or square tiles (two per row, as high as two wide buttons)
- **Blocks → columns → tiles**, all with editable titles and drag and drop (also on touch screens)
- **Sorting** per column: A–Z, by color or by most clicks; filter by color; live search (Enter opens the first hit)
- **Top links tile**: shows your most clicked links, Top 5 or Top 10
- **Weather and outside temperature** in the top right (Open-Meteo, no API key); click it to change the city
- **Digital clock** (24 h or 12 h AM/PM) with a **coffee break** animation at 09:30 and 15:00 for one minute (times are configurable)
- **Dark and light theme**
- **Responsive**, uses the full browser width
- **Export / import** as a JSON file for backups

<img width="1380" height="771" alt="Bildschirmfoto 2026-11-04 um 08 58 42" src="https://github.com/user-attachments/assets/f72bfd70-3cb6-4712-8bac-1c1888650438" />
<img width="418" height="487" alt="Bildschirmfoto 2026-11-04 um 08 57 56" src="https://github.com/user-attachments/assets/87d5afd3-28f6-4650-9d96-fc66acd062ff" />

## Quick start

1. Download `index.html`or set this link as your homepage: alpine-marmot.github.io/linkboard/
2. Open it in your browser.
3. Click **Edit** (top right) to add blocks, columns and links.
4. Optional: set the file as your browser's home page, e.g. `file:///path/to/index.html`.

You can also host it with **GitHub Pages** (Settings → Pages → deploy from branch `main`, folder `/root`) and use that address as your start page. Hosted over https, the weather request also works in browsers that restrict local files, such as Safari.

## Usage

| What | How |
| --- | --- |
| Add / edit / delete things | Click **Edit**, then use the buttons in the header, blocks, columns and tiles |
| Move tiles, columns, blocks | Edit mode, drag and drop (touch screens: press and hold briefly) |
| Sort a column | Edit mode, "Sort" menu in the column header |
| Clock and break times | Click the clock |
| Weather city | Click the weather |
| Backup | Edit mode, **Export** / **Import** |

## Data and privacy

Everything is saved in your browser's local storage, per browser and device. Use **Export** to back up or move your links (click counts are included; clock settings, theme, palette and weather city are not).

The page contacts these services:

- [Open-Meteo](https://open-meteo.com) for the weather (the coordinates of your chosen city)
- Google's favicon service for the small link icons (the domain names of your links)
- [cdnjs](https://cdnjs.com) for the drag and drop library [SortableJS](https://github.com/SortableJS/Sortable)

The default weather location is Bern; change it by clicking the weather.

## License

[MIT](LICENSE)
