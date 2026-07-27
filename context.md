# Kontext & Anforderungen – Gruppe 5, Kurs 3WI-SP-23

Diese Datei fasst alle projektrelevanten Informationen zusammen, damit Claude Code
in einem neuen Gespräch sofort produktiv mitarbeiten kann.

---

## 1. Kurs und Gruppe

- **Kurs:** 3WI-SP-23 – Software-Projekt Case Study, DHSN (Duale Hochschule Sachsen)
- **Dozent:** Prof. Dr. Steffen Greiffenberg
- **Gruppe 5:** Marco, Karl, Ben, Marwin, Samira, Luca

**Grundprinzip des Kurses:**
Nicht die App-Idee steht zuerst, sondern die Frage: *Was muss ein späterer Prototyp leisten, damit er für mein Thema ein brauchbares Beispiel wird?* Jede Person arbeitet ein individuelles Theoriegebiet am gemeinsamen Projekt.

---

## 2. Gemeinsames Projekt: „Züge von Hanoi – Software"

Eine Android-App (Kotlin / Jetpack Compose), die:
1. Den **Ist-Zustand** des Hanoi-Rätsels erkennt (Kamera oder manuelle Eingabe)
2. Eine **optimale Lösung** berechnet (rekursiver Algorithmus)
3. Die **Züge automatisch / halbautomatisch** steuert
   (Visualisierung + optional physische Hardware via GPIO/Arduino)

**Zielgruppen der App:**
- Lernende (Studierende, die Rekursion verstehen wollen)
- Rätsel-Enthusiasten (optimale Lösungen finden)
- Maker (physische Hardware ansteuern)

**Was das Projekt für alle Themen leisten muss:**
- Bewusste Architekturentscheidungen (für Marco)
- Aktives Arbeiten mit Scrum-Elementen (für Luca)
- Anforderungserhebung mit Nutzern und SCRUM-Backlog (für Ben)
- Arbeit mit VCS (Git), Commit- und PR-Dokumentation (für Karl)
- Nutzerverhalten bei Mobile Apps (für Marwin)
- Aufbau einer Software Requirements Specification (für Samira)

---

## 3. Themen und Anforderungen pro Person

### Karl Bremer

#### Thema 1: Technische Schulden
**Folienbezug:** `12 - Stimme des Entwicklers`, `23 - Architektur`, `24 - Muster`

Bewusste und unbewusste Kompromisse erkennen und dokumentieren. Arbeit mit VCS (Git): Commit-Qualität, PR-Dokumentation, Refactoring-Bedarf.

**Artefakte:** Debt-Log, Codebeispiele, Architekturentscheidungen, Begründung von Kompromissen unter Zeitdruck.

**Anforderungen:**
- [ ] Ein **Backlog-Abschnitt für technische Schulden** ist vorhanden; Schulden werden explizit als eigene Kategorie erfasst
- [ ] Die **Boy Scout Rule** wird dokumentiert angewendet: Code wird bei jeder Änderung minimal verbessert
- [ ] Regelmäßige **Refactoring-Einträge** sind im Sprint-Backlog sichtbar (mindestens einmal pro Sprint)
- [ ] **Code Smells** (lange Methoden, duplizierter Code, große Klassen) werden im Code Review identifiziert und behoben
- [ ] Technische Schulden mit hohen "Zinsen" (häufig geänderter Code) werden priorisiert abgebaut

#### Thema 2: Voice of Developer
**Folienbezug:** `12 - Stimme des Entwicklers`, `04 - Qualität`, `23 - Architektur`

Anforderungen aus Entwicklersicht sichtbar machen: Wartbarkeit, Schnittstellen, Fehlerberichte, Monitoring, Integration. Quality Scenarios für nicht-funktionale Anforderungen.

**Artefakte:** Entwickleranforderungen, Begründungen, Konflikte mit Kundenanforderungen, Quality Scenarios (Stimulus/Quelle/Umgebung/Artefakt/Antwort/Metrik).

