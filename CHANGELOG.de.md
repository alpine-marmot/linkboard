# Änderungsprotokoll (Changelog)

Deutsch · [English](CHANGELOG.md)

Hier stehen alle wichtigen Änderungen an Linkboard. Das Format folgt [Keep a Changelog](https://keepachangelog.com/de/1.1.0/), die Versionsnummern folgen der [Semantischen Versionierung](https://semver.org/lang/de/).

## [Unveröffentlicht]

### Neu
- **Link-Check:** Ein optionaler grüner oder roter Punkt in jeder Kachel zeigt, ob der Server des Links antwortet. Scheitert die erste Anfrage, folgt ein zweiter Versuch mit einer anderen Anfrageart. Die Ergebnisse werden 15 Minuten zwischengespeichert. Ein grauer Punkt heisst "nicht geprüft" (Prüfung läuft noch, offline oder von der Seite aus nicht prüfbar, zum Beispiel `http://`-Links und lokale Adressen bei einer über https ausgelieferten Seite). Der Check lässt sich pro Link abschalten.
- **Statistik:** Ein neuer Button neben den Farbpunkten öffnet eine Diagrammansicht mit den 10 meistgeklickten Links und dem Klickverlauf pro Tag (14 Tage), Woche (12 Wochen) oder Monat (12 Monate), für alle Links oder einen einzelnen.
- **Einstellungen** (Zahnrad oben rechts; auch die Uhr öffnet sie): Uhrformat (24 h oder 12 h AM/PM), Pausenzeiten, Pausen-Erinnerung nur optisch oder mit kurzem Signalton, Link-Check ein/aus, Statistik ein/aus.
- **Pausen-Erinnerung mit Ton** (optional): ein kurzer Zweiklang zu Beginn der Kaffeepause. Browser erlauben ihn erst, nachdem du die Seite einmal angeklickt hast.
- **Vierte Farbpalette:** Graustufen.
- **Alle öffnen:** Ein Button im Kopf jeder Spalte öffnet alle Links dieser Spalte mit einem Klick in neuen Tabs (jeder zählt als Klick).
- Die Seite bittet den Browser, bei keiner Anfrage einen Referrer zu senden.
- **Zwei Sprachen:** Die ganze Oberfläche lässt sich mit dem neuen quadratischen Button **DE/EN** neben dem Hell/Dunkel-Umschalter zwischen Deutsch und Englisch wechseln. Beim ersten Start gilt die Browsersprache. Deine eigenen Block-, Spalten- und Linknamen werden nie übersetzt. Die Beispielinhalte entstehen in der Sprache des ersten Starts.
- **Lesezeichen-Import:** **Import** liest jetzt auch Lesezeichen-Dateien (HTML) aus Chrome, Edge, Firefox und Safari. Ein Auswahlfenster zeigt alle Ordner und Links mit Haken, Suche und "Alle / Keine / Nur neue". Anordnung: Ordnerstruktur übernehmen (Ordner wird Block, Unterordner wird Spalte, grosse Ordner werden in Spalten zu höchstens 20 Links geteilt) oder flach in Spalten "Import 1, 2, 3 …". Farbe: abwechselnd pro Spalte oder eine Farbe, aus allen vier Paletten. Schon vorhandene Links, Doppelte in der Datei und nicht öffenbare Adressen (`chrome://`, `file://`) werden angezeigt, aber abgewählt. Der Link-Check für importierte Links ist standardmässig aus.

### Geändert
- **Die Kaffeepause ist jetzt optional und standardmässig aus.** Wer sie bisher nutzte, schaltet sie einmalig in den Einstellungen unter *Funktionen* ein. Die Einstellungen zu Zeiten, Ton und Vorschau erscheinen erst, wenn der Haken gesetzt ist.
- **Mehr Link-Arten:** Adressen ohne `//` wie `spotify:…`, `facetime:…`, `maps:…`, `geo:…` bleiben jetzt unverändert (bisher wurde ihnen fälschlich `https://` vorangestellt). `javascript:`, `data:`, `vbscript:` und `blob:` werden nicht mehr angenommen. Der Lesezeichen-Import übernimmt jetzt auch App-Links und andere Adressarten (nicht `file:`, `chrome:`, `about:` und ähnliche). Favicon-Anfragen an Google gehen nur noch für Web-Links (`http`, `https`).
- Uhr- und Pauseneinstellungen sind aus dem Uhr-Dialog in die zentralen Einstellungen umgezogen. Bestehende Werte werden automatisch übernommen (`startseite-v1-clock` wird zu `startseite-v1-settings`).
- Bei ausgeschalteter Statistik wird kein täglicher Klickverlauf mehr aufgezeichnet. Der einfache Klickzähler pro Link läuft weiter, weil ihn die Kachel "Top-Links" und die Sortierung "Meiste Klicks" brauchen.
- Die Kopfzeile ist kompakter, sodass Wetter, Uhr und Buttons ab etwa 1366 px Fensterbreite in einer Zeile bleiben, auch im Bearbeitungsmodus.

### Dokumentation
- README: neuer Abschnitt *Link-Arten* mit Beispielen und Einschränkungen; Datenschutz-Abschnitt überarbeitet (Übersicht "Auf einen Blick", Hinweise zu Drittanbieter-Cookies, fehlender Integritätsprüfung für SortableJS, Personendaten in `mailto:`/`tel:`-Kacheln, Wetter-Anfrage mit Bern als Standardort).
- README (Deutsch und Englisch): wo die Daten in Chrome, Edge, Firefox und Safari gespeichert werden, welche externen Dienste kontaktiert werden, Hinweise für den Einsatz in der IT, Schweizer Datenschutzrecht (DSG) und der Safari-Hinweis zur 7-Tage-Grenze beim Speicher samt Empfehlung, in Safari die lokale Datei zu nutzen.

### Kompatibilität
- Exporte aus 1.0.0 lassen sich importieren. Neue Felder (Kachelform, Link-Check, Klickverlauf) sind optional.

## [1.0.0] - 2026-11-04

Erste öffentliche Version.

### Neu
- Link-Kacheln mit Name, Adresse und Farbe, breit oder quadratisch, Öffnen in neuem Tab.
- Blöcke, Spalten und Kacheln mit editierbaren Titeln und Drag-and-Drop.
- Sortieren pro Spalte (A–Z, Farbe, meiste Klicks), Farbfilter und Live-Suche.
- Kachel "Top-Links" (Top 5 oder Top 10).
- Wetter mit Aussentemperatur (Open-Meteo), digitale Uhr mit Kaffeepausen-Animation um 09:30 und 15:00.
- Drei Farbpaletten, dunkles und helles Design, responsives Layout.
- Export und Import als JSON-Datei.
- README auf Deutsch und Englisch, MIT-Lizenz.

[Unveröffentlicht]: https://github.com/alpine-marmot/linkboard/compare/v1.0.0...HEAD
[1.0.0]: https://github.com/alpine-marmot/linkboard/releases/tag/v1.0.0
