# Empathetic AI Chatbot (Multimodal) — Starter

> Educational project for **supportive screening** only. Not a medical device. Not for emergencies.
> In emergencies in India: **112**, Tele-MANAS **14416 / 1-800-891-4416**, KIRAN **1800-599-0019**.

## How to Run (Step-by-Step)
1) **Unzip** this folder.
2) Open a terminal in the project root and create a virtual env:
   ```bash
   python -m venv .venv
   # Windows:
   .venv\Scripts\activate
   # macOS/Linux:
   source .venv/bin/activate
   ```
3) **Install dependencies:**
   ```bash
   pip install --upgrade pip
   pip install -r requirements.txt
   ```
4) **Run the API:**
   ```bash
   uvicorn src.app.main:app --reload
   ```
5) **Open docs:** visit http://127.0.0.1:8000/docs in your browser.
6) **Test chat endpoint** (no audio):
   ```bash
   curl -X POST http://127.0.0.1:8000/chat/ -F "text=I feel very anxious recently and not sleeping well"
   ```
7) **Try PHQ-9 scoring:** in Swagger UI, open /screeners/phq9 and send 9 answers (0–3).
8) **Code to read/edit:** explore `src/` to customize modules (safety, risk, empathy etc.).
9) **Next steps:** replace stub models with trained models (see comments in code).

## Project Layout
```
src/
  app/               # FastAPI app + routes
  safety/            # crisis detector & policy
  screeners/         # PHQ-9 / GAD-7 scoring
  nlp/               # empathy & text risk (stubs)
  audio/             # ASR & audio affect (stubs)
  video/             # video affect (stub)
  fusion/            # late fusion (stub)
  utils/             # logging & redaction
  eval/              # metrics, red-team cases
```