**Anforderungen:**
- [ ] Architekturentscheidungen (z.B. Wahl des UI-Frameworks) sind im Projekt schriftlich durch Entwicklerperspektive **begründet**
- [ ] Entwickler haben Qualitätsziele (Wartbarkeit, Testbarkeit) als **Entwickler-Stories** formuliert und ins Backlog aufgenommen
- [ ] Entwicklerfeedback zu Machbarkeit fließt in die Anforderungsverfeinerung ein (dokumentiert im Refinement)

---

### Ben Möckel

#### Thema 1: Epics, User Stories und Szenarien
**Folienbezug:** `08 - Epics`, `13 - Modelle`, `07 - SRS`

Anforderungen in natürlicher Sprache strukturieren und für Entwicklung nutzbar machen.

**4 Epics im Projekt:**
1. Zustandserkennung – System erkennt aktuellen Hanoi-Zustand
2. Lösungsberechnung – optimale Lösung für jeden gültigen Zustand
3. Interaktive Steuerung – Lösung schrittweise nachvollziehen oder automatisch ausführen
4. Lernmodus – Nutzer versteht, warum bestimmte Züge gemacht werden

**Artefakte:** Epic Backlog (MoSCoW), User Story Map, Akzeptanzkriterien, Änderungsprotokoll, Traceability Matrix.

**Anforderungen:**
- [ ] Alle Hauptfunktionen der App sind in **Epics** strukturiert
- [ ] Jedes Epic ist in **User Stories** nach dem Format "Als [Rolle] möchte ich [Funktion], damit [Nutzen]" zerlegt
- [ ] Alle User Stories erfüllen die **INVEST-Kriterien** (Independent, Negotiable, Valuable, Estimable, Small, Testable)
- [ ] Jede User Story besitzt **Akzeptanzkriterien** im Gherkin-Format ("Gegeben… wenn… dann…")
- [ ] Ein **Story Mapping** ist erstellt, das den Backbone (Nutzerreise) und die Priorisierung zeigt
- [ ] Das erste lauffähige **MVP-Release** ist durch Story Mapping definiert
- [ ] Stories enthalten **keine Implementierungsdetails** (Was, nicht Wie)
- [ ] Stories wurden per **Planning Poker** geschätzt
- [ ] Zu kritischen User Stories existieren **Szenarien**, die Sonderfälle und Fehlerverhalten beschreiben

#### Thema 2: Diffusion, Lock-In und Plattformentscheidungen
**Folienbezug:** `21 - Technologische Innovation`, `26 - UI`, `23 - Architektur`

Wie Plattformen, Standards und Ökosysteme Entscheidungen beeinflussen. Analyse von Technologiewahl (Android, Jetpack Compose, Room) auf Lock-In-Effekte und Wechselkosten.

**Artefakte:** Entscheidungsmatrix (Android vs. Flutter), Lock-In-Analyse, Diffusionsanalyse, Architecture Decision Records (ADRs).

**Anforderungen:**
- [ ] Die **Plattformentscheidung** (nativ Android vs. Cross-Platform) ist dokumentiert und technisch begründet
- [ ] Die Begründung berücksichtigt **Vendor Lock-in-Risiken** (z.B. proprietäre APIs, Cloud-Abhängigkeiten)
- [ ] Für alle eingesetzten Technologien ist das **Reifegrad-Niveau** (Early Majority / Late Majority) bewertet
- [ ] Abhängigkeiten von proprietären Services sind **minimiert** oder mit Migrationsplan versehen

---

### Samira Drögsler

#### Thema 1: SRS als integrierendes Projektdokument
**Folienbezug:** `07 - SRS`, `03 - Systemanalyse`, `13 - Modelle`

Aufbau einer Software Requirements Specification nach IEEE 29148. Systemkontext, interne/externe Elemente, Schnittstellen, Funktionen, Constraints.

**Artefakte:** SRS-Dokument, Systemkontextdiagramm, Schnittstellenbeschreibungen, Verweise auf Modelle.

**Besondere Frage (aus Einzelgespräch):** Ist ein SRS ein Produktbacklog oder umgekehrt? SRS im agilen Umfeld – Vor-/Nachteile. Verlauf des SRS im Projektverlauf beobachten.

