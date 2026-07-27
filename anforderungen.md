# Anforderungen – Züge von Hanoi App

Dieses Dokument listet alle Anforderungen, die das Projekt erfüllen muss, um die Prüfungsthemen aller Teammitglieder zu bedienen. Die Anforderungen sind nach Themenblock gegliedert.

---

## Übersicht der Themenblöcke

| Person | Thema 1 | Thema 2 |
|---|---|---|
| Karl Bremer | Technische Schulden | Voice of Developer |
| Ben Möckel | Epics, User Stories & Szenarien | Diffusion, Lock-In und Plattformentscheidungen |
| Samira Drögsler | SRS als integrierendes Projektdokument | Projektplanung und Umgang mit Unsicherheit |
| Marwin Lohmann | Mobile-First & responsive Gestaltung | Architektur Prinzipien im kleinen Projekt |
| Marco Weber | Architekturstile und -modelle | Quality-Scenarios für nichtfunktionale Anforderungen |
| Luca Neubert | Agiles Arbeiten mit SCRUM-Elementen | Qualität von Anforderungen |

---

## 1. Technische Schulden & Voice of Developer (Karl Bremer)

### Technische Schulden
- [ ] Ein **Backlog-Abschnitt für technische Schulden** ist vorhanden; Schulden werden explizit als eigene Kategorie erfasst
- [ ] Die **Boy Scout Rule** wird dokumentiert angewendet: Code wird bei jeder Änderung minimal verbessert
- [ ] Regelmäßige **Refactoring-Einträge** sind im Sprint-Backlog sichtbar (mindestens einmal pro Sprint)
- [ ] **Code Smells** (lange Methoden, duplizierter Code, große Klassen) werden im Code Review identifiziert und behoben
- [ ] Technische Schulden mit hohen "Zinsen" (häufig geänderter Code: z.B. Bluetooth-Kommunikation) werden priorisiert abgebaut

### Voice of Developer
- [ ] Architekturentscheidungen (z.B. Wahl des UI-Frameworks, Bluetooth-Bibliothek) sind im Projekt schriftlich durch Entwicklerperspektive **begründet**
- [ ] Entwickler haben Qualitätsziele (Wartbarkeit, Testbarkeit) als **Entwickler-Stories** formuliert und ins Backlog aufgenommen
- [ ] Entwicklerfeedback zu Machbarkeit fließt in die Anforderungsverfeinerung ein (dokumentiert im Refinement)

---

## 2. Epics, User Stories & Szenarien (Ben Möckel)

### Epics & User Stories
- [ ] Alle Hauptfunktionen der App sind in **Epics** strukturiert (z.B. "Zugsteuerung", "Verbindungsmanagement", "Streckenverwaltung")
- [ ] Jedes Epic ist in **User Stories** nach dem Format "Als [Rolle] möchte ich [Funktion], damit [Nutzen]" zerlegt
- [ ] Alle User Stories erfüllen die **INVEST-Kriterien** (Independent, Negotiable, Valuable, Estimable, Small, Testable)
- [ ] Jede User Story besitzt **Akzeptanzkriterien** im Gherkin-Format ("Gegeben… wenn… dann…")
- [ ] Ein **Story Mapping** ist erstellt, das den Backbone (Nutzerreise) und die Priorisierung zeigt
- [ ] Das erste lauffähige **MVP-Release** ist durch Story Mapping definiert
- [ ] Stories enthalten **keine Implementierungsdetails** (Was, nicht Wie)
- [ ] Stories wurden per **Planning Poker** geschätzt

### Szenarien
- [ ] Zu kritischen User Stories existieren **Szenarien**, die Sonderfälle und Fehlerverhalten beschreiben (z.B. Verbindungsabbruch beim Fahren)

---

## 3. Diffusion, Lock-In und Plattformentscheidungen (Ben Möckel)

- [ ] Die **Plattformentscheidung** (nativ Android vs. Cross-Platform) ist dokumentiert und technisch begründet
- [ ] Die Begründung berücksichtigt **Vendor Lock-in-Risiken** (z.B. proprietäre BT-APIs, Cloud-Abhängigkeiten)
- [ ] Für alle eingesetzten Technologien ist das **Reifegrad-Niveau** (Early Majority / Late Majority) bewertet
- [ ] Abhängigkeiten von proprietären Services sind **minimiert** oder mit Migrationsplan versehen
- [ ] Die Wahl von Bluetooth LE als Kommunikationstechnologie ist mit Verweis auf **Verbreitung und Standardisierung** begründet

