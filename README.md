# Zongze Knob Study // Mousewheel Mechanic (Level 03)
### ESP32-S3 Rotary Encoder &rarr; Mousewheel Cadans // [DOC 06 Hardware-Abstraktie]

Interactieve hardware-abstractie en browser-simulatie van een ESP32-S3 rotary encoder gekoppeld aan een gesimuleerd OLED micro-display.

🌐 **Live Demo:** [https://maxdoesborgh.github.io/zongze-mousewheel/](https://maxdoesborgh.github.io/zongze-mousewheel/)

---

## ⚡ Direct Starten

Je hebt geen build-stap nodig. Je kunt het bestand direct openen:

1. **Direct in de browser openen:**
   Dubbelklik simpelweg op `index.html` of open het via Finder in Chrome, Safari of Firefox.

2. **Of via een lokale ontwikkelserver:**
   ```bash
   npx serve .
   # of met Vite:
   npm install
   npm run dev
   ```

---

## 🎮 Besturing & Fysica

- **Mes-cadans (Rotatie):** Scroll continu met je **muiswiel** (of swipe met 2 vingers op het trackpad). Dit bouwt de procedurale inertie en rotatiesnelheid op.
- **Snijdruk (Tool Pressure):** Houd de **Linkermuisknop**, **Middenmuisklik**, of **Spatiebalk** ingedrukt.
- **On-Screen Knoppen:** Onder het scherm zijn touch/muis knoppen beschikbaar om druk vast te houden of een impuls te geven.

---

## 🔬 Technische Eigenschappen

- **HiDPI / Retina Canvas Rendering:** Automatische `window.devicePixelRatio` schaling voor haarscherpe vectorlijnen en OLED-contrast.
- **Web Audio API Synthese:** Real-time procedurele percussieve audio-synthese (houtige impacttransiënt en mes-snede click) zonder externe audio-bestanden.
- **DOC 06 Fysische Cadans & Demping:**
  - Wrijvingscoëfficiënt: `wheelVelocity *= 0.91`
  - Kinematica: `wave = Math.sin(cutCycle)`
  - Snijtrigger: `toolPressure && wave > 0.94 && (cutCycle - lastSliceProgress > 2.5)`
  - Schijfjesfysica met zwaartekracht, stuiterimpuls en rotatie.

