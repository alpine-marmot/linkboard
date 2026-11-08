# Linkboard

[Deutsch](README.de.md) · English

A single-file browser start page: your links as colored tiles, grouped into blocks and columns, with weather, a clock and a search bar. No build step, no framework, no account. Everything is stored in your browser.

> **Important if you use Safari:** Safari deletes the stored data of a website (including your links) after 7 days of Safari use without any click or keystroke on that site. With the hosted GitHub Pages version your links can therefore disappear. In Safari, please use the **downloaded `index.html` opened from your computer** instead of the GitHub link, and make an **Export** from time to time. The 7-day rule is documented for websites. For local files we found no confirmation that it applies, but their behavior in Safari is not officially documented either, so regular exports remain advisable. Details: *Data and privacy*.

## Features

- **Link tiles** with name, URL and color (4 color palettes including grayscale, plus a free color picker), opened in a new tab
- **Two tile shapes**: wide buttons or square tiles (two per row, as high as two wide buttons)
- **Blocks → columns → tiles**, all with editable titles and drag and drop (also on touch screens)
- **Sorting** per column: A–Z, by color or by most clicks; filter by color; live search (Enter opens the first hit)
- **Top links tile**: shows your most clicked links, Top 5 or Top 10
- **Open all**: a button in every column header opens all links of that column in new tabs with one click (each counts as a click; your browser may ask you to allow pop-ups)
- **Link check**: an optional green or red dot shows whether a link's server responds (not whether the page itself exists); can be switched off per link or globally in the settings
- **Statistics**: a chart view (bar-chart button next to the color dots) shows your most clicked links and the click history per day, week or month; only clicks made through this page are counted; can be switched off in the settings (then no daily history is recorded)
- **Weather and outside temperature** in the top right (Open-Meteo, no API key); click it to change the city
- **Digital clock** (24 h or 12 h AM/PM) with a **coffee break** animation at 09:30 and 15:00 for one minute (times are configurable, optionally with a short chime)
- **Settings** (gear icon, top right): clock format, break times, optional sound, link check on/off, statistics on/off
- **Dark and light theme**
- **Responsive**, uses the full browser width
- **Export / import** as a JSON file for backups

## Quick start

1. Download `index.html`.
2. Open it in your browser.
3. Click **Edit** (top right) to add blocks, columns and links.
4. Optional: set the file as your browser's home page, e.g. `file:///path/to/index.html`.

You can also host it with **GitHub Pages** (Settings → Pages → deploy from branch `main`, folder `/root`) and use that address as your start page. Not recommended for Safari: see the note at the top.

## Usage

| What | How |
| --- | --- |
| Add / edit / delete things | Click **Edit**, then use the buttons in the header, blocks, columns and tiles |
| Move tiles, columns, blocks | Edit mode, drag and drop (touch screens: press and hold briefly) |
| Sort a column | Edit mode, "Sort" menu in the column header |
| Settings (clock, breaks, sound, link check, statistics) | Click the gear icon (or the clock) |
| Weather city | Click the weather |
| Statistics | Click the bar-chart button next to the color dots |
| Open all links of a column | Click *Alle öffnen* in the column header (not in edit mode) |
| Backup | Edit mode, **Export** / **Import** |

## Data and privacy

*Status: November 2026. Technical description, not legal advice. Please check the current terms of the services named below yourself.*

Linkboard has no server of its own. The author does not receive, collect or store any data. Everything you enter stays in your browser, apart from the requests to third-party services listed further down.

### What is stored, and where

Linkboard saves its data in the **local storage** of your browser (`localStorage`) as plain text (JSON). Nothing is written anywhere else, and the page itself sets no cookies.

- `startseite-v1`: blocks, columns and tiles (name, URL, color, shape, link check on/off), click counters and the daily click history
- `startseite-v1-chk`: results of the link check (URL, reachable yes/no, time of the check)
- `startseite-v1-settings`: settings (clock format, break times, sound, link check on/off, statistics on/off)
- `startseite-v1-loc`: weather city (name and coordinates), only after you changed it
- `startseite-v1-pal`, `startseite-v1-theme`: color palette and light/dark theme

