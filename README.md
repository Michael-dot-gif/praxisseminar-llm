# LLM-gestütztes Leitlinien- und Prompt-System zur Fragebogenentwicklung (Version 2.0)

Dieses Repository enthält die Dokumentation und das finale Prompt-System für die **LLM-gestützte Erstellung und Vorevaluierung wissenschaftlicher Fragebögen** in **NotebookLM**.

---

## 1. Ziel des Projekts

Ziel des Projekts ist die Konzeption, Erprobung und Evaluation eines wissenschaftlich fundierten, praxistauglichen **Leitlinien- und Prompt-Systems (Version 2.0)**. Das System unterstützt Forschende und Praktiker dabei, Befragungsinstrumente in der Arbeits- und Organisationsforschung mithilfe von Large Language Models (LLMs) zu entwickeln. 

Das Artefakt verbindet etablierte psychometrische Phasenmodelle der Skalenentwicklung mit modernen Verfahren der KI-gestützten Item-Generierung (Retrieval-Augmented Generation, Multi-Agenten-Review) und sichert den Gesamtprozess durch verbindliche **Human-in-the-Loop-Gates (HITL-Gates)** ab.

---

## 2. Problemstellung

Die traditionelle Konstruktion wissenschaftlicher Fragebögen ist ein zeit- und ressourcenintensiver Prozess, der von der theoretischen Domain-Definition über qualitative Pretests bis hin zur psychometrischen Feldvalidierung reicht (*Artino et al., 2014; Boateng et al., 2018; Morgado et al., 2017*). Der naive oder unstrukturierte Einsatz von Sprachmodellen zur Fragebogenerstellung birgt jedoch erhebliche methodische Risiken:

* **Theoretical Drift & Halluzinationen:** Ohne strikte Quellenbindung erzeugen Sprachmodelle Gegenstände oder Items ohne theoretisches Fundament (*Zhang & Zhang, 2025*).
* **Mangelnde psychometrische Passung:** Oberflächlich flüssige Formulierungen enthalten häufig versteckte Mängel wie doppelte Verneinungen, doppelseitige Fragen (*double-barreled items*) oder unklare Antwortskalen (*Artino et al., 2014; Lee et al., 2025*).
* **Pseudo-Validität (*In-silico Validity Illusion*):** Es besteht die Gefahr, qualitative KI-Bewertungen fälschlicherweise als Nachweis empirischer Validität oder Bias-Freiheit auszugeben (*Stanton, 2026; Russel-Lasalandra, 2025*).
* **Fehlende Transparenz:** Undeutliche Herkunft von Items (Übersetzung vs. Kontextanpassung vs. Neukonstruktion) erschwert die wissenschaftliche Nachvollziehbarkeit.

---

## 3. Finales Artefakt Version 2.0

Das finale Artefakt stellt ein vollkommen strukturiertes, sequenzielles Prompt-System für NotebookLM dar. Es steuert den Entwicklungsprozess von der Quellengrundierung bis zur Vorbereitung empirischer kognitiver Pretests.

### 3.1 Strikte Herkunftstaxonomie
Jedes generierte Item wird lückenlos genau einer von vier Herkunftskategorien zugeordnet:
* `[Original unverändert]`: Nativ deutschsprachige, valide Originalskala aus den hochgeladenen Quellen.
* `[Übersetzt]`: Aus einer englischen Originalskala der Quellen übersetzt, ohne den inhaltlichen Kontext zu verändern.
* `[Kontextuell angepasst]`: Aus den Quellen entnommen, aber begrifflich an den spezifischen Zielkontext angepasst.
* `[In-silico neu konstruiert]`: Auf Basis der theoretischen Konstruktdefinition vollständig neu erzeugt.

