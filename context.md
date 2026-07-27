# Kontext: Case Study – Gruppe 5, Kurs 3WI-SP-23

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

## 3. Themen aller Gruppenmitglieder (je 2 Theorieblöcke)

### Karl Bremer
**Thema 1: Technische Schulden** | Folienbezug: `12 - Stimme des Entwicklers`, `23 - Architektur`, `24 - Muster`

Bewusste und unbewusste Kompromisse erkennen und dokumentieren. Arbeit mit VCS (Git): Commit-Qualität, PR-Dokumentation, Refactoring-Bedarf.

**Artefakte:** Debt-Log, Codebeispiele, Architekturentscheidungen, Begründung von Kompromissen unter Zeitdruck.

**Thema 2: Voice of Developer** | Folienbezug: `12 - Stimme des Entwicklers`, `04 - Qualität`, `23 - Architektur`

Anforderungen aus Entwicklersicht sichtbar machen: Wartbarkeit, Schnittstellen, Fehlerberichte, Monitoring, Integration. Quality Scenarios für nicht-funktionale Anforderungen.

**Artefakte:** Entwickleranforderungen, Begründungen, Konflikte mit Kundenanforderungen, Quality Scenarios (Stimulus/Quelle/Umgebung/Artefakt/Antwort/Metrik).

---

### Ben Möckel
**Thema 1: Epics, User Stories und Szenarien** | Folienbezug: `08 - Epics`, `13 - Modelle`, `07 - SRS`

Anforderungen in natürlicher Sprache strukturieren und für Entwicklung nutzbar machen.

**4 Epics im Projekt:**
1. Zustandserkennung – System erkennt aktuellen Hanoi-Zustand
2. Lösungsberechnung – optimale Lösung für jeden gültigen Zustand
3. Interaktive Steuerung – Lösung schrittweise nachvollziehen oder automatisch ausführen
4. Lernmodus – Nutzer versteht, warum bestimmte Züge gemacht werden

**Artefakte:** Epic Backlog (MoSCoW), User Story Map, Akzeptanzkriterien, Änderungsprotokoll, Traceability Matrix.

**Thema 2: Diffusion, Lock-In und Plattformentscheidungen** | Folienbezug: `21 - Technologische Innovation`, `26 - UI`, `23 - Architektur`

Wie Plattformen, Standards und Ökosysteme Entscheidungen beeinflussen. Analyse von Technologiewahl (Android, Jetpack Compose, Room) auf Lock-In-Effekte und Wechselkosten.

**Artefakte:** Entscheidungsmatrix (Android vs. Flutter), Lock-In-Analyse, Diffusionsanalyse, Architecture Decision Records (ADRs).

---

### Samira Drögsler
**Thema 1: SRS als integrierendes Projektdokument** | Folienbezug: `07 - SRS`, `03 - Systemanalyse`, `13 - Modelle`

Aufbau einer Software Requirements Specification nach IEEE 29148. Systemkontext, interne/externe Elemente, Schnittstellen, Funktionen, Constraints.

**Artefakte:** SRS-Dokument, Systemkontextdiagramm, Schnittstellenbeschreibungen, Verweise auf Modelle.

**Thema 2: Projektplanung und Umgang mit Unsicherheit** | Folienbezug: `22 - Design Thinking`, `03 - Systemanalyse`, `12 - Stimme des Entwicklers`

Planung in einem kleinen, unsicheren Softwareprojekt: Backlog, Aufwandsschätzung, Risiken, Impediment List und Anpassungen.

**Artefakte:** Ursprüngliche Planung, Änderungen, Gründe, Auswirkungen auf Ergebnis und Teamarbeit.

**Besondere Frage (aus Einzelgespräch):** Ist ein SRS ein Produktbacklog oder umgekehrt? SRS im agilen Umfeld – Vor-/Nachteile. Verlauf des SRS im Projektverlauf beobachten.

---

### Marwin Lohmann
**Thema 1: Mobile First und responsive Gestaltung** | Folienbezug: `26 - UI`

Gestaltung unter Bedingungen mobiler Endgeräte: Layout für verschiedene Bildschirmgrößen, Ausrichtungen, Nutzungssituationen, Android-Fragmentierung.

**Artefakte:** Layoutvarianten, Testgeräte/Emulatoren, Fragmentierungsprobleme, Designentscheidungen.

**Thema 2: Architekturprinzipien im kleinen Projekt** | Folienbezug: `23 - Architektur`

Prinzipien wie Modularität, Kohäsion, Kopplung, Separation of Concerns, Information Hiding, Dependency Injection gezielt anwenden.

**Artefakte:** Vorher/Nachher-Struktur, Codeausschnitte, Entscheidung, Grenzen der Anwendung.

---

### Marco Weber
**Thema 1: Architekturstile und Architekturmodelle** | Folienbezug: `23 - Architektur`

Bewusste Wahl eines Architekturmodells (Client-Server, Schichtenarchitektur, Event Driven Architecture, Microservices etc.) und kritische Einordnung.

**Artefakte:** Vergleich von Alternativen, Architekturentscheidung, Diagramme, Risiken.

**Thema 2: Quality Scenarios für nicht-funktionale Anforderungen** | Folienbezug: `12 - Stimme des Entwicklers`, `04 - Qualität`, `23 - Architektur`

Qualitätsanforderungen konkret, prüfbar und architekturrelevant formulieren. Szenarien mit Stimulus, Quelle, Umgebung, Artefakt, Antwort und Metrik.

**Artefakte:** Quality Scenarios, abgeleitete Entwurfsentscheidungen, Mess- oder Prüfansatz.

---

### Luca Neubert
**Thema 1: Agiles Arbeiten mit Scrum-Elementen** | Folienbezug: `22 - Design Thinking`

Scrum nicht vollständig nachspielen, sondern geeignete Elemente bewusst einsetzen: Sprints, Backlog, Rollen, Daily Scrum, Sprint Review, Retrospektive.

**Artefakte:** Backlog, Sprint-Ziele, Review-Ergebnisse, Impediment List, Anpassungen.

**Thema 2: Qualität von Anforderungen** | Folienbezug: `06 - Qualität von Anforderungen`, `04 - Qualität`

Korrektheit, Vollständigkeit, Verständlichkeit, Konsistenz, Testbarkeit, Nachvollziehbarkeit und Realisierbarkeit von Anforderungen prüfen.

**Artefakte:** Checkliste, Review-Ergebnisse, verbesserte Fassungen, Reflexion der Kriterien (ISO/IEC/IEEE 29148).

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

## 7. Relevante Kurskonzepte nach Vorlesung

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



