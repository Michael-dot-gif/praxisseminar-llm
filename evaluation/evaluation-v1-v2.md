# Evaluation und Weiterentwicklung von Version 1 zu Version 2

Dokumentation der kritischen Re-Evaluation des Prototyps (Version 1) und der daraus abgeleiteten Weiterentwicklung zum finalen Artefakt (Version 2.0).

---

## 1. Ausgangspunkt und Ziel der Evaluation

Nach dem ersten vollständigen Durchlauf des 4-Phasen-Workflows am Demonstrationsfall „KI-Readiness von Mitarbeitenden“ wurde der Prototyp (Version 1) einer kritischen methodischen Re-Evaluation unterzogen. 

**Ziel der Evaluation** war es, den Workflow anhand etablierter psychometrischer Standards (*Artino et al., 2014; Boateng et al., 2018; Morgado et al., 2017*) sowie aktueller Erkenntnisse zur KI-gestützten Testenentwicklung (*Lee et al., 2025; Russel-Lasalandra, 2025; Stanton, 2026; Zhang & Zhang, 2025*) zu prüfen. Dabei sollten methodische Schwachstellen, unzulässige Gütebehauptungen und praktische Handhabungsengpässe identifiziert und in einer überarbeiteten Version 2.0 behoben werden.

---

## 2. Stärken von Version 1

Der initiale Prototyp zeigte in der Anwendung bereits wesentliche funktionale Stärken:

* **Strukturierte Phasentrennung:** Die Aufteilung in vier sequenzielle Schritte verhinderte ein unkontrolliertes „Halluzinieren auf Vorrat“ und verankerte die Itemerzeugung in der theoretischen Quellengrundierung.
* **Erkennung von Construct Crossovers:** Das LLM erwies sich als effektiv bei der Identifikation inhaltlicher Fehlzuordnungen (z. B. Erkennung von Roh-Item 3.2 als Anthropomorphismus-Konstrukt statt Kollaborationsbereitschaft).
* **Praktische Pretest-Vorbereitung:** Die automatisierte Ableitung zielgerichteter *Verbal Probes* (kognitive Testfragen) schlug eine erfolgreiche Brücke von der *In-silico*-Vorstrukturierung zur empirischen Prüfung der Antwortprozess-Validität (*Artino et al., 2014*).
* **Effektive Verdichtung:** Der Workflow verdichtete den 27-Item-Rohpool erfolgreich auf ein händelbares 15-Item-Set für den Unternehmenskontext.

---

## 3. Identifizierte Schwächen und methodische Probleme von Version 1

Bei der genauen Analyse traten jedoch schwerwiegende methodische Defizite zu Tage:

1. **Unschärfe bei der Herkunftskennzeichnung:**
   * Englischsprachige Original-Items (z. B. aus *AIRS* oder *MAIRS-MS*) wurden ins Deutsche übersetzt, aber fälschlicherweise als `[Übernommen]` deklariert. Da jede Übersetzung eine linguistisch-kulturelle Transformation darstellt (*Artino et al., 2014*), ist dieses Label methodisch irreführend.
2. **Entstehen der *In-silico Validity Illusion*:**
   * Das System formulierte Selektionsbegründungen in Phase 3 so, als lieferte die KI eine gesicherte psychometrische Güteprüfung. Ein LLM kann ohne reale Befragungsdaten jedoch weder Faktorladungen, noch Diskriminanzvalidität (HTMT) oder Reliabilitäten bestimmen (*Stanton, 2026*).
3. **Unzulässige Behauptung von Bias-Freiheit:**
   * V1 bescheinigte den Items „Fairness und Bias-Freiheit“. Da Sprachmodelle auf potenziell verzerrten Trainingsdaten basieren, können sie demografischen oder kulturellen Bias (*Differential Item Functioning / DIF*) nicht valide ausschließen (*Russel-Lasalandra et al., 2026; Stanton, 2026*).
