# Helix Editor Dokumentation

## Einführung

Helix ist ein moderner, modaler Texteditor. Modales Editieren bedeutet, dass wir in verschiedenen Modi mit Text arbeiten können. Die zwei Hauptmodi sind:

- Normalmodus: Tasten führen Befehle aus, anstatt Zeichen zu tippen
- Einfügemodus: Wird zum Eingeben von Zeichen verwendet

## Grundlegende Bewegung

Cursorbewegung im Normalmodus:

- `h` - links
- `j` - runter
- `k` - hoch
- `l` - rechts

## Beenden

- `:q` oder `:quit` - beenden (nur wenn keine ungespeicherten Änderungen)
- `:q!` oder `:quit!` - beenden ohne ungespeicherte Änderungen
- `:wq` oder `:write-quit` - speichern und beenden

## Löschen und Einfügen

- `d` - Zeichen unter dem Cursor löschen
- `i` - Einfügemodus vor dem Cursor aktivieren
- `a` - Einfügemodus nach dem Cursor aktivieren (append)
- `I` - Einfügemodus am Zeilenanfang aktivieren
- `A` - Einfügemodus am Zeilenende aktivieren
- `o` - neue Zeile unten einfügen und Einfügemodus aktivieren
- `O` - neue Zeile oben einfügen und Einfügemodus aktivieren

## Speichern

- `:w` oder `:write` - aktuelle Datei speichern
- Optionaler Dateiname/Pfad kann angegeben werden

## Bewegung und Auswahl

- `w` - vorwärts zum Anfang des nächsten Wortes
- `e` - vorwärts zum Ende des aktuellen Wortes
- `b` - rückwärts zum Anfang des aktuellen Wortes
- `W`, `E`, `B` - wie Kleinbuchstabenvarianten, aber nur bei Leerzeichen stoppen

## Änderungsbefehle

- `c` - ausgewählten Text löschen und Einfügemodus aktivieren
- `d` - ausgewählten Text löschen
- Zahl + Befehl: Befehl mehrmals ausführen (z.B. `2w`)

## Auswahlmodus

- `v` - Auswahlmodus ein/ausschalten
- `x` - ganze Zeile auswählen
- `;` - Auswahl auf Cursor reduzieren

## Kopieren und Einfügen

- `y` - ausgewählten Text kopieren (yank)
- `p` - nach dem Cursor einfügen
- `P` - vor dem Cursor einfügen
- `Space + y/p` - Operationen mit der Systemzwischenablage

## Suchen

- `/` - vorwärts suchen
- `?` - rückwärts suchen
- `n` - nächster Treffer
- `N` - vorheriger Treffer
- Unterstützt reguläre Ausdrücke

## Mehrfachcursor

- `C` - Cursor zur nächsten passenden Zeile duplizieren
- `Alt-C` - Cursor zur vorherigen passenden Zeile duplizieren
- `s` - Übereinstimmungen im ausgewählten Text auswählen
- `&` - Auswahlungen ausrichten

## Weitere Funktionen

