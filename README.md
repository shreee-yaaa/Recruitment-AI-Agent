*# 🤖 Recruitment AI Agent*

An AI-powered recruitment assistant that helps HR professionals evaluate resumes against job descriptions and generate personalized interview/rejection emails.

---

## 🚀 Features
- Upload or generate **Job Descriptions (JD)**
- Upload up to **10 resumes** (PDF/DOCX)
- Automatic **resume scoring** (0–100)
- Detect **missing skills & remarks**
- Highlight **best-matched candidate**
- Generate **personalized emails**:
  - Interview call email (for best candidate)
  - Rejection email (for others)

---

## 🛠️ Tech Stack
- **Backend:** FastAPI (Python)
- **Frontend:** Streamlit Dashboard
- **AI Models:**
  - `all-MiniLM-L6-v2` (SentenceTransformers) for JD ↔ Resume semantic matching
  - GPT (or HuggingFace LLM) for generating professional emails
- **Utilities:** pdfplumber / docx for text extraction

---

## 📂 Project Structure
recruitment-agent/
├─ backend/
│ ├─ main.py # FastAPI entrypoint
│ ├─ utils.py # Helpers (text extraction, preprocessing)
│ ├─ matching.py # Resume ↔ JD matching logic
│ ├─ jd_generator.py # AI-powered JD generation
│ ├─ email_generator.py # AI-powered email generation
│ └─ requirements.txt # Backend dependencies
├─ frontend/
│ ├─ streamlit_app.py # Streamlit dashboard
│ └─ requirements.txt # Frontend dependencies
├─ examples/
│ ├─ jd_sample.txt
│ ├─ resume1.pdf
│ └─ resume2.pdf
└─ README.md

---

## ⚙️ Setup Instructions

###  **Clone the repository** (or download ZIP):

```bash
git clone https://github.com/your-username/Recruitment-AI-Agent.git
cd Recruitment-AI-Agent

**Create a virtual environment**
```bash
python -m venv .venv

**Activate the virtual environment**
```bash
.venv\Scripts\activate

**Install dependencies:**
```bash
pip install -r requirements.txt

---

*##  How to Run the Project Locally*

### Backend (FastAPI)
```bash
cd backend
uvicorn main:app --reload

### Frontend (Streamlit)
```bash
cd frontend
streamlit run streamlit_app.py

---
🧠 Description of the AI Logic
The Recruitment AI Agent uses a combination of NLP techniques to match resumes with job descriptions:

- **Text Extraction**: Converts PDFs and DOCX resumes into plain text.
- **Embedding Generation**: Uses sentence-transformers to convert JD and resume text into numerical embeddings.
- **Similarity Matching**: Computes cosine similarity between the job description and each resume to rank candidates.
- **Scoring & Ranking**: Provides a relevance score for each candidate and ranks them accordingly.

---

📊 Explanation of Model Choices

- **Sentence-Transformers**: Chosen for efficient and accurate semantic text embeddings.  
- **FastAPI**: Provides a lightweight, fast, and modern backend API for serving requests.  
- **Streamlit**: Used for creating a user-friendly interface without extensive frontend coding.  
- **Cosine Similarity**: Simple and effective metric for semantic text comparison.  
- **PyTorch**: Required for sentence-transformers models.

---
📄 Example JD and Resume Files
To test the system locally, you can use:

- `examples/example_jd.txt` – Example Job Description  
- `examples/resume_raj.txt` – Example Resume 1  
- `examples/resume_rita.txt` – Example Resume 2
