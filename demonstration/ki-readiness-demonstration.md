# Demonstrationsfall: Entwicklung eines Fragebogens zur KI-Readiness von Mitarbeitenden

Dokumentation der praktischen Erprobung des **Leitlinien- und Prompt-Systems v2.0** in NotebookLM.

---

## 1. Ausgangslage und Ziel des Demonstrationsfalls

Ein Unternehmen möchte mit einem quantitativen Fragebogen die **individuelle KI-Readiness seiner Mitarbeitenden** messen. Ziel des Demonstrationsfalls ist es, das entwickelte 4-Phasen-Leitlinien- und Prompt-System v2.0 an einem realen, praxisrelevanten Szenario der Arbeits- und Organisationsforschung zu testen und schrittweise von der theoretischen Quellengrundierung bis zur Pretest-Vorbereitung durchzuführen.

---

## 2. Theoretische Eingrenzung von KI-Readiness

Auf Basis der in NotebookLM geladenen Fachliteratur (*Wang et al., 2026; Karaca et al., 2021; Boyacı & Söyük, 2025; Lee et al., 2025; Tomaževič et al., 2026; Jöhnk et al., 2021*) wird KI-Readiness auf Mitarbeitendenebene wie folgt definiert:

> **KI-Readiness von Mitarbeitenden** ist der mehrdimensionale psychologische, kognitive und verhaltensbezogene Bereitschaftszustand eines Mitarbeitenden, KI-Technologien zu akzeptieren, ihre Funktionsweise zu verstehen, emotionale Barrieren (wie Ängste) abzubauen und KI-Systeme effektiv sowie verantwortungsvoll im Arbeitsalltag einzusetzen.

### Abgrenzung: Individuelle vs. Organisationale Readiness
Der Fokus des Befragungsinstruments liegt bewusst auf der **individuellen Ebene**. Organisationale Faktoren (wie Infrastruktur, IT-Budgets oder Management-Strategien) werden ausgeklammert, da sie von einzelnen Mitarbeitenden im Fragebogen oft nicht valide beurteilt werden können. Organisationale Aspekte fließen ausschließlich als **subjektiv wahrgenommenes Enablement** (erhaltene Befähigung, Zeitressourcen und Leitlinien durch das Unternehmen) ein (*Tomaževič et al., 2026*).

---

## 3. Priorisierte Dimensionen und verwendete Quellen

Zur Erstellung eines kompakten, praxistauglichen Fragebogens (Bearbeitungszeit ca. 3–5 Minuten) wurden aus der Literatur vier kernrelevante Dimensionen priorisiert:

1. **Selbstwirksamkeit & Kognition:** Zutrauen in KI-Verständnis, Bedienung und kritische Ergebniskontrolle.
   * *Quellengrundlage:* AIRS (*Wang et al., 2026*), MAIRS-MS (*Karaca et al., 2021; Boyacı & Söyük, 2025*), Explainability/Control (*Paper Fragebogen 4; Lee et al., 2025; Datensatz_v1*).
2. **Optimismus & Comfort:** Effizienzerwartung vs. Abwesenheit von Lern- und Verlegenheitsängsten.
   * *Quellengrundlage:* AIRS (*Wang et al., 2026*), AAAW (*Park et al., 2024; Lee et al., 2025*), TRI (*Parasuraman, 2000; Wang et al., 2026*).
3. **Mensch-KI-Kollaboration & Aufgabenpassung:** Eignung von KI für Aufgaben und Nutzung als partnerartiges Werkzeug bei Komplexität und Routine.
   * *Quellengrundlage:* AIRS (*Wang et al., 2026*), Task-Technology Fit (*Paper Fragebogen 3; Goodhue & Thompson, 1995*), Delegation/Automation (*Jöhnk et al., 2021; Paper Fragebogen 4*).
4. **Wahrgenommenes organisationales Enablement:** Gefühltes Vorhandensein von Schulungen, Zeiträumen und Richtlinien im Betrieb.
   * *Quellengrundlage:* HR Development & Planning (*Tomaževič et al., 2026; Jöhnk et al., 2021*).

*Antwortformat:* Einheitliche **5-stufige Likert-Skala** mit vollständiger verbaler Beschriftung (*1 = Stimme gar nicht zu, 2 = Stimme eher nicht zu, 3 = Teils/teils, 4 = Stimme eher zu, 5 = Stimme vollkommen zu*).

