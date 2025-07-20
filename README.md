# 📊 Financial RAG Assistant

![Python](https://img.shields.io/badge/python-3.10+-blue.svg)
![LangChain](https://img.shields.io/badge/langchain-%F0%9F%94%A5-success)
![FAISS](https://img.shields.io/badge/FAISS-VectorSearch-green)
![Groq](https://img.shields.io/badge/Groq-LLM%20powered-orange)
![License](https://img.shields.io/badge/license-MIT-blue)

A powerful **Retrieval-Augmented Generation (RAG)** assistant built with **LangChain**, **FAISS**, and **Groq LLaMA3-8B** to extract insights from financial 10-Q reports and answer questions with high accuracy and speed.

---

## 🚀 Features

- 📁 Upload and process any SEC 10-Q PDF
- ❓ Ask financial questions (like net income, revenue, legal cases, etc.)
- ⚡ Powered by Groq’s ultra-fast LLaMA3 models
- 🧠 Contextual search with FAISS + Sentence Transformers
- 🛡️ Answer filtering to avoid hallucinations
- 🖥️ Interactive Gradio UI with real-time responses

---

## 🧠 Architecture Overview

```mermaid
flowchart TD
    A[PDF Upload] --> B[Extract Text with PyMuPDF]
    B --> C[Split into Chunks]
    C --> D[Embed with BGE-small]
    D --> E[Store in FAISS Vector DB]
    F[User Question] --> G[Embed Question]
    G --> H[Retrieve Top 5 Chunks from FAISS]
    H --> I[Groq LLaMA3-8B LLM]
    I --> J[Generate Final Answer]
    J --> K[Display in Gradio UI]
