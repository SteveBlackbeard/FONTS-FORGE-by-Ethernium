# 🛠️ FONTS FORGE di Ethernium

![Foglio Campione Ethernium](../ethernium_sheet_hq.png)

Un toolkit professionale e all'avanguardia per **progettare, compilare e visualizzare font vettoriali personalizzati** a partire da semplici fogli campione rasterizzati, disegnati a mano o basati su griglia (PNG).

Costruito con precisione da analisi forense ed estetica cyberpunk.

---

## ✨ Caratteristiche

- **Pipeline Generico da Raster a Vettoriale**: Suddivide automaticamente i campioni basati su griglia in bounding box di caratteri perfetti, estrae i contorni dei glifi e li converte in formati vettoriali.
- **Snapping Geometrico e Levigatura**: Snapping angolare configurabile (45° / 90°) e filtri morfologici dei bordi per rimuovere le scalettature mantenendo i dettagli nitidi.
- **Fitting delle Curve di Bézier**: Classificazione automatica di Bézier quadratica/cubica mediante analisi dell'angolo di deflessione per curve di livello professionale.
- **Motore di Simmetria a Doppio Livello**: Rispecchia i contorni da sinistra a destra per una simmetria matematicamente perfetta sia a livello vettoriale che pixel.
- **Watermarking Forense**: Incorporamento steganografico delle coordinate basato su LSB per la prova di paternità.
- **Tabelle OpenType Professionali**: Metriche verticali OS/2 robuste, hinting per il rendering a schermo `gasp`, record di copyright e mappe di crenatura legacy.
- **Output Multi-Formato**: Genera `.ttf`, `.woff` e `.woff2` in una singola compilazione.

---

## 🌐 Strumenti Web Interattivi

| Strumento | Descrizione |
|------|-------------|
| `preview_font.html` | Griglia completa dei caratteri con copia negli appunti, campione a cascata (12px–72px) e codice di incorporamento CSS |
| `ascii_generator.html` | Generatore di arte ASCII in tempo reale basato su Canvas con molteplici modalità di rendering |
| `presentation_generator.html` | Renderer premium di schede di presentazione per poster dimostrativi |
| `unicode_converter.html` | Mappa e convertitore di simboli runici e speciali Unicode |

---

## 🚀 Crea il Tuo Font Personalizzato in 4 Passaggi

### Passaggio 1: Disegna il Tuo Foglio Campione
Disegna o costruisci i glifi del tuo font in una singola immagine PNG. Organizza i caratteri da sinistra a destra per righe.

### Passaggio 2: Configura il Tuo Progetto
Copia `configs/template.json` in `configs/my_font.json` e definisci:
- `"sheet"`: Il nome del tuo file PNG
- `"font"`: Copyright, nome della famiglia, nome dello stile
- `"rows"`: Coordinate Y e lista ordinata dei caratteri per riga

> 💡 **Auto-calibrazione**: Esegui `python tools/calibrate_sheet.py my_sheet.png` per rilevare automaticamente i limiti Y.

### Passaggio 3: Compila
```bash
pip install -r requirements.txt
python -m font_forge configs/my_font.json
```

### Passaggio 4: Anteprima e Distribuzione
Apri `preview_font.html` nel tuo browser per ispezionare la griglia dei glifi, testare le dimensioni e ottenere il codice di incorporamento.

---

## 🔬 Strumenti per Sviluppatori

| Script | Scopo |
|--------|--------|
| `tools/calibrate_sheet.py` | Scansione automatizzata dei limiti Y e suggerimenti per le bande |
| `tools/debug_rows.py` | Sovrapposizione di verifica visiva delle sezioni di coordinate |
| `tools/audit_font.py` | Verifica dell'integrità dei limiti verticali compilati e degli intervalli di glifi |
| `tools/validate_font.py` | Auditor delle specifiche OpenType (report superato/avviso/errore) |
| `tools/font_to_ascii.py` | Converte il testo in banner ASCII ad alta risoluzione per il terminale |
| `tools/export_atlas.py` | Genera un atlante visivo dei glifi dal TTF compilato |

---

## 📦 Requisiti

```bash
pip install -r requirements.txt
```

Richiede **Python 3.8+** con `opencv-python`, `numpy`, `fonttools` e `Pillow`.

---

## 📄 Licenza

Questo toolkit è open source e disponibile sotto la [Licenza MIT](../LICENSE.txt).

---

<p align="center">
  <b>FONTS FORGE</b> — Forgiato da <a href="https://github.com/SteveBlackbeard">Ethernium</a>
</p>
