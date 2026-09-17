# Applied AI

Runnable demonstrations for an applied-AI course. The notebooks pair models and concepts with checks, diagnostics, and limitations so the result is more than a happy-path API call. The interactive HTML explorer uses a fixed seeded simulation.

## Demo catalog

| Demonstration | What it shows | Runtime inputs |
|---|---|---|
| [Bias–Variance Tradeoff Explorer](bias-variance.html) | Interactive polynomial complexity with estimated bias² and variance | Synthetic data; Plotly.js loaded from CDN |
| [MLP MNIST Error Analysis](mlp-mnist-error-analysis.ipynb) | Dense neural network, confusion matrix, and confident mistakes | MNIST download |
| [CNN + Saliency on CIFAR-10](cnn-cifar10-saliency.ipynb) | Trained convolutional model, class errors, and input-gradient saliency | CIFAR-10 download; several CPU minutes |
| [Shortcut Learning Audit](shortcut-learning-audit.ipynb) | Counterfactual tests for a classifier exploiting a spurious corner marker | Fully synthetic |
| [YOLO Object Detection](yolo-object-detection.ipynb) | Inline boxes, detection tables, and confidence-threshold sensitivity | YOLO11n runtime download; public-domain/CC0 images |
| [Variational Autoencoder](variational-autoencoder-mnist.ipynb) | Reconstruction, KL loss, latent clusters, and generated digit manifold | MNIST download |
| [Word2Vec Semantic Geometry](word2vec-semantic-geometry.ipynb) | Skip-gram negative sampling implemented from scratch | Fully synthetic |
| [DistilBERT Sentiment Inference](bert-sentiment-inference.ipynb) | Pinned transformer inference, tokenization, and ambiguous examples | Hugging Face model download |
| [SHAP Model Explanations](shap-model-explanations.ipynb) | Global and local explanations with known signal and noise | Fully synthetic |
| [Local RAG over Shakespeare](rag.ipynb) | Chunking, embeddings, FAISS retrieval, grounding, and local generation | User-supplied text, embedding model, and Ollama |

The seven course-model notebooks listed above contain clean, top-to-bottom executed outputs. Model weights, datasets, webcam captures, and generated training artifacts are not stored in Git. The local RAG notebook is intentionally not executed because it requires a user-supplied corpus and a running Ollama model.

## Run the course demos

```bash
python -m venv .venv
source .venv/bin/activate
python -m pip install -r requirements-course-demos.txt
jupyter lab
```

Open `bias-variance.html` directly in a browser while online so it can load Plotly.js. The Word2Vec and SHAP notebooks run without network access after package installation. BERT, YOLO, MNIST, and CIFAR-10 download their documented runtime assets into ignored `data/` paths.

For the smaller shortcut-learning environment, install `requirements-shortcut-learning.txt` instead.

## Run the local RAG notebook

```bash
python -m venv .venv
source .venv/bin/activate
brew install ollama
brew services start ollama
ollama pull llama3:8b
python -m pip install jupyter faiss-cpu sentence-transformers ollama numpy
jupyter lab rag.ipynb
```

Place a licensed UTF-8 copy of Shakespeare's complete works at `data/shakespeare.txt`. The `data/` directory is intentionally ignored; review the source terms before downloading or redistributing any corpus.

## Reproducibility and scope

- Randomized training notebooks use explicit seeds and executable assertions; the HTML explorer uses fixed seeded simulation.
- Executed notebooks retain plots and bounded result tables so GitHub readers can inspect the outcome without rerunning heavy models.
- See [third-party notices](THIRD_PARTY_NOTICES.md) for runtime model, dataset, image, and licensing links.
- These are educational prototypes, not production or safety-critical systems. Saliency and SHAP describe model behavior rather than causality; confidence is not correctness; and small demonstrations do not establish fairness or deployment readiness.
