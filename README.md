# Applied AI

Small, runnable demonstrations of applied artificial intelligence concepts.

## RAG notebook

[`rag.ipynb`](rag.ipynb) builds a local retrieval-augmented generation pipeline over Shakespeare's works. It covers:

1. text cleaning and document construction;
2. overlapping chunk generation;
3. sentence-transformer embeddings and a FAISS index;
4. semantic retrieval and prompt assembly; and
5. local generation with Ollama and `llama3:8b`.

The final question is intentionally out of domain, making it useful for examining whether the system follows its supplied context rather than inventing an answer.

## Run locally

The notebook was written for macOS and expects Python, Jupyter, and [Ollama](https://ollama.com/).

```bash
brew install ollama
brew services start ollama
ollama pull llama3:8b
python -m venv .venv
source .venv/bin/activate
python -m pip install jupyter faiss-cpu sentence-transformers ollama numpy
jupyter lab rag.ipynb
```

Place a UTF-8 copy of Shakespeare's complete works at `data/shakespeare.txt` before running the data-preparation cells. Review the source's license and terms before redistributing it.

## Scope

This is an educational prototype, not a production RAG service. It does not yet include automated evaluation, persistent indexing, prompt-injection defenses, or deployment hardening.
