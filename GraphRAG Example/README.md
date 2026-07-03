# GraphRAG vs. Baseline RAG: Solving Multi-Hop Reasoning

This example demonstrates **GraphRAG**, an advanced RAG approach that builds a knowledge
graph over a corpus so an LLM can perform **multi-hop reasoning** — answering questions
that require connecting facts across several documents. The notebook builds a GraphRAG
index and a traditional vector RAG index over the same corpus of news articles, then
compares them head-to-head on a set of multi-hop questions.

## What the notebook covers

- Initial setup and a utility for pretty-printing query responses
- Loading and parsing a corpus of articles (`data/corpus_complete.json`)
- Building a **GraphRAG** index with LlamaIndex's `PropertyGraphIndex`
- Building a **traditional vector RAG** index for comparison
- Visualizing the knowledge graph (rendered to `knowledge_graph.html`)
- Running the same questions through both engines and comparing accuracy on multi-hop
  reasoning tasks

## Prerequisites

- Python 3.11+
- An OpenAI API key

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

4. Edit `.env` and add your API key:
   - `OPENAI_API_KEY` — your OpenAI API key

## Running the demo

1. Launch Jupyter and open `main.ipynb`:

   ```bash
   jupyter notebook main.ipynb
   ```

2. Run all cells to see the demo in action.

After the graph index is built, open the generated `knowledge_graph.html` in your browser
to explore the knowledge graph visually.

## Notes

- Building the property graph index issues a number of LLM calls and may take several
  minutes on first run; the index is persisted to `./storage/` and reused afterward.
- A pre-rendered `knowledge_graph_sample.html` is included so you can preview what the
  graph visualization looks like before running the notebook.

---

Written and developed by **Amin Amiri**. Released under the [MIT License](../LICENSE).