**Anforderungen:**
- [ ] Ein **SRS-Dokument** nach IEEE 830-Gliederung ist vorhanden und gepflegt
- [ ] Das SRS enthält ein **Systemkontext-Diagramm** (System als Black Box mit allen externen Akteuren)
- [ ] Alle **Schnittstellen** sind beschrieben: UI, Protokoll, ggf. REST-API, Android OS-Schnittstellen
- [ ] Das SRS enthält **funktionale Anforderungen** (vollständig, eindeutig, prüfbar)
- [ ] Das SRS enthält **nicht-funktionale Anforderungen** als messbare Szenarien
- [ ] Das SRS ist **rückverfolgbar**: Jede Anforderung ist einer Quelle (Stakeholder, Szenario) zugeordnet
- [ ] Das SRS wird **iterativ gepflegt** (nicht einmal erstellt und vergessen)
- [ ] Das SRS verknüpft Use Cases / User Stories mit Qualitätsszenarien zu einem kohärenten Gesamtbild

#### Thema 2: Projektplanung und Umgang mit Unsicherheit
**Folienbezug:** `22 - Design Thinking`, `03 - Systemanalyse`, `12 - Stimme des Entwicklers`

Planung in einem kleinen, unsicheren Softwareprojekt: Backlog, Aufwandsschätzung, Risiken, Impediment List und Anpassungen.

**Artefakte:** Ursprüngliche Planung, Änderungen, Gründe, Auswirkungen auf Ergebnis und Teamarbeit.

**Anforderungen:**
- [ ] Ein **Sprint-Plan** ist vorhanden mit definierten Zielen pro Iteration
- [ ] Unsicherheiten und Risiken sind im **Risikoregister** erfasst
- [ ] Der Projektplan unterscheidet zwischen **sicheren Anforderungen** und **Annahmen / offenen Punkten**
- [ ] Technische Spikes zur Risikoreduzierung sind als **eigene Backlog-Einträge** sichtbar

---

### Marwin Lohmann

#### Thema 1: Mobile First und responsive Gestaltung
**Folienbezug:** `26 - UI`

Gestaltung unter Bedingungen mobiler Endgeräte: Layout für verschiedene Bildschirmgrößen, Ausrichtungen, Nutzungssituationen, Android-Fragmentierung.

**Artefakte:** Layoutvarianten, Testgeräte/Emulatoren, Fragmentierungsprobleme, Designentscheidungen.

**Anforderungen:**
- [ ] Die App ist für **mobile Nutzung als primären Formfaktor** entwickelt (kein nachträgliches Shrinking vom Desktop)
- [ ] Alle Layouts sind mit **Jetpack Compose** implementiert (kein statisches XML-Only-Layout)
- [ ] Es werden **keine absoluten Pixel-Angaben** verwendet; ausschließlich `dp` und `sp`
- [ ] Alle Touch-Targets sind mindestens **48×48 dp** groß
- [ ] Das UI folgt **Material Design 3** (Farben, Typografie, Komponenten aus dem offiziellen M3-System)
- [ ] Die App wurde auf **verschiedenen Bildschirmgrößen** getestet (small, normal, large)
- [ ] **Gesten** sind sinnvoll integriert (Swipe, Tap, Long Press) statt ausschließlich Buttons
- [ ] Die **Google Core App Quality**-Checkliste ist durchgeführt: CR-0 (alle Screens), CR-1 (Home-Taste), CR-2 (App-Wechsel)
- [ ] Es gibt keine **ANR-Fehler** und keine Abstürze im Normalbetrieb
- [ ] Die App lädt innerhalb von **< 2 Sekunden** nach Start

#### Thema 2: Architekturprinzipien im kleinen Projekt
**Folienbezug:** `23 - Architektur`

Prinzipien wie Modularität, Kohäsion, Kopplung, Separation of Concerns, Information Hiding, Dependency Injection gezielt anwenden.

**Artefakte:** Vorher/Nachher-Struktur, Codeausschnitte, Entscheidung, Grenzen der Anwendung.