---

## 4. Anwendung der Phasen 1 bis 4 des Leitlinienmodells v2.0

### Phase 1: Quellengrundierung & Skalendesign
* **Aktion:** Generierung der theoretischen Konstruktspezifikation und Erfassung von Quellenlücken.
* **Ergebnis:** Identifikation der vier Ziel-Dimensionen. Festhalten der Quellenlücke, dass objektive KI-Leistungstests (z. B. rechnerische Prüfung von Halluzinationen) in den Selbsteinschätzungs-Quellen nicht existieren.
* **🛑 HITL-Gate 1:** Forschender gibt Konstruktdefinition, Ausklammerung abstrakter Governance-Themen und die 5-stufige Skalenkonfiguration frei.

### Phase 2: Überpoolte Item-Generierung & Herkunftstaxonomie
* **Aktion:** Erzeugung eines überpoolten Roh-Itempools von **27 Items** (ca. 2- bis 3-fache Menge der Zielanzahl).
* **Ergebnis:** Zuordnung der Items zu den vier Herkunftskategorien und Identifikation von Bedarfen für N/A-Optionen und Filterfragen.
* **🛑 HITL-Gate 2:** Forschender sichtet den Roh-Itempool auf Tonalität und Anwendbarkeit.

### Phase 3: Zweistufige Heuristische LLM-Prüfung (In-silico-Screening)
* **Phase 3a (Inhaltlicher Review / Construct Alignment):** Identifikation und Entfernung von *Construct Crossovers*. Beispielsweise wurde Roh-Item 3.2 (*„Ich glaube, dass KI die Ziele einer Aufgabe verstehen kann“*) gestrichen, da es die wahrgenommene Systemintelligenz/Anthropomorphismus misst und nicht die Kollaborationsbereitschaft des Mitarbeitenden.
* **Phase 3b (Sprachlich-Methodischer Review & Redundanz):** Bereinigung semantischer Doppelungen und methodischer Hürden. Reduktion des Pools von 27 auf 15 finale Ziel-Items.

### Phase 4: Finales HITL-Gatekeeping & Pretest-Leitfaden
* **Aktion:** Zusammenstellung der finalen 15-Item-Matrix, Erstellung gezielter *Verbal Probing* Fragen für kognitive Interviews und Ausweisung des methodischen Disclaimers.
* **🛑 HITL-Gate 3 (Final):** Menschliche Endfreigabe der Pretest-Unterlagen.

---

## 5. Entwicklung vom Roh-Itempool zum bereinigten 15-Item-Fragebogen

| Dimension | Roh-Items (Phase 2) | Gestrichene Items & Hauptgrund | Finale Items (Phase 3b) |
| :--- | :--- | :--- | :--- |
| **1. Selbstwirksamkeit & Kognition** | 7 Items | • Item 1.1 (Redundanz zu 1.3)<br>• Item 1.4 („Begriffe präzise erklären“ setzt Hürde zu hoch / Bodeneffekt)<br>• Item 1.6 (Redundanz zu 1.3) | **4 Items** |
| **2. Optimismus & Comfort** | 7 Items | • Item 2.2 (Vermischung von Alltags- und Arbeitsleben)<br>• Item 2.5 (Negativformulierung erzeugt Methodenfaktor)<br>• Item 2.6 (Inhaltlich durch 2.1 und 2.7 abgedeckt) | **4 Items** |
| **3. Mensch-KI-Kollaboration** | 7 Items | • Item 3.1 (Redundanz zu 2.1 und 3.5)<br>• Item 3.2 (Construct Crossover zu Anthropomorphismus)<br>• Item 3.6 (Qualitätssteigerung in 3.4 abgedeckt) | **4 Items** |
| **4. Organisationales Enablement** | 6 Items | • Item 4.2 (Sprachlich unscharf bezüglich Person vs. System)<br>• Item 4.5 (Teamaustausch sekundär)<br>• Item 4.6 (Resultat der anderen Items) | **3 Items** |
| **Gesamt** | **27 Items** | **12 Items gestrichen** | **15 Items** |

---

## 6. Finale 15 Items mit Herkunftskategorie und Quellenbezug

### Dimension 1: Selbstwirksamkeit & Kognition

* **Item 1.1 `[Übersetzt]`**
  * *Text:* „Ich habe das Vertrauen zu verstehen, wie KI-Technologien/-Produkte funktionieren.“
  * *Quelle:* AIRS (SEC2; *Wang et al., 2026*)
