# Frontend Toolchain

Übung 05 der HTL Krems mit npm, Sass, Bootstrap, Bootstrap Icons und BrowserSync. Die Beispielseite verwendet ein responsives Grid, Buttons und lokal eingebundene Icons.

## Voraussetzungen

- Node.js 22 oder neuer inklusive npm
- Git für das Klonen

## Installation

1. Klone das Repository und wechsle in den Projektordner.

   ```sh
   git clone https://github.com/SimonTrachsler/bootstrap-sass-project.git
   cd bootstrap-sass-project
   ```

   Wenn du den Projektordner bereits lokal hast, öffne dort ein Terminal.

2. Installiere die Abhängigkeiten und erzeuge die CSS-Datei.

   ```sh
   npm install
   npm run scss:build
   ```

   Falls PowerShell das Skript `npm.ps1` blockiert, verwende `npm.cmd` anstelle von `npm`.

## Entwicklung mit Live-Reload

1. Starte im ersten Terminal `npm run scss:watch`. Sass kompiliert beim Start und nach jeder Änderung am SCSS.
2. Starte im zweiten Terminal `npm run serve`. Öffne danach `http://127.0.0.1:3000`. Falls Port 3000 belegt ist, zeigt BrowserSync den verwendeten Port im Terminal an.
3. Ändere zum Testen den Text der Überschrift in `index.html`. BrowserSync lädt die Seite neu. Ändere anschließend `$primary` in `src/scss/style.scss`. Nach dem Sass-Build erscheinen die neuen Farben automatisch im Browser.
4. Beende die Prozesse mit `Strg+C` im jeweiligen Terminal.

| Befehl | Funktion |
| --- | --- |
| `npm run scss:build` | Erstellt einmalig minifiziertes CSS und kopiert die Icon-Schriften nach `dist/css/fonts/`. |
| `npm run scss:watch` | Überwacht SCSS-Änderungen und erstellt bei Bedarf neues CSS mit Source Map. |
| `npm run serve` | Startet BrowserSync und beobachtet HTML-Dateien und CSS in `dist/css/`. |

## Projektstruktur

- `index.html` enthält die Beispielseite und bindet das generierte Stylesheet ein.
- `src/scss/style.scss` enthält die Bootstrap-Variablen, die globalen Regeln, das Grid, die Buttons, ausgewählte Utilities und Bootstrap Icons.
- `dist/css/` entsteht beim Build und enthält `style.css` sowie die Icon-Schriften. Git ignoriert diesen Ausgabeordner und `node_modules/`.
