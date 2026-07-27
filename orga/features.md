# Feature-Liste: Züge von Hanoi

> **Architektur-Constraint:** Kein Backend / kein Server — die gesamte Anwendungslogik (Algorithmus, Zustandsverwaltung, Steuerung) läuft vollständig in der App selbst.

> **Technologie:** Native Android App mit **Kotlin** + Jetpack Compose

### Warum Kotlin?

| | Kotlin | Flutter (Dart) | React Native (JS/TS) |
|---|---|---|---|
| **Erstklassiger Android-Support** | ✅ Offizielle Google-Sprache seit 2017 | ⚠️ Cross-Platform, Android-APIs nur per Plugin | ⚠️ JavaScript-Bridge, höhere Latenz |
| **UI-Toolkit** | ✅ Jetpack Compose (Google, nahtlose Android-Integration) | ⚠️ Eigenes Widget-System (ausgereift, aber Drittanbieter) | ⚠️ Eigenes Komponenten-System (Drittanbieter, JS-Bridge) |
| **Hardware-Zugriff** (HTTP-Requests an Raspberry Pi) | ✅ Nativ via OkHttp/Ktor | ✅ Via http-Package | ✅ Via fetch/axios |
| **Null Safety** | ✅ Eingebaut | ✅ Eingebaut | ⚠️ Nur mit TypeScript |
| **Coroutines** (asynchrone Steuerung) | ✅ Nativ | ✅ async/await | ⚠️ Komplexer |
| **Kein Lock-In durch Drittanbieter** | ✅ Direkt auf Android-SDK | ⚠️ Flutter-Framework | ⚠️ Meta/Microsoft |

**Fazit:** Da die App direkten Hardwarezugriff (Zugsteuerung) benötigt und ausschließlich auf Android läuft, ist eine native Kotlin-App die einfachste und zuverlässigste Wahl — ohne zusätzliche Abstraktionsschichten oder Framework-Abhängigkeiten.

---

## F1 — Digitaler Zwilling der Strecke

<small><span style="color:#1A8AFF">Themen: **Marwin** – Mobile First & Responsive Gestaltung · **Marwin** – Architekturprinzipien (MVVM, SoC) · **Marco** – Architekturstile (C4, Observer-Pattern) · **Ben** – Diffusion/Lock-In (Plattformwahl für Visualisierung)</span></small>

Visualisierung der Modellbahnanlage als digitalen Zwilling. Die Strecke ist fest vorgegeben.

- Streckenplan grafisch darstellen (evtl. vorhandenes Projekt einbinden)
- **Vordefinierte Standardstrecke** als feste Konfiguration
- Aktuelle Zugpositionen anzeigen (optimistisch: App spiegelt gesendete Befehle, keine Sensor-Rückmeldung)
- Zugnummern / -bezeichnungen sichtbar machen

---

## F2 — Ist- und Soll-Zustand definieren

<small><span style="color:#1A8AFF">Themen: **Ben** – Epics, User Stories & Szenarien (zentrale Nutzerinteraktion) · **Samira** – SRS (funktionale Anforderungen) · **Luca** – Qualität von Anforderungen (INVEST, Akzeptanzkriterien)</span></small>

Konfiguration des Ausgangszustands und des Zielzustands der Zugpositionen.

- **Ist-Zustand:** aktuelle Positionen manuell per Drag & Drop setzen
- **Soll-Zustand:** Zielpositionen per Drag & Drop festlegen oder zufällig generieren lassen
- Beide Zustände lokal speichern und laden können (z. B. als JSON-Export/-Import)

---

## F3 — Algorithmische Lösung (automatische Steuerung)

<small><span style="color:#1A8AFF">Themen: **Marco** – Architekturstile (Command-Pattern für Zugbefehle, Repository) · **Marco** – Quality Scenarios (Reaktionszeit, Fehlertoleranz) · **Karl** – Technische Schulden / Voice of Developer (Algorithmus-Qualität, Wartbarkeit) · **Samira** – SRS (funktionale Kernanforderung)</span></small>

Das System berechnet selbstständig, wie die Züge vom Ist- in den Soll-Zustand überführt werden.

- Lösungsalgorithmus implementieren (analog zum Türme-von-Hanoi-Prinzip)
- Schritt-für-Schritt-Plan der Zugbewegungen generieren
- Lösung im Digitalen Zwilling animiert abspielen
- Optionale Parameter: Geschwindigkeit, Schrittmodus (manuell / automatisch)

---

## F4 — Steuerungsoptionen & Statusanzeige

<small><span style="color:#1A8AFF">Themen: **Marwin** – Mobile First (Touch-Targets, Gesten, Material Design 3) · **Marco** – Quality Scenarios (Reaktionszeit < 150 ms) · **Ben** – Epics/User Stories (Steuerungs-Epic) · **Luca** – Scrum (Definition of Done, Akzeptanzkriterien)</span></small>

Bedienelemente und Live-Informationen zur laufenden Lösung.

- **Start / Stop / Pause** der automatischen Abarbeitung
- **Schrittweise Ausführung** (ein Zug pro Klick vorwärts/rückwärts)
- **Geschwindigkeitsregler** für die Animationsgeschwindigkeit
- **Rangierzähler:** Anzeige wie viele Rangierungen insgesamt benötigt werden
- **Fortschrittsanzeige:** bereits ausgeführte vs. verbleibende Schritte (z. B. Schritt 4 / 11)
- **Optimierungshinweis:** Vergleich der berechneten Lösung mit der theoretischen Mindestanzahl an Rangierungen

---

## F5 — Anbindung an echte Zugsteuerung

<small><span style="color:#1A8AFF">Themen: **Marco** – Architekturstile (Facade & Proxy für Hardware-Abstraktion, Singleton für Verbindungsinstanz) · **Marwin** – Architekturprinzipien (Information Hiding, Hardware-Schicht) · **Karl** – Voice of Developer (Entwickleranforderungen an Hardware-Schnittstelle) · **Ben** – Diffusion/Lock-In (Abhängigkeit von proprietärer Hardware)</span></small>

Übertragung der berechneten Lösung auf die physische Modellbahnanlage.

- Schnittstelle zur realen Steuerungshardware: **HTTP-Requests an Raspberry Pi(s)**
- Berechnete Fahrbefehle automatisch an echte Züge senden
- Synchronisation zwischen digitalem Zwilling und physischer Anlage
- Fehlerbehandlung bei Abweichungen (z. B. Zug nicht an erwarteter Position)

---

## Ausblick (optional — nur wenn Kernfeatures stabil)

### A1 — Freier Streckeneditor

<small><span style="color:#1A8AFF">Themen: **Marwin** – Mobile First (Drag & Drop, Touch-Gesten) · **Ben** – Epics/User Stories (optionales Epic) · **Samira** – Projektplanung & Umgang mit Unsicherheit (Feature unter Vorbehalt)</span></small>

Eigene Strecken aus vordefinierten Einzelteilen per Drag & Drop zusammenbauen.

- Bibliothek an Streckenbauteilen (Gerade, Kurve, Weiche, Prellbock etc.)
- Teile per Drag & Drop auf einer Arbeitsfläche platzieren und verbinden
- Validierung ob die zusammengestellte Strecke gültig/geschlossen ist
- Eigene Strecke speichern und als Alternative zur Standardstrecke laden
