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


    
DATA PREPARATION

1. Follow instructions at: https://github.com/KaiDMML/FakeNewsNet/

2. Organize under data/gossipcop/ and data/politifact/ as:
 ```  
data/fakenewsnet_dataset/
├── gossipcop/real/
├── gossipcop/fake/
├── politifact/real/
└── politifact/fake/
```
3. Run Collection Script (provided in FakeNewsNet GitHub)

```python src/news_content_collection.py --root data/fakenewsnet_dataset --output data/processed_samples.json```



LAUNCH THE NOTEBOOK



 ```jupyter lab``` (in terminal) and run all cells TOP to BOTTOM





RESULTS    
  
After training you should see output similar to: 

```📊 Final PolitiFact Results:
✅ Accuracy:             0.8681
🎯 F1 Score:             0.8894
🔍 Precision:            0.9345
📥 Recall:               0.8788

📖 Avg Text Confidence:  0.5630
🖼️ Avg Image Confidence: 0.5058
📚 Avg KG Confidence:    0.4931

📊 Final GossipCop Results:
✅ Accuracy:             0.8851
🎯 F1 Score:             0.9297
🔍 Precision:            0.9265
📥 Recall:               0.9592

📖 Avg Text Confidence:  0.4319
🖼️ Avg Image Confidence: 0.4414
📚 Avg KG Confidence:    0.4933
```

