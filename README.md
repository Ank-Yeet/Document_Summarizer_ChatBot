<div align="center">
  
# 🧠 InferaDoc
**High-Performance AI Document Assistant**

[![FastAPI](https://img.shields.io/badge/FastAPI-005571?style=for-the-badge&logo=fastapi)](https://fastapi.tiangolo.com)
[![React](https://img.shields.io/badge/react-%2320232a.svg?style=for-the-badge&logo=react&logoColor=%2361DAFB)](https://reactjs.org/)
[![PostgreSQL](https://img.shields.io/badge/postgresql-4169e1?style=for-the-badge&logo=postgresql&logoColor=white)](https://postgresql.org)
[![LangChain](https://img.shields.io/badge/LangChain-1C3C3C?style=for-the-badge&logo=langchain)](https://langchain.com)

InferaDoc is an advanced agentic document analysis platform. Upload your documents, ask complex questions, and let the AI instantly search, summarize, and retrieve precise information. 
</div>

---

## 🧠 Key Features

* 📄 Upload and process documents (PDF / TXT)
* 🔍 Semantic search using vector embeddings
* 🤖 Context-aware Q&A over documents
* 🧾 Automatic summarization of long texts
* 🧠 Agentic workflow (multi-step reasoning + tool use)
* ⚡ Fast vector retrieval using ChromaDB
* 🔒 Fully local inference using Ollama (no API dependency)

---

## 🏗️ Architecture

User Query
↓
Embedding Model
↓
Vector Database (ChromaDB)
↓
Relevant Context Retrieval
↓
LLM via Ollama (Agentic Reasoning)
↓
Final Answer / Summary

---

## 🛠️ Tech Stack

* **Language:** Python
* **LLM Runtime:** Ollama
* **Vector DB:** ChromaDB
* **Frameworks/Libraries:** LangChain / LlamaIndex (if used)
* **Embeddings:** Sentence Transformers / Ollama embeddings
* **Frontend (optional):** Streamlit / CLI

---

## ⚙️ Installation & Setup

### 1. Clone the repository

```bash
git clone https://github.com/your-username/repo-name.git
cd repo-name
```

### 2. Install dependencies

```bash
pip install -r requirements.txt
```

### 3. Install and run Ollama

Download from: https://ollama.com

Run a model:

```bash
ollama run llama3
```

---

## ▶️ Usage

### Run the chatbot:

```bash
cd frontend

# Install Node dependencies
npm install

# Start the Vite development server
npm run dev
# The website will be available at http://localhost:5173
```

## 🧠 How it Works

1. **Document Upload**: When you upload a `.pdf` or `.docx`, the backend extracts the text, chunks it intelligently, and creates 768-dimensional embeddings, inserting them directly into PostgreSQL.
2. **ReAct Loop**: Upon asking a question, LangGraph's ReAct agent intercepts it. The AI chooses one of several tools (e.g., `document_search`, `topic_summarizer`, `full_document_summary`, `web_search`) to contextually gather the right data before answering.
3. **Streaming**: As the model generates its final thought, words are streamed chunk-by-chunk over HTTP via Server-Sent Events straight to the React frontend UI.

---
*Built from scratch to redefine context-aware chat experiences.*
