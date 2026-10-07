# AI-# 📄 AI Resume ATS Checker

Upload a resume (PDF or DOCX) and get an **ATS score**, a score breakdown, keyword gaps,
prioritized improvements, and example bullet rewrites, powered by **Google Gemini Flash** and **Streamlit**.

## Features
- PDF and DOCX resume parsing
- Overall ATS score (0-100) with breakdown: formatting, keywords, content, readability
- Optional job description for targeted keyword matching
- Strengths, weaknesses, and prioritized fixes
- Rewritten example bullet points
- Download the report as JSON

## Run locally
```bash
git clone https://github.com/<your-username>/<your-repo>.git
cd <your-repo>
python -m venv venv
source venv/bin/activate        # Windows: venv\Scripts\activate
pip install -r requirements.txt
streamlit run app.py
```
Paste your Gemini API key in the sidebar (free key: https://aistudio.google.com/apikey).

Optional: create `.streamlit/secrets.toml` so you don't have to paste it every time:
```toml
GEMINI_API_KEY = "your-key-here"
```
**Never commit this file.**

## Deploy on Streamlit Community Cloud
1. Push this repo to GitHub (`app.py`, `requirements.txt`, `README.md`).
2. Go to https://share.streamlit.io and sign in with GitHub.
3. Click **Create app**, choose your repo, branch `main`, main file `app.py`.
4. Open **Advanced settings → Secrets** and add: `GEMINI_API_KEY = "your-key-here"`
5. Click **Deploy**.

## Notes
- Scanned (image-only) PDFs can't be read, which is also true for real ATS systems.
- Change the model via `MODEL_NAME` in `app.py` (default `gemini-2.5-flash`).
- The score is an AI estimate, not the output of any specific commercial ATS.
