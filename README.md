# LlamaIndex RAG Examples

[![Python](https://img.shields.io/badge/Python-3.11%2B-blue.svg)](https://www.python.org/)
[![LlamaIndex](https://img.shields.io/badge/Built%20with-LlamaIndex-6f42c1.svg)](https://www.llamaindex.ai/)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](./LICENSE)
[![Notebooks](https://img.shields.io/badge/Format-Jupyter-orange.svg)](https://jupyter.org/)

A compact, hands-on collection of **Retrieval-Augmented Generation (RAG)** reference
implementations built with [LlamaIndex](https://www.llamaindex.ai/). Each example is a
self-contained Jupyter notebook that you can read, run, and adapt to your own documents
and models.

The repository contrasts two complementary approaches:

| Example | Technique | Best for | LLM / Backend |
| ------- | --------- | -------- | ------------- |
| [GraphRAG](./GraphRAG%20Example) | Property-graph knowledge index | Complex, **multi-hop** questions that connect facts across documents | OpenAI |
| [Simple Vector Index](./Simple%20Vector%20Index%20Example) | Dense vector retrieval | Straightforward semantic search / Q&A over documents | Groq + Hugging Face |

---

## Why two examples?

- **GraphRAG** builds a *knowledge graph* over your corpus, so it can reason across
  multiple sources and answer questions that require chaining several facts together
  (multi-hop reasoning). The notebook also builds a baseline vector index side-by-side so
  you can directly compare the two approaches on the same questions.
- **Simple Vector Index** is the classic RAG pipeline: parse documents, embed them,
  store the vectors, and answer questions with an LLM. It is the fastest way to get a
  working RAG system running over your own PDFs.

If you are new to RAG, start with the **Simple Vector Index Example**. If you need to
answer complex questions that span multiple documents, explore the **GraphRAG Example**.

---

## Repository structure

```
llamaindex-rag-examples/
├── GraphRAG Example/              # Graph-based RAG with multi-hop reasoning (OpenAI)
│   ├── data/                      # Sample news corpus (JSON)
│   ├── main.ipynb                 # Walkthrough notebook
│   ├── requirements.txt           # Example-specific dependencies
│   ├── .env.example               # Template for API keys
│   └── README.md
├── Simple Vector Index Example/   # Classic vector RAG (Groq + Hugging Face)
│   ├── data/                      # Sample PDF document
│   ├── main.ipynb                 # Walkthrough notebook
│   ├── requirements.txt           # Example-specific dependencies
│   ├── .env.example               # Template for API keys
│   └── README.md
├── requirements.txt               # Combined dependencies for both examples
├── LICENSE
└── README.md
```

---

## Quick start

Each example is independent and ships with its own `README.md`, `requirements.txt`, and
`.env.example`. In general:

```bash
# 1. Clone the repository
git clone https://github.com/<your-username>/llamaindex-rag-examples.git
cd llamaindex-rag-examples

# 2. Move into the example you want to run
cd "Simple Vector Index Example"      # or: cd "GraphRAG Example"

# 3. Create and activate a virtual environment
python -m venv .venv
source .venv/bin/activate              # On Windows: .venv\Scripts\activate

# 4. Install dependencies
pip install -r requirements.txt

# 5. Configure your API keys
cp .env.example .env                   # then edit .env

# 6. Launch Jupyter and open main.ipynb
jupyter notebook
```

See each example's `README.md` for the exact API keys it requires.

---

## Requirements

- Python **3.11+**
- A Jupyter environment (`jupyter notebook` or `jupyter lab`)
- API keys depending on the example:
  - **GraphRAG Example** — an OpenAI API key
  - **Simple Vector Index Example** — a Groq API key, a LlamaIndex Cloud (LlamaParse) key, and a Hugging Face token

---

## Author

Written and developed by **Amin Amiri**.

## License

Released under the [MIT License](./LICENSE). © 2026 Amin Amiri.
