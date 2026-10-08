# Quellenübersicht des Projekts

Dieses Dokument führt alle **18 wissenschaftliche Fachpublikationen und 1 Arbeitsdokument** auf, die im NotebookLM-Projekt als theoretische und methodische Grundlage für die Entwicklung des **Leitlinien- und Prompt-Systems (Version 2.0)** verwendet wurden.

---

## 1. Klassische Fragebogen- und Skalenentwicklung

Diese Quellen liefern das methodische Fundament für psychometrische Gütekriterien, den Ablauf von Skalenentwicklungen, Überpoolungsverfahren sowie die Durchsetzung kognitiver Pretests.

* **Artino et al. (2014) – *Developing questionnaires for educational research***
  * *Funktion im Projekt:* Methodische Grundlage für das 7-Schritte-Framework der Fragebogenentwicklung, Grundierung für kognitive Interviews (*Verbal Probing*) zur Prüfung der Antwortprozess-Validität (*Response Process Validity*) in Phase 4.
* **Boateng et al. (2018) – *Best Practices for Developing and Validating Scales***
  * *Funktion im Projekt:* Leitfaden für die phasenbasierte Skalenkonstruktion (Item-Generierung, Überpoolung, Item-Reduktion, Validierung). Begründung für die dynamische Überpoolung (2- bis 5-fach) in Phase 1 und Phase 2.
* **Morgado et al. (2017) – *Scale development practices in the human and social sciences***
  * *Funktion im Projekt:* Systematische Übersicht psychometrischer Schwachstellen in der Literatur; Untermauerung der Notwendigkeit einer klaren Phasentrennung und Inhaltsvalidierung.

---

## 2. LLM-gestützte Item- und Fragebogengenerierung

Diese Studien adressieren die Nutzung von Sprachmodellen zur automatisierten Testentwicklung, die Entfaltung von Multi-Agenten-Netzwerken, qualitative Redundanzprüfungen und die Risiken automatisierter Gütebehauptungen (*In-silico Validity Illusion*).

* **Lee et al. (2025) – *AI-powered Automatic Item Generation***
  * *Funktion im Projekt:* Methodische Vorlage für rollenbasierte Review-Systeme (Multi-Agent-Framework) zur Item-Generierung sowie Bereitstellung der AAAW-Skala (*Attitudes Toward AI at Work*) zur Messung von KI-Ängsten.
* **Russell-Lasalandra et al. (2026) – *Generative psychometrics via AI-GENIE: Automatic item generation and validation with network-integrated evaluation***
  * *Funktion im Projekt:* Referenzmodell für die automatisierte Generierung und Redundanzbereinigung von Items (*AI-GENIE*); theoretischer Hintergrund für die qualitative Redundanzprüfung in Phase 3b.
* **Stanton et al. (2026) – *Mini-review: considering impacts of artificial intelligence on the development of measurement scales***
  * *Funktion im Projekt:* Warnung vor dem unkritischen Einsatz generativer KI; theoretische Begründung für den methodischen Disclaimer und die strikte Abgrenzung zwischen KI-Heuristik und empirischer Feldvalidierung.
* **Yuan et al. (2026) – *Research on the development of an automated questionnaire generation system***
  * *Funktion im Projekt:* Beleg für die Leistungsfähigkeit von Fine-Tuned Sprachmodellen bei der Einhaltung psychometrischer Formulierungsregeln und Readability-Standards.

---

## 3. Halluzinationsvermeidung, RAG und Transparenz

Diese Quelle begründet die Notwendigkeit, das Sprachmodell durch Retrieval-Augmented Generation (RAG) streng an die geladenen Quellen zu binden.

* **Zhang & Zhang (2025) – *Hallucination Mitigation for Retrieval-Augmented Large Language Models: A Review***
  * *Funktion im Projekt:* Wissenschaftliche Begründung für die RAG-Quellengrundierung in Phase 1 zur Vermeidung von theoretischem Drift und Halluzinationen bei der Definition von Konstrukten.

---

