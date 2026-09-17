# Third-Party Models and Data

The repository does not commit the model checkpoints or datasets listed below. Runtime downloads use ignored local caches where noted; package-provided images and CDN assets remain in their documented locations. Review the linked provenance, licenses, and terms before reuse or redistribution.

## Transformer sentiment model

`bert-sentiment-inference.ipynb` uses the pinned Hugging Face model [`distilbert/distilbert-base-uncased-finetuned-sst-2-english`](https://huggingface.co/distilbert/distilbert-base-uncased-finetuned-sst-2-english) at revision `714eb0fa89d2f80546fda750413ed43d93601a13`. The model card describes its training data, license, intended use, and limitations.

## Ultralytics YOLO

`yolo-object-detection.ipynb` uses the Ultralytics package and the runtime-downloaded `yolo11n.pt` checkpoint. The notebook verifies the checkpoint against SHA-256 `0ebbc80d4a7680d14987a577cd21342b65ecfd94632bd9a8da63ae6417644ee1` before loading it. Ultralytics documents YOLO11 under [AGPL-3.0 and Enterprise licensing options](https://docs.ultralytics.com/models/yolo11/). The checkpoint is deliberately excluded from Git.

The executed notebook embeds annotated versions of three `skimage.data` examples. The [scikit-image data documentation](https://scikit-image.org/docs/stable/api/skimage.data) identifies the astronaut photograph as public domain and the Chelsea cat and coffee photographs as CC0.

## MNIST and CIFAR-10

The MLP and VAE notebooks download [MNIST through torchvision](https://docs.pytorch.org/vision/stable/generated/torchvision.datasets.MNIST.html); original dataset provenance is documented on the [MNIST site](https://yann.lecun.org/exdb/mnist/index.html). The CNN notebook downloads [CIFAR-10 through torchvision](https://docs.pytorch.org/vision/stable/generated/torchvision.datasets.CIFAR10.html); original provenance and citation information are on the [CIFAR-10 site](https://www.cs.toronto.edu/~kriz/cifar.html). Neither dataset is committed.

## Plotly.js

`bias-variance.html` loads Plotly.js 2.30.0 from Plotly's `cdn.plot.ly` CDN. Plotly.js is distributed under the [MIT license](https://github.com/plotly/plotly.js/blob/master/LICENSE).

## Local RAG models

`rag.ipynb` uses [`sentence-transformers/all-MiniLM-L6-v2`](https://huggingface.co/sentence-transformers/all-MiniLM-L6-v2) for embeddings and the `llama3:8b` model served through Ollama. Review the [Ollama model page](https://ollama.com/library/llama3) and the linked [Meta Llama 3 Community License](https://ollama.com/library/llama3/blobs/4fa551d4f938) before downloading or redistributing model files.

## Locally generated material

The Word2Vec, SHAP, shortcut-learning, and bias–variance demonstrations generate their inputs locally. They do not bundle external datasets or pretrained weights.