* **Item 1.2 `[Übersetzt]`**
  * *Text:* „Ich habe das Vertrauen, die verschiedenen Funktionen von KI-Technologien/-Produkten effektiv zu nutzen.“
  * *Quelle:* AIRS (SEC3; *Wang et al., 2026*)
* **Item 1.3 `[Kontextuell angepasst]`**
  * *Text:* „Ich kann KI-gestützte Informationen und Analysen effektiv mit meinem eigenen Fachwissen kombinieren.“
  * *Quelle:* MAIRS-MS (Ability 1; *Karaca et al., 2021; Boyacı & Söyük, 2025*)
* **Item 1.4 `[In-silico neu konstruiert]`**
  * *Text:* „Ich fühle mich in der Lage, die Ergebnisse und Vorschläge von KI-Systemen kritisch auf ihre Richtigkeit zu überprüfen.“
  * *Quelle:* Explainability / Control (*Paper Fragebogen 4; Lee et al., 2025; Datensatz_v1*)

### Dimension 2: Optimismus & Comfort

* **Item 2.1 `[Übersetzt]`**
  * *Text:* „Ich glaube, dass KI-Technologien/-Produkte meine tägliche Arbeit effizienter machen.“
  * *Quelle:* AIRS (OPT2; *Wang et al., 2026*)
* **Item 2.2 `[Kontextuell angepasst]`**
  * *Text:* „Ich fühle mich nicht unwohl oder verlegen, wenn bei der Nutzung von KI-Anwendungen vor Kolleginnen oder Kollegen Schwierigkeiten auftauchen.“
  * *Quelle:* AIRS (COM1; *Wang et al., 2026*)
* **Item 2.3 `[Übersetzt]`**
  * *Text:* „Ich empfinde keine Angst oder Unruhe davor, den Umgang mit KI-Anwendungen zu erlernen.“
  * *Quelle:* AIRS (SEC4/COM; *Wang et al., 2026*)
* **Item 2.4 `[In-silico neu konstruiert]`**
  * *Text:* „Ich blicke optimistisch darauf, wie künstliche Intelligenz meine künftigen Arbeitsaufgaben vereinfachen wird.“
  * *Quelle:* TRI Optimism (*Parasuraman, 2000; Wang et al., 2026*)

### Dimension 3: Mensch-KI-Kollaboration & Aufgabenpassung

* **Item 3.1 `[Kontextuell angepasst]`**
  * *Text:* „Die Funktionen von KI-Systemen passen gut zu den Anforderungen meiner täglichen Arbeitsaufgaben.“
  * *Quelle:* Task-Technology Fit (*Paper Fragebogen 3; Goodhue & Thompson, 1995*)
* **Item 3.2 `[Kontextuell angepasst]`**
  * *Text:* „Der Einsatz von KI unterstützt mich effektiv bei der Lösung komplexer Aufgaben oder Analysen in meinem Arbeitsbereich.“
  * *Quelle:* TTF / Perceived Performance (*Paper Fragebogen 3; Datensatz_v1*)
* **Item 3.3 `[Kontextuell angepasst]`**
  * *Text:* „Ich nutze KI-Werkzeuge als partnerartige Unterstützung bei der Erstellung, Planung oder Überarbeitung von Arbeitsergebnissen.“
  * *Quelle:* AIRS (CLW1; *Wang et al., 2026*)
* **Item 3.4 `[In-silico neu konstruiert]`**
  * *Text:* „Ich bin bereit, Routineaufgaben an KI-Systeme abzugeben, um mich auf anspruchsvollere Arbeitsinhalte zu konzentrieren.“
  * *Quelle:* Automation / Delegation (*Jöhnk et al., 2021; Paper Fragebogen 4*)

### Dimension 4: Wahrgenommenes organisationales Enablement

* **Item 4.1 `[Übersetzt]`**
  * *Text:* „Unser Unternehmen bietet adäquate Schulungen und Weiterbildungen zum Thema KI für die Mitarbeitenden an.“
  * *Quelle:* HR Development (HRD4; *Tomaževič et al., 2026*)
* **Item 4.2 `[Kontextuell angepasst]`**
  * *Text:* „Mein Unternehmen stellt mir ausreichend Zeit und Ressourcen bereit, um mich in den Umgang mit KI-Tools einzuarbeiten.“
  * *Quelle:* HR Planning & Development (*Tomaževič et al., 2026; Jöhnk et al., 2021*)
