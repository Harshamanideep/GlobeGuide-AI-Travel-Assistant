# GlobeGuide-AI-Travel-Assistant

A scalable Generative AI–powered travel assistant built with:

- **FastAPI** backend (Gemini Streaming + Function Calling, OpenAI Assistants API)  
- **Next.js 14** frontend  
- **Streamlit** frontend for Python users  
- Database layer using **Pydantic + SQLAlchemy + Neon PostgreSQL**  
- Interactive maps using **Google Maps JS API** (Next.js) and **Plotly + MapBox** (Streamlit)

---

## Features

- Gemini Pro Streaming & Function Calling  
- OpenAI Assistants API integration  
- Fully streamed responses from backend to frontend  
- Interactive travel maps  
- Real-time FastAPI data handling  
- Simple Streamlit UI for quick prototyping  

---

## Run Locally

### 1. Backend (FastAPI)

```bash
cd backend/src
pip install -r requirements.txt
uvicorn main:app
```

Test endpoint:

```
POST http://localhost:8000/travel_assistant?prompt="Share 2 places to visit in UAE"
```

---

### 2. Streamlit Frontend

```bash
streamlit run app.py
```

Open:  
http://localhost:8501

---

### 3. Next.js Frontend

```bash
pnpm install
pnpm dev
```

Open:  
http://localhost:3000

---

## Run with Docker

### Build and Run Backend

```bash
docker build -t travel_ai_service .
docker run --env-file .env -d -p 80:80 travel_ai_service
```

### Push to Docker Hub

```bash
docker tag travel_ai_service <username>/travel_ai_service:latest
docker push <username>/travel_ai_service:latest
```

### Deploy on Google Cloud Run

```bash
gcloud run deploy travel-ai-service --image <username>/travel_ai_service:latest
```
---

## Next.js Deployment (Docker)

```bash
docker buildx build --platform linux/amd64 -t nextjs_travel_ai .
docker run --env-file .env -d -p 3000:8000 nextjs_travel_ai
docker push <username>/nextjs_travel_ai:latest
gcloud run deploy nextjs-travel-ai --image <username>/nextjs_travel_ai:latest
```
