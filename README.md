# Handout-Vorlage im Stil der Universität-Leipzig-Präsentation

A4-Vorlage mit dem Logo und der Farbpalette der bereitgestellten Präsentation. Ein schmaler Streifen aus roten und aquamarinen Dreiecken wiederholt deren geometrische Gestaltung am rechten Seitenrand. Der Textbereich bleibt davon frei.

## Schnellstart

1. Den gesamten Ordner für ein neues Handout kopieren.
2. Titel, Name, Institut, Veranstaltung und Datum in `Angaben.tex` eintragen.
3. Die Beispielinhalte in `main.tex` ersetzen.
4. `main.tex` mit **XeLaTeX oder LuaLaTeX** zweimal kompilieren. Der zweite Durchlauf setzt Seitenverweise und Hintergrundpositionen korrekt.

In Overleaf den Ordnerinhalt hochladen, `main.tex` als Hauptdatei und XeLaTeX als Compiler auswählen.

Lokal mit latexmk:

```text
latexmk main.tex
```

Oder direkt:

```text
xelatex -interaction=nonstopmode -halt-on-error main.tex
xelatex -interaction=nonstopmode -halt-on-error main.tex
```

LuaLaTeX kann auf dieselbe Weise verwendet werden. pdfLaTeX wird wegen `fontspec` nicht unterstützt. Die benötigten Pakete gehören zu üblichen TeX-Live- und MiKTeX-Installationen. Es sind weder Shell-Escape noch ein Literaturprogramm nötig.

## Dateien

| Datei | Inhalt |
|---|---|
| `main.tex` | Zwei Beispielseiten mit Text, Tabelle, Merksatz, Formel und Notizzeilen |
| `Angaben.tex` | Wiederverwendbare Angaben zu Titel und Veranstaltung |
| `leipzig-handout.sty` | Farben, Schrift, Abstände, Randmuster und Kopf-/Fußzeilen |
| `images/logo_leipzig.pdf` | Unverändertes Logo aus der Ausgangspräsentation |
| `.latexmkrc` | Build-Einstellungen für XeLaTeX |

## Inhalt und Gestaltung anpassen

- **Neue Abschnitte:** `\section{Titel}` und `\subsection{Titel}` verwenden. Für Überschriften ohne Nummer eignet sich `\section*{Titel}`.
- **Merksatz:** `\begin{merksatz}[Eigener Titel] ... \end{merksatz}`. Der Kasten kann bei längeren Texten über Seiten umbrechen.
- **Notizzeilen:** `\notizlinien[4]` erzeugt vier Linien.
- **Quellenhinweis:** `\quelle{Ihre Angabe}` setzt eine kleine graue Quellenzeile.
- **Seitenumbrüche:** Der Inhalt fließt wie in einem normalen Textdokument automatisch weiter. Das `\newpage` im Beispiel dient nur der Demonstration und kann entfernt werden. Tabellen in `tabularx` bleiben zusammen; für Tabellen über mehrere Seiten eignet sich ein entsprechendes Langtabellen-Paket.
- **Randmuster ausblenden:** In `main.tex` die Zeile `\Randmusterfalse` aktivieren.
- **Farben oder Muster ändern:** Die Farbcodes und die beschrifteten TikZ-Pfade stehen am Anfang von `leipzig-handout.sty`.
- **Schrift:** Arial, falls vorhanden; andernfalls TeX Gyre Heros. Bei einem anderen Rechner können dadurch leichte Unterschiede im Zeilenumbruch entstehen.
- **Druck:** Das Muster reicht bis an die rechte Blattkante. Ein Drucker ohne Randlosdruck kann den äußersten Teil abschneiden. Der Text und die Fußzeile liegen innerhalb der Druckränder.

Die Gestaltung ist aus der bereitgestellten Präsentation abgeleitet. Die Beispieltexte und Literaturangaben sind Platzhalter und enthalten keine Studienergebnisse. Die vorhandene Präsentation bleibt unverändert.
