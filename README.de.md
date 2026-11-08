# Linkboard

Deutsch · [English](README.md)

Eine Browser-Startseite in einer einzigen Datei: deine Links als farbige Kacheln, gegliedert in Blöcke und Spalten, dazu Wetter, Uhr und Suchleiste. Kein Build-Schritt, kein Framework, kein Konto. Alles wird in deinem Browser gespeichert.

> **Wichtig, wenn du Safari nutzt:** Safari löscht die gespeicherten Daten einer Website (auch deine Links) nach 7 Tagen Safari-Nutzung, in denen du auf dieser Website nicht geklickt oder getippt hast. Bei der gehosteten Version über GitHub Pages können deine Links deshalb verschwinden. Nutze in Safari bitte die **heruntergeladene `index.html`, die du von deinem Computer aus öffnest**, statt den GitHub-Link, und mache ab und zu einen **Export**. Die 7-Tage-Regel ist für Websites dokumentiert. Für lokale Dateien haben wir keine Bestätigung gefunden, dass sie gilt, ihr Verhalten in Safari ist aber auch nicht offiziell dokumentiert, deshalb bleiben regelmässige Exporte ratsam. Details: *Daten und Datenschutz*.

## Funktionen

- **Link-Kacheln** mit Name, Adresse und Farbe (4 Farbpaletten, darunter Graustufen, plus freie Farbwahl), Öffnen in einem neuen Tab
- **Zwei Kachelformen**: breite Buttons oder quadratische Kacheln (zwei pro Reihe, so hoch wie zwei breite Buttons)
- **Blöcke → Spalten → Kacheln**, alle mit editierbaren Titeln und Drag-and-Drop (auch auf Touchscreens)
- **Sortieren** pro Spalte: A–Z, nach Farbe oder nach meisten Klicks; Filter nach Farbe; Live-Suche (Enter öffnet den ersten Treffer)
- **Top-Links-Kachel**: zeigt die meistgeklickten Links, Top 5 oder Top 10
- **Alle öffnen**: Ein Button im Kopf jeder Spalte öffnet alle Links dieser Spalte mit einem Klick in neuen Tabs (jeder zählt als Klick; der Browser fragt eventuell, ob Pop-ups erlaubt sind)
- **Link-Check**: ein optionaler grüner oder roter Punkt zeigt, ob der Server eines Links antwortet (nicht, ob die Seite selbst existiert); pro Link oder global in den Einstellungen abschaltbar
- **Statistik**: eine Diagrammansicht (Balken-Symbol neben den Farbpunkten) zeigt die meistgeklickten Links und den Klickverlauf pro Tag, Woche oder Monat; gezählt werden nur Klicks über diese Seite; in den Einstellungen abschaltbar (dann wird kein Tagesverlauf mehr aufgezeichnet)
- **Wetter und Aussentemperatur** oben rechts (Open-Meteo, kein API-Schlüssel); per Klick änderst du den Ort
- **Digitale Uhr** (24 h oder 12 h AM/PM) mit einer **Kaffeepause**-Animation um 09:30 und 15:00 für eine Minute (Zeiten einstellbar, auf Wunsch mit kurzem Signalton)
- **Einstellungen** (Zahnrad oben rechts): Uhrformat, Pausenzeiten, optionaler Ton, Link-Check ein/aus, Statistik ein/aus
- **Dunkles und helles Design**
- **Responsiv**, nutzt die volle Browserbreite
- **Export / Import** als JSON-Datei für Sicherungen

## Schnellstart

1. `index.html` herunterladen.
2. Im Browser öffnen.
3. Oben rechts auf **Bearbeiten** klicken, um Blöcke, Spalten und Links anzulegen.
4. Optional: die Datei als Startseite des Browsers eintragen, z. B. `file:///Pfad/zu/index.html`.

Du kannst die Seite auch mit **GitHub Pages** veröffentlichen (Settings → Pages → Deploy from branch `main`, Ordner `/root`) und diese Adresse als Startseite nutzen. Für Safari nicht empfohlen: siehe den Hinweis ganz oben.

## Bedienung

| Was | Wie |
| --- | --- |
| Etwas hinzufügen / ändern / löschen | **Bearbeiten** klicken, dann die Buttons in Kopfzeile, Blöcken, Spalten und Kacheln benutzen |
| Kacheln, Spalten, Blöcke verschieben | Bearbeitungsmodus, Drag-and-Drop (Touchscreen: kurz gedrückt halten) |
| Spalte sortieren | Bearbeitungsmodus, Menü „Sortieren“ im Spaltenkopf |
| Einstellungen (Uhr, Pausen, Ton, Link-Check, Statistik) | auf das Zahnrad oder die Uhr klicken |
| Wetterort | auf das Wetter klicken |
| Statistik | auf das Balken-Symbol neben den Farbpunkten klicken |
| Alle Links einer Spalte öffnen | im Spaltenkopf auf *Alle öffnen* klicken (nicht im Bearbeitungsmodus) |
| Sicherung | Bearbeitungsmodus, **Export** / **Import** |

