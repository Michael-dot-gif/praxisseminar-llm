# LLM-gestützte Fragebogenentwicklung mit NotebookLM

## Projektziel
Dieses Repository dokumentiert die Entwicklung eines Leitlinien- und Prompt-Systems zur wissenschaftlich fundierten, LLM-gestützten Erstellung und Vorprüfung von Fragebögen in NotebookLM.

Das Artefakt wurde im Rahmen eines Design-Science-Research-Prozesses entwickelt und iterativ von Version 1 zu Version 2 weiterentwickelt.

## Problemstellung
Die automatisierte Erstellung wissenschaftlicher Fragebögen mit Large Language Models bietet Potenziale hinsichtlich Geschwindigkeit, Strukturierung und Quellenverarbeitung. Gleichzeitig bestehen Risiken wie Halluzinationen, unklare Itemherkunft, semantische Fehlzuordnungen und die Gefahr, heuristische LLM-Prüfungen mit empirischer Validierung zu verwechseln.

Das entwickelte Leitlinienmodell adressiert diese Probleme durch:
- konsequente Quellenbindung,
- Human-in-the-Loop-Kontrollpunkte,
- transparente Item-Herkunft,
- getrennte inhaltliche und sprachlich-methodische Reviews,
- klare Abgrenzung zwischen LLM-gestützter Vorstrukturierung und empirischer Validierung.

## Artefakt
Das finale Artefakt besteht aus einem vierphasigen Leitlinien- und Prompt-System:

1. Quellengrundierung und Konstruktspezifikation
2. Itemgenerierung und Herkunftstaxonomie
3. Zweistufige heuristische Prüfung
4. Ergebnismatrix und Pretest-Vorbereitung

Zwischen den Phasen sind verbindliche Human-in-the-Loop-Gates integriert.

## Demonstrationsfall
Das Artefakt wurde am Anwendungsfall „KI-Readiness von Mitarbeitenden“ demonstriert.

Hierzu wurden unter anderem Konstrukte wie Selbstwirksamkeit und Kognition, Optimismus und Comfort, Mensch-KI-Kollaboration sowie wahrgenommenes organisationales Enablement berücksichtigt.

Das Ergebnis der Demonstration ist ein heuristisch bereinigter 15-Item-Fragebogenentwurf. Dieser stellt kein empirisch validiertes Messinstrument dar.

## Evaluation
Die erste Version des Artefakts wurde praktisch getestet und anschließend systematisch evaluiert.

Zentrale Schwächen von Version 1 waren:
- unpräzise Herkunftskennzeichnung,
- zu starke Validitätsformulierungen,
- starre Vorgaben zu Überpoolung und Antwortskalen,
- zu wenige Human-in-the-Loop-Kontrollpunkte.

Diese Punkte wurden in Version 2 gezielt überarbeitet.

## Repository-Struktur

- `artifact/leitlinienmodell-v2.md` – finale Leitlinien
- `artifact/prompt-system-v2.md` – direkt einsetzbare NotebookLM-Prompts
- `demonstration/ki-readiness-demonstration.md` – Demonstration des Artefakts
- `evaluation/evaluation-v1-v2.md` – Evaluation und Iteration von V1 zu V2
- `notebooklm/notebooklm-chatverlauf.docx` – vollständiger NotebookLM-Chatverlauf
- `notebooklm/zugangslink.md` – Zugriff auf das verwendete NotebookLM-Projekt
- `literature/quellenuebersicht.md` – Übersicht der verwendeten Literatur

## Methodische Abgrenzung
Das Artefakt unterstützt die theoriegeleitete Konstruktion, Strukturierung und heuristische Vorprüfung von Fragebögen.

Es ersetzt keine:
- kognitiven Pretests mit realen Personen,
- empirischen Feldstudien,
- Reliabilitäts- oder Validitätsanalysen,
- Faktorenanalysen,
- Item-Response-Analysen.

Empirische Güte kann erst anhand realer Befragungsdaten geprüft werden.