**Anforderungen:**
- [ ] Die Architektur folgt dem **MVVM-Muster**: View (Compose) → ViewModel → Repository
- [ ] **Separation of Concerns** ist umgesetzt: Logik ist strikt von UI-Code getrennt
- [ ] **Dependency Injection** (Hilt oder Koin) wird eingesetzt; kein manuelles `new` für Services und Repositories
- [ ] Es gibt **keine zyklischen Abhängigkeiten** zwischen Modulen (Acyclic Dependencies Principle)
- [ ] Die Architektur ist in **3–4 klar abgegrenzten Modulen/Paketen** strukturiert (UI, Domain, Data, Hardware)
- [ ] **Information Hiding**: Interne Implementierungsdetails der Hardware-Schicht sind nicht direkt aus der UI zugänglich

---

### Marco Weber

#### Thema 1: Architekturstile und Architekturmodelle
**Folienbezug:** `23 - Architektur`

Bewusste Wahl eines Architekturmodells (Client-Server, Schichtenarchitektur, Event Driven Architecture, Microservices etc.) und kritische Einordnung.

**Artefakte:** Vergleich von Alternativen, Architekturentscheidung, Diagramme, Risiken.

**Anforderungen:**
- [ ] Der gewählte **Architekturstil** (z.B. Schichtenarchitektur, Client-Server) ist im SAD dokumentiert und begründet
- [ ] Ein **C4-Modell** (mindestens Context- und Container-Ebene) ist als Architekturdokumentation vorhanden
- [ ] **Entwurfsmuster** sind im Quellcode bewusst eingesetzt und im SAD dokumentiert:
  - Observer (z.B. Status → UI via StateFlow/LiveData)
  - Repository (Abstraktion der Hardware-Kommunikation)
  - Command (Steuerungsbefehle als Objekte gekapselt)
  - Facade (vereinfachte Steuerungs-API für die Business Logic)
  - Proxy (Verbindungscheck vor Hardware-Aufrufen)
  - Singleton (Manager: genau eine Verbindungsinstanz)
- [ ] Für jedes eingesetzte Muster existiert ein **Klassendiagramm** (nur musterspezifische Elemente)
- [ ] Alle Stellen im Code, an denen ein Muster verwendet wird, sind **dokumentiert** (SAD Abschnitt 8)

#### Thema 2: Quality Scenarios für nicht-funktionale Anforderungen
**Folienbezug:** `12 - Stimme des Entwicklers`, `04 - Qualität`, `23 - Architektur`

Qualitätsanforderungen konkret, prüfbar und architekturrelevant formulieren. Szenarien mit Stimulus, Quelle, Umgebung, Artefakt, Antwort und Metrik.

**Artefakte:** Quality Scenarios, abgeleitete Entwurfsentscheidungen, Mess- oder Prüfansatz.

**Anforderungen** (Schema: Stimulus → Quelle → Artefakt → Umgebung → Antwort → Antwortmaß):
- [ ] **Reaktionszeit**: Nutzer gibt Steuerbefehl → System reagiert in **< 150 ms**
- [ ] **Verbindungsabbruch**: Verbindung verloren → App zeigt Fehlermeldung in **< 2 Sekunden**, startet automatischen Reconnect
- [ ] **Usability**: Neuer Nutzer ohne Anleitung → erste Grundfunktion in **< 2 Minuten** bedienbar
- [ ] **Ressourcenverbrauch**: 30 Minuten Normalbetrieb → Akkuverbrauch **< 15%** auf Standard-Smartphone
- [ ] **Fehlertoleranz**: Ungültige Eingabe oder unerwarteter Gerätezustand → App stürzt nicht ab, zeigt verständliche Fehlermeldung
- [ ] Alle Quality Scenarios sind im **SRS und im SAD** referenziert
- [ ] Quality Scenarios sind als **automatisierte Tests** oder **manuelle Testprotokolle** abgesichert

---

### Luca Neubert

#### Thema 1: Agiles Arbeiten mit Scrum-Elementen
**Folienbezug:** `22 - Design Thinking`

Scrum nicht vollständig nachspielen, sondern geeignete Elemente bewusst einsetzen: Sprints, Backlog, Rollen, Daily Scrum, Sprint Review, Retrospektive.

