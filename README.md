# Build a Retrieval-Augmented Generation (RAG) System

This project demonstrates how to build a Retrieval-Augmented Generation (RAG) pipeline using LangChain, OpenAI models, and ChromaDB in a Jupyter/Colab environment. The pipeline enables you to answer questions based on content extracted from your own PDF documents, making LLMs truly useful for private, organization-specific, or domain-specific information retrieval.

---

## Project Overview & Purpose

RAG combines document retrieval with Large Language Models (LLMs), empowering you to:
- Ask complex questions about your PDF documents.
- Get detailed, accurate, and context-grounded answers.
- Build intelligent Q&A systems for research, healthcare, legal, and enterprise data without training a custom model.

---

## How RAG Works

A RAG system merges two powerful techniques:

1. **Retrieval:** Finds relevant information from your data (e.g., PDFs) using semantic search and embeddings.
2. **Augmented Generation:** Feeds the retrieved context into an LLM (like OpenAI GPT) so its answer is grounded in your documents, not just its training data.

**Pipeline Diagram:**

```
User Question
     │
     ▼
[Vector Search / Retriever]  ◀─────────────┐
     │                                     │
     ▼                                     │
Relevant Text Chunks (from PDFs)           │
     │                                     │
     ▼                                     │
[Prompt + Large Language Model (LLM)]      │
     │                                     │
     ▼                                     │
Grounded Answer (quotes/references your data)
```

---

## Step-by-Step Instructions

### 1. Setup Dependencies

In your Colab/Jupyter environment, install all required libraries:

```python
!pip install -q langchain langchain-community openai chromadb tiktoken pypdf langchain_openai
```

### 2. Store Your OpenAI API Key

In Google Colab:
- Go to the menu: `Runtime → Manage Secrets`
- Add a secret named `OPENAI_API_KEY` with your OpenAI key.

In Jupyter/locally:
```python
import os
os.environ["OPENAI_API_KEY"] = "<your-key-here>"
```

### 3. Prepare Your PDFs

Place all your PDF files in a directory, e.g., `/content`, if running in Colab.

### 4. Run the Notebook

Open [`Build_a_Retrieval_Augmented_Generation_(RAG).ipynb`](https://github.com/ikramkakar/Build-a-Retrieval-Augmented-Generation-RAG-/blob/main/Build_a_Retrieval_Augmented_Generation_(RAG).ipynb) and run each cell sequentially:

- **Install and import libraries**
- **Read/Load the PDF files**
- **Split documents into text chunks**
- **Generate embeddings and build a local ChromaDB**
- **Set up the RAG pipeline**
- **Ask your questions!**

### 5. Example Usage

Try running:
```python
query = "What is the notice period for a Medical Officer who wants to resign?"
response = rag_chain.invoke(query)
print(response)
```
You will get an answer grounded in the relevant PDF content.

---

## Why Use RAG?

- Unlock your PDFs for AI-powered Q&A.
- Answers are traceable, trustworthy, and up-to-date.
- No retraining or prompt engineering needed—just upload documents and ask questions.

---
