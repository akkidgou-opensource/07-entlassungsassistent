# Spickzettel Entlassungsassistent · 8 Stunden

Acht Blöcke. Jeden Prompt in Claude Code kopieren, das Ergebnis prüfen, dann weiter. Wer schneller ist, baut frei, die „Fertig, wenn“-Punkte gelten trotzdem.

| Block | Zeit | Thema |
|---|---|---|
| 1 | 30 Min. | Setup |
| 2 | 60 Min. | Vorgaben: Briefaufbau und Nachbehandlungsvorlage |
| 3 | 45 Min. | Eingabeformular |
| 4 | 60 Min. | KI schreibt den Brief-Baustein |
| 5 | 75 Min. | Nachbehandlungsschema mit Terminen |
| 6 | 75 Min. | Auf Richtigkeit prüfen |
| 7 | 45 Min. | Bearbeiten, Drucken, Robustheit |
| 8 | 60 Min. | Ergebnis, Demo, Pitch |

Bleiben 30 Minuten Puffer.

## Block 1 · Setup
Schlüssel eintragen: `.env.example` zu `.env` kopieren und den ausgehändigten Schlüssel eintragen (im Texteditor, nicht über Claude Code).
```
Lies README.md und CLAUDE.md und sieh dir daten/beispielfall_01.md an. Prüfe, ob Node.js ab Version 20 installiert ist, und lege die leeren Ordner prompt, vorlagen und ergebnisse an. Sag mir in drei Sätzen, was als Nächstes kommt.
```
**Fertig, wenn:** Node passt und `.env` existiert.

## Block 2 · Vorgaben (ohne Code)
Der wichtigste Block, die Qualität der App entscheidet sich hier.
- **Eine** Verletzung auswählen (Vorschlag: die aus dem Beispielfall)
- `spec.md`: Aufbau des Brief-Bausteins (Abschnitte, Länge, Ton)
- `vorlagen/nachbehandlung.md`: das Nachbehandlungsschema für diese Verletzung, vom Medizin-Team geschrieben, nach Phasen oder Wochen gegliedert, mit Quelle (siehe `daten/QUELLEN.md`)
- Festlegen, welche Angaben individuell sind (Seite, OP-Datum, Belastung laut Operateur, Besonderheiten)

**Fertig, wenn:** Vorlage und Briefaufbau von zwei Personen gegengelesen sind.

## Block 3 · Eingabeformular
```
Baue die Grundversion: server.js und public/index.html. Ein Formular mit den Feldern Diagnose, Seite, OP oder Behandlung, OP-Datum, Entlassdatum, Verlauf (Freitext), Belastung laut Operateur, Besonderheiten. Ein Button „Beispielfall laden“ füllt das Formular mit den Angaben aus daten/beispielfall_01.md. Der Hinweis aus CLAUDE.md ist immer sichtbar.
```
**Fertig, wenn:** das Formular auf Laptop und Handy bedienbar ist.

## Block 4 · KI schreibt den Brief-Baustein
```
Ergänze den Button „Brief-Baustein erstellen“. Er schickt die Formulardaten an einen Endpunkt /api/brief, der die Anthropic Messages API aufruft. Der System-Prompt wird bei jeder Anfrage frisch aus prompt/system.md gelesen und enthält den Briefaufbau WORTGETREU aus spec.md. Die KI verwendet nur Angaben aus dem Formular, erfindet keine Befunde und schreibt „[bitte ergänzen]“, wo etwas fehlt. Schlüssel und Modell kommen nur aus .env.
```
**Fertig, wenn:** für den Beispielfall ein Brief-Baustein erscheint.

## Block 5 · Nachbehandlungsschema mit Terminen
```
Ergänze den Button „Nachbehandlungsschema erstellen“. Der Server liest vorlagen/nachbehandlung.md und gibt sie zusammen mit den Formulardaten an die KI. Die KI darf die Vorlage nur an den Fall anpassen (Seite, Daten, Besonderheiten), aber keine Phase, Frist oder Belastungsangabe ändern oder ergänzen. Berechne aus dem OP-Datum konkrete Kalenderdaten für jede Phase und jeden Kontrolltermin im Programmcode, nicht durch die KI. Ausgabe als gut lesbare Tabelle für die Patientin oder den Patienten.
```
**Fertig, wenn:** das Schema konkrete Daten zeigt und inhaltlich der Vorlage entspricht.

## Block 6 · Auf Richtigkeit prüfen
Brief und Schema Zeile für Zeile prüfen:
- Stimmen Seite, Daten, Diagnose, Eingriff?
- Weicht das Schema irgendwo von der Vorlage ab?
- Steht etwas im Brief, das nicht im Formular stand?

Funde notieren, pro Durchlauf **eine** Prompt-Änderung. Danach einen zweiten Fall selbst schreiben (andere Seite, anderes Datum, eine Besonderheit) und als Blind-Fall verwenden.

**Fertig, wenn:** drei dokumentierte Durchläufe vorliegen.

## Block 7 · Bearbeiten, Drucken, Robustheit
```
Mache beide Ergebnisse direkt auf der Seite editierbar und ergänze „Kopieren“ und „Drucken/als PDF“. Verständliche Meldungen bei fehlenden Pflichtfeldern, fehlendem Netz und Zeitüberschreitung. Fehlt die Vorlagendatei, erscheint ein klarer Hinweis statt eines erfundenen Schemas.
```
**Fertig, wenn:** der Ausdruck auf eine Seite passt und ohne Vorlage kein Schema entsteht.

## Block 8 · Ergebnis, Demo, Pitch
- Blind-Fall **einmal** laufen lassen, Ergebnis nicht nachbessern
- `ergebnis.md`: Aufbau, gefundene Fehler, Limitationen (eine Verletzung, erfundene Fälle)
- Demo zweimal durchspielen, Ausdruck als Backup
- Pitch: Problem, Live-Demo, wie geprüft, nächste Schritte
