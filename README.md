# 📊 Financial RAG Assistant

![Python](https://img.shields.io/badge/python-3.10+-blue.svg)
![LangChain](https://img.shields.io/badge/langchain-%F0%9F%94%A5-success)
![FAISS](https://img.shields.io/badge/FAISS-VectorSearch-green)
![Groq](https://img.shields.io/badge/Groq-LLM%20powered-orange)
![License](https://img.shields.io/badge/license-MIT-blue)

A powerful RAG-based (Retrieval Augmented Generation) assistant built with **LangChain**, **FAISS**, and **Groq LLaMA3-8B** to extract insights from financial 10-Q reports and answer questions with high accuracy and speed.

---

## 🚀 Features

- ✅ Upload and analyze any 10-Q PDF
- 🔍 Ask financial questions and get instant bullet-point answers
- 🧠 LLM-powered with Groq's blazing-fast LLaMA3 8B model
- 🗃️ Semantic search using FAISS and Sentence Transformers
- 🔐 Relevance filtering to prevent hallucinations
- 💻 Interactive Gradio interface
- ⚠️ Context-aware QA (won’t answer if context is missing)

---

## 🧠 Architecture Overview

```mermaid
flowchart TD
    A[User Uploads 10-Q PDF] --> B[Text Extracted via PyMuPDF]
    B --> C[Chunked via Recursive Text Splitter]
    C --> D[Embeddings Generated (BGE-small)]
    D --> E[Stored in FAISS Vector DB]
    F[User Asks Question] --> G[Question Embedded]
    G --> H[Relevant Chunks Retrieved from FAISS]
    H --> I[Context + Question sent to Groq LLM]
    I --> J[LLM Generates Final Answer]
    J --> K[Answer Displayed in Gradio UI]