4. **Fehlende Zwischen-Inseln für menschliche Kontrolle (HITL):**
   * V1 besaß nur am Ende von Phase 4 ein Kontrollgate. Dadurch fehlte die Möglichkeit, die Theoriebasis (Phase 1) oder den Roh-Itempool (Phase 2) manuell freizugeben, bevor die KI Folgeschritte berechnete.
5. **Methodische Starrheit:**
   * Der Überpoolungsfaktor war starr auf „genau 2-fach“ fixiert, und das Skalenformat war ausnahmslos auf eine 5-stufige Likert-Skala festgelegt. Dies widerspricht methodischen Best Practices, die je nach Konstruktkomplexität Überpoolungen vom 3- bis 5-fachen (*Boateng et al., 2018*) sowie 7-stufige Skalen bei bipolaren Konstrukten empfehlen (*Artino et al., 2014*).
6. **Überforderung der Review-Phase:**
   * Die Abfrage von Inhalt, Sprache, Bias und Redundanz in einem einzigen Kombi-Prompt führte dazu, dass subtile sprachliche Nuancen (z. B. kognitive Hürden durch Negationen) untergingen.

---

## 4. Kategorisierung der Anpassungen

Aus den Schwachstellen wurden konkrete Anpassungen abgeleitet und nach ihrer Priorität eingeordnet:

### Zwingende Änderungen (Must-Have)
* **4-stufige Herkunftstaxonomie:** Strikte Unterscheidung zwischen `[Original unverändert]`, `[Übersetzt]`, `[Kontextuell angepasst]` und `[In-silico neu konstruiert]`.
* **Entkopplung von Validitätsbehauptungen:** Konsequente begriffliche Ersetzung von „Validierung“ durch „heuristische Plausibilitätsprüfung“ sowie Einfügen eines verpflichtenden methodischen Disclaimers.
* **Verankerung zusätzlicher HITL-Gates:** Einfügen von Freigabepunkten nach Phase 1 (Theorie) und Phase 2 (Roh-Itempool).

### Sinnvolle Verbesserungen (Should-Have)
* **Flexibilisierung der Konfiguration:** Dynamische Festlegung von Überpoolungsfaktor und Skalenformat in Phase 1 anhand des Konstrukttyps.
* **Entflechtung von Phase 3:** Aufteilung der Review-Phase in Phase 3a (*Inhalt & Construct Alignment*) und Phase 3b (*Sprache & Redundanz*).
* **Sonderfunktions-Check:** Systematische Prüfung der Items auf die Notwendigkeit von Filterfragen oder „Nicht anwendbar (N/A)“-Optionen.

### Optionale Erweiterungen (Nice-to-Have)
* Automatisierter Audit Trail zur Nachverfolgung von Item-Anpassungen.
* Synthetisches Pretesting mittels Persona-Simulationen (vor der empirischen Prüfung).

---

## 5. Konkrete Änderungen von V1 zu V2

| Bereich | Version 1 (Prototyp) | Version 2.0 (Finales Artefakt) |
| :--- | :--- | :--- |
| **Güte-Anspruch** | Bezeichnete KI-Analysen als „Qualitätsprüfung“ / „Validierung“. | Bezeichnet KI-Analysen explizit als „heuristische Plausibilitätsprüfung“; erfordert Disclaimer. |
| **Herkunfts-Taxonomie** | Unscharf (Übersetzungen fälschlicherweise als `[Übernommen]` deklariert). | **4-stufige Taxonomie:** Strikte Unterscheidung von *Original*, *Übersetzt*, *Angepasst* und *In-silico*. |
| **Menschliche Kontrolle** | 1 Gatekeeper am Ende des Prozesses (Phase 4). | **3 HITL-Gates:** Nach Phase 1 (Theorie), Phase 2 (Roh-Items) und Phase 4 (Pretest-Set). |
| **Review-Struktur** | 1 überforderter Kombi-Prompt in Phase 3. | **2-stufiges Screening:** Phase 3a (Inhalt/Alignment) und Phase 3b (Sprache/Redundanz). |
| **Skalendesign & Überpool** | Starr vorgegeben (2x Überpool, 5-stufige Skala). | Kontextbezogen in Phase 1 theoretisch begründet und konfiguriert. |
| **Sonderfunktionen** | Vernachlässigt. | Systematische Kennzeichnung von Bedarfen für N/A-Optionen und Filterfragen. |

