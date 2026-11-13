# 07 · Entlassungsassistent

> Prototyp für den AKKI Hackathon 2026. Nur Beispielfälle, kein Medizinprodukt, kein Ersatz für ärztliche Beurteilung.

**Bereich:** Entlassung

**Idee:** Aus Diagnose, Verlauf und OP oder Behandlung erstellt die KI automatisch einen Entlassungsbrief-Baustein und ein individualisiertes Nachbehandlungsschema.

**Vorschlag zur Eingrenzung:** Eine Verletzung, ein Beispielfall. Die KI schreibt den Abschnitt „Verlauf und Procedere“ und ein Nachbehandlungsblatt für die Patientin oder den Patienten.

## Warum
Entlassungsdokumentation und individuelle Nachbehandlungspläne werden für ähnliche Fälle immer wieder von Hand neu erstellt.

## Was am Ende stehen soll
- Eingabe von Diagnose, Verlauf und OP oder Behandlung (Freitext oder Formular)
- Automatisch erzeugter Entlassungsbrief-Baustein
- Individualisiertes Nachbehandlungsschema (Termine, Reha-Hinweise)

**Erfolgskriterium:** Für mindestens einen Beispielfall liegen Brief und Schema vor.

## So startet ihr
1. Oben auf **Code → Download ZIP** klicken und entpacken.
2. Im entpackten Ordner ein Terminal öffnen und `claude` eingeben.
3. `SPICKZETTEL.md` öffnen und mit Block 1 beginnen.

## Was in diesem Repo liegt
| Datei | Wofür |
|---|---|
| `SPICKZETTEL.md` | Umsetzungsplan für 8 Stunden, Block für Block |
| `CLAUDE.md` | Regeln, an die sich Claude Code hält |
| `daten/QUELLEN.md` | Beispielbriefe und Nachbehandlungsempfehlungen mit Lizenz |
| `daten/beispielfall_01.md` | Ein frei erfundener Fall als Eingabe |
| `daten/grascco/` | 62 synthetische deutsche Arztbriefe als Stilvorlage |

## Stolpersteine
- Inhaltliche Korrektheit sicherstellen: Das Nachbehandlungsschema kommt aus einer vom Team hinterlegten Vorlage, nicht aus dem Wissen der KI
- Umfang auf einen Beispielfall begrenzen
- Brief für Kolleginnen und Kollegen und Blatt für Patientinnen und Patienten sind zwei verschiedene Texte

## Für Erfahrene
- Nachbehandlungsblatt zusätzlich in einfacher Sprache
- Termine als Kalenderdatei exportieren
- Zweite Verletzung mit eigener Vorlage ergänzen und zeigen, dass die App die richtige wählt
