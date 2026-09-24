# Entwurfsatelier

Ein Werkzeug zum Entwerfen von Kleidung — nicht zum Konstruieren von
Schnittmustern. Es zeigt, wie ein Kleidungsstück aussehen soll; der
eigentliche Schnitt entsteht danach in Seamly2D.

**Live:** https://nahol2021.github.io/entwurfsatelier/

## Wie es funktioniert

Ein Kleidungsstück besteht aus einer **Basis** (Oberteil, Hose),
austauschbaren **Bausteinen** je Steckplatz und **Details** obendrauf.
Aus 2 Basen und ihren Bausteinen ergeben sich 1340 Kombinationen.

- **Vorne und hinten sind gekoppelt.** Weite, Länge, Ärmel und Körperform
  gelten für beide Ansichten; Halsausschnitt und Details getrennt.
- **Symmetrisch oder asymmetrisch.** Beim Umschalten wird die rechte Seite
  einmal nach links kopiert, danach lassen sich beide getrennt ändern.
- **Drei Reiter.** Bausteine · Form (Regler) · Punkte (frei ziehen).
- **Eigene Entwürfe werden zu Basen.** Was im Inventar liegt, ist ein
  neuer Ausgangspunkt.

## Technik

Eine einzige HTML-Datei, keine Abhängigkeiten außer einer Schrift von
Google Fonts. Kein Build, kein Server. Die Kontur wird als zwei Ketten
aus Knotenpunkten gespeichert (rechte und linke Seite), daraus entstehen
kubische Bézierkurven, deren Ecken tangential verrundet werden.

Das Inventar liegt im `localStorage` des Browsers und hängt damit an der
Adresse der Seite. Über „Inventar sichern / einlesen" lässt es sich als
JSON-Datei mitnehmen.
