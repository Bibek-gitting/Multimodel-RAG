# 🚀 MultiModal RAG

> **An end-to-end Multimodal Retrieval-Augmented Generation (RAG) system capable of understanding PDFs, DOCX files, scanned documents, and images using OCR, semantic retrieval, vector search, and Large Language Models.**

![Python](https://img.shields.io/badge/Python-3.11+-blue)
![FastAPI](https://img.shields.io/badge/FastAPI-Backend-green)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-PGVector-blue)
![License](https://img.shields.io/badge/License-MIT-yellow)

---

# Table of Contents

- Overview
- Features
- Architecture
- Project Workflow
- Tech Stack
- Folder Structure
- Installation
- Configuration
- Running the Project
- API Endpoints
- AI Pipeline
- Future Improvements
- Contributing
- License

---

# Overview

MultiModal RAG is an AI-powered document intelligence system that enables users to upload documents or images and ask natural language questions. The system extracts text (including OCR for scanned files), builds semantic embeddings, stores them in PGVector, retrieves the most relevant chunks, optionally re-ranks them, and generates grounded responses using an LLM.

---

# Features

- PDF support
- DOCX support
- Image support (PNG/JPG/JPEG)
- OCR for scanned documents
- Semantic chunking
- Dense vector embeddings
- PostgreSQL + PGVector
- Semantic retrieval
- LLM-powered answers
- FastAPI backend
- Frontend UI
- Modular architecture

---

# Architecture

```text
                User
                  │
          Upload Document
                  │
       ┌──────────┴──────────┐
       │                     │
 Text Extraction       Image Extraction
       │                     │
       └─────── OCR ─────────┘
                  │
          Semantic Chunking
                  │
          Embedding Generation
                  │
        PostgreSQL + PGVector
                  │
          Similarity Retrieval
                  │
             Re-ranking
                  │
                  LLM
                  │
             Final Response
```

---

# AI Pipeline

1. Upload document or image.
2. Detect file type.
3. Extract text and images.
4. OCR scanned pages.
5. Split into semantic chunks.
6. Generate embeddings.
7. Store vectors with metadata.
8. Retrieve relevant chunks.
9. Re-rank retrieved context.
10. Generate grounded answer.

---

# Tech Stack

| Category | Technology |
|-----------|------------|
| Backend | FastAPI |
| Language | Python |
| Database | PostgreSQL + PGVector |
| OCR | OCR Microservice |
| Embeddings | CLIP / HuggingFace |
| Vision Model | Qwen VL |
| Frontend | HTML, CSS, JavaScript |

---

# Folder Structure

```text
Multimodel-RAG/
├── backend/
├── frontend/
├── OCR-microservice/
├── requirements.txt
└── README.md
```

---

# Installation

```bash
git clone https://github.com/Bibek-gitting/Multimodel-RAG.git

cd Multimodel-RAG

python -m venv venv

# Windows
venv\Scripts\activate

# Linux
source venv/bin/activate

pip install -r requirements.txt
```

---

# Configuration

Configure your PostgreSQL database and PGVector connection.

Store secrets inside environment variables instead of hardcoding them.

Example:

```env
DB_HOST=localhost
DB_PORT=5432
DB_NAME=rag_db
DB_USER=postgres
DB_PASSWORD=password
```

---

# Running

Start OCR

```bash
cd OCR-microservice
python OCR_service.py
```

Backend

```bash
cd backend
python fastapi_main.py
```

Frontend

Open `frontend/index.html`

---

# API

## Upload

```http
POST /upload
```

## Query

```http
POST /query
```

Example

```json
{
  "question":"Explain the uploaded document."
}
```

---

# Retrieval Process

- Embed the query.
- Search PGVector.
- Retrieve top-k chunks.
- Re-rank.
- Pass context to LLM.
- Return answer.

---

# Why RAG?

Traditional LLMs rely only on training data.

RAG grounds responses using retrieved document context, reducing hallucinations while allowing the model to answer questions about newly uploaded documents.

---

# Future Improvements

- Hybrid Search (BM25 + Dense)
- Streaming Responses
- Authentication
- Docker
- Kubernetes
- Redis Cache
- Multi-user support
- Citation generation
- Conversation memory

---

# Contributing

Contributions are welcome.

1. Fork repository
2. Create branch
3. Commit changes
4. Open Pull Request

---

# License

MIT License

---

# Author

**Bibek**

GitHub: https://github.com/Bibek-gitting
