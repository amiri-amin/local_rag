# Building a Custom RAG Pipeline with LlamaIndex and Llama 3.2

This example shows how to build a classic **Retrieval-Augmented Generation (RAG)**
pipeline with [LlamaIndex](https://www.llamaindex.ai/): parse a PDF document, embed it
with a Hugging Face model, index the embeddings in a vector store, and answer questions
with Groq's Llama 3.2 LLM. The vector store is persisted to disk so it can be reused
without re-indexing.

## What the notebook covers

- Loading and parsing a PDF document with **LlamaParse**
- Creating vector embeddings with a Hugging Face model
  (`sentence-transformers/all-MiniLM-L6-v2`)
- Building a `VectorStoreIndex` and querying it with **Groq**'s Llama 3.2 LLM
- Persisting the vector store to `./storage/` for reuse

## Prerequisites

- Python 3.11+
- A Groq API key
- A LlamaIndex Cloud (LlamaParse) API key
- A Hugging Face token

## Setup

1. Create and activate a Python virtual environment:

   ```bash
   python -m venv .venv
   source .venv/bin/activate      # On Windows: .venv\Scripts\activate
   ```

2. Install the required packages:

   ```bash
   pip install -r requirements.txt
   ```

3. Create your environment file from the template:

   ```bash
   cp .env.example .env
   ```

4. Edit `.env` and add your API keys:
   - `GROQ_API_KEY` — your Groq API key
   - `LLAMA_CLOUD_API_KEY` — your LlamaIndex Cloud (LlamaParse) API key
   - `HF_TOKEN` — your Hugging Face token

## Running the demo

1. Launch Jupyter and open `main.ipynb`:

   ```bash
   jupyter notebook main.ipynb
   ```

2. Run all cells to see the demo in action.

## Notes

- Make sure all required API keys are set in `.env` before running the notebook.
- The demo ships with a sample PDF (`data/2025_Tucson_Hybrid_user_manual.pdf`). Point the
  loader at your own document to run the pipeline over your own data.

---

Written and developed by **Amin Amiri**. Released under the [MIT License](../LICENSE).
