# Datenquellen Entlassungsassistent

## Im Repo
| Datei | Inhalt | Herkunft und Lizenz |
|---|---|---|
| `beispielfall_01.md` | Ein Fall mit Diagnose, Eingriff und Verlauf als Eingabe | Frei erfunden für den Hackathon, medizinisch nicht geprüft. Frei verwendbar. |
| `grascco/` | 62 synthetische deutsche Arztbriefe als Stilvorlage für den Brief-Baustein | [GraSCCo, Zenodo 10.5281/zenodo.6539131](https://doi.org/10.5281/zenodo.6539131), CC BY 4.0 |

## Fachliche Grundlagen (nur verlinkt, nicht kopiert)
| Quelle | Wofür | Hinweis |
|---|---|---|
| [Nachbehandlungsempfehlungen des Arbeitskreises Traumarehabilitation der DGOU](https://dgou.de/q-s/empfehlungen-in-o-und-u/) | Phasen, Ziele und Maßnahmen der Nachbehandlung nach Verletzungen und Operationen, gegliedert nach Körperregion | Als PDF frei abrufbar, aber urheberrechtlich geschützt. Nicht ins Repo kopieren. Die aktuelle Auflage auf der Seite prüfen. |
| Hausinterne Nachbehandlungsschemata der Teammitglieder | Vorlage für das eigene Schema | Nur verwenden, wenn die eigene Klinik zustimmt. Keine Patientendaten. |

## Empfehlung für den Hackathon
- Das Nachbehandlungsschema schreibt das Medizin-Team selbst in `vorlagen/nachbehandlung.md`, in eigenen Worten und mit Quellenangabe. Die KI passt es nur an den Fall an.
- GraSCCo-Briefe mit orthopädisch-unfallchirurgischem Bezug als Stilbeispiele heraussuchen. Die Texte sind medizinisch nicht immer plausibel, als Vorlage für Ton und Aufbau aber gut geeignet.
- Einen zweiten Fall im selben Format wie `beispielfall_01.md` schreiben und als Blind-Fall verwenden.

## Bei Verwendung angeben
Modersohn L, Schulz S, Lohr C, Hahn U. GRASCCO – The First Publicly Shareable, Multiply-Alienated German Clinical Text Corpus. Stud Health Technol Inform. 2022;296:66-72.