**Artefakte:** Backlog, Sprint-Ziele, Review-Ergebnisse, Impediment List, Anpassungen.

**Anforderungen:**
- [ ] Das Team arbeitet in **Sprints** (empfohlen: 1–2 Wochen) mit definierten Sprint-Zielen
- [ ] Ein **Product Backlog** ist vorhanden, priorisiert und gepflegt
- [ ] Regelmäßige **Sprint Reviews** und **Retrospektiven** finden statt und sind dokumentiert
- [ ] **Daily Stand-ups** (oder äquivalente kurze Sync-Meetings) werden durchgeführt
- [ ] Eine **Definition of Done (DoD)** ist festgelegt (z.B. Code review, Tests bestanden, Dokumentation aktualisiert)
- [ ] **Velocity** wird pro Sprint gemessen (Story Points abgeschlossen vs. geplant)
- [ ] Refactoring ist Teil der DoD

#### Thema 2: Qualität von Anforderungen
**Folienbezug:** `06 - Qualität von Anforderungen`, `04 - Qualität`

Korrektheit, Vollständigkeit, Verständlichkeit, Konsistenz, Testbarkeit, Nachvollziehbarkeit und Realisierbarkeit von Anforderungen prüfen.

**Artefakte:** Checkliste, Review-Ergebnisse, verbesserte Fassungen, Reflexion der Kriterien (ISO/IEC/IEEE 29148).

**Anforderungen:**
- [ ] Alle Anforderungen im Backlog und SRS sind auf **SMART-Kriterien** geprüft (Spezifisch, Messbar, Akzeptiert, Realistisch, Terminiert)
- [ ] **Antipatterns** in Anforderungen sind eliminiert: keine vagen Adjektive ("benutzerfreundlich", "schnell"), keine Nominalisierungen ohne klaren Akteur
- [ ] Jede Anforderung hat **genau eine Interpretation** (Eindeutigkeits-Test: zwei Leser → gleiche Schlussfolgerung)
- [ ] Anforderungen beschreiben **Was**, nicht **Wie** (kein Vorschreiben von Implementierungen)
- [ ] Ein **Peer-Review-Prozess** für Anforderungen ist etabliert: jede Story wird von einem anderen Teammitglied geprüft
- [ ] Akzeptanzkriterien sind im **Gherkin-Format** verfasst (Gegeben… wenn… dann…)

---

## 4. Verbindungen und Spannungen zwischen den Themen

**Verbindungen (aus Gruppenarbeit):**

| Thema A | Thema B | Verbindung |
|---------|---------|------------|
| Ben: User Stories | Samira: SRS | Stories werden Teil des SRS; SRS strukturiert die Anforderungen |
| Ben: User Stories | Luca: Scrum | Stories leben im Scrum-Backlog; Scrum-Sprints priorisieren Stories |
| Ben: User Stories | Luca: Qualität von Anforderungen | Akzeptanzkriterien müssen Qualitätskriterien erfüllen |
| Ben: Diffusion/Lock-In | Marco: Architekturstile | Plattformwahl beeinflusst Architekturmuster; Lock-In durch Architekturentscheidungen |
| Marco: Architekturstile | Marco: Quality Scenarios | Architekturentscheidungen werden durch Quality Scenarios begründet |
| Marco: Architekturstile | Karl: Tech. Schulden | Architekturentscheidungen erzeugen oder vermeiden technische Schulden |
| Karl: Tech. Schulden | Karl: Voice of Developer | Entwickleranforderungen decken Schulden auf; VoD verhindert neue Schulden |
| Karl: Voice of Developer | Samira: SRS | Entwickleranforderungen fließen ins SRS ein |
| Marwin: Mobile First | Marwin: Architekturprinzipien | Mobile-First-Design erfordert Separation of Concerns, klare ViewModel-Struktur |
| Samira: SRS | Samira: Projektplanung | SRS-Umfang hängt von Projektplanung ab; Unsicherheit beeinflusst SRS-Tiefe |
| Luca: Scrum | Samira: Projektplanung | Scrum ist eine Form der Projektplanung unter Unsicherheit |

