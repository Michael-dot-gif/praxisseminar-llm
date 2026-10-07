Leitlinien- und Prompt-System für die LLM-gestützte Fragebogenentwicklung (Version 2.0)

Dieses Dokument enthält die finale Spezifikation des Leitlinien- und Prompt-Systems (v2.0) für die wissenschaftlich fundierte, LLM-gestützte Erstellung und Vorevaluierung von Fragebögen in NotebookLM.

1. Systemüberblick & Methodische Abgrenzung

Das System unterstützt Forschende und Praktiker bei der Vorbereitung wissenschaftlicher Messinstrumente unter Nutzung von Large Language Models (LLMs). Es ergänzt klassische phasenbasierte Frameworks der Skalenentwicklung um automatisierte Generierungs- und Screening-Verfahren, verankert das Sprachmodell strikt in geladenen Quellen und unterwirft den Prozess einer durchgängigen menschlichen Kontrolle (Human-in-the-Loop).

Abgrenzung: NotebookLM-Scope vs. Externe Systeme

Für eine wissenschaftlich korrekte Anwendung unterscheidet das System strikt zwischen den Möglichkeiten innerhalb von NotebookLM und notwendigen externen Arbeitsschritten:

┌─────────────────────────────────────────────────┬─────────────────────────────────────────────────┐
│     Infrastruktur innerhalb von NotebookLM      │      Externe Arbeitsschritte & Systeme          │
├─────────────────────────────────────────────────┼─────────────────────────────────────────────────┤
│ • RAG-gestützte Konzeption aus Quelldokumenten  │ • Mathematisch-statistische Berechnungen         │
│   (Zhang & Zhang 2025) [6, 11].                │   (EGA, UVA, CFA, IRT-Analysen, PLS-SEM)        │
│ • Kontextualisierte Item-Generierung            │   via R/Python [10, 12, 13].                    │
│   (Lee et al. 2025) [1, 14].                   │ • Empirische Feld-Datenerhebungen an echten     │
│ • Heuristische In-silico-Vorselektion           │   Probanden-Stichproben [3, 15, 16].            │
│   (Lee et al. 2025; Stanton 2026) [17, 18].     │ • Kognitive Pretest-Interviews (Think-Aloud)    │
│ • Ableitung von Verbal Probes für Pretests      │   mit Personen der Zielgruppe                   │
│   (Artino et al. 2014) [3, 19, 20].             │   (Artino et al. 2014) [3, 20, 21].             │
└─────────────────────────────────────────────────┴─────────────────────────────────────────────────┘

2. Der 4-Phasen-Workflow im Überblick

Der Workflow verläuft in vier aufeinander aufbauenden Phasen. Um Semantic Drift und die unkritische Übernahme generierter Texte zu verhindern, ist jede Phase durch ein verbindliches Human-in-the-Loop-Gate (HITL-Gate) geschützt:

[Phase 1: Grounding & Konfiguration] ──► 🛑 HITL-Gate 1: Freigabe Theorie & Skalendesign
                                                   │
[Phase 2: Überpoolung & Taxonomie]   ──► 🛑 HITL-Gate 2: Sichtung & Freigabe Roh-Itempool
                                                   │
[Phase 3a: Inhaltlicher Review]      ──► [Phase 3b: Sprachlich-Methodischer Review]
                                                   │
[Phase 4: Ergebnismatrix & Pretest]  ──► 🛑 HITL-Gate 3 (Final): Freigabe des Pretest-Sets

3. Das Prompt-System (Phase 1 bis 4)

Die folgenden Prompts sind so formuliert, dass sie nacheinander in die Chat-Schnittstelle von NotebookLM eingegeben werden können. Sie nutzen das Retrieval-Augmented Generation (RAG) Prinzip, um Antworten direkt an den hochgeladenen Quellen auszurichten.

Phase 1: Quellengrundierung, Konstruktspezifikation & Skalendesign

Ziel: Theoretische Definition des Zielkonstrukts ausschließlich aus der geladenen Literatur sowie Festlegung des kontextbezogenen Skalendesigns.

Prompt 1 (In NotebookLM einzugeben):

Du agierst als wissenschaftlicher Experte für Psychometrie und Fragebogenkonstruktion.
Wir beginnen mit Phase 1 der Skalenentwicklung für das folgende Zielkonstrukt: [NAME DES KONSTRUKTS EINSETZEN] im Anwendungskontext: [ZIELGRUPPE / UNTERNEHMENSKONTEXT EINSETZEN].

