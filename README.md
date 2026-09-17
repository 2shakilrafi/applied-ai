# Applied AI

Small, runnable demonstrations of applied artificial intelligence concepts. The notebooks emphasize not only how models work, but also how to test whether they work for the intended reason.

## Demonstrations

### [Shortcut Learning Audit](shortcut-learning-audit.ipynb)

This fully synthetic computer-vision lab shows how a classifier can earn excellent ordinary test accuracy by relying on an accidental corner marker. It then:

1. evaluates the model under random, flipped, and removed-marker shifts;
2. visualizes the learned pixel coefficients as a global sensitivity map;
3. measures a paired counterfactual marker swap; and
4. mitigates the failure by diversifying the training data.

The notebook is deterministic, contains its executed outputs, generates all data locally, and needs no external dataset or pretrained-model download.

```bash
python -m venv .venv
source .venv/bin/activate
python -m pip install -r requirements-shortcut-learning.txt
jupyter lab shortcut-learning-audit.ipynb
```

### [Local RAG over Shakespeare](rag.ipynb)

This notebook builds a transparent retrieval-augmented generation pipeline with overlapping chunks, sentence-transformer embeddings, a FAISS index, evidence previews, grounded prompt construction, and local generation through [Ollama](https://ollama.com/) with `llama3:8b`.

The final question is intentionally out of domain, making it useful for checking whether the model abstains instead of answering from outside knowledge.

```bash
brew install ollama
brew services start ollama
ollama pull llama3:8b
python -m venv .venv
source .venv/bin/activate
python -m pip install jupyter faiss-cpu sentence-transformers ollama numpy
jupyter lab rag.ipynb
```

Place a licensed UTF-8 copy of Shakespeare's complete works at `data/shakespeare.txt` before running the RAG notebook. The `data/` directory is intentionally ignored by Git; review the source's terms before downloading or redistributing it.

## Scope

These are educational prototypes, not production systems. The shortcut-learning notebook uses synthetic data and does not constitute a fairness certification. The RAG notebook does not yet provide a labeled retrieval evaluation, persistent indexing, prompt-injection defenses, or deployment hardening.
