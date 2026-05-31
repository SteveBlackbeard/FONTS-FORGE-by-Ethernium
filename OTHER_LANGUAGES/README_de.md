# 🛠️ FONTS FORGE von Ethernium

![Ethernium Schriftmusterblatt](../ethernium_sheet_hq.png)

Ein professionelles, hochmodernes Toolkit zum **Entwerfen, Kompilieren und Visualisieren benutzerdefinierter Vektorschriften** ausgehend von einfachen handgezeichneten oder rasterbasierten Musterblättern (PNG).

Entwickelt mit forensischer Präzision und Cyberpunk-Ästhetik.

---

## ✨ Funktionen

- **Generische Raster-zu-Vektor-Pipeline**: Teilt rasterbasierte Muster automatisch in perfekte Zeichen-Begrenzungsrahmen auf, extrahiert Glyphenkonturen und konvertiert sie in Vektorformate.
- **Geometrisches Einrasten und Glätten**: Konfigurierbares Winkeleinrasten (45° / 90°) und morphologische Kantenfilter zur Beseitigung von Treppenstufen bei gleichzeitiger Beibehaltung scharfer Details.
- **Bézier-Kurvenanpassung**: Automatische quadratische/kubische Bézier-Klassifikation mittels Ablenkungswinkelanalyse für Kurven in professioneller Qualität.
- **Dual-Layer-Symmetrie-Engine**: Spiegelt Konturen von links nach rechts für mathematisch perfekte Symmetrie auf Vektor- und Pixelebene.
- **Forensisches Wasserzeichen**: LSB-basierte steganografische Koordinateneinbettung zum Nachweis der Urheberschaft.
- **Professionelle OpenType-Tabellen**: Robuste vertikale OS/2-Metriken, `gasp`-Bildschirmrendering-Hinting, Urheberrechtseinträge und Legacy-Kerning-Karten.
- **Mehrformat-Ausgabe**: Erzeugt `.ttf`, `.woff` und `.woff2` in einem einzigen Build.

---

## 🌐 Interaktive Web-Tools

| Tool | Beschreibung |
|------|-------------|
| `preview_font.html` | Vollständiges Zeichenraster mit Kopieren in die Zwischenablage, Wasserfall-Muster (12px–72px) und CSS-Einbettungscode |
| `ascii_generator.html` | Echtzeit-Canvas-basierter ASCII-Art-Generator mit mehreren Rendering-Modi |
| `presentation_generator.html` | Premium-Präsentationskarten-Renderer für Showcase-Poster |
| `unicode_converter.html` | Runen- und Sonderzeichen-Unicode-Karte und -Konverter |

---

## 🚀 Erstellen Sie Ihre eigene Schrift in 4 Schritten

### Schritt 1: Zeichnen Sie Ihr Musterblatt
Zeichnen oder konstruieren Sie Ihre Schriftglyphen in einem einzigen PNG-Bild. Ordnen Sie die Zeichen zeilenweise von links nach rechts an.

### Schritt 2: Konfigurieren Sie Ihr Projekt
Kopieren Sie `configs/template.json` nach `configs/my_font.json` und definieren Sie:
- `"sheet"`: Ihr PNG-Dateiname
- `"font"`: Urheberrecht, Familienname, Stilname
- `"rows"`: Y-Koordinaten und geordnete Zeichenliste pro Zeile

> 💡 **Automatische Kalibrierung**: Führen Sie `python tools/calibrate_sheet.py my_sheet.png` aus, um die Y-Grenzen automatisch zu erkennen.

### Schritt 3: Kompilieren
```bash
pip install -r requirements.txt
python -m font_forge configs/my_font.json
```

### Schritt 4: Vorschau und Bereitstellung
Öffnen Sie `preview_font.html` in Ihrem Browser, um das Glyphenraster zu prüfen, Größen zu testen und den Einbettungscode abzurufen.

---

## 🔬 Entwickler-Tools

| Skript | Zweck |
|--------|--------|
| `tools/calibrate_sheet.py` | Automatisierte Y-Grenzen-Erkennung und Bandvorschläge |
| `tools/debug_rows.py` | Visuelle Überprüfungsüberlagerung der Koordinatenschnitte |
| `tools/audit_font.py` | Integritätsüberprüfung der kompilierten vertikalen Grenzen und Glyphenbereiche |
| `tools/validate_font.py` | OpenType-Spezifikations-Auditor (Bestanden/Warnung/Fehler-Berichte) |
| `tools/font_to_ascii.py` | Konvertiert Text in hochauflösende Terminal-ASCII-Banner |
| `tools/export_atlas.py` | Generiert einen visuellen Glyphenatlas aus der kompilierten TTF |

---

## 📦 Voraussetzungen

```bash
pip install -r requirements.txt
```

Erfordert **Python 3.8+** mit `opencv-python`, `numpy`, `fonttools` und `Pillow`.

---

## 📄 Lizenz

Dieses Toolkit ist Open Source und unter der [MIT-Lizenz](../LICENSE.txt) verfügbar.

---

<p align="center">
  <b>FONTS FORGE</b> — Geschmiedet von <a href="https://github.com/SteveBlackbeard">Ethernium</a>
</p>
