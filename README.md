# Adobe-India-Hackathon25
# Challenge 1A – PDF Structure Extraction

This is my solution for Challenge 1A of the Adobe Hackathon.  
The goal was to extract the structural outline (like headings and subheadings) from a given PDF file and convert it into a clean, hierarchical JSON format.

---

##  What I Did

I used **PyMuPDF** to read the PDF and analyze the font size and weight of each text block to identify headings.

- Larger fonts and bold styles are treated as higher-level headings (like H1, H2, etc.)
- The script processes each page and captures all meaningful structure
- Output is saved in a simple JSON format with the page number, heading level, and text

---

## 📁 Input Format

All input PDFs are placed in the `/input` directory.

---

## 🧾 Output Format

The output for each PDF is saved in `/output/filename.json` with this structure:

```json
{
  "title": "E0H1CM114",
  "outline": [
    {
      "level": "H1",
      "text": "Executive Summary",
      "page": 2
    },
    {
      "level": "H2",
      "text": "Goals and Objectives",
      "page": 3
    }
  ]
}


How to Run It (Docker)
 docker build --platform linux/amd64 -t heading_extractor:1a .
docker run --rm -v ${PWD}/Datasets/input:/app/input -v ${PWD}/Datasets/output:/app/output --network none heading_extractor:1a


Challenge - 1(a)/
├── Datasets/
│   ├── input/
│   └── output/
├── process_pdfs.py
├── Dockerfile
├── requirements.txt
├── README.md






---
