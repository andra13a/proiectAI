# MindCore

MindCore is an AI-powered web application designed to help
students learn using their own course materials.

Users can upload PDF documents, ask questions about their
content, and practice with quizzes and flashcards.

## Team Innovators

- Radulescu Cristina Maria
- Dobrota Iasmina Maria
- Dutu Stefania Andra
- Stoia Vlad Eugen
- Popescu Marius Valentin

## Features

- User registration and authentication.
- Uploading course materials in PDF format.
- Chatting with an AI assistant based on uploaded documents.
- Displaying relevant sources, including document names and page numbers.
- Generating quizzes and flashcards for revision.
- Saving and viewing conversation history.

## How It Works

The application extracts text from PDF documents and splits it
into chunks. These chunks are converted into vector embeddings
and stored in Qdrant.

When a question is submitted, relevant chunks are retrieved
and sent to the AI model through Groq to generate an answer.
This approach is called RAG (Retrieval-Augmented Generation).

## Technologies

- **Frontend:** React, Vite, CSS, and Framer Motion.
- **Backend:** Python and FastAPI.
- **Artificial intelligence:** Groq and Sentence Transformers.
- **Data storage:** PostgreSQL and Qdrant.
- **PDF processing:** PyMuPDF.
- **Authentication:** JWT.
- **Containers:** Docker and Docker Compose.

## Project Structure

- `frontend/` — the application interface.
- `backend/` — the API, authentication, and document processing.
- `docker-compose.yml` — Docker service configuration.

## Getting Started

1. Download or clone the repository.
2. Copy `backend/.env.example` to `backend/.env` and configure
   the PostgreSQL connection, Qdrant settings, and Groq API key.
3. Set up the `MindCore` PostgreSQL schema and the required tables.
   The project archive does not include an SQL initialization script.
4. Install the backend dependencies from `backend/requirements.txt`
   and start the API from the `backend` directory:
   `uvicorn app.main:app --reload`
5. From the `frontend` directory, run `npm install`,
   followed by `npm run dev`.
6. Open the application at `http://localhost:5173`.

The backend is available at `http://localhost:8000`,
and the API documentation at `http://localhost:8000/docs`.
