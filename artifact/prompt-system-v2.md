# Prompt-System für die LLM-gestützte Fragebogenentwicklung (Version 2.0)

Dieses Dokument enthält die direkt einsetzbaren finalen Prompts des **Prompt-Systems (v2.0)** für **NotebookLM**. Die Prompts werden sequenziell nacheinander in die Chat-Schnittstelle eingegeben.

---

## Phase 1: Quellengrundierung, Konstruktspezifikation & Skalendesign

```text
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

"Methodischer Disclaimer: Dieses Instrument stellt das Ergebnis einer strukturierten, LLM-gestützten In-silico-Vorselektion dar. Aus den heuristischen Prüfschritten dieses Sprachmodells lässt sich keinerlei empirische Validität (wie faktorielle Struktur, Reliabilität, Diskriminanzvalidität oder Bias-Freiheit) drive/ableiten. Vor einem wissenschaftlichen oder praktischen Einsatz muss das Instrument zwingend kognitiv pretestiert (Response Process Validity) und an einer realen Feldstichprobe statistisch evaluiert werden."
🛑 HUMAN-IN-THE-LOOP (HITL-Gate 3 / Final): Der Forschende unterzieht die Ergebnismatrix einer abschließenden inhaltlichen Prüfung, gibt den Pretest-Leitfaden frei und leitet die empirische Feldüberprüfung ein.