---

## 4. SRS als integrierendes Projektdokument (Samira Drögsler)

- [ ] Ein **SRS-Dokument** nach IEEE 830-Gliederung ist vorhanden und gepflegt
- [ ] Das SRS enthält ein **Systemkontext-Diagramm** (System als Black Box mit allen externen Akteuren)
- [ ] Alle **Schnittstellen** sind beschrieben: UI, Bluetooth LE Protokoll, ggf. REST-API, Android OS-Schnittstellen
- [ ] Das SRS enthält **funktionale Anforderungen** (vollständig, eindeutig, prüfbar)
- [ ] Das SRS enthält **nicht-funktionale Anforderungen** (Reaktionszeit, Akkuverbrauch, Verfügbarkeit) als messbare Szenarien
- [ ] Das SRS ist **rückverfolgbar**: Jede Anforderung ist einer Quelle (Stakeholder, Szenario) zugeordnet
- [ ] Das SRS wird **iterativ gepflegt** (nicht einmal erstellt und vergessen)
- [ ] Das SRS verknüpft Use Cases / User Stories mit Qualitätsszenarien zu einem kohärenten Gesamtbild

---

## 5. Projektplanung und Umgang mit Unsicherheit (Samira Drögsler)

- [ ] Ein **Sprint-Plan** ist vorhanden mit definierten Zielen pro Iteration
- [ ] Unsicherheiten und Risiken (z.B. Hardware-Verfügbarkeit, unbekannte BT-Protokolle) sind im **Risikoregister** erfasst
- [ ] Der Projektplan unterscheidet zwischen **sicheren Anforderungen** und **Annahmen / offenen Punkten**
- [ ] Technische Spikes zur Risikoreduzierung (z.B. BT-Prototyp) sind als **eigene Backlog-Einträge** sichtbar

---

## 6. Mobile-First & Responsive Gestaltung (Marwin Lohmann)

- [ ] Die App ist für **mobile Nutzung als primären Formfaktor** entwickelt (kein nachträgliches Shrinking vom Desktop)
- [ ] Alle Layouts sind mit **Jetpack Compose** implementiert (kein statisches XML-Only-Layout)
- [ ] Es werden **keine absoluten Pixel-Angaben** verwendet; ausschließlich `dp` und `sp`
- [ ] Alle Touch-Targets sind mindestens **48×48 dp** groß
- [ ] Das UI folgt **Material Design 3** (Farben, Typografie, Komponenten aus dem offiziellen M3-System)
- [ ] Die App wurde auf **verschiedenen Bildschirmgrößen** getestet (small, normal, large)
- [ ] **Gesten** sind sinnvoll integriert (Swipe, Tap, Long Press) statt ausschließlich Buttons
- [ ] Die **Google Core App Quality**-Checkliste ist durchgeführt: CR-0 (alle Screens), CR-1 (Home-Taste), CR-2 (App-Wechsel)
- [ ] Es gibt keine **ANR-Fehler** (App Not Responding) und keine Abstürze im Normalbetrieb
- [ ] Die App lädt innerhalb von **< 2 Sekunden** nach Start

---

## 7. Architekturprinzipien im kleinen Projekt (Marwin Lohmann)

- [ ] Die Architektur folgt dem **MVVM-Muster**: View (Compose) → ViewModel → Repository
- [ ] **Separation of Concerns** ist umgesetzt: Bluetooth-Logik ist strikt von UI-Code getrennt
- [ ] **Dependency Injection** (Hilt oder Koin) wird eingesetzt; kein manuelles `new` für Services und Repositories
- [ ] Es gibt **keine zyklischen Abhängigkeiten** zwischen Modulen (Acyclic Dependencies Principle)
- [ ] Die Architektur ist in **3–4 klar abgegrenzten Modulen/Paketen** strukturiert (UI, Domain, Data, BT)
- [ ] **Information Hiding**: Interne Implementierungsdetails der Bluetooth-Schicht sind nicht direkt aus der UI zugänglich

---

## 8. Architekturstile und -modelle (Marco Weber)

