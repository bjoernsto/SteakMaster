# 🔥 Steak Master

> Der perfekte Garprozess — interaktiver Steak-Timer mit Echtzeit-Kerntemperatur-Schätzung

![HTML](https://img.shields.io/badge/HTML-5-orange?style=flat-square&logo=html5)
![CSS](https://img.shields.io/badge/CSS-3-blue?style=flat-square&logo=css3)
![JavaScript](https://img.shields.io/badge/JavaScript-ES6+-yellow?style=flat-square&logo=javascript)
![License](https://img.shields.io/badge/Lizenz-MIT-green?style=flat-square)

---

## 📖 Über das Projekt

**Steak Master** ist eine Single-Page Web-App, die dich Schritt für Schritt durch den perfekten Grillprozess führt. Basierend auf Gargrad, Fleischdicke und Grilltemperatur werden die Grillphasen dynamisch berechnet — inklusive Echtzeit-Schätzung der Kerntemperatur.

**[➡ Live Demo ansehen](https://dein-username.github.io/steak-master/)**

---

## ✨ Features

| Feature | Beschreibung |
|---|---|
| 🥩 **Gargrad-Auswahl** | Rare bis Well Done mit Zieltemperaturangabe |
| 📏 **Fleischdicke** | 10–50 mm per Slider einstellbar |
| 🌡️ **Grilltemperatur** | 150–300 °C — beeinflusst Garzeiten direkt |
| ⏱️ **Phasen-Timer** | Visueller Countdown-Ring pro Grillphase |
| 🌡️ **Kerntemperatur-Schätzung** | Echtzeit-Schätzung während des Garens |
| 📊 **Gargrad-Balken** | Live-Anzeige von Roh → Well Done |
| 👁️ **Nächste Phase Vorschau** | Immer sichtbar zur Vorbereitung |
| 🚨 **Alarm-Overlay** | Visuelle & haptische Benachrichtigung |
| ⏸️ **Pause-Funktion** | Timer pausieren und fortsetzen |
| 📱 **Mobil-optimiert** | Responsive Design für alle Geräte |

---

## 🚀 Schnellstart

### Option 1 — Direkt öffnen

```bash
# Repository klonen
git clone https://github.com/dein-username/steak-master.git

# Datei im Browser öffnen
open steak-master/steak-timer.html
```

### Option 2 — GitHub Pages

1. Repository forken
2. In den Repo-Einstellungen **Pages** aktivieren
3. Branch `main`, Ordner `/ (root)` auswählen
4. App ist unter `https://dein-username.github.io/steak-master/` erreichbar

### Option 3 — Lokaler Dev-Server

```bash
# Mit Python
python3 -m http.server 8080

# Oder mit Node.js (npx)
npx serve .

# Dann im Browser öffnen
open http://localhost:8080/steak-timer.html
```

---

## 📐 Wie funktioniert die Kerntemperatur-Schätzung?

Die App schätzt die Kerntemperatur anhand eines physikalisch plausiblen Modells:

### Direkte Hitzephase
- Oberfläche erhitzt sich schnell, Kern langsamer
- Lineare Näherung: Kern steigt von Kühlschranktemperatur (~4 °C) auf ~40 °C

### Indirekte Garphase (ab >25 mm Dicke)
- **Sigmoid-Kurve:** `temp = start + 0.5 * (1 - cos(π * t)) * (ziel - start)`
- Startet langsam, beschleunigt in der Mitte, verlangsamt sich am Zielwert
- Heizrate abhängig von Dicke und Grilltemperatur

### Ruhephase
- Temperatur steigt noch ~2 °C nach (Carry-over cooking)
- Danach langsames Abfallen

### Gargrad-Referenz

| Gargrad | Kerntemperatur |
|---|---|
| Blue Rare | 40–48 °C |
| Rare | 48–52 °C |
| Medium Rare | 52–55 °C |
| Medium | 55–60 °C |
| Medium Well | 60–65 °C |
| Well Done | 65 °C+ |

---

## 🧱 Projektstruktur

```
steak-master/
│
├── steak-timer.html     # Gesamte App (Single File)
├── README.md            # Diese Datei
├── LICENSE              # MIT Lizenz
└── .gitignore           # Git Ausschlüsse
```

> Die App ist bewusst als **Single HTML File** gebaut — keine Dependencies, kein Build-Prozess, sofort einsatzbereit.

---

## 🔧 Anpassungen

### Garzeiten kalibrieren

In der Funktion `calcPhases()` können Basiszeiten angepasst werden:

```javascript
// Direkte Grillzeit pro Seite (Basis: 20mm, 230°C)
const searBase = 110 * tf * tempF; // Sekunden

// Heizrate beim indirekten Garen (°C/Sekunde)
const heatingRate = (7 - thickness * 0.04) * (grillTemp / 230) / 60;
```

### Neuen Gargrad hinzufügen

Im `DONENESS`-Array am Anfang des Scripts:

```javascript
const DONENESS = [
  { id: 'blue-rare', label: 'Blue Rare', tempMin: 40, tempMax: 48, targetTemp: 44, color: '#6d1a1a' },
  // ...
];
```

---

## 🤝 Contributing

Pull Requests sind willkommen! Für größere Änderungen bitte zuerst ein Issue öffnen.

1. Fork erstellen
2. Feature-Branch anlegen: `git checkout -b feature/mein-feature`
3. Änderungen committen: `git commit -m 'feat: mein Feature'`
4. Branch pushen: `git push origin feature/mein-feature`
5. Pull Request öffnen

---

## 📋 Roadmap

- [ ] Bluetooth-Thermometer Integration (Web Bluetooth API)
- [ ] Mehrere Steaks gleichzeitig tracken
- [ ] Rezepte & Marinaden-Tipps pro Gargrad
- [ ] PWA / Offline-Support
- [ ] Mehrsprachigkeit (EN/DE)

---

## 📄 Lizenz

Dieses Projekt steht unter der **MIT Lizenz** — siehe [LICENSE](LICENSE) für Details.

---

<div align="center">
  Gemacht mit 🔥 für perfekte Steaks
</div>