**Spannungen (dokumentiert im Gruppenblick):**
- Architekturprinzipien (Marwin) ←→ Architekturmodelle (Marco): unterschiedliche Abstraktionsebene
- Quality Scenarios (Marco) ←→ SRS (Samira): Überschneidung bei nicht-funktionalen Anforderungen
- Architekturmodelle (Marco) ←→ Lock-In/Plattformentscheidungen (Ben): Wechselwirkung zwischen Stil und Plattform
- Epics/User Stories (Ben) ←→ Scrum (Luca): Wer schreibt die Stories – PO oder Team?
- Scrum-Tempo ←→ SRS-Dokumentationstiefe: Wie viel Dokumentation ist agil noch sinnvoll?

---

## 5. Pflichtartefakte des Projekts

| Artefakt | Thema |
|---|---|
| Product Backlog (mit Epics, Stories, Tech-Debt-Einträgen) | Epics, SCRUM, Tech. Schulden |
| Story Map (Backbone + Priorisierung) | Epics |
| SRS-Dokument (IEEE 830) inkl. Systemkontext | SRS |
| SAD-Dokument inkl. C4-Modell, Muster-Dokumentation (Abschnitt 8) | Architektur, Muster |
| Quality Scenarios (mind. 5, messbar) | Quality-Scenarios |
| Plattformentscheidung (dokumentiert + begründet) | Lock-In/Plattform |
| Sprint-Protokolle (Reviews, Retros, DoD) | SCRUM |
| Anforderungs-Review-Protokoll | Qualität von Anforderungen |
| Technische Schulden-Log | Technische Schulden |
| UI-Testprotokoll (Core App Quality) | Mobile-First |

---

## 6. Relevante Kurskonzepte nach Vorlesung

| Vorlesung | Thema                        | Schlüsselbegriffe                                                              |
|-----------|------------------------------|--------------------------------------------------------------------------------|
| 03        | Systemanalyse                | Systemgrenze, Umwelt, Input/Output, soziotechnisches System                    |
| 04        | Qualität                     | ISO 25010, Qualitätsmerkmale, Checkliste                                       |
| 05        | Anforderungen                | Funktionale / nicht-funktionale Anforderungen, Validierung, Verifizierung      |
| 06        | Qualität von Anforderungen   | ISO/IEC/IEEE 29148, Korrektheit, Vollständigkeit, Testbarkeit, Traceability    |
| 07        | SRS                          | Systemkontext, Produktfunktionen, Schnittstellen, User Characteristics         |
| 08        | Epics                        | Epics, User Stories, Szenarien, Akzeptanzkriterien, Zerlegung                  |
| 09        | Personas                     | Persona-Steckbriefe, Touchpoints, Zielgruppenidentifikation                    |
| 10        | Voice of Customer            | Interview, 5W1H/KIPLING, Lastenheft, Kundenanforderungen                       |
| 11        | KANO                         | Basis-/Leistungs-/Begeisterungsanforderungen, MoSCoW, Priorisierung            |
| 12        | Voice of Developer           | Tech. Schulden, Quality Scenarios, Stimulus/Quelle/Umgebung/Artefakt/Antwort   |
| 13        | Modelle                      | Use-Case-, Aktivitäts-, Klassendiagramme, Konsistenz                           |
| 21        | Technologische Innovation    | Diffusion, Lock-In, Netzeffekte, First Mover, Ecosystem Co-Evolution           |
| 22        | Design Thinking / Scrum      | Empathie-Define-Ideate-Prototype-Test, Sprints, Backlog, Retrospektive         |
| 23        | Architektur                  | Sichten, Prinzipien, Modularität, SoC, Dependency Injection, Architekturstile  |
| 24        | Muster                       | Observer, DAO, Proxy, Gang-of-Four, Kontext/Problem/Lösung/Konsequenzen        |
| 25        | UML                          | Component Diagram, Deployment Diagram, Interfaces, Deployment Targets          |
| 26        | UI                           | Jetpack Compose, Material Design, Mobile First, ViewModel, Usability           |
| 27        | Testen                       | Dynamisches Testen, Regression, Emulator vs. Gerät, SUS, Fehlerklassifikation |
