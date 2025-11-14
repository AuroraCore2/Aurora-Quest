📚 AI-Powered Study Planner

An intelligent study companion that helps students plan, learn, and revise efficiently using AI, RAG-based search, voice tutoring, real-time progress tracking, and adaptive quizzes.
Built with FastAPI + Next.js, Agora RTC, OpenAI, and Pinecone.

🚀 Features
🔹 Smart Study Plan Generator

Creates a personalized plan based on syllabus, exam date, and daily study hours

Updates automatically based on completion

🔹 PDF Knowledge Base (RAG)

Upload PDFs → processed into embeddings

Pinecone vector search for accurate, context-aware answers

AI chat trained on the user's uploaded notes

🔹 AI Voice Tutor (Agora + GPT)

Real-time AI voice-based tutoring

Low-latency WebRTC

Perfect for hands-free learning

🔹 Adaptive Quiz Generator

Auto-generates MCQs and short questions

Difficulty adjusts to user performance

🔹 Gamification

XP, streaks, badges

Weekly/monthly progress dashboard

Motivates consistent learning

🔹 Real-Time Sync

WebSockets for instant updates of tasks, progress, XP, and quizzes

🏗️ Tech Stack
Frontend

Next.js

TailwindCSS

Zustand / Redux

Backend

FastAPI

REST API + WebSockets

Pydantic models

AI + Storage

OpenAI

Pinecone Vector DB

PostgreSQL / pgvector

Voice

Agora RTC

📁 Folder Structure
/frontend
   /components
   /pages
   /utils

/backend
   /routes
   /models
   /services
   /database
   main.py

/ml
   /pdf_processing
   /quiz_generator
   /voice_tutor

🔧 Setup Instructions
Backend Setup
cd backend
pip install -r requirements.txt
uvicorn main:app --reload

Frontend Setup
cd frontend
npm install
npm run dev

Environment Variables

Create a .env file with:

OPENAI_API_KEY=your_key
PINECONE_API_KEY=your_key
AGORA_APP_ID=your_id
JWT_SECRET=your_secret
DATABASE_URL=postgres_url

🔐 Authentication (JWT)

We use JWT Access + Refresh tokens.
When the user logs in:

Server generates:

access_token
refresh_token


Access token is used for short-term authorized requests

Refresh token is used to generate new access tokens

📊 Progress, XP & Streak Logic
Progress Formula
progress = (completed_tasks / total_tasks) * 100

XP Rewards
+10 XP  → Task completed
+20 XP  → Quiz completed
+30 XP  → Voice tutoring session
+50 XP  → Daily streak bonus

Streak Formula
If user completes ≥ 1 task today:
      streak += 1
Else:
      streak = 0

🧠 RAG (PDF → Embeddings → Vector Search)
PDF Processing Steps
1. Extract text from PDF
2. Split text into chunks
3. Generate embeddings using OpenAI
4. Store embeddings in Pinecone
5. Query Pinecone on user questions

Query Pipeline
User question → Embedding → Pinecone search → Relevant chunks → GPT Answer

🎤 Voice Tutor (Agora + OpenAI)
Real-Time Voice Flow
Agora Audio Stream → FastAPI WebSocket → Transcription → GPT Response → Text-to-Speech → User

🛠 API Endpoints (Examples)
Fetch study plan
GET /plan

Update task status
POST /task/update

Get AI chat response
POST /ai/chat

Generate quiz
POST /quiz/generate

🎯 Future Improvements

Add spaced repetition

Recommendations based on weak subjects

Long-term learning analytics

AI-generated flashcards

Mobile app version

🤝 Contributing

Pull requests are welcome!
Open an issue for bugs, features, or enhancements.

⭐ Support

If you like this project, please ⭐ the repository!