## 4. KI-Readiness und verwandte Konstrukte

Diese Quellen liefern die theoretischen Definitionen, Subdimensionen und validierten Skalen zur Messung von KI-Readiness auf individueller und organisationaler Ebene.

* **Wang et al. (2026) – *Artificial intelligence readiness scale (AIRS)***
  * *Funktion im Projekt:* Primäre Quellengrundlage für die individuelle KI-Readiness (Faktoren: *Self-Efficacy & Cognition*, *Optimism*, *Collaborative Learning & Working*, *Comfort*); Basis für die `[Übersetzten]` Items in Phase 2.
* **Karaca et al. (2021) – *Medical Artificial Intelligence Readiness Scale for Medical Students (MAIRS-MS)***
  * *Funktion im Projekt:* Zweite Hauptquelle für individuelle Readiness-Dimensionen (*Cognition*, *Ability*, *Vision*, *Ethics*); Grundlage für die `[Kontextuell angepassten]` Items zu Fähigkeit und Wissen.
* **Boyacı & Söyük (2025) – *Healthcare workers' readiness for medical artificial intelligence***
  * *Funktion im Projekt:* Empirischer Nachweis der Übertragbarkeit der MAIRS-MS auf berufstätige Angestellte im Organisationskontext.
* **Jöhnk et al. (2021) – *Ready or not: Stakeholder-driven dimensions of AI readiness***
  * *Funktion im Projekt:* Systematisierung organisatorischer Readiness-Faktoren (Strategie, Ressourcen, Wissen, Kultur, Daten) und Grundlage für die Konstruktabgrenzung zwischen individueller und korporativer Readiness.
* **Tomaževič et al. (2026) – *AI readiness as a human-centered organizational capability: evidence on the role of HR development in public administration***
  * *Funktion im Projekt:* Nachweis, dass *HR Development* (Schulungen/Befähigung) der zentrale organisationale Treiber für die individuelle Bereitschaft von Mitarbeitenden ist; Basis für Dimension 4 (*Organisationales Enablement*).

---

## 5. Bereitgestellte Beispielstudien und Datensätze

Diese Quellen dienten als Anwendungsbeispiele für spezifische Nutzungskontexte, Vertrauensmodelle und empirische Item-Vorlagen.

* **Paper Fragebogen 1 – *Motivations zur KI-Adoption im Gesundheitswesen***
  * *Funktion im Projekt:* Dual-Appraisal-Beispielmodell zur Bewertung von Bedrohung vs. Effektivität digitaler Werkzeuge.
* **Paper Fragebogen 2 – *Adoptionsmotivation für Smart-Energy-Apps***
  * *Funktion im Projekt:* Anwendungsbeispiel für die Verknüpfung von Verhaltentheorien (UTAUT2 / RAA) bei Technologieakzeptanz.
* **Paper Fragebogen 3 – *Task-Technology Fit in Virtual Reality***
  * *Funktion im Projekt:* Vorlage für die Konstruktion von *Task-Technology Fit* (TTF) Items zur Messung der Eignung von KI für konkrete Arbeitsaufgaben in Dimension 3.
* **Paper Fragebogen 4 – *Vertrauen von Unternehmensentscheidern in ChatGPT***
  * *Funktion im Projekt:* Empirische Vertrauensskala (*Ability*, *Benevolence*, *Integrity*) zur Ableitung von Items bezüglich Systemtransparenz und Kontrolle.
* **Paper Fragebogen 5 – *Sozio-technische Interaktionen in virtuellen Meetings***
  * *Funktion im Projekt:* Beispiel für die Messung technischer Unterstützung auf die Arbeitsdedikation im virtuellen Büroalltag.
* **Datensatz_v1.docx – *Sammlung strukturierter Befragungsinstrumente***
  * *Funktion im Projekt:* Textuelle Vorlage konkreter Likert-Items zu Vertrauen, Ängsten, Arbeitsanforderungen und Akzeptanz zur Transformation in den überpoolten Roh-Itempool.