## Daten und Datenschutz

*Stand: November 2026. Technische Beschreibung, keine Rechtsberatung. Bitte prüfe die aktuellen Bedingungen der unten genannten Dienste selbst.*

Linkboard hat keinen eigenen Server. Der Autor erhält, sammelt und speichert keine Daten. Alles, was du eingibst, bleibt in deinem Browser, abgesehen von den Anfragen an Drittdienste, die weiter unten aufgeführt sind.

### Was wird wo gespeichert?

Linkboard speichert seine Daten im **lokalen Speicher** deines Browsers (`localStorage`) als Klartext (JSON). Sonst wird nichts geschrieben, und die Seite selbst setzt keine Cookies.

- `startseite-v1`: Blöcke, Spalten und Kacheln (Name, Adresse, Farbe, Form, Link-Check ein/aus), Klickzähler und tägliche Klickhistorie
- `startseite-v1-chk`: Ergebnisse des Link-Checks (Adresse, erreichbar ja/nein, Zeitpunkt der Prüfung)
- `startseite-v1-settings`: Einstellungen (Uhrformat, Pausenzeiten, Ton, Link-Check ein/aus, Statistik ein/aus)
- `startseite-v1-loc`: Wetterort (Name und Koordinaten), nur nachdem du ihn geändert hast
- `startseite-v1-pal`, `startseite-v1-theme`: Farbpalette und helles/dunkles Design

Das bedeutet:

- Die Daten gehören zu einem Browser, einem Browserprofil, einem Gerät und einer Seitenadresse. Linkboard in Chrome und in Firefox, oder als lokale Datei und über GitHub Pages geöffnet, hat getrennte Daten. Mit **Export** und **Import** nimmst du sie mit.
- Nach unserem Kenntnisstand verschlüsseln Browser den lokalen Speicher nicht selbst. Wer Zugriff auf dein Benutzerkonto oder auf einen unverschlüsselten Datenträger hat, kann ihn lesen. Nutze getrennte Benutzerkonten und eine Festplattenverschlüsselung (zum Beispiel BitLocker oder FileVault).
- Die Export-Datei ist JSON im Klartext und enthält alle Links und die Klickhistorie. Bewahre sie entsprechend auf.
- Lege keine Passwörter, Tokens oder andere Geheimnisse in Link-Adressen ab.
- Private Fenster behalten die Daten nach dem Schliessen nicht.
- Synchronisierungsfunktionen der Browser übertragen den lokalen Speicher normalerweise nicht. Das ist nicht garantiert, prüfe bei Bedarf die Sync-Einstellungen deines Browsers.

### Speicherort je Browser

Die Pfade sind Beispiele für das Standardprofil. Der Profilordner kann anders heissen (zum Beispiel `Profile 1`). Die Dateien sind nicht dafür gedacht, von Hand geöffnet zu werden.