---

## 6. Ergebnisse des gezielten V2-Tests am Demonstrationsfall

Der erneute Test von Version 2.0 am KI-Readiness-Fragebogen bestätigte den methodischen Mehrwert:

1. **Ehrliche Herkunftsdeklaration:** Kein einziges der 15 Items erhielt das Label `[Original unverändert]`, da alle englischsprachigen Quellen übersetzt oder kontextuell angepasst wurden. Fünf Items wurden sauber als `[Übersetzt]` (Item 1.1, 1.2, 2.1, 2.3, 4.1), sieben als `[Kontextuell angepasst]` (z. B. Item 1.3, 2.2, 3.1, 3.2, 3.3, 4.2, 4.3) und drei als `[In-silico neu konstruiert]` (Item 1.4, 2.4, 3.4) ausgewiesen.
2. **Steuerung durch HITL-Gates:** HITL-Gate 1 verhinderte die voreilige Itemerzeugung und schloss abstrakte Corporate-Governance-Themen (wie IT-Budgets) vorab aus. HITL-Gate 2 ermöglichte die manuelle Sichtung des 27-Item-Rohpools vor dem KI-Screening.
3. **Qualitätsgewinn durch getrennte Reviews:** Phase 3a deckte isoliert theoretische Fehlzuordnungen auf (Streichung von Roh-Item 3.2 als Anthropomorphismus-Konstrukt). Phase 3b identifizierte sprachliche Risiken (wie Negationseffekte bei Item 2.2) und formulierte gezielte Warnhinweise für den Pretest.
4. **Praxisgerechte Sonderoptionen:** V2 identifizierte bei den Items zur Mensch-KI-Kollaboration (3.1 & 3.2) die Notwendigkeit von Vorschalt-Filterfragen für Mitarbeitende ohne KI-Praxis sowie bei Item 4.1 (Schulungsangebot) den Bedarf für eine Kategorie „Kein Angebot vorhanden“.

---

## 7. Gegenüberstellung: Version 1 vs. Version 2

┌─────────────────────────────────────────┬─────────────────────────────────────────┐ │           Version 1 (Prototyp)          │      Version 2.0 (Finales Artefakt)     │ ├─────────────────────────────────────────┼─────────────────────────────────────────┤ │ • Illusion automatisierter Validität.   │ • Strikte methodische Entkopplung.      │ │ • Unklare Herkunft von Übersetzungen.   │ • Transparente 4-stufige Taxonomie.     │ │ • Einziger Kontrollpunkt am Prozessende.│ • Drei verankerte HITL-Gates.           │ │ • Starre Vorgaben für Skala & Überpool. │ • Konfigurations-Empfehlung in Phase 1. │ │ • Überforderter Review-Prompt.          │ • Zweistufiges Screening (3a/3b).       │ │ • Fehlende Beachtung von N/A-Bedarfen.  │ • Erfassung von Filterfragen & N/A.     │ └─────────────────────────────────────────┴─────────────────────────────────────────┘

---

## 8. Schlussbewertung

Version 2.0 wurde als **finales Artefakt** festgelegt, da sie die grundlegenden Schwachstellen des Prototyps behebt, ohne die Praktikabilität in NotebookLM zu gefährden. 

Sie verhindert wissenschaftlich unzulässige Gütebehauptungen (*In-silico Validity Illusion*), stellt durch die Herkunftstaxonomie und die drei HITL-Gates die volle Transparenz und menschliche Steuerung sicher und bereitet Befragungsinstrumente durch den Pretest-Leitfaden optimal auf die notwendige empirische Feldvalidierung vor.
