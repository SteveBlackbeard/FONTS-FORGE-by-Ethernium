# 🛠️ FONTS FORGE por Ethernium

![Hoja de Muestras de Ethernium](../ethernium_sheet_hq.png)

Un kit de herramientas profesional y de última generación para **diseñar, compilar y visualizar fuentes vectoriales personalizadas** a partir de hojas de muestras rasterizadas simples, dibujadas a mano o basadas en cuadrícula (PNG).

Construido con precisión de grado forense y estética cyberpunk.

---

## ✨ Características

- **Pipeline Genérico de Rasterizado a Vectorial**: Divide automáticamente las muestras basadas en cuadrícula en cuadros delimitadores de caracteres perfectos, extrae los contornos de los glifos y los convierte a formatos vectoriales.
- **Ajuste Geométrico y Suavizado**: Ajuste angular configurable (45° / 90°) y filtros morfológicos de bordes para eliminar irregularidades manteniendo los detalles nítidos.
- **Ajuste de Curvas Bézier**: Clasificación automática de Bézier cuadrática/cúbica mediante análisis de ángulo de deflexión para curvas de grado profesional.
- **Motor de Simetría de Doble Capa**: Refleja los contornos de izquierda a derecha para una simetría matemáticamente perfecta tanto a nivel vectorial como de píxeles.
- **Marca de Agua Forense**: Incrustación esteganográfica de coordenadas basada en LSB para prueba de autoría.
- **Tablas OpenType Profesionales**: Métricas verticales OS/2 robustas, indicaciones de renderizado en pantalla `gasp`, registros de derechos de autor y mapas de interletraje heredados.
- **Salida Multiformato**: Genera `.ttf`, `.woff` y `.woff2` en una sola compilación.

---

## 🌐 Herramientas Web Interactivas

| Herramienta | Descripción |
|------|-------------|
| `preview_font.html` | Cuadrícula de caracteres completa con copiar al portapapeles, muestra en cascada (12px–72px) y código de incrustación CSS |
| `ascii_generator.html` | Generador de arte ASCII en tiempo real basado en canvas con múltiples modos de renderizado |
| `presentation_generator.html` | Renderizador premium de tarjetas de presentación para pósters de exhibición |
| `unicode_converter.html` | Mapa y conversor de símbolos rúnicos y especiales Unicode |

---

## 🚀 Crea Tu Fuente Personalizada en 4 Pasos

### Paso 1: Dibuja Tu Hoja de Muestras
Dibuja o construye los glifos de tu fuente en una sola imagen PNG. Organiza los caracteres de izquierda a derecha en filas.

### Paso 2: Configura Tu Proyecto
Copia `configs/template.json` a `configs/my_font.json` y define:
- `"sheet"`: El nombre de tu archivo PNG
- `"font"`: Derechos de autor, nombre de familia, nombre de estilo
- `"rows"`: Coordenadas Y y lista ordenada de caracteres por fila

> 💡 **Autocalibración**: Ejecuta `python tools/calibrate_sheet.py my_sheet.png` para detectar los límites Y automáticamente.

### Paso 3: Compila
```bash
pip install -r requirements.txt
python -m font_forge configs/my_font.json
```

### Paso 4: Previsualiza y Despliega
Abre `preview_font.html` en tu navegador para inspeccionar la cuadrícula de glifos, probar tamaños y obtener el código de incrustación.

---

## 🔬 Herramientas para Desarrolladores

| Script | Propósito |
|--------|--------|
| `tools/calibrate_sheet.py` | Escaneo automatizado de límites Y y sugerencias de bandas |
| `tools/debug_rows.py` | Verificación visual superpuesta de segmentos de coordenadas |
| `tools/audit_font.py` | Verificación de integridad de los límites verticales compilados y rangos de glifos |
| `tools/validate_font.py` | Auditor de especificaciones OpenType (informes de aprobado/advertencia/error) |
| `tools/font_to_ascii.py` | Convierte texto en banners ASCII de alta resolución para terminal |
| `tools/export_atlas.py` | Genera un atlas visual de glifos a partir del TTF compilado |

---

## 📦 Requisitos

```bash
pip install -r requirements.txt
```

Requiere **Python 3.8+** con `opencv-python`, `numpy`, `fonttools` y `Pillow`.

---

## 📄 Licencia

Este kit de herramientas es de código abierto y está disponible bajo la [Licencia MIT](../LICENSE.txt).

---

<p align="center">
  <b>FONTS FORGE</b> — Forjado por <a href="https://github.com/SteveBlackbeard">Ethernium</a>
</p>