### 3.2 Methodischer Disclaimer (Verpflichtender Bestandteil aller Ausgaben)
> **Methodischer Disclaimer:** Dieses Instrument stellt das Ergebnis einer strukturierten, LLM-gestützten In-silico-Vorselektion dar. Aus den heuristischen Prüfschritten dieses Sprachmodells lässt sich keinerlei empirische Validität (wie faktorielle Struktur, Reliabilität, Diskriminanzvalidität oder Bias-Freiheit) ableiten. Vor einem wissenschaftlichen oder praktischen Einsatz muss das Instrument zwingend kognitiv pretestiert (Response Process Validity) und an einer realen Feldstichprobe statistisch evaluiert werden.

---

## 4. Der 4-Phasen-Workflow

Der Workflow gliedert sich in vier sequenzielle Phasen, die durch drei verbindliche menschliche Freigabepunkte (HITL-Gates) geschützt sind:

[Phase 1: Grounding & Skalendesign] ──► 🛑 HITL-Gate 1: Freigabe Theorie & Skalendesign │ [Phase 2: Überpoolung & Taxonomie]  ──► 🛑 HITL-Gate 2: Sichtung & Freigabe Roh-Itempool │ [Phase 3a: Inhaltlicher Review]     ──► [Phase 3b: Sprachlich-Methodischer Review] │ [Phase 4: Ergebnismatrix & Pretest] ──► 🛑 HITL-Gate 3 (Final): Freigabe des Pretest-Sets

1. **Phase 1: Quellengrundierung & Skalendesign:** Extraktion der theoretischen Konstruktdefinition, Erfassung von Quellenlücken und Begründung von Überpoolungsfaktor und Antwortskala.
   * 🛑 **HITL-Gate 1:** Menschliche Freigabe der Theoriebasis, Quellenlücken und des Skalendesigns.
2. **Phase 2: Überpoolte Item-Generierung & Taxonomie:** Generierung der mehrfachen Itemmenge (z. B. 2x–4x Überpoolung), Zuweisung der 4-stufigen Herkunftstaxonomie und Prüfung auf N/A-Optionen/Filterfragen.
   * 🛑 **HITL-Gate 2:** Menschliche Sichtung des Roh-Itempools auf Tonalität, Passung und Vollständigkeit.
3. **Phase 3a: Inhaltlicher Review (*Construct Alignment*):** Heuristische Prüfung der inhaltlichen Passung und Ausschluss von *Construct Crossovers*.
4. **Phase 3b: Sprachlich-Methodischer Review & Redundanz:** Optimierung von Sprache/Satzbau und qualitative Redundanzfilterung zur Auswahl der Zielitems.
5. **Phase 4: Ergebnismatrix & Pretest-Leitfaden:** Zusammenstellung der finalen Matrix und Ableitung gezielter *Verbal Probes* für kognitive Interviews (*Think-Aloud*).
   * 🛑 **HITL-Gate 3 (Final):** Menschliche Freigabe des Pretest-Sets und Überführung in die empirische Feldprüfung.

---

## 5. Demonstrationsfall: KI-Readiness von Mitarbeitenden

Das Leitlinienmodell v2.0 wurde am Anwendungsfall der Entwicklung eines kompakten Befragungsinstruments zur **individuellen KI-Readiness von Mitarbeitenden** erprobt. Basierend auf den Quellen (*Wang et al., 2026; Karaca et al., 2021; Boyacı & Söyük, 2025; Lee et al., 2025; Tomaževič et al., 2026*) wurden vier priorisierte Dimensionen ausgewählt und zu einem bereinigten 15-Item-Fragebogen verdichtet:

| Dimension | Ziel-Konstrukt | Quellengrundlage | Final-Set |
| :--- | :--- | :--- | :--- |
| **1. Selbstwirksamkeit & Kognition** | Zutrauen in KI-Verständnis, Nutzung & Ergebniskontrolle | AIRS (SEC), MAIRS-MS (Ability), Explainability | 4 Items |
| **2. Optimismus & Comfort** | Effizienzerwartung vs. Abwesenheit von Lern-/Sozialangst | AIRS (OPT/COM), AAAW (Anxiety), TRI | 4 Items |
| **3. Mensch-KI-Kollaboration** | Aufgabenpassung & KI als Partner bei Komplexität/Routine | Task-Technology Fit, AIRS (CLW), Delegation | 4 Items |
| **4. Organisationales Enablement** | Subjektives Gefühl der Befähigung (Schulung/Zeit/Regeln) | HR Development (*Tomaževič et al., 2026*) | 3 Items |

