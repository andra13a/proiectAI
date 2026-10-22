# MindCore

MindCore este o aplicație web cu inteligență artificială, creată
pentru a ajuta studenții să învețe folosind propriile materiale de curs.

Utilizatorii pot încărca documente PDF, adresa întrebări despre
conținutul acestora și exersa prin quiz-uri și flashcard-uri.

## Echipa Innovators

- Radulescu Cristina Maria
- Dobrota Iasmina Maria
- Dutu Stefania Andra
- Stoia Vlad Eugen
- Popescu Marius Valentin

## Funcționalități

- Înregistrare și autentificare.
- Încărcarea materialelor de curs în format PDF.
- Chat cu un asistent AI pe baza documentelor încărcate.
- Afișarea surselor relevante, cu numele documentului și pagina.
- Generarea de quiz-uri și flashcard-uri pentru recapitulare.
- Salvarea și consultarea istoricului conversațiilor.

## Cum funcționează

Aplicația extrage textul din documentele PDF și îl împarte în
fragmente. Acestea sunt transformate în reprezentări vectoriale
și stocate în Qdrant.

La primirea unei întrebări, sunt căutate fragmentele relevante,
care sunt apoi trimise modelului AI prin Groq pentru formularea
răspunsului. Această abordare se numește RAG
(Retrieval-Augmented Generation).

## Tehnologii

- **Frontend:** React, Vite, CSS și Framer Motion.
- **Backend:** Python și FastAPI.
- **Inteligență artificială:** Groq și Sentence Transformers.
- **Stocarea datelor:** PostgreSQL și Qdrant.
- **Prelucrarea PDF-urilor:** PyMuPDF.
- **Autentificare:** JWT.
- **Containere:** Docker și Docker Compose.

## Structura proiectului

- `frontend/` — interfața aplicației.
- `backend/` — API-ul, autentificarea și procesarea documentelor.
- `docker-compose.yml` — configurarea serviciilor Docker.

## Rulare

1. Descarcă sau clonează repository-ul.
2. Copiază `backend/.env.example` în `backend/.env` și completează
   conexiunea PostgreSQL, configurarea Qdrant și cheia API Groq.
3. Pregătește schema PostgreSQL `MindCore` și tabelele necesare.
   Arhiva nu include un script SQL de inițializare.
4. Instalează dependențele backend din `backend/requirements.txt`
   și pornește API-ul din directorul `backend`:
   `uvicorn app.main:app --reload`
5. Din directorul `frontend`, rulează `npm install`,
   apoi `npm run dev`.
6. Accesează aplicația la `http://localhost:5173`.

Backend-ul este disponibil la `http://localhost:8000`,
iar documentația API la `http://localhost:8000/docs`.