* **Item 4.3 `[Kontextuell angepasst]`**
  * *Text:* „Ich erhalte von meiner Organisation klare Leitlinien und Unterstützung zur sicheren und verantwortungsvollen Nutzung von KI.“
  * *Quelle:* Ethical Governance (*Tomaževič et al., 2026; Jöhnk et al., 2021*)

---

## 7. Identifizierte N/A-Optionen und Filterfragen

1. **Items 3.1 & 3.2 (Mensch-KI-Kollaboration):** Mitarbeitende, die in ihrer Rolle aktuell noch keine KI nutzen können oder dürfen, erzeugen auf einer Likert-Skala Verzerrungen. Das Modell schlägt eine **Vorschalt-Filterfrage** (*„Nutzen Sie in Ihrer täglichen Arbeit bereits KI-Werkzeuge?“*) oder eine **„Nicht anwendbar (N/A)“**-Option vor.
2. **Item 4.1 (Schulungen im Unternehmen):** Falls im Unternehmen gar keine KI-Schulungen existieren, unterscheidet die Option „Stimme gar nicht zu“ nicht sauber zwischen einem *schlechten* Angebot und dem *völligen Fehlen*. Es wird eine Zusatzkategorie *„Kein Angebot vorhanden“* empfohlen.

---

## 8. Vorbereitung der kognitiven Pretests (Verbal Probing)

Zur Überprüfung der **Antwortprozess-Validität** (*Response Process Validity; Artino et al., 2014*) in anschließenden kognitiven Interviews (*Think-Aloud*, \\(n = 5\text{--}15\\)) wurden spezifische Testfragen und Beobachtungshinweise abgeleitet:

* **Item 1.1 (*Vertrauen zu verstehen*):** 
  * *Verbal Probe:* „Was bedeutet für Sie in diesem Satz 'verstehen, wie KI funktioniert' – denken Sie dabei an die mathematische Programmierung oder an die praktische Funktionsweise im Büro?“
  * *Hinweis:* Prüfen, ob Befragte durch das Wort „funktionieren“ abgeschreckt werden, weil sie Informatik-Tiefenwissen vermuten.
* **Item 1.2 (*Funktionen nutzen*):** 
  * *Verbal Probe:* „An welche konkreten KI-Anwendungen oder Tools haben Sie bei der Beantwortung gedacht?“
  * *Hinweis:* Prüfen, ob Befragte nur an Chatbots oder auch an eingebettete Software (z. B. Excel/ERP) denken.
* **Item 2.2 (*Nicht unwohl/verlegen fühlen*):** 
  * *Verbal Probe:* „Gab es bei dieser Frage Stellen, die Sie zweimal lesen mussten?“
  * *Hinweis:* Prüfen, ob die Formulierung „nicht unwohl“ Verwirrung erzeugt (Negations-Effekt).
* **Item 3.3 (*Partnerartige Unterstützung*):** 
  * *Verbal Probe:* „Was löst der Begriff 'partnerartige Unterstützung' bei Ihnen aus?“
  * *Hinweis:* Prüfen, ob das Wort als anthropomorph abgelehnt wird.
* **Item 4.1 (*Adäquate Schulungen*):** 
  * *Verbal Probe:* „Was bedeutet für Sie in diesem Zusammenhang 'adäquat'?“
  * *Hinweis:* Prüfen, ob Befragte ohne Schulungsangebot eine N/A-Option vermissen.

---

## 9. Methodische Grenzen und Disclaimer

Die Vorstrukturierung des Fragebogens in NotebookLM ersetzt keine empirische psychometrische Evaluierung an Realdaten.

> **Methodischer Disclaimer:**
> Dieses Instrument stellt das Ergebnis einer strukturierten, LLM-gestützten In-silico-Vorselektion dar. Aus den heuristischen Prüfschritten dieses Sprachmodells lässt sich keinerlei empirische Validität (wie faktorielle Struktur, Reliabilität, Diskriminanzvalidität oder Bias-Freiheit) ableiten. Vor einem wissenschaftlichen oder praktischen Einsatz muss das Instrument zwingend kognitiv pretestiert (Response Process Validity) und an einer realen Feldstichprobe statistisch evaluiert werden.
