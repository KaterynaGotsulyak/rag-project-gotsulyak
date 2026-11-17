# rag-project-gotsulyak

A RAG assistant for beginner programmers that answers questions about the Python language based on the official documentation and cites its sources.

## Scenario

The user is a beginner who knows basic Python syntax and reads English. They ask a question, for example "How do I create a virtual environment?", and get a short answer with references to documentation files. If the documentation has no answer, the system says so explicitly.

## Stack

Python 3.11+, Chroma vector store, BAAI/bge-small-en-v1.5 embedding model (sentence-transformers), Qwen2.5-7B-Instruct generation model via Ollama. Corpus: Python documentation (python/cpython, Doc directory, tag v3.14.10). Stack parameters are stored in `config/config.yaml`.

## Installation

```bash
python3 -m venv .venv
source .venv/bin/activate        # Windows: .venv\Scripts\activate
pip install -r requirements.txt

# Ollama: https://ollama.com/download
ollama pull qwen2.5:7b-instruct
```

## Structure

```
config/       stack configuration
src/
  ingestion/    data ingestion
  embeddings/   embeddings and vector index
  retrieval/    retrieval
  evaluation/   quality evaluation
reports/      lab reports (reports/lab-N/)
```
