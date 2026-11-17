# Interview AI

Interview AI is a React application that creates personalized interview
preparation plans from a job description and a candidate profile. It uses the
API in `../Backend` for authentication, AI-generated reports, and resume
downloads.

## Features

- Register and sign in with cookie-based authentication.
- Submit a job description, resume, or self-description.
- Generate an interview plan with:
  - technical questions,
  - behavioral questions,
  - model answers and question intent,
  - a match score and skill gaps,
  - a day-by-day preparation roadmap.
- Download a tailored resume from an interview report.

## Prerequisites

- Node.js 18 or newer
- MongoDB
- A Google Gemini API key

## Setup

Install dependencies in both applications:

```bash
cd Backend
npm install

cd ../Frontend
npm install
```

Create `Backend/.env` with:

```dotenv
MONGO_URI=mongodb://127.0.0.1:27017/interview-ai
JWT_SECRET=replace-with-a-long-random-secret
GOOGLE_GENAI_API_KEY=your-google-gemini-api-key
```

Do not commit `.env` or expose the Gemini API key in frontend code.

## Run locally

Start the API in one terminal:

```bash
cd Backend
npm run dev
```

Start the Vite development server in another:

```bash
cd Frontend
npm run dev
```

Open [http://localhost:5173](http://localhost:5173). The frontend expects the
API at `http://localhost:3000`, and the backend is configured to allow that
origin with credentials.

## Frontend scripts

Run these commands from `Frontend/`:

| Command | Description |
| --- | --- |
| `npm run dev` | Start the Vite development server |
| `npm run build` | Create a production build |
| `npm run preview` | Preview the production build |
| `npm run lint` | Run ESLint |

## Application routes

- `/login` — sign in
- `/register` — create an account
- `/` — create and view interview plans
- `/interview/:interviewId` — view a generated plan