Aufgabe:
1. Erstelle eine präzise theoretische Definition des Zielkonstrukts ausschließlich auf Basis der hochgeladenen Quellen.
2. Identifiziere bestehende Subdimensionen oder Facetten dieses Konstrukts.
3. Grenze das Zielkonstrukt explizit von verwandten Nachbarkonstrukten ab.
4. Quellenlücken-Check: Benenne transparent, welche Aspekte des Konstrukts in den vorliegenden Quellen fehlen oder unvollständig sind.
5. Methodische Empfehlung zur Konfiguration (Begründe kurz):
   - Empfohlener Überpoolungsfaktor (z. B. 2-fach bei einfachen Konstrukten vs. 3- bis 5-fach bei komplexen, multidimensionalen Konstrukten).
   - Empfohlene Antwortskala (z. B. 5-stufig unipolar bei Intensitäten/Häufigkeiten vs. 7-stufig bipolar bei differenzierten Einstellungen) inklusive Vorschlag für die verbalen Anker.

Wichtig: Nutze ausschließlich die hochgeladenen Quellen. Erfinde keine theoretischen Hintergründe aus deinem Trainingswissen.

🛑 HUMAN-IN-THE-LOOP (HITL-Gate 1): Der Forschende prüft die Konstruktdefinition, die identifizierten Quellenlücken und die Konfigurationsempfehlung. Erst nach manueller Freigabe oder Anpassung wird Phase 2 gestartet.

Phase 2: Kontextualisierte Item-Generierung & Herkunftstaxonomie

Ziel: Erzeugung eines überpoolten Roh-Itempools unter Einhaltung formeller Item-Schreibregeln und Zuweisung einer präzisen Herkunftstaxonomie.

Prompt 2 (In NotebookLM einzugeben):

Auf Basis der freigegebenen Konstruktdefinition und Konfiguration aus Phase 1 starten wir nun Phase 2: Die Item-Generierung.

Ziel: Generiere für die geplante Skalenlänge von [ANZAHL, z. B. 4] Items pro Dimension den vereinbarten Überpool von [ANZAHL x FAKTOR, z. B. 8 bis 12] Items.

Formulierungsregeln:
- Einfache, klare und unbolische Sprache (angepasst an das Sprachniveau der Zielgruppe).
- Keine Fachjargons, keine Doppelverneinungen und keine doppelseitigen Fragen (double-barreled items).
- Verwende die in Phase 1 festgelegte, vollständig beschriftete Antwortskala.

Prüfung auf Sonderfunktionen:
- Kennzeichne bei jedem Item, ob eine „Nicht anwendbar (N/A)“-Option erforderlich ist (z. B. wenn Befragte ohne Vor-Erfahrung die Frage sonst nicht valide beantworten können).
- Schlage gegebenenfalls eine Filterfrage vor, falls das Item praktische Nutzung voraussetzt.

Strikte Herkunftstaxonomie (Ordne JEDES Item genau EINER dieser 4 Kategorien zu):
- [Original unverändert]: Nativ deutschsprachige, valide Originalskala aus den Quellen.
- [Übersetzt]: Aus einer englischen Originalskala der Quellen übersetzt, ohne den inhaltlichen Kontext zu verändern.
- [Kontextuell angepasst]: Aus den Quellen entnommen, aber begrifflich/inhaltlich an den spezifischen Zielkontext angepasst.
- [In-silico neu konstruiert]: Auf Basis der theoretischen Konstruktdefinition vollständig neu erzeugt.

Gib die Items nummeriert, sortiert nach Subdimensionen und inklusive der zugehörigen Quelle aus.

🛑 HUMAN-IN-THE-LOOP (HITL-Gate 2): Der Forschende sichtet den Roh-Itempool auf Tonalität, Passung zur Zielgruppe und Vollständigkeit. Erst nach Freigabe startet die zweistufige LLM-Filterung.

Phase 3: Zweistufige Heuristische LLM-Prüfung (In-silico-Screening)

Ziel: Inhaltliche und sprachlich-methodische Vor-Filterung zur Reduktion von Mängeln und Redundanzen. Die Ausgaben dieser Phase stellen eine qualitative Heuristik dar und ersetzen keine statistischen Validierungsprüfungen.

Prompt 3a: Inhaltlicher Review (Construct Alignment & Crossover-Check)

Führe Phase 3a der Item-Prüfung durch. Der Fokus liegt ausschließlich auf der INHALTLICHEN PASSUNG (Construct Alignment).

Aufgabe:
1. Prüfe für jedes Item des Überpools, ob es das zugewiesene Zielkonstrukt exakt trifft (Correspondence).
2. Construct-Crossover-Check: Identifiziere gezielt Items, die fälschlicherweise eher ein Nachbarkonstrukt oder eine andere Dimension messen als die, der sie aktuell zugeordnet sind.
3. Sortiere Items aus, die inhaltlich am Zielkonstrukt vorbeigehen oder Fehlzuordnungen aufweisen, und begründe die Streichung kurz.

