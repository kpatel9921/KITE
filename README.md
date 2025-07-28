# KITE
KITE: A Knowledge-Integrated Text–Image Encoder for Multimodal Fake News Detection

KITE (Knowledge-Integrated Text–Image Encoder) is an end-to-end framework for detecting fake news by jointly modeling textual content, visual context, and factual knowledge. It combines RoBERTa and CLIP backbones with a Graph Attention Network over Wikidata facts, then fuses all three modalities in a lightweight cross-modal Transformer, yielding state-of-the-art performance on the GossipCop and PolitiFact benchmarks.

	• Tri-modal Fusion
	Integrates text, image, and knowledge representations within a unified Transformer layer.

	• Knowledge-Aware Encoding
	Builds per-article mini-knowledge graphs from Wikidata and encodes them via a two-layer GAT.

	• End-to-End Fine-tuning
	Selectively unfreezes the last layers of RoBERTa and CLIP for domain adaptation.
 
	• Per-Modality Confidence Scores
	Outputs text, image, and knowledge confidence alongside the final real/fake prediction for interpretability.

	• Focal Loss & Threshold Tuning
	Uses focal loss for imbalanced data and data-driven threshold selection to maximize F1 score.

INSTALLATION

```git clone https://github.com/<your-username>/KITE.git```

Create a virtual environment

```python3 -m venv venv```

```source venv/bin/activate```

Install dependencies

```pip install -r requirements.txt```

```python -m spacy download en_core_web_sm```


DATA PREPARATION

1. Follow instructions at: https://github.com/KaiDMML/FakeNewsNet/

2. Organize under data/gossipcop/ and data/politifact/ as:
   
data/fakenewsnet_dataset/

├── gossipcop/real/

├── gossipcop/fake/

├── politifact/real/

└── politifact/fake/

