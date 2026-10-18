基于HTML的纯前端PDF转换器，支持图片、文本、网页等多格式批量转换，本地处理不上传。
[🌐 English Version](#english)

# 📄 PDF 转换器（HTML 单文件版）

一个纯前端、零依赖后端的 PDF 转换工具。只需一个 HTML 文件，在浏览器中即可将多种常见格式批量转换为 PDF，所有处理均在本地完成，文件不会上传到任何服务器。

## ✨ 核心特性

- **批量上传**：支持一次选择或拖拽多个文件，统一管理与转换。
- **多格式支持**
  - 图片：PNG、JPG/JPEG、WEBP、GIF、BMP、AVIF、SVG、ICO
  - 文本：TXT、CSV、TSV、MD、JSON、XML、LOG、YAML、INI、源码文件（JS/TS/PY/JAVA/C/C++/GO/RS/PHP/RB/SH/SQL 等）
  - 网页：HTML、HTM、XHTML
- **两种输出方式**：合并为一个 PDF，或每个文件单独生成 PDF。
- **页面设置**：可选 A4 / Letter 页面尺寸，支持纵向与横向。
- **无损优先**：JPG 原字节直嵌，PNG 像素无损并保留透明通道；文本与网页以高 DPI 无损位图嵌入，无明显 JPEG 伪影。
- **体积可控**：提供“压缩”选项（限制最大边 2400px、JPEG 85%），在质量与体积间灵活取舍。
- **隐私安全**：全部转换在浏览器本地完成，不上传、不留存。
- **零安装**：无需构建、无需服务器，双击 HTML 即可使用。

## 🚀 使用方法

1. 下载并保存为 `pdf-converter.html`。
2. 用现代浏览器（Chrome / Edge / Firefox / Safari）打开。
3. 点击上传区选择文件，或将文件拖拽到页面中。
4. 按需设置输出方式、页面尺寸、方向与图片处理模式。
5. 点击“开始转换”，完成后自动下载 PDF。

> 提示：首次使用需联网加载 jsPDF 与 html2canvas 两个 CDN 库。

## ⚙️ 技术说明

- 基于 **jsPDF** 生成 PDF，**html2canvas** 渲染网页内容。
- 图片在无损模式下不经过 canvas 重编码，由 PDF 渲染器在显示时缩放。
- 文本与 HTML 以位图形式嵌入，因此文字**不可选中、不可搜索**；如需矢量文字，可扩展为嵌入 TTF 字体后调用 `pdf.text()` 输出。

## ⚠️ 已知边界

- 暂不支持 `.docx`、`.xlsx`、`.pptx` 等 Office 格式（需服务端解析）。
- GIF 仅取第一帧，动画会丢失。
- HTML 分页按像素切分，长内容可能出现跨页截断。
- 无损模式下高分辨率图片会显著增大 PDF 体积。

## 📄 许可

可自由用于个人与商业项目，请保留出处说明。

---

<a id="english"></a>
# 📄 PDF Converter (Single-File HTML)

A fully client-side PDF conversion tool with zero backend. Just one HTML file lets you batch-convert multiple common formats into PDF right in the browser. All processing happens locally — your files are never uploaded to any server.

## ✨ Key Features

- **Batch upload**: Select or drag in multiple files at once, managed and converted together.
- **Multi-format support**
  - Images: PNG, JPG/JPEG, WEBP, GIF, BMP, AVIF, SVG, ICO
  - Text: TXT, CSV, TSV, MD, JSON, XML, LOG, YAML, INI, and source files (JS/TS/PY/JAVA/C/C++/GO/RS/PHP/RB/SH/SQL, etc.)
  - Web pages: HTML, HTM, XHTML
- **Two output modes**: Merge everything into one PDF, or generate a separate PDF per file.
- **Page settings**: A4 or Letter size, with portrait or landscape orientation.
- **Lossless-first**: JPG is embedded as raw bytes with no re-encoding; PNG is embedded losslessly with alpha preserved. Text and web pages are embedded as high-DPI lossless bitmaps with no visible JPEG artifacts.
- **Size control**: A "compress" option (max side 2400px, JPEG 85%) lets you trade quality for file size.
- **Privacy by design**: Everything runs locally in the browser — no uploads, no storage.
- **Zero install**: No build step, no server. Just open the HTML file.

## 🚀 How to Use

1. Download and save as `pdf-converter.html`.
2. Open it in a modern browser (Chrome / Edge / Firefox / Safari).
3. Click the upload area to pick files, or drag and drop them onto the page.
4. Adjust the output mode, page size, orientation, and image handling as needed.
5. Click "Start Conversion" and the PDF will download automatically when finished.

> Note: An internet connection is required on first use to load the jsPDF and html2canvas libraries from CDN.

## ⚙️ Technical Notes

- PDFs are generated with **jsPDF**; web content is rendered with **html2canvas**.
- In lossless mode, images are not re-encoded through canvas — the PDF renderer scales them at display time.
- Text and HTML are embedded as bitmaps, so text is **not selectable or searchable**. For vector text, the tool can be extended to embed a TTF font and output via `pdf.text()`.

## ⚠️ Known Limitations

- Office formats such as `.docx`, `.xlsx`, and `.pptx` are not supported (they require server-side parsing).
- GIF only captures the first frame; animation is lost.
- HTML pagination is pixel-based, so long content may be cut across pages.
- In lossless mode, high-resolution images can significantly increase PDF size.

## 📄 License

Free to use for personal and commercial projects; please retain attribution.
