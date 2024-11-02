# Document Parsing with Python and Google Colab
This project parses and extracts data from PDF documents using Python libraries like unstructured, Tesseract OCR, and additional dependencies for handling various document elements (text, tables, images, lists).

## Prerequisites
Python 3.10+
Google Colab or local Python environment
Tesseract OCR
Installation
## Run the following in Google Colab:

```bash
!pip install --quiet "unstructured[all-docs]" pillow pydantic lxml matplotlib
!sudo apt-get update
!sudo apt-get install poppler-utils libleptonica-dev tesseract-ocr libtesseract-dev python3-pil tesseract-ocr-eng tesseract-ocr-script-latn
!pip install unstructured-pytesseract
!pip install tesseract-ocr
```

### Usage
1. **Mount Google Drive:**
```bash
from google.colab import drive
drive.mount('/content/drive')
```

2. **Parse PDF:**
 ```bash
  from unstructured.partition.pdf import partition_pdf

raw_pdf_elements = partition_pdf(
    filename="/content/drive/MyDrive/Rag/attention.pdf",
    strategy="hi_res",
    extract_images_in_pdf=True,
    extract_image_block_types=["Image", "Table"],
    extract_image_block_output_dir="extracted_data"
)
```
