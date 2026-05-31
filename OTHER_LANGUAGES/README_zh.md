# 🛠️ FONTS FORGE by Ethernium

![Ethernium 样本表](../ethernium_sheet_hq.png)

一款专业且先进的工具包，用于从简单的手绘或基于网格的光栅样本表（PNG）**设计、编译和可视化自定义矢量字体**。

以法证级精度和赛博朋克美学打造。

---

## ✨ 功能特点

- **通用光栅转矢量流水线**：自动将基于网格的样本拆分为精确的字符边界框，提取字形轮廓，并将其转换为矢量格式。
- **几何对齐与平滑**：可配置的角度对齐（45° / 90°）和形态学边缘滤波器，在保持清晰细节的同时消除锯齿。
- **贝塞尔曲线拟合**：使用偏转角分析进行自动二次/三次贝塞尔分类，实现专业级曲线。
- **双层对称引擎**：在矢量和像素两个层面进行左右镜像轮廓，实现数学上完美的对称性。
- **法证水印**：基于LSB的隐写坐标嵌入，用于著作权证明。
- **专业OpenType表**：稳健的OS/2垂直度量、`gasp`屏幕渲染提示、版权记录和传统字距映射。
- **多格式输出**：在单次构建中生成`.ttf`、`.woff`和`.woff2`。

---

## 🌐 交互式Web工具

| 工具 | 描述 |
|------|-------------|
| `preview_font.html` | 完整的字符网格，支持复制到剪贴板、瀑布式样本（12px–72px）和CSS嵌入代码 |
| `ascii_generator.html` | 基于Canvas的实时ASCII艺术生成器，支持多种渲染模式 |
| `presentation_generator.html` | 用于展示海报的高级演示卡渲染器 |
| `unicode_converter.html` | 如尼文字及特殊符号Unicode映射和转换器 |

---

## 🚀 4步创建你的自定义字体

### 第1步：绘制样本表
在单张PNG图像中绘制或构建你的字体字形。将字符从左到右按行排列。

### 第2步：配置你的项目
将`configs/template.json`复制为`configs/my_font.json`并定义：
- `"sheet"`：你的PNG文件名
- `"font"`：版权信息、字体族名、样式名
- `"rows"`：Y坐标和每行的有序字符列表

> 💡 **自动校准**：运行`python tools/calibrate_sheet.py my_sheet.png`可自动检测Y边界。

### 第3步：编译
```bash
pip install -r requirements.txt
python -m font_forge configs/my_font.json
```

### 第4步：预览与部署
在浏览器中打开`preview_font.html`，检查字形网格、测试字号并获取嵌入代码。

---

## 🔬 开发者工具

| 脚本 | 用途 |
|--------|--------|
| `tools/calibrate_sheet.py` | 自动Y边界扫描和条带建议 |
| `tools/debug_rows.py` | 坐标切片的可视化验证叠加 |
| `tools/audit_font.py` | 编译后垂直边界和字形范围的完整性验证 |
| `tools/validate_font.py` | OpenType规范审计（通过/警告/失败报告） |
| `tools/font_to_ascii.py` | 将文本转换为高分辨率终端ASCII横幅 |
| `tools/export_atlas.py` | 从编译后的TTF生成可视化字形图集 |

---

## 📦 环境要求

```bash
pip install -r requirements.txt
```

需要**Python 3.8+**以及`opencv-python`、`numpy`、`fonttools`和`Pillow`。

---

## 📄 许可证

本工具包为开源项目，基于[MIT许可证](../LICENSE.txt)发布。

---

<p align="center">
  <b>FONTS FORGE</b> — 由 <a href="https://github.com/SteveBlackbeard">Ethernium</a> 锻造
</p>