- [ ] Der gewählte **Architekturstil** (z.B. Schichtenarchitektur, Client-Server) ist im SAD dokumentiert und begründet
- [ ] Ein **C4-Modell** (mindestens Context- und Container-Ebene) ist als Architekturdokumentation vorhanden
- [ ] **Entwurfsmuster** sind im Quellcode bewusst eingesetzt und in Abschnitt 8 des SAD dokumentiert:
  - Observer (z.B. Bluetooth-Status → UI via StateFlow/LiveData)
  - Repository (Abstraktion der BT-Hardware-Kommunikation)
  - Command (Steuerungsbefehle als Objekte gekapselt)
  - Facade (vereinfachte Steuerungs-API für die Business Logic)
  - Proxy (Verbindungscheck vor BT-Aufrufen)
  - Singleton (BluetoothManager: genau eine Verbindungsinstanz)
- [ ] Für jedes eingesetzte Muster existiert ein **Klassendiagramm** (nur musterspezifische Elemente)
- [ ] Alle Stellen im Code, an denen ein Muster verwendet wird, sind **dokumentiert** (Abschnitt 8 SAD)

---

## 9. Quality-Scenarios für nichtfunktionale Anforderungen (Marco Weber)

Jedes Szenario folgt dem Schema: **Stimulus → Quelle → Artefakt → Umgebung → Antwort → Antwortmaß**

- [ ] **Reaktionszeit**: Nutzer gibt Steuerbefehl → Bluetooth-Paket gesendet → Zug reagiert in **< 150 ms**
- [ ] **Verbindungsabbruch**: BT-Verbindung verloren → App zeigt Fehlermeldung in **< 2 Sekunden**, startet automatischen Reconnect
- [ ] **Usability**: Neuer Nutzer ohne Anleitung → erste Grundfunktion in **< 2 Minuten** bedienbar
- [ ] **Ressourcenverbrauch**: 30 Minuten Normalbetrieb → Akkuverbrauch **< 15%** auf Standard-Smartphone
- [ ] **Fehlertoleranz**: Ungültige Eingabe oder unerwarteter Gerätezustand → App stürzt nicht ab, zeigt verständliche Fehlermeldung
- [ ] Alle Quality Scenarios sind im **SRS und im SAD** referenziert
- [ ] Quality Scenarios sind als **automatisierte Tests** (Unit/Integration) oder **manuelle Testprotokolle** abgesichert

---

## 10. Agiles Arbeiten mit SCRUM-Elementen (Luca Neubert)

- [ ] Das Team arbeitet in **Sprints** (empfohlen: 1–2 Wochen) mit definierten Sprint-Zielen
- [ ] Ein **Product Backlog** ist vorhanden, priorisiert und gepflegt
- [ ] Regelmäßige **Sprint Reviews** und **Retrospektiven** finden statt und sind dokumentiert
- [ ] **Daily Stand-ups** (oder äquivalente kurze Sync-Meetings) werden durchgeführt
- [ ] Eine **Definition of Done (DoD)** ist festgelegt (z.B. Code review, Tests bestanden, Dokumentation aktualisiert)
- [ ] **Velocity** wird pro Sprint gemessen (Story Points abgeschlossen vs. geplant)
- [ ] Refactoring ist Teil der DoD

---

## 11. Qualität von Anforderungen (Luca Neubert)

- [ ] Alle Anforderungen im Backlog und SRS sind auf **SMART-Kriterien** geprüft (Spezifisch, Messbar, Akzeptiert, Realistisch, Terminiert)
- [ ] **Antipatterns** in Anforderungen sind eliminiert: keine vagen Adjektive ("benutzerfreundlich", "schnell"), keine Optionen statt Festlegungen, keine Nominalisierungen ohne klaren Akteur
- [ ] Jede Anforderung hat **genau eine Interpretation** (Eindeutigkeits-Test: zwei Leser → gleiche Schlussfolgerung)
- [ ] Anforderungen beschreiben **Was**, nicht **Wie** (kein Vorschreiben von Implementierungen)
- [ ] Ein **Peer-Review-Prozess** für Anforderungen ist etabliert: jede Story wird von einem anderen Teammitglied auf Qualitätskriterien geprüft
- [ ] Akzeptanzkriterien sind im **Gherkin-Format** verfasst (Gegeben… wenn… dann…)

---

## Zusammenfassung: Pflichtartefakte des Projekts

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
