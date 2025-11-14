📚 AI-Powered Study Planner

An intelligent study companion that helps students plan, learn, and revise efficiently using AI, RAG search, voice tutoring, adaptive quizzes, and real-time progress tracking.
Built with FastAPI, Next.js, Agora RTC, OpenAI, and Pinecone.

<img width="1912" height="930" alt="image" src="https://github.com/user-attachments/assets/128ce0a2-6d06-4943-adf5-a2544c4625c7" />



🚀 Features
Smart Study Plan Generator

Generates a personalized study plan based on syllabus and exam dates

Auto-updates progress when tasks are completed

PDF Knowledge Base (RAG)

Upload PDFs and convert them into embeddings

Pinecone vector search provides accurate, context-aware answers

AI Voice Tutor (Agora + GPT)

Real-time voice tutoring

Interactive concept explanations

Low latency using Agora

Adaptive Quiz Generator

Automatically generates MCQs and short questions

Adjusts difficulty dynamically

Gamification

XP, streaks, badges

Weekly and monthly progress analytics

Real-Time Sync

WebSockets for instant updates for tasks, progress, XP, quizzes

🏗️ Tech Stack
Frontend

Next.js

TailwindCSS

Zustand or Redux

Backend

FastAPI

REST APIs and WebSockets

Pydantic models

AI + Storage

OpenAI

Pinecone Vector DB

PostgreSQL or pgvector

Voice

Agora RTC

📁 Folder Structure

Frontend, backend, and ML modules are organized into component-based folders such as components, pages, routes, models, services, and pdf/quiz/voice utilities.

🔧 Setup Overview

Install dependencies for backend and frontend

Run FastAPI server

Run Next.js development server

Add environment variables like OPENAI keys, Pinecone keys, Agora ID, JWT secret, and DB URL

🔐 Authentication (JWT)

Uses JWT access and refresh tokens

Access tokens secure authorized endpoints

Refresh tokens generate new access tokens when expired

📊 Progress, XP & Streak Logic
Progress

Calculated as: completed tasks divided by total tasks multiplied by 100.

XP System

Completing tasks, quizzes, and voice sessions gives XP

Daily streaks give bonus XP

Streak Logic

Streak increases when at least one task is completed daily.
Resets when the user skips a day.

🧠 RAG (PDF → Embeddings → Vector Search)
How It Works

PDFs are processed, text extracted, chunked, converted to embeddings

Embeddings stored in Pinecone

When the user asks a question, the system searches relevant chunks and GPT generates the answer

🎤 Voice Tutor (Agora + OpenAI)
Flow

User speaks → Agora audio stream

Server transcribes

GPT generates answer

AI responds via voice

🛠 API Endpoints (High-Level)

Get study plan

Update task

AI chat

Quiz generation

🎯 Future Improvements

Spaced repetition

Weak-topic recommendations

Flashcards

Learning analytics

