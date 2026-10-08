# Leitlinienmodell für die LLM-gestützte Fragebogenentwicklung (Version 2.0)

Dieses Dokument beschreibt das methodische Leitlinienmodell zur wissenschaftlich fundierten, LLM-gestützten Erstellung und Vorevaluierung von Fragebögen in **NotebookLM**.

---

## 1. Systemüberblick & Methodische Abgrenzung

as Leitlinienmodell verbindet etablierte phasenbasierte Frameworks der psychometrischen Skalenentwicklung mit modernen Verfahren der KI-gestützten Item-Generierung (Retrieval-Augmented Generation, sequenzielles rollenbasiertes In-silico-Review) und sichert den Gesamtprozess durch verbindliche **Human-in-the-Loop-Gates (HITL-Gates)** ab.

### Abgrenzung: NotebookLM-Scope vs. Externe Systeme

Für eine wissenschaftlich korrekte Anwendung unterscheidet das Modell strikt zwischen den Möglichkeiten innerhalb von NotebookLM und notwendigen externen Arbeitsschritten:

┌─────────────────────────────────────────────────┬─────────────────────────────────────────────────┐ │     Infrastruktur innerhalb von NotebookLM      │      Externe Arbeitsschritte & Systeme          │ ├─────────────────────────────────────────────────┼─────────────────────────────────────────────────┤ │ • RAG-gestützte Konzeption aus Quelldokumenten  │ • Mathematisch-statistische Berechnungen         │ │   (Zhang & Zhang 2025).                         │   (EGA, UVA, CFA, IRT-Analysen, PLS-SEM)        │ │ • Kontextualisierte Item-Generierung            │   via R/Python.                                 │ │   (Lee et al. 2025).                            │ • Empirische Feld-Datenerhebungen an echten     │ │ • Heuristische In-silico-Vorselektion           │   Probanden-Stichproben.                        │ │   (Lee et al. 2025; Stanton 2026).              │ • Kognitive Pretest-Interviews (Think-Aloud)    │ │ • Ableitung von Verbal Probes für Pretests      │   mit Personen der Zielgruppe                   │ │   (Artino et al. 2014).                         │   (Artino et al. 2014).                         │ └─────────────────────────────────────────────────┴─────────────────────────────────────────────────┘

---

## 2. Der 4-Phasen-Workflow

Der Entwicklungsprozess verläuft in vier sequenziellen Phasen, die durch drei verbindliche menschliche Freigabepunkte geschützt sind:

[Phase 1: Grounding & Konfiguration] ──► 🛑 HITL-Gate 1: Freigabe Theorie & Skalendesign │ [Phase 2: Überpoolung & Taxonomie]   ──► 🛑 HITL-Gate 2: Sichtung & Freigabe Roh-Itempool │ [Phase 3a: Inhaltlicher Review]      ──► [Phase 3b: Sprachlich-Methodischer Review] │ [Phase 4: Ergebnismatrix & Pretest]  ──► 🛑 HITL-Gate 3 (Final): Freigabe des Pretest-Sets

### Phase 1: Quellengrundierung, Konstruktspezifikation & Skalendesign
Extraktion der theoretischen Konstruktdefinition ausschließlich aus der geladenen Literatur, Erfassung von Quellenlücken sowie Festlegung des kontextbezogenen Skalendesigns (Überpoolungsfaktor und Antwortskala).

### Phase 2: Kontextualisierte Item-Generierung & Herkunftstaxonomie
Erzeugung eines überpoolten Roh-Itempools unter Einhaltung formeller Item-Schreibregeln, Zuweisung einer präzisen 4-stufigen Herkunftstaxonomie und Prüfung auf N/A-Optionen oder Filterfragen.

### Phase 3: Zweistufige Heuristische LLM-Prüfung (In-silico-Screening)
Qualitative Vor-Filterung zur Reduktion von Mängeln und Redundanzen in zwei spezialisierten Teilschritten:
* **Phase 3a (Inhaltlicher Review):** Prüfung des *Construct Alignment* und Ausschluss von *Construct Crossovers*.
* **Phase 3b (Sprachlich-Methodischer Review):** Optimierung von Sprache/Satzbau und qualitative Redundanzfilterung.

### Phase 4: Finales HITL-Gatekeeping & Pretest-Leitfaden
Zusammenstellung der finalen Ergebnismatrix und Vorbereitung empirischer kognitiver Interviews (*Think-Aloud* & *Verbal Probing*) zur Prüfung der Antwortprozess-Validität (*Response Process Validity*).

---

## 3. Human-in-the-Loop-Gates (HITL-Gates)

Um *Semantic Drift* und die unkritische Übernahme generierter Texte zu verhindern, ist der Workflow durch drei zentrale Kontrollpunkte abgesichert:

* 🛑 **HITL-Gate 1 (Nach Phase 1):** Der Forschende prüft die Konstruktdefinition, die identifizierten Quellenlücken und die Konfigurationsempfehlung (Überpoolungsfaktor & Skalenstufen). Erst nach manueller Freigabe oder Anpassung wird Phase 2 gestartet.
* 🛑 **HITL-Gate 2 (Nach Phase 2):** Der Forschende sichtet den Roh-Itempool auf Tonalität, Passung zur Zielgruppe und Vollständigkeit. Erst nach Freigabe startet die zweistufige LLM-Filterung.
* 🛑 **HITL-Gate 3 / Final (Nach Phase 4):** Der Forschende unterzieht die Ergebnismatrix einer abschließenden inhaltlichen Prüfung, gibt den Pretest-Leitfaden frei und leitet die empirische Feldüberprüfung ein.

---

## 4. Strikte Herkunftstaxonomie

Jedes generierte Item wird lückenlos genau einer von vier Herkunftskategorien zugeordnet:

* **`[Original unverändert]`:** Nativ deutschsprachige, valide Originalskala aus den hochgeladenen Quellen.
* **`[Übersetzt]`:** Aus einer englischen Originalskala der Quellen übersetzt, ohne den inhaltlichen Kontext zu verändern.
* **`[Kontextuell angepasst]`:** Aus den Quellen entnommen, aber begrifflich/inhaltlich an den spezifischen Zielkontext angepasst.
* **`[In-silico neu konstruiert]`:** Auf Basis der theoretischen Konstruktdefinition vollständig neu erzeugt.

---

## 5. Methodische Best Practices & Klarstellungen

1. **Keine universellen Stichprobenschwellen:** In der empirischen Skalenvalidierung existieren keine starren Mindestgrößen als pauschale Regel. Die erforderliche Stichprobenstärke hängt von Faktoren wie der Kommunalität der Items, dem Grad der Überdetermination der Faktoren, dem gewählten Auswertungsverfahren (EFA, CFA, IRT, PLS-SEM) und dem Ausmaß fehlender Werte ab.
2. **Saubere Herkunftskennzeichnung:** Übersetzungen fremdsprachiger Originalskalen stellen eine sprachlich-kulturelle Transformation dar und müssen stets als `[Übersetzt]` oder `[Kontextuell angepasst]` deklariert werden, um den Bedarf für Pretests sichtbar zu machen.
3. **Vermeidung der *In-silico Validity Illusion*:** Ein Sprachmodell kann die linguistische Struktur von Texten analysieren, besitzt jedoch kein theoretisches Weltwissen und ersetzt keine menschlichen Probandenantworten. Aus den heuristischen Prüfschritten lässt sich keine empirische Validität ableiten.