- `u` - rückgängig machen
- `U` - wiederherstellen
- `.` - letzte Einfügung wiederholen
- `~` - Groß-/Kleinschreibung umschalten
- `` ` `` - in Kleinbuchstaben umwandeln
- `Alt-`` ` ``- in Großbuchstaben umwandeln
- `Ctrl-c` - Zeile kommentieren/Kommentar entfernen

## Fensterverwaltung

- `Ctrl-w nv` - neue vertikale Teilung
- `Ctrl-w ns` - neue horizontale Teilung
- `Ctrl-w h/j/k/l` - zwischen Fenstern wechseln
- `Ctrl-w q` - aktuelles Fenster schließen
- `Ctrl-w o` - alle anderen Fenster schließen
- `:vs` / `:hs` - Teilung mit Dateinamen öffnen

## Match-Modus

Der Match-Modus, aktiviert mit der `m`-Taste, wird für die Behandlung von Klammern und anderen gepaarten Zeichen verwendet:

- `mm` - zum passenden Zeichen springen
- `mi(` - Inhalt zwischen Klammern auswählen
- `ma(` - Klammern und deren Inhalt auswählen
- `ms(` - ausgewählten Text mit Klammern umschließen
- `md(` - umschließende Klammern löschen
- `mr([` - Klammern durch anderen Typ ersetzen

Andere gepaarte Zeichen können anstelle von Klammern verwendet werden, z.B. `{}`, `[]`, `""`, `''`.

## Register-Nutzung

Register sind zeichenidentifizierte Container, die verschiedenen Zwecken dienen können:
- Text kopieren/ausschneiden
- Suchausdrücke speichern
- Makros speichern

- `"<ch>` - Register auswählen (z.B. `"a`)
- Mit `y`-Befehl in ausgewähltes Register speichern
- Mit `p` oder `P` aus ausgewähltem Register einfügen

## Makros

Makros sind Befehlssequenzen, die später wiedergegeben werden können:

- `Q` - Makroaufzeichnung starten (Standard: `@`-Register)
- `Q` - Makroaufzeichnung beenden
- `q` - Makro aus `@`-Register abspielen
- `"<ch>Q` - Makro in bestimmtes Register aufzeichnen
- `"<ch>q` - Makro aus bestimmtem Register abspielen

## Suchen und Auswahl

- `*` - nach Wort unter dem Cursor suchen
- `n`/`N` im `v`-Modus - neue Auswahl zum nächsten/vorherigen Treffer hinzufügen
- `Ctrl-s` - Position in Sprungsliste speichern
- `Ctrl-i`/`Ctrl-o` - vor/zurück in der Sprungsliste
- `gw` - Zwei-Zeichen-Labels für schnelle Navigation anzeigen

## Auswahlverwaltung

- `)` / `(` - primäre Auswahl vor/zurück bewegen
- `Alt-,` - primäre Auswahl entfernen
- `Alt-)` / `Alt-(` - Auswahlinhalt tauschen
- `S` - Auswahlen basierend auf Regex-Muster aufteilen

## Zeilenmanipulation

- `J` - ausgewählte Zeilen verbinden
- `>` / `<` - Einrückung erhöhen/verringern
- `Ctrl-a` / `Ctrl-x` - Zahl erhöhen/verringern

## Erweiterte Fensterverwaltung

- `Ctrl-w t` - Fensteranordnung transponieren
- `Ctrl-w H/J/K/L` - Fenster in angegebene Richtung verschieben
- `Space f` - Dateiauswahl öffnen
  - `Ctrl-v` - ausgewählte Datei in vertikaler Teilung öffnen
  - `Ctrl-s` - ausgewählte Datei in horizontaler Teilung öffnen

## Tipps und Tricks

1. Die meisten Befehle können kombiniert werden:
   - Zahl + Befehl: mehrfache Ausführung
   - Register + Befehl: Operation mit bestimmtem Register
   - Bewegung + Operation: Operation auf durch Bewegung ausgewähltem Text

2. Effiziente Bearbeitungsstrategien:
   - `.`-Befehl für wiederholte Änderungen verwenden
   - Mehrfachcursor für paralleles Bearbeiten
   - Match-Modus für strukturierten Text
   - Makros für komplexe Operationssequenzen

3. Suchen und Ersetzen:
   - Auswahl im betroffenen Bereich
   - `s`-Befehl zum Auswählen von Musterübereinstimmungen
   - `c`-Befehl zum Ausführen der Änderung

4. Fensterverwaltungsmuster:
   - Vertikale Teilung für paralleles Code- und Dokumentationsbearbeiten
   - Horizontale Teilung zum Vergleichen verschiedener Dateiteile
   - Mehrere Fenster zum Anzeigen von Referenzmaterialien

## Konfiguration

Helix kann konfiguriert werden über:
- `~/.config/helix/config.toml` - allgemeine Einstellungen
- `~/.config/helix/languages.toml` - sprachspezifische Einstellungen

Für detaillierte Konfigurationsoptionen siehe die offizielle Dokumentation.

## Zusammenfassung

Helix ist ein leistungsstarker, moderner Texteditor, der:
- Modales Editieren für Effizienz nutzt
- Umfangreiche Befehls- und Funktionshandhabung bietet
- Mehrfachcursor und -auswahlen unterstützt
- Flexible Fensterverwaltung ermöglicht
- Konfigurierbar und erweiterbar ist

Für effektive Nutzung:
1. Grundlegende Bewegungs- und Bearbeitungsbefehle lernen
2. Fortgeschrittene Funktionen schrittweise beherrschen
3. Konfiguration an eigene Arbeitsabläufe anpassen
4. Regelmäßig neue Befehle üben
