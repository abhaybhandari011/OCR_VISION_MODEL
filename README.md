## 🧠 OCR + Groq Vision PDF Extractor

This repository contains a **Google Colab–ready notebook** that extracts **text and tables** from **scanned PDF documents** using two approaches:

1. **Tesseract OCR (Baseline)** – converts scanned images to text
2. **Groq Vision LLaMA 4 Model** – performs multimodal document understanding using
   `meta-llama/llama-4-scout-17b-16e-instruct` via Groq’s API

It automatically generates structured, Markdown-like text and recreates the content into a new, searchable PDF file.

---

### 🚀 Features

* 📄 PDF → image conversion using `pdf2image`
* 🔍 OCR extraction using **Tesseract**
* 🧩 Advanced extraction and layout reconstruction via **Groq Vision model**
* 🗂️ Recreates the extracted content (text + tables) into clean **searchable PDFs**
* 💾 Saves both outputs:

  * `pdf_ocr.pdf` — Tesseract-only OCR
  * `pdf_groq.pdf` — Groq Vision-processed structured PDF

---

### 🧰 Tech Stack

| Category          | Tool / Library                                       |
| ----------------- | ---------------------------------------------------- |
| OCR               | `pytesseract`, `pdf2image`                           |
| AI Model          | `Groq` (`meta-llama/llama-4-scout-17b-16e-instruct`) |
| PDF Generation    | `fpdf`                                               |
| Vision Processing | `Pillow (PIL)`                                       |
| Environment       | Google Colab / Python 3.10+                          |

---

### ⚙️ Setup Instructions

#### **Option 1: Run on Google Colab (Recommended)**

1. Upload your **scanned PDF** (e.g., `input_scanned.pdf`)
2. Open the notebook in Colab and run all cells
3. Enter your **Groq API key** when prompted
4. Download your results from the `outputs/` folder

#### **Option 2: Run Locally**

```bash
git clone https://github.com/<your-username>/<repo-name>.git
cd <repo-name>
pip install -r requirements.txt
python ocr_groq_pipeline.py
```

---

### 🔑 Environment Variables

| Variable       | Description                                                                        |
| -------------- | ---------------------------------------------------------------------------------- |
| `GROQ_API_KEY` | Your Groq developer API key (obtain from [Groq Console](https://console.groq.com)) |

You can set it inline in Colab:

```python
os.environ["GROQ_API_KEY"] = "your_api_key_here"
```

---

### 🧩 Output Files

| File                    | Description                                       |
| ----------------------- | ------------------------------------------------- |
| `pdf_ocr.pdf`           | Simple OCR output using Tesseract                 |
| `pdf_groq.pdf`          | Structured output using Groq Vision model         |
| `/outputs/groq_images/` | Temporary folder containing converted page images |

---

### 📘 Example Workflow

```python
# Step 1: Convert PDF → Images
# Step 2: Run OCR (Tesseract) → pdf_ocr.pdf
# Step 3: Run Groq Vision Extraction → pdf_groq.pdf
```

Each page is processed independently, and the results are combined into a final, human-readable structured PDF.

---

### 📄 Example Result

| Approach              | Output Description                                                   |
| --------------------- | -------------------------------------------------------------------- |
| **Tesseract OCR**     | Plain text output with minimal layout reconstruction                 |
| **Groq Vision Model** | Well-structured Markdown output with headers, paragraphs, and tables |

---

### ⚡ Requirements

* Python 3.9+
* Groq SDK (`pip install groq`)
* Tesseract installed (`apt install tesseract-ocr`)
* Colab runtime (or local environment)

---

### 🧠 Future Improvements

* Render Markdown tables & headings with formatting in the PDF
* Add multilingual OCR support
* Integrate layout-detection models (e.g., `LayoutLMv3` or `DocTR`) for finer reconstruction

---

### 🧑‍💻 Author

**Abhay Bhandari**
🚀 Backend Developer | Data Science & AI Enthusiast

Would you like me to also include a **`requirements.txt`** file with exact dependencies (for Colab + local setup)?