*Antwortskala:* 5-stufige Likert-Skala mit vollständiger Beschriftung (*1 = Stimme gar nicht zu* bis *5 = Stimme vollkommen zu*).

---

## 6. Evaluation von Version 1 zu Version 2

Die vergleichende Evaluation zeigte wesentliche methodische Fortschritte von V1 zu V2:

* **Klarheit der Herkunft:** V1 klassifizierte deutsche Übersetzungen fälschlicherweise als `[Übernommen]`. V2 führt die exakte Kategorie `[Übersetzt]` ein und macht den Bedarf für sprachliche Re-Validierung transparent.
* **Entkopplung von Pseudo-Validität:** V1 bescheinigte „bestandene Qualitätsprüfung“ und „Bias-Freiheit“. V2 verwendet konsequent die Formulierung „heuristisch bereinigter Vorschlag“ und schließt mit einem zwingenden Disclaimer ab.
* **Einführung von HITL-Gates:** V1 besaß nur einen End-Kontrollpunkt. V2 etabliert drei Gates (nach Theorie, nach Roh-Items und vor dem Pretest).
* **Entflechtung der Review-Phase:** Die Aufteilung von Phase 3 in 3a (Inhalt/Alignment) und 3b (Sprache/Redundanz) deckte spezifische *Construct Crossovers* auf (z. B. Streichung von Item 3.2 „Systemverständnis“ aus Kollaboration).
* **Flexibilisierung von Skalendesign & Sondertypen:** V2 ersetzt starre Vorgaben durch kontextbezogene Begründungen und integriert N/A-Optionen sowie Filterfragen.

---

## 7. Methodische Abgrenzung des Artefakts

Das Artefakt leistet eine hochwertige **In-silico-Vorselektion und Pretest-Vorbereitung**. Folgende Grenzen sind methodisch zu beachten:

┌─────────────────────────────────────────────────┬─────────────────────────────────────────────────┐ │     Infrastruktur innerhalb von NotebookLM      │      Externe Arbeitsschritte & Systeme          │ ├─────────────────────────────────────────────────┼─────────────────────────────────────────────────┤ │ • RAG-gestützte Konzeption aus Quelldokumenten  │ • Mathematisch-statistische Berechnungen         │ │   (Zhang & Zhang, 2025).                        │   (EGA, UVA, CFA, IRT-Analysen, PLS-SEM)        │ │ • Kontextualisierte Item-Generierung            │   via R/Python.                                 │ │   (Lee et al., 2025).                           │ • Empirische Feld-Datenerhebungen an echten     │ │ • Heuristische In-silico-Vorselektion           │   Probanden-Stichproben.                        │ │   (Lee et al., 2025; Stanton, 2026).            │ • Kognitive Pretest-Interviews (Think-Aloud)    │ │ • Ableitung von Verbal Probes für Pretests      │   mit Personen der Zielgruppe                   │ │   (Artino et al., 2014).                        │   (Artino et al., 2014).                        │ └─────────────────────────────────────────────────┴─────────────────────────────────────────────────┘

* **Keine empirische Parameterbestimmung:** Faktorladungen, Kriteriumsvalidität, Diskriminanzvalidität (HTMT) und Reliabilitäten (Cronbachs Alpha) können nicht durch Sprachmodelle simuliert werden, sondern erfordern echte Probandendaten.
* **Keine starren Stichprobenschwellen:** In der Fachliteratur existieren keine universellen Mindeststichproben. Die erforderliche Stichprobengröße richtet sich nach Faktoren wie Kommunalitäten, Modellkomplexität und dem gewählten Schätzverfahren (EFA, CFA, PLS-SEM).
* **Unverzichtbarkeit kognitiver Interviews:** Das LLM generiert zwar Verbal Probing Leitfäden, kann aber die kognitive Informationsverarbeitung realer Probanden (*Response Process Validity*) nicht ersetzen.