**Google Chrome** (Ordner `Local Storage/leveldb`)
- Windows: `%LOCALAPPDATA%\Google\Chrome\User Data\Default\Local Storage\leveldb\`
- macOS: `~/Library/Application Support/Google/Chrome/Default/Local Storage/leveldb/`
- Linux: `~/.config/google-chrome/Default/Local Storage/leveldb/`

**Microsoft Edge** (gleicher Aufbau wie Chrome)
- Windows: `%LOCALAPPDATA%\Microsoft\Edge\User Data\Default\Local Storage\leveldb\`
- macOS: `~/Library/Application Support/Microsoft Edge/Default/Local Storage/leveldb/`
- Linux: `~/.config/microsoft-edge/Default/Local Storage/leveldb/`

**Mozilla Firefox** (im Profilordner, ein Unterordner pro Seitenadresse)
- Profilordner unter Windows: `%APPDATA%\Mozilla\Firefox\Profiles\<Profil>\`
- Profilordner unter macOS: `~/Library/Application Support/Firefox/Profiles/<Profil>/`
- Profilordner unter Linux: `~/.mozilla/firefox/<Profil>/`
- Daten: `storage/default/<Adresse>/ls/data.sqlite`, zum Beispiel `https+++alpine-marmot.github.io`. Die Werte sind komprimiert gespeichert.

**Apple Safari**
- macOS: Der Ort hängt von der macOS- und Safari-Version ab: `~/Library/Safari/LocalStorage/` (ältere Versionen), `~/Library/WebKit/WebsiteData/` (neuere Versionen) und innerhalb der Safari-Sandbox `~/Library/Containers/com.apple.Safari/Data/Library/WebKit/WebsiteData/Default/`.
- iPhone und iPad: in der App-Sandbox von Safari, für Nutzer nicht zugänglich.
- Safari löscht den lokalen Speicher einer Website nach 7 Tagen Safari-Nutzung, in denen du auf dieser Website nicht geklickt oder getippt hast (Intelligent Tracking Prevention). Bei der gehosteten Version (GitHub Pages) können deine Links verschwinden, wenn du sie eine Weile nicht nutzt. Nutze in Safari deshalb die heruntergeladene lokale Datei statt der gehosteten Seite und exportiere regelmässig.

### Lokale Datei oder gehostete Version

- Firefox (ab Version 92): Jeder Dateipfad hat einen eigenen Speicher. Wenn du `index.html` verschiebst oder umbenennst, startet Linkboard leer. Stelle deine Daten mit **Import** wieder her.
- Chrome und Edge: Lokale Dateien teilen sich einen Speicherbereich (mindestens innerhalb desselben Ordners). Dieses Verhalten ist nicht standardisiert und kann sich ändern. Andere lokale HTML-Seiten könnten daher die Daten von Linkboard lesen oder überschreiben. Wenn das wichtig ist, betreibe Linkboard auf einem Webserver.
- Safari: Nutze die heruntergeladene lokale Datei statt des GitHub-Pages-Links (siehe Hinweis ganz oben). Die 7-Tage-Regel ist für Websites dokumentiert. Für lokale Dateien haben wir keine Bestätigung gefunden, dass sie gilt, und ihr Verhalten in Safari ist auch nicht offiziell dokumentiert. Mache in jedem Fall regelmässige Exporte.

### Daten ansehen oder löschen

- Ansehen: Entwicklerwerkzeuge öffnen. Chrome und Edge: `F12`, Reiter *Application*, *Local Storage*. Firefox: `F12`, Reiter *Storage*, *Local Storage*. Safari: In den Einstellungen das Menü Entwickler aktivieren, dann *Web-Inspektor einblenden*, Reiter *Speicher*, *Lokaler Speicher*.
- Löschen: entweder die Schlüssel, die mit `startseite-v1` beginnen, in den Entwicklerwerkzeugen entfernen, oder die Websitedaten in den Browsereinstellungen löschen (Bereich Datenschutz, "Cookies und Websitedaten" oder "Websitedaten"; die Menübezeichnungen unterscheiden sich je nach Version). Mache vorher einen **Export**, wenn du deine Links behalten willst.

### Welche externen Dienste werden kontaktiert?

Alle Anfragen sendet dein Browser direkt, ohne Referrer-Angabe (die Seite bittet den Browser, keine zu senden). Sie enthalten immer deine IP-Adresse und die üblichen Browserangaben (zum Beispiel den User-Agent).

- **Open-Meteo** (`api.open-meteo.com`, `geocoding-api.open-meteo.com`): Wetter. Gesendet werden die Koordinaten des gewählten Ortes und, wenn du den Ort änderst, der eingetippte Name. Betrieben von der OpenMeteo GmbH, Schweiz. Laut Projektdokumentation wird die kostenlose API von Servern in Europa und Nordamerika ausgeliefert. Die kostenlose API ist **nur für nichtkommerzielle Nutzung** gedacht (weniger als 10'000 Aufrufe pro Tag); für kommerzielle Nutzung braucht es einen kostenpflichtigen Plan. Die Daten stehen unter CC BY 4.0: *Weather data by Open-Meteo.com* (https://open-meteo.com). Bedingungen: https://open-meteo.com/en/terms
- **Favicon-Dienst von Google** (`www.google.com/s2/favicons`): die kleinen Link-Symbole. Gesendet wird der **Domainname jeder Link-Kachel** (nur der Hostname, ohne Pfad und Parameter). **Das schliesst die Hostnamen interner Server ein.**
- **cdnjs / Cloudflare** (`cdnjs.cloudflare.com`): liefert bei jedem Laden der Seite die Drag-and-Drop-Bibliothek SortableJS aus (ausser dein Browser hat sie im Zwischenspeicher).
- **Die verlinkten Websites** (Link-Check): eine kurze Anfrage (HEAD, und ein GET, falls diese scheitert) an jeden Link mit eingeschaltetem Check, höchstens alle 15 Minuten pro Link. Sie wird ohne Cookies und ohne Referrer gesendet. Die Zielserver sehen deine IP-Adresse in ihren Logs. Der Check lässt sich pro Link oder global in den Einstellungen abschalten.
- **GitHub Pages** (nur bei der gehosteten Version): GitHub liefert die Seite aus und verarbeitet Besucher-IP-Adressen gemäss seiner Datenschutzerklärung. Deine Links werden nicht an GitHub übertragen.

Es gibt derzeit keinen Schalter, um das Wetter oder die Favicons abzuschalten.

### Hinweise für den Einsatz in der IT

- Interne Hostnamen gelangen an den Favicon-Dienst von Google, solange die Kachel ein http(s)-Link ist. Trage interne Server nicht ein, solange das für dich nicht akzeptabel ist, oder entferne das Favicon-Bild aus dem Quelltext (in `index.html` nach `google.com/s2/favicons` suchen).
- Lade `Sortable.min.js` herunter und binde es von deinem eigenen Server ein statt von cdnjs, wenn du keine Anfragen an Cloudflare willst.
- Der Link-Check erzeugt Anfragen (und Log-Einträge) auf den Zielservern. Er kann Überwachung oder Angriffserkennung auslösen. Schalte ihn bei sensiblen Zielen oder global in den Einstellungen ab.
- Die Klickhistorie zeigt, welche Werkzeuge eine Person nutzt. Halte sie lokal, lege fest, wer auf Exporte und Backups zugreifen darf, und nutze sie nicht zur Leistungs- oder Verhaltenskontrolle. Die Statistik lässt sich in den Einstellungen abschalten.
- Die kostenlose Open-Meteo-API ist nicht für kommerzielle Nutzung gedacht. Für den Firmeneinsatz brauchst du einen kostenpflichtigen Plan, eine eigene Instanz oder du verzichtest auf das Wetter.

### Schweizer Datenschutzrecht

Das Bundesgesetz über den Datenschutz (DSG, SR 235.1) und die Datenschutzverordnung (DSV, SR 235.11) gelten seit dem 1. September 2023.

- **Verantwortung:** Wer Linkboard einsetzt und über Zweck und Mittel entscheidet, ist Verantwortlicher (Privatperson oder Organisation). Der Autor liefert nur den Quellcode, hat keinen Zugriff auf deine Daten und bearbeitet keine.
- **Personendaten (Art. 5 Bst. a DSG):** alle Angaben, die sich auf eine bestimmte oder bestimmbare natürliche Person beziehen. Je nach Zusammenhang können IP-Adressen, Link-Sammlungen und die Klickhistorie Personendaten sein.
- **Bekanntgabe an Dritte und ins Ausland (Art. 16 DSG):** Die oben genannten Dienste erhalten IP-Adressen. Für Empfänger in den USA sind keine weiteren Garantien nötig, wenn der Empfänger nach dem Swiss-U.S. Data Privacy Framework zertifiziert ist (Anhang 1 DSV, Ziffer 44, in Kraft seit 15. September 2024). Prüfe die Zertifizierung von Google, Cloudflare und GitHub unter https://www.dataprivacyframework.gov/list. Für Open-Meteo gelten die oben genannten Serverstandorte.
- **Informationspflicht (Art. 19 DSG):** Wenn du Linkboard anderen Personen anbietest (zum Beispiel Mitarbeitenden oder Kundschaft) und Personendaten wie oben beschrieben an Dritte gelangen, musst du angemessen informieren, in der Regel mit einer Datenschutzerklärung.
- **Datensicherheit (Art. 8 DSG):** Triff angemessene technische und organisatorische Massnahmen, zum Beispiel Zugriffsschutz, Festplattenverschlüsselung und sorgfältigen Umgang mit Export-Dateien.
- **Arbeitsverhältnis:** Im Arbeitsverhältnis gelten zusätzlich die Regeln zur Bearbeitung von Arbeitnehmerdaten (Art. 328b des Obligationenrechts).

Dieser Text ersetzt keine Beratung durch deine Datenschutzberatung, den Rechtsdienst oder die IT-Sicherheit. Siehe auch den Eidgenössischen Datenschutz- und Öffentlichkeitsbeauftragten (EDÖB): https://www.edoeb.admin.ch

## Änderungsprotokoll

Siehe [CHANGELOG.de.md](CHANGELOG.de.md) (Deutsch) und [CHANGELOG.md](CHANGELOG.md) (English).

## Lizenz

[MIT](LICENSE)
