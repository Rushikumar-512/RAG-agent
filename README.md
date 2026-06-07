# 🏏 Cricket Rules AI - RAG Chatbot

An production-ready, low-code AI Agent built using **n8n** that utilizes Retrieval-Augmented Generation (RAG) to answer questions about the official rules, regulations, scoring systems, and match guidelines of cricket. 

The architecture is split into two independent phases: **Data Ingestion** (storing document embeddings into a vector database) and **Live Chat Retrieval** (querying the database in real-time to answer user questions).

---

## 🚀 Features
* **Agentic RAG Architecture:** Separates the heavy lifting of data ingestion from live, low-latency user chat execution.
* **Vector Embeddings:** Uses OpenAI Embeddings to turn unstructured document rules into mathematical vector representations.
* **Cloud Vector Storage:** Utilizes Supabase (via pgvector) for fast, persistent semantic search retrieval.
* **Zero-Code Workflows:** Built entirely using visual automation nodes within n8n.

---

## 🛠️ Tech Stack & Nodes Used
* **Automation Platform:** [n8n](https://n8n.io/)
* **AI Framework:** Advanced AI (n8n Native Agent & Tools)
* **LLM / Chat Model:** OpenAI (GPT-4o / GPT-3.5-Turbo)
* **Embedding Model:** OpenAI Text Embedding 3 (Small/Large)
* **Vector Database:** Supabase (PostgreSQL with `pgvector`)
* **Data Loader:** Default Document Loader & Text Splitter

---

## 📐 Workflow Architecture

The workflow consists of two distinct data flows on a single canvas:

### 1. Ingestion Flow (Bottom Pipeline)
* **Trigger:** Manual or webhook-based execution when documentation updates.
* **Process:** 1. Downloads the cricket rules data file.
  2. Passes the file through the **Default Data Loader** to
