# 🛠️ FONTS FORGE par Ethernium

![Planche Spécimen Ethernium](../ethernium_sheet_hq.png)

Une boîte à outils professionnelle et à la pointe de la technologie pour **concevoir, compiler et visualiser des polices vectorielles personnalisées** à partir de planches spécimen tramées simples, dessinées à la main ou basées sur une grille (PNG).

Conçu avec une précision de niveau médico-légal et une esthétique cyberpunk.

---

## ✨ Fonctionnalités

- **Pipeline Générique Raster vers Vecteur** : Découpe automatiquement les spécimens basés sur une grille en boîtes englobantes de caractères parfaites, extrait les contours des glyphes et les convertit en formats vectoriels.
- **Accrochage Géométrique et Lissage** : Accrochage angulaire configurable (45° / 90°) et filtres morphologiques de bords pour supprimer les crénelages tout en conservant les détails nets.
- **Ajustement de Courbes de Bézier** : Classification automatique quadratique/cubique de Bézier par analyse d'angle de déflexion pour des courbes de qualité professionnelle.
- **Moteur de Symétrie Double Couche** : Miroir des contours de gauche à droite pour une symétrie mathématiquement parfaite aux niveaux vectoriel et pixel.
- **Tatouage Numérique Médico-légal** : Intégration stéganographique de coordonnées basée sur les LSB pour preuve de paternité.
- **Tables OpenType Professionnelles** : Métriques verticales OS/2 robustes, indications de rendu écran `gasp`, enregistrements de droits d'auteur et cartes de crénage héritées.
- **Sortie Multi-Format** : Génère `.ttf`, `.woff` et `.woff2` en une seule compilation.

---

## 🌐 Outils Web Interactifs

| Outil | Description |
|------|-------------|
| `preview_font.html` | Grille de caractères complète avec copie dans le presse-papiers, spécimen en cascade (12px–72px) et code d'intégration CSS |
| `ascii_generator.html` | Générateur d'art ASCII en temps réel basé sur Canvas avec plusieurs modes de rendu |
| `presentation_generator.html` | Moteur de rendu premium de cartes de présentation pour affiches de démonstration |
| `unicode_converter.html` | Carte et convertisseur de symboles runiques et spéciaux Unicode |

---

## 🚀 Créez Votre Police Personnalisée en 4 Étapes

### Étape 1 : Dessinez Votre Planche Spécimen
Dessinez ou construisez les glyphes de votre police dans une seule image PNG. Organisez les caractères de gauche à droite en lignes.

### Étape 2 : Configurez Votre Projet
Copiez `configs/template.json` vers `configs/my_font.json` et définissez :
- `"sheet"` : Le nom de votre fichier PNG
- `"font"` : Droits d'auteur, nom de famille, nom de style
- `"rows"` : Coordonnées Y et liste ordonnée de caractères par ligne

> 💡 **Auto-calibration** : Exécutez `python tools/calibrate_sheet.py my_sheet.png` pour détecter automatiquement les limites Y.

### Étape 3 : Compilez
```bash
pip install -r requirements.txt
python -m font_forge configs/my_font.json
```

### Étape 4 : Prévisualisez et Déployez
Ouvrez `preview_font.html` dans votre navigateur pour inspecter la grille de glyphes, tester les tailles et récupérer le code d'intégration.

---

## 🔬 Outils pour Développeurs

| Script | Fonction |
|--------|--------|
| `tools/calibrate_sheet.py` | Scan automatisé des limites Y et suggestions de bandes |
| `tools/debug_rows.py` | Superposition de vérification visuelle des tranches de coordonnées |
| `tools/audit_font.py` | Vérification d'intégrité des limites verticales compilées et des plages de glyphes |
| `tools/validate_font.py` | Auditeur de spécifications OpenType (rapports réussi/avertissement/échec) |
| `tools/font_to_ascii.py` | Convertit du texte en bannières ASCII haute résolution pour le terminal |
| `tools/export_atlas.py` | Génère un atlas visuel de glyphes à partir du TTF compilé |

---

## 📦 Prérequis

```bash
pip install -r requirements.txt
```

Nécessite **Python 3.8+** avec `opencv-python`, `numpy`, `fonttools` et `Pillow`.

---

## 📄 Licence

Cette boîte à outils est open source et disponible sous la [Licence MIT](../LICENSE.txt).

---

<p align="center">
  <b>FONTS FORGE</b> — Forgé par <a href="https://github.com/SteveBlackbeard">Ethernium</a>
</p>
