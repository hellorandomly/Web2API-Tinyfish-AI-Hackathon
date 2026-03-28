# Web2API TinyFish AI Hackathon

Web2API is a FastAPI web app for turning messy websites into structured outputs.

It includes two workflows:

- Storefront extraction: uses TinyFish + OpenAI to extract product-like results and render them in a table and UI preview
- Website analysis: fetches a live page, infers schema/page structure, and generates sample API endpoints

## Features

- FastAPI backend
- TinyFish-powered extraction
- OpenAI-powered schema shaping and showcase generation
- Product table preview
- UI-based product preview
- Website analysis studio
- Generated sample API endpoints

## Local run

```bash
python -m venv .venv
.venv\Scripts\activate
pip install -r requirements.txt
uvicorn main:app --reload
```

Open:

- `http://127.0.0.1:8000/`
- `http://127.0.0.1:8000/docs`

## Environment variables

Create a `.env` file with:

```env
TINYFISH_API_KEY=your_tinyfish_key
OPENAI_API_KEY=your_openai_key
```

Optional:

```env
TINYFISH_URL=https://agent.tinyfish.ai/v1/automation/run
```

## Deploy

For Render:

- Build command:
  `pip install -r requirements.txt`
- Start command:
  `uvicorn main:app --host 0.0.0.0 --port $PORT`

## Notes

- The website-analysis workflow stores results in memory, so they reset on redeploy/restart.
- This is acceptable for a hackathon demo but not persistent production storage.
