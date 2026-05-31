# 🛠️ FONTS FORGE por Ethernium

![Folha de Amostras Ethernium](../ethernium_sheet_hq.png)

Um toolkit profissional e de última geração para **projetar, compilar e visualizar fontes vetoriais personalizadas** a partir de folhas de amostras rasterizadas simples, desenhadas à mão ou baseadas em grade (PNG).

Construído com precisão de nível forense e estética cyberpunk.

---

## ✨ Funcionalidades

- **Pipeline Genérico de Raster para Vetor**: Divide automaticamente amostras baseadas em grade em caixas delimitadoras de caracteres perfeitas, extrai contornos de glifos e os converte para formatos vetoriais.
- **Encaixe Geométrico e Suavização**: Encaixe angular configurável (45° / 90°) e filtros morfológicos de bordas para remover serrilhado mantendo detalhes nítidos.
- **Ajuste de Curvas de Bézier**: Classificação automática de Bézier quadrática/cúbica usando análise de ângulo de deflexão para curvas de nível profissional.
- **Motor de Simetria de Dupla Camada**: Espelha contornos da esquerda para a direita para simetria matematicamente perfeita nos níveis vetorial e de pixel.
- **Marca d'Água Forense**: Incorporação esteganográfica de coordenadas baseada em LSB para comprovação de autoria.
- **Tabelas OpenType Profissionais**: Métricas verticais OS/2 robustas, hinting de renderização de tela `gasp`, registros de direitos autorais e mapas de kerning legados.
- **Saída Multiformato**: Gera `.ttf`, `.woff` e `.woff2` em uma única compilação.

---

## 🌐 Ferramentas Web Interativas

| Ferramenta | Descrição |
|------|-------------|
| `preview_font.html` | Grade completa de caracteres com cópia para a área de transferência, amostra em cascata (12px–72px) e código de incorporação CSS |
| `ascii_generator.html` | Gerador de arte ASCII em tempo real baseado em Canvas com múltiplos modos de renderização |
| `presentation_generator.html` | Renderizador premium de cartões de apresentação para pôsteres de demonstração |
| `unicode_converter.html` | Mapa e conversor de símbolos rúnicos e especiais Unicode |

---

## 🚀 Crie Sua Fonte Personalizada em 4 Passos

### Passo 1: Desenhe Sua Folha de Amostras
Desenhe ou construa os glifos da sua fonte em uma única imagem PNG. Organize os caracteres da esquerda para a direita em linhas.

### Passo 2: Configure Seu Projeto
Copie `configs/template.json` para `configs/my_font.json` e defina:
- `"sheet"`: O nome do seu arquivo PNG
- `"font"`: Direitos autorais, nome da família, nome do estilo
- `"rows"`: Coordenadas Y e lista ordenada de caracteres por linha

> 💡 **Autocalibração**: Execute `python tools/calibrate_sheet.py my_sheet.png` para detectar os limites Y automaticamente.

### Passo 3: Compile
```bash
pip install -r requirements.txt
python -m font_forge configs/my_font.json
```

### Passo 4: Visualize e Implante
Abra `preview_font.html` no seu navegador para inspecionar a grade de glifos, testar tamanhos e obter o código de incorporação.

---

## 🔬 Ferramentas para Desenvolvedores

| Script | Finalidade |
|--------|--------|
| `tools/calibrate_sheet.py` | Varredura automatizada de limites Y e sugestões de faixas |
| `tools/debug_rows.py` | Sobreposição de verificação visual das fatias de coordenadas |
| `tools/audit_font.py` | Verificação de integridade dos limites verticais compilados e intervalos de glifos |
| `tools/validate_font.py` | Auditor de especificações OpenType (relatórios aprovado/aviso/falha) |
| `tools/font_to_ascii.py` | Converte texto em banners ASCII de alta resolução para terminal |
| `tools/export_atlas.py` | Gera um atlas visual de glifos a partir do TTF compilado |

---

## 📦 Requisitos

```bash
pip install -r requirements.txt
```

Requer **Python 3.8+** com `opencv-python`, `numpy`, `fonttools` e `Pillow`.

---

## 📄 Licença

Este toolkit é de código aberto e está disponível sob a [Licença MIT](../LICENSE.txt).

---

<p align="center">
  <b>FONTS FORGE</b> — Forjado por <a href="https://github.com/SteveBlackbeard">Ethernium</a>
</p>
