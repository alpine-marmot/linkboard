# Änderungsprotokoll (Changelog)

Deutsch · [English](CHANGELOG.md)

Hier stehen alle wichtigen Änderungen an Linkboard. Das Format folgt [Keep a Changelog](https://keepachangelog.com/de/1.1.0/), die Versionsnummern folgen der [Semantischen Versionierung](https://semver.org/lang/de/).

## [Unreleased]

## [1.1.0] 2026-11-04

### Neu
- **Link-Check:** Ein optionaler grüner oder roter Punkt in jeder Kachel zeigt, ob der Server des Links antwortet. Scheitert die erste Anfrage, folgt ein zweiter Versuch mit einer anderen Anfrageart. Die Ergebnisse werden 15 Minuten zwischengespeichert. Ein grauer Punkt heisst "nicht geprüft" (Prüfung läuft noch, offline oder von der Seite aus nicht prüfbar, zum Beispiel `http://`-Links und lokale Adressen bei einer über https ausgelieferten Seite). Der Check lässt sich pro Link abschalten.
- **Statistik:** Ein neuer Button neben den Farbpunkten öffnet eine Diagrammansicht mit den 10 meistgeklickten Links und dem Klickverlauf pro Tag (14 Tage), Woche (12 Wochen) oder Monat (12 Monate), für alle Links oder einen einzelnen.
- **Einstellungen** (Zahnrad oben rechts; auch die Uhr öffnet sie): Uhrformat (24 h oder 12 h AM/PM), Pausenzeiten, Pausen-Erinnerung nur optisch oder mit kurzem Signalton, Link-Check ein/aus, Statistik ein/aus.
- **Pausen-Erinnerung mit Ton** (optional): ein kurzer Zweiklang zu Beginn der Kaffeepause. Browser erlauben ihn erst, nachdem du die Seite einmal angeklickt hast.
- **Vierte Farbpalette:** Graustufen.
- **Alle öffnen:** Ein Button im Kopf jeder Spalte öffnet alle Links dieser Spalte mit einem Klick in neuen Tabs (jeder zählt als Klick).
- Die Seite bittet den Browser, bei keiner Anfrage einen Referrer zu senden.

### Geändert
- Uhr- und Pauseneinstellungen sind aus dem Uhr-Dialog in die zentralen Einstellungen umgezogen. Bestehende Werte werden automatisch übernommen (`startseite-v1-clock` wird zu `startseite-v1-settings`).
- Bei ausgeschalteter Statistik wird kein täglicher Klickverlauf mehr aufgezeichnet. Der einfache Klickzähler pro Link läuft weiter, weil ihn die Kachel "Top-Links" und die Sortierung "Meiste Klicks" brauchen.
- Die Kopfzeile ist kompakter, sodass Wetter, Uhr und Buttons ab etwa 1366 px Fensterbreite in einer Zeile bleiben, auch im Bearbeitungsmodus.

### Dokumentation
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

[Unveröffentlicht]: https://github.com/alpine-marmot/linkboard/compare/v1.1.0...HEAD
[1.1.0]: https://github.com/alpine-marmot/linkboard/compare/v1.0.0...v1.1.0
