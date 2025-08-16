# 🤖 TDS Data Analyst Agent

A full-stack **FastAPI** application that works as a data analyst agent.  
It accepts **questions (.txt)** and optional **datasets (.csv, .xlsx, .json, .parquet, images)**, then uses **LangChain + Google Generative AI** to analyze and answer queries with charts, tables, and insights.

Frontend (`index.html`) is provided for uploading files and viewing results.

---

## 🚀 Features
- FastAPI backend with async API endpoints.
- File upload support (`questions.txt` + datasets).
- Intelligent agent powered by **LangChain** + **Google Gemini**.
- Automatic chart rendering with base64 images.
- Frontend UI with drag-and-drop file upload.

---

## 📂 Project Structure

├── app.py # FastAPI backend
├── index.html # Frontend UI
├── requirements.txt # Python dependencies
├── Dockerfile # Container definition
├── .gitignore # Git ignore rules
└── README.md # Project docs


---

## 🛠️ Setup (Local)

### 1. Create virtual environment
```bash
python -m venv venv
source venv/bin/activate   # Linux / Mac
venv\Scripts\activate      # Windows
2. Install dependencies
pip install -r requirements.txt

3. Set environment variables

Create a .env file:

GOOGLE_API_KEY=your_google_genai_key
GOOGLE_MODEL=gemini-2.5-pro
LLM_TIMEOUT_SECONDS=150

4. Run locally
uvicorn app:app --reload --host 0.0.0.0 --port 8000


App will be available at: http://localhost:8000

🐳 Run with Docker
1. Build image
docker build -t data-analyst-agent .

2. Run container
docker run -it --rm -p 8000:8000 --env-file .env data-analyst-agent

🧪 API Usage
Health Check
curl http://localhost:8000/api

Analyze Data
curl -X POST "http://localhost:8000/api" \
  -F "questions_file=@questions.txt" \
  -F "data_file=@dataset.csv"


Response: JSON with answers, numbers, or base64 charts.

📊 Frontend

Open http://localhost:8000 in browser to use drag-and-drop web UI.

⚡ Tech Stack

FastAPI + Uvicorn

LangChain + Google Generative AI

pandas, numpy, matplotlib, seaborn

BeautifulSoup4, requests

Dockerized deployment