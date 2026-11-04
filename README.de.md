# Linkboard

Deutsch · [English](README.md)

Eine Browser-Startseite in einer einzigen Datei: deine Links als farbige Kacheln, gegliedert in Blöcke und Spalten, dazu Wetter, Uhr und Suchleiste. Kein Build-Schritt, kein Framework, kein Konto. Alles wird in deinem Browser gespeichert.

<img width="1384" height="678" alt="Bildschirmfoto 2026-11-04 um 08 59 09" src="https://github.com/user-attachments/assets/fdaab89a-ad26-41a0-8cfb-505b6af49a88" />

## Funktionen

- **Link-Kacheln** mit Name, Adresse und Farbe (3 Farbpaletten plus freie Farbwahl), Öffnen in einem neuen Tab
- **Zwei Kachelformen**: breite Buttons oder quadratische Kacheln (zwei pro Reihe, so hoch wie zwei breite Buttons)
- **Blöcke → Spalten → Kacheln**, alle mit editierbaren Titeln und Drag-and-Drop (auch auf Touchscreens)
- **Sortieren** pro Spalte: A–Z, nach Farbe oder nach meisten Klicks; Filter nach Farbe; Live-Suche (Enter öffnet den ersten Treffer)
- **Top-Links-Kachel**: zeigt die meistgeklickten Links, Top 5 oder Top 10
- **Wetter und Aussentemperatur** oben rechts (Open-Meteo, kein API-Schlüssel); per Klick änderst du den Ort
- **Digitale Uhr** (24 h oder 12 h AM/PM) mit einer **Kaffeepause**-Animation um 09:30 und 15:00 für eine Minute (Zeiten einstellbar)
- **Dunkles und helles Design**
- **Responsiv**, nutzt die volle Browserbreite
- **Export / Import** als JSON-Datei für Sicherungen

<img width="1380" height="771" alt="Bildschirmfoto 2026-11-04 um 08 58 42" src="https://github.com/user-attachments/assets/f72bfd70-3cb6-4712-8bac-1c1888650438" />
<img width="418" height="487" alt="Bildschirmfoto 2026-11-04 um 08 57 56" src="https://github.com/user-attachments/assets/87d5afd3-28f6-4650-9d96-fc66acd062ff" />

## Schnellstart

1. `index.html` herunterladen.
2. Im Browser öffnen.
3. Oben rechts auf **Bearbeiten** klicken, um Blöcke, Spalten und Links anzulegen.
4. Optional: die Datei als Startseite des Browsers eintragen, z. B. `file:///Pfad/zu/index.html`.

Du kannst die Seite auch mit **GitHub Pages** veröffentlichen (Settings → Pages → Deploy from branch `main`, Ordner `/root`) und diese Adresse als Startseite nutzen. Über https funktioniert die Wetterabfrage auch in Browsern, die lokale Dateien einschränken, etwa Safari.

## Bedienung

| Was | Wie |
| --- | --- |
| Etwas hinzufügen / ändern / löschen | **Bearbeiten** klicken, dann die Buttons in Kopfzeile, Blöcken, Spalten und Kacheln benutzen |
| Kacheln, Spalten, Blöcke verschieben | Bearbeitungsmodus, Drag-and-Drop (Touchscreen: kurz gedrückt halten) |
| Spalte sortieren | Bearbeitungsmodus, Menü „Sortieren“ im Spaltenkopf |
| Uhr und Pausenzeiten | auf die Uhr klicken |
| Wetterort | auf das Wetter klicken |
| Sicherung | Bearbeitungsmodus, **Export** / **Import** |

## Daten und Datenschutz

Alles liegt im lokalen Speicher deines Browsers, pro Browser und Gerät. Mit **Export** sicherst du deine Links oder nimmst sie mit (Klickzähler sind enthalten; Uhr-Einstellungen, Design, Palette und Wetterort nicht).

Die Seite kontaktiert diese Dienste:

- [Open-Meteo](https://open-meteo.com) für das Wetter (die Koordinaten des gewählten Ortes)
- den Favicon-Dienst von Google für die kleinen Link-Symbole (die Domainnamen deiner Links)
- [cdnjs](https://cdnjs.com) für die Drag-and-Drop-Bibliothek [SortableJS](https://github.com/SortableJS/Sortable)

Der Standardort für das Wetter ist Bern; per Klick auf das Wetter änderst du ihn.

## Lizenz

[MIT](LICENSE)