What this means:

- The data belongs to one browser, one browser profile, one device and one page address. Linkboard opened in Chrome and in Firefox, or as a local file and from GitHub Pages, has separate data. Use **Export** and **Import** to move it.
- As far as we know, browsers do not encrypt local storage themselves. Anyone with access to your user account or to an unencrypted disk can read it. Use separate user accounts and disk encryption (for example BitLocker or FileVault).
- The export file is plain-text JSON and contains all your links and the click history. Store it accordingly.
- Do not put passwords, tokens or other secrets into link URLs.
- Private windows do not keep the data after they are closed.
- Browser sync features normally do not transfer local storage. This is not guaranteed, so check your browser's sync settings if it matters.

### Storage location by browser

The paths are examples for the default profile. The profile folder can have another name (for example `Profile 1`). The files are not meant to be opened by hand.

**Google Chrome** (folder `Local Storage/leveldb`)
- Windows: `%LOCALAPPDATA%\Google\Chrome\User Data\Default\Local Storage\leveldb\`
- macOS: `~/Library/Application Support/Google/Chrome/Default/Local Storage/leveldb/`
- Linux: `~/.config/google-chrome/Default/Local Storage/leveldb/`

**Microsoft Edge** (same structure as Chrome)
- Windows: `%LOCALAPPDATA%\Microsoft\Edge\User Data\Default\Local Storage\leveldb\`
- macOS: `~/Library/Application Support/Microsoft Edge/Default/Local Storage/leveldb/`
- Linux: `~/.config/microsoft-edge/Default/Local Storage/leveldb/`

**Mozilla Firefox** (inside the profile folder, one subfolder per page address)
- Profile folder on Windows: `%APPDATA%\Mozilla\Firefox\Profiles\<profile>\`
- Profile folder on macOS: `~/Library/Application Support/Firefox/Profiles/<profile>/`
- Profile folder on Linux: `~/.mozilla/firefox/<profile>/`
- Data: `storage/default/<address>/ls/data.sqlite`, for example `https+++alpine-marmot.github.io`. The values are stored compressed.

**Apple Safari**
- macOS: the location depends on the macOS and Safari version: `~/Library/Safari/LocalStorage/` (older versions), `~/Library/WebKit/WebsiteData/` (newer versions) and inside the Safari sandbox `~/Library/Containers/com.apple.Safari/Data/Library/WebKit/WebsiteData/Default/`.
- iPhone and iPad: inside the app sandbox of Safari, not accessible to the user.
- Safari deletes the local storage of a website after 7 days of Safari use without any click or keystroke on that website (Intelligent Tracking Prevention). With the hosted version (GitHub Pages) your links can disappear if you do not use it for a while. In Safari, therefore use the downloaded local file instead of the hosted page, and make regular exports.

### Local file or hosted version

- Firefox (since version 92): every file path has its own storage. If you move or rename `index.html`, Linkboard starts empty. Restore your data with **Import**.
- Chrome and Edge: local files share one storage area (at least within the same folder). This behavior is not standardized and may change. Other local HTML pages could therefore read or overwrite Linkboard's data. If that matters, host Linkboard on a web server.
- Safari: use the downloaded local file rather than the GitHub Pages link (see the note at the top). The 7-day rule is documented for websites. For local files we found no confirmation that it applies, and their behavior in Safari is not officially documented either. Make regular exports in any case.

### View or delete the data

- View: open the developer tools. Chrome and Edge: `F12`, tab *Application*, *Local Storage*. Firefox: `F12`, tab *Storage*, *Local Storage*. Safari: enable the Develop menu in the settings, then *Show Web Inspector*, tab *Storage*, *Local Storage*.
- Delete: either remove the keys starting with `startseite-v1` in the developer tools, or delete the website data in the browser settings (privacy section, "cookies and site data" or "website data"; the menu names vary by version). Make an **Export** first if you want to keep your links.

### Which external services are contacted?

All requests are sent directly by your browser, without referrer information (the page asks the browser not to send one). They always include your IP address and the usual browser information (for example the user agent).

- **Open-Meteo** (`api.open-meteo.com`, `geocoding-api.open-meteo.com`): weather. Sent: the coordinates of the selected city and, when you change the city, the name you typed. Operated by OpenMeteo GmbH, Switzerland. According to the project documentation, the free API is served from servers in Europe and North America. The free API is for **non-commercial use only** (fewer than 10,000 calls per day); commercial use needs a paid plan. The data is licensed under CC BY 4.0: *Weather data by Open-Meteo.com* (https://open-meteo.com). Terms: https://open-meteo.com/en/terms
- **Google favicon service** (`www.google.com/s2/favicons`): the small link icons. Sent: the **domain name of every link tile** (host name only, without path or query). **This includes the host names of internal servers.**
- **cdnjs / Cloudflare** (`cdnjs.cloudflare.com`): delivers the drag and drop library SortableJS each time the page is loaded (unless your browser has it cached).
- **The linked websites** (link check): a short request (HEAD, and a GET if that fails) to every link with the check switched on, at most every 15 minutes per link. It is sent without cookies and without a referrer. The target servers see your IP address in their logs. The check can be switched off per link or globally in the settings.
- **GitHub Pages** (only if you use the hosted version): GitHub delivers the page and processes visitor IP addresses according to its privacy statement. Your links are not transmitted to GitHub.

There is currently no switch to turn off the weather or the favicons.

### Notes for use in IT environments

- Internal host names reach the Google favicon service as long as the tile is an http(s) link. Do not enter internal servers while this is not acceptable for you, or remove the favicon image from the source code (search for `google.com/s2/favicons` in `index.html`).
- Download `Sortable.min.js` and load it from your own server instead of cdnjs if you do not want requests to Cloudflare.
- The link check creates requests (and log entries) on the target servers. It can trigger monitoring or intrusion detection. Switch it off for sensitive targets or globally in the settings.
- The click history shows which tools a person uses. Keep it local, define who may access exports and backups, and do not use it for performance or behavior monitoring. Statistics can be switched off in the settings.
- The free Open-Meteo API is not meant for commercial use. For company use, take a paid plan, host your own instance, or do not use the weather.

### Swiss data protection law

The Federal Act on Data Protection (FADP/DSG, SR 235.1) and the Data Protection Ordinance (DSV, SR 235.11) have applied since 1 September 2023.

- **Responsibility:** whoever uses Linkboard and decides on its purpose and means is the controller (a private person or an organization). The author only provides the source code, has no access to your data and processes none.
- **Personal data (Art. 5 let. a FADP):** any information relating to an identified or identifiable person. Depending on the context, IP addresses, link collections and the click history can be personal data.
- **Disclosure to third parties and abroad (Art. 16 FADP):** the services above receive IP addresses. For recipients in the USA, no further safeguards are needed only if the recipient is certified under the Swiss-U.S. Data Privacy Framework (Annex 1 DSV, number 44, in force since 15 September 2024). Check the certification of Google, Cloudflare and GitHub at https://www.dataprivacyframework.gov/list. For Open-Meteo, the server locations named above apply.
- **Duty to inform (Art. 19 FADP):** if you offer Linkboard to other people (for example employees or customers) and personal data is disclosed to third parties as described above, you must inform them appropriately, usually in a privacy notice.
- **Data security (Art. 8 FADP):** take appropriate technical and organizational measures, such as access protection, disk encryption and careful handling of export files.
- **Employment:** in an employment relationship the rules on processing employee data apply in addition (Art. 328b of the Code of Obligations).

This text does not replace advice from your data protection officer, legal department or IT security. See also the Federal Data Protection and Information Commissioner (FDPIC): https://www.edoeb.admin.ch

## Changelog

See [CHANGELOG.md](CHANGELOG.md) (English) and [CHANGELOG.de.md](CHANGELOG.de.md) (Deutsch).

## License

[MIT](LICENSE)
