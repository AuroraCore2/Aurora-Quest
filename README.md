### Team Members-
- Asiya Arif<br>
- Anjali Singh<br>
- Akansha Kambley<br>

## 📚 AI-Powered Study Planner

An intelligent study companion that helps students plan, learn, and revise efficiently using AI, RAG search, voice tutoring, adaptive quizzes, and real-time progress tracking.
Built with FastAPI, Next.js, Agora RTC, OpenAI, and Pinecone.

<img width="1834" height="911" alt="image" src="https://github.com/user-attachments/assets/3e546fb2-dc8f-4b19-869f-52fd89f17f25" />


### 🚀 Features
- Smart Study Plan Generator<br>
- Generates a personalized study plan based on syllabus and exam dates<br>
- Auto-updates progress when tasks are completed<br>
- PDF Knowledge Base (RAG)<br>
- Upload PDFs and convert them into embeddings<br>
- Pinecone vector search provides accurate, context-aware answers<br>
- AI Voice Tutor (Agora + GPT)<br>
- Real-time voice tutoring<br>
- Interactive concept explanations<br>
- Low latency using Agora<br>
- Adaptive Quiz Generator<br>
- Automatically generates MCQs and short questions<br>
- Adjusts difficulty dynamically<br>
- Gamification<br>
- XP, streaks, badges<br>
- Weekly and monthly progress analytics<br>
- Real-Time Sync<br>
- WebSockets for instant updates for tasks, progress, XP, quizzes

### 🏗️ Tech Stack
- Frontend<br>
- Next.js<br>
- TailwindCSS<br>
- Zustand or Redux<br>
- Backend<br>
- FastAPI<br>
- REST APIs and WebSockets<br>
- Pydantic models<br>
- AI + Storage<br>
- OpenAI<br>
- Pinecone Vector DB<br>
- PostgreSQL or pgvector<br>
- Voice<br>
- Agora RTC

### 📁 Folder Structure

Frontend, backend, and ML modules are organized into component-based folders such as components, pages, routes, models, services, and pdf/quiz/voice utilities.

### 🔧 Setup Overview

- Install dependencies for backend and frontend<br>
- Run FastAPI server<br>
- Run Next.js development server<br>
- Add environment variables like OPENAI keys, Pinecone keys, Agora ID, JWT secret, and DB URL

### 🔐 Authentication (JWT)

- Uses JWT access and refresh tokens<br>
- Access tokens secure authorized endpoints<br>
- Refresh tokens generate new access tokens when expired

### 📊 Progress, XP & Streak Logic

- Progress<br>
- Calculated as: completed tasks divided by total tasks multiplied by 100.<br>
- XP System<br>
- Completing tasks, quizzes, and voice sessions gives XP<br>
- Daily streaks give bonus XP<br>
- Streak Logic<br>
- Streak increases when at least one task is completed daily.<br>
- Resets when the user skips a day.<br>

### 🧠 RAG (PDF → Embeddings → Vector Search)

- How It Works<br>
- PDFs are processed, text extracted, chunked, converted to embeddings<br>
- Embeddings stored in Pinecone<br>
- When the user asks a question, the system searches relevant chunks and GPT generates the answer

### 🎤 Voice Tutor (Agora + OpenAI)

Flow<br>
- User speaks → Agora audio stream<br>
- Server transcribes<br>
- GPT generates answer<br>
- AI responds via voice<br>
  
### 🛠 API Endpoints (High-Level)

- Get study plan<br>
- Update task<br>
- AI chat<br>
- Quiz generation

### 🎯 Future Improvements

- Spaced repetition<br>
- Weak-topic recommendations<br>
- Flashcards<br>
- Learning analytics

