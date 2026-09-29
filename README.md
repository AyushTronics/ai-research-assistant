# 📚 AI Research Assistant

An AI-powered research assistant for interacting with research papers using Retrieval-Augmented Generation (RAG), FAISS vector search, and Large Language Models.

Upload research papers, ask questions about their content, generate structured summaries, or use the assistant for general knowledge queries through a simple Streamlit interface.

## 🚀 Features

- 📄 Upload one or multiple research papers in PDF format
- 🔎 RAG-based question answering
- 🧠 LLM-powered responses using OpenRouter
- 📚 FAISS-based semantic vector search
- 📝 Research paper summarization
- 🌐 General knowledge question answering
- 🔖 Source/page citations for retrieved information
- 💬 Interactive Streamlit chat interface

## 🏗️ Architecture

User → Streamlit UI → Query Routing → FAISS Retriever → Relevant Chunks → LLM → Grounded Answer → Source Citations

For summarization:

User → Streamlit UI → Full Document Text → LLM → Structured Summary

## 🔄 RAG Pipeline

1. User uploads a research paper in PDF format.
2. The document is processed and divided into smaller text chunks.
3. Text chunks are converted into vector embeddings.
4. Embeddings are stored in a FAISS vector database.
5. The user's question is converted into an embedding.
6. FAISS retrieves the most relevant document chunks.
7. Retrieved chunks are provided to the LLM as context.
8. The LLM generates an answer grounded in the retrieved context.
9. Source references are displayed with the response.

## 🤖 Application Modes

### 🔎 Research Question

Questions related to uploaded research papers are handled through the RAG pipeline.

Example:

What is the main contribution of this paper?

### 📝 Research Paper Summarization

The assistant can generate a structured summary of an uploaded research paper covering:

- Main Objective
- Methodology
- Key Findings
- Conclusion

### 🌐 General Knowledge

Questions that do not depend on the uploaded research paper can be answered directly by the LLM.

Example:

What is gradient descent?

## 🛠️ Tech Stack

- Python — Core programming language
- Streamlit — Web application interface
- LangChain — Document and RAG workflow
- FAISS — Vector similarity search
- Sentence Transformers — Text embeddings
- PyPDF — PDF document processing
- OpenRouter — LLM API provider
- Llama 3.3 70B — Response generation

## 📁 Project Structure

AI-Research-Assistant/

├── agents.py
├── create_vector_db.py
├── retriever.py
├── router.py
├── streamlit_app.py
├── requirements.txt
├── .env.example
├── .gitignore
├── LICENSE
├── README.md
└── Result Output/

### File Overview

**streamlit_app.py** — Handles the Streamlit interface, PDF uploads, chat interaction, and application flow.

**create_vector_db.py** — Processes uploaded documents and creates the FAISS vector database.

**retriever.py** — Loads and manages the document retriever used for semantic search.

**router.py** — Provides lightweight routing between summarization requests and normal questions.

**agents.py** — Contains the LLM functions for research question answering, summarization, and general knowledge responses.

## ⚙️ Installation

Clone the repository:

git clone https://github.com/AyushTronics/ai-research-assistant.git

cd ai-research-assistant

Create a virtual environment:

python3 -m venv venv

Activate it on macOS/Linux:

source venv/bin/activate

Install dependencies:

pip install -r requirements.txt

## 🔑 Environment Setup

Create a `.env` file in the project root and add:

OPENROUTER_API_KEY=your_api_key_here

Replace the value with your own OpenRouter API key.

Never commit your `.env` file or expose your API key publicly.

## ▶️ Run the Application

Start the application using:

python -m streamlit run streamlit_app.py

The Streamlit interface will open in your browser.

## 💡 Example Queries

After uploading a research paper, try:

- What is the main contribution of this paper?
- What are the key components of the proposed architecture?
- What datasets were used in the experiments?
- What are the advantages of the proposed approach?
- What are the limitations discussed by the authors?

For summarization, type:

summarize

## 📸 Screenshots

The repository includes screenshots demonstrating:

- Research Assistant Interface
- Research Paper Upload
- RAG Question Answering
- General Knowledge Agent
- Research Paper Summarization

## 🔮 Future Improvements

- Multi-paper comparison
- Conversation memory
- Improved query routing
- Hybrid keyword and semantic retrieval
- Research paper metadata extraction
- Automated retrieval evaluation
- Support for additional document formats

## 🎯 Learning Outcomes

This project provides practical experience with:

- Retrieval-Augmented Generation
- Vector databases
- Semantic search
- Text embeddings
- LLM application development
- Prompt engineering
- PDF document processing
- Streamlit application development
- Source-grounded question answering

## 📜 License

This project is intended for educational and research purposes.