Prompt 3b: Sprachlich-Methodischer Review & Redundanzfilter

Führe nun Phase 3b auf den in Phase 3a verbliebenen Items durch. Der Fokus liegt auf SPRACHE, METHODIK und REDUNDANZ.

Aufgabe:
1. Sprachliche Prägnanz: Identifiziere und korrigiere unsaubere Formulierungen, versteckte Schiefen oder doppelte Verneinungen.
2. Redundanz-Filter: Identifiziere Item-Paare, die semantisch nahezu identische Aussagen ausdrücken. Streiche jeweils das schwächere oder kompliziertere Item.
3. Vorauswahl: Wähle pro Dimension die besten [FINAL BENÖTIGTE ANZAHL, z. B. 3-4] Items aus.

Wichtiger Hinweis zur Auswertung:
Bescheinige für die ausgewählten Items KEINE „empirische Validität“ oder „Bias-Freiheit“. Deklariere das Ergebnis explizit als „heuristisch bereinigten Vorschlag zur menschlichen Begutachtung“.

Phase 4: Finales HITL-Gatekeeping & Pretest-Leitfaden

Ziel: Zusammenstellung der finalen Ergebnismatrix und Vorbereitung empirischer kognitiver Interviews (Think-Aloud & Verbal Probing) zur Prüfung der Antwortprozess-Validität (Response Process Validity).

Prompt 4 (In NotebookLM einzugeben):

Erstelle das finale Übergabedokument für die menschliche Endprüfung und die empirische Pretest-Vorbereitung.

Aufgabe:
1. Ergebnismatrix: Erstelle eine übersichtliche Tabelle mit allen ausgewählten finalen Items enthaltend:
   - Item-ID & Finaler Item-Text
   - Zugeordnete Konstruktdimension
   - Exakte Herkunftskategorie ([Original unverändert], [Übersetzt], [Kontextuell angepasst] oder [In-silico neu konstruiert])
   - Notwendigkeit von N/A-Optionen oder Filterfragen
   - Kurze theoretische Begründung
2. Pretest-Leitfaden (Verbal Probing): Formuliere für jedes Item 1–2 gezielte Testfragen (Comprehension / Specific Probes) für kognitive Interviews (Think-Aloud).
3. Beachtungs-Hinweise für den Forschenden:
   - Worauf muss beim Pretest besonders geachtet werden (z. B. Verständnisprüfungen bei [Übersetzten] Items oder Akzeptanzprüfungen bei [In-silico neu konstruierten] Items)?

4. Schließe das Dokument zwingend mit folgendem methodischen Disclaimer ab:

"Methodischer Disclaimer: Dieses Instrument stellt das Ergebnis einer strukturierten, LLM-gestützten In-silico-Vorselektion dar. Aus den heuristischen Prüfschritten dieses Sprachmodells lässt sich keinerlei empirische Validität (wie faktorielle Struktur, Reliabilität, Diskriminanzvalidität oder Bias-Freiheit) ableiten. Vor einem wissenschaftlichen oder praktischen Einsatz muss das Instrument zwingend kognitiv pretestiert (Response Process Validity) und an einer realen Feldstichprobe statistisch evaluiert werden."

🛑 HUMAN-IN-THE-LOOP (HITL-Gate 3 / Final): Der Forschende unterzieht die Ergebnismatrix einer abschließenden inhaltlichen Prüfung, gibt den Pretest-Leitfaden frei und leitet die empirische Feldüberprüfung ein.

4. Methodische Best Practices & Klarstellungen

Keine universellen Stichprobenschwellen: In der empirischen Skalenvalidierung existieren keine starren Mindestgrößen als pauschale Regel. Die erforderliche Stichprobenstärke hängt von Faktoren wie der Kommunalität der Items, dem Grad der Überdetermination der Faktoren, dem gewählten Auswertungsverfahren (EFA, CFA, IRT, PLS-SEM) und dem Ausmaß fehlender Werte ab.

Saubere Herkunftskennzeichnung: Übersetzungen fremdsprachiger Originalskalen stellen eine sprachlich-kulturelle Transformation dar und müssen stets als [Übersetzt] oder [Kontextuell angepasst] deklariert werden, um den Bedarf für Pretests sichtbar zu machen.

Vermeidung der In-silico Validity Illusion: Ein Sprachmodell kann die linguistische Struktur von Texten analysieren, besitzt jedoch kein theoretisches Weltwissen und ersetzt keine menschlichen Probandenantworten.
