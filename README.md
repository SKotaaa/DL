# DecisionLens

DecisionLens is an AI-powered decision analysis system that helps users upload documents, ask questions, and get clear, evidence-based answers. It uses Retrieval-Augmented Generation (RAG) to search through uploaded content, retrieve the most relevant context, and generate explainable responses using a local **Ollama** model.

## Overview

DecisionLens is designed to turn unstructured documents into useful insights. Instead of giving generic answers, it focuses on document-grounded responses with supporting context, making it easier to understand decisions, compare options, and find important details quickly.

## Features

* Document upload and processing
* RAG-based question answering
* Semantic search using embeddings
* Local LLM integration with **Ollama**
* Context-aware and explainable responses
* Fast retrieval with FAISS
* Clean and interactive UI
* Support for multiple document formats
* Secure and modular backend architecture

## How it works

1. A user uploads a document.
2. The document is parsed and split into chunks.
3. Embeddings are generated for each chunk.
4. Chunks are stored in a vector index such as FAISS.
5. When the user asks a question, the most relevant chunks are retrieved.
6. The retrieved context is sent to the Ollama model.
7. The model generates a grounded and explainable answer.

## Tech Stack

### Frontend

* React
* Tailwind CSS
* Vite

### Backend

* FastAPI / Node.js (as applicable in your project)
* Python
* REST APIs

### AI / RAG

* Ollama
* FAISS
* SentenceTransformers or similar embedding model
* Document chunking and retrieval pipeline

### Optional Services

* PostgreSQL / MongoDB / Firebase for metadata storage
* Docker for deployment

## Project Structure

```bash
DecisionLens/
├── frontend/
├── backend/
├── models/
├── uploads/
├── data/
├── src/
├── .env
└── README.md
```

## Getting Started

### Prerequisites

Make sure you have the following installed:

* Node.js
* Python 3.10+
* Ollama
* Git

### Install Ollama

Install and run Ollama from the official website, then pull your preferred model.

Example:

```bash
ollama pull llama3
```

You can replace `llama3` with any model supported in your setup.

### Backend Setup

```bash
cd backend
pip install -r requirements.txt
```

Create a `.env` file in the backend folder:

```env
OLLAMA_MODEL=llama3
OLLAMA_BASE_URL=http://localhost:11434
EMBEDDING_MODEL=sentence-transformers/all-MiniLM-L6-v2
```

Run the backend:

```bash
uvicorn main:app --reload
```

### Frontend Setup

```bash
cd frontend
npm install
npm run dev
```

## Usage

1. Open the application in your browser.
2. Upload a document.
3. Ask a question related to the document.
4. View the retrieved context and generated answer.
5. Use the response for analysis, comparison, or decision support.

## Example Use Cases

* Summarizing reports
* Comparing options from documents
* Extracting key points from PDFs
* Finding answers inside uploaded files
* Supporting decision-making with evidence

## Environment Variables

| Variable          | Description                            |
| ----------------- | -------------------------------------- |
| `OLLAMA_MODEL`    | Name of the local Ollama model         |
| `OLLAMA_BASE_URL` | Ollama API base URL                    |
| `EMBEDDING_MODEL` | Embedding model used for vectorization |
| `DATABASE_URL`    | Database connection string             |
| `SECRET_KEY`      | Application secret key                 |

## API Endpoints

### `POST /upload`

Uploads and processes a document.

### `POST /query`

Accepts a user question and returns a grounded answer using retrieved context.

### `GET /health`

Checks whether the backend is running.

## Advantages

* Uses local Ollama inference instead of depending on a cloud LLM
* Reduces API cost
* Keeps responses grounded in uploaded documents
* Easier to explain and trust
* Good for private or offline-friendly workflows

## Future Improvements

* Multi-document comparison
* Chat history support
* Better document preview UI
* OCR support for scanned files
* Role-based access control
* Export answers as PDF
* Improved analytics dashboard

## Screenshots

Add screenshots of your dashboard, upload page, and chat interface here.

## Contributing

Contributions are welcome. Feel free to fork the repository, create a feature branch, and submit a pull request.

## License

Add your preferred license here.

## Acknowledgements

* Ollama
* FAISS
* SentenceTransformers
* React
* FastAPI

---

Built with focus on explainability, document intelligence, and practical AI decision support.
