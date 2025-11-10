# LegalClauseSimilarity_DL

Implementation of BiLSTM and Attention-based Encoder models for detecting semantic similarity in legal text datasets.

---

## 📘 Project Overview
This project was developed as part of **Deep Learning Assignment 2 (CS-452)** at **FAST-NUCES Islamabad**.  
The goal is to identify semantic similarity between legal clauses — determining whether two clauses express the same or closely related meanings, even if worded differently.

---

## 🧠 Models Implemented
Two baseline deep learning architectures were trained from scratch (no pre-trained transformers):

1. **BiLSTM (Bidirectional LSTM)**  
   - Captures sequential dependencies and bidirectional context.
   - Performs well for structured, formal language such as legal text.

2. **Attention-Based Encoder**  
   - Focuses on the most important tokens in a sentence.
   - Lightweight and faster to train.

Both models use an embedding layer, are trained on the same dataset, and evaluated using multiple NLP metrics.

---

## 🧹 Dataset
- **Source:** [Kaggle – Legal Clause Dataset](https://www.kaggle.com/datasets/bahushruth/legalclausedataset)  
- Each CSV file represents a distinct clause category (e.g., *acceleration*, *bank-accounts*, *confidentiality*).  
- Only 40 % of each file was loaded to prevent RAM overflow in Colab.  
- Total samples used: ~60 000 clauses.  
- Split: **80 % training**, **20 % testing**.  

---

## ⚙️ Pre-Processing Steps
- Tokenization using Keras `Tokenizer` (vocabulary size = 10 000).  
- Sequence padding/truncation to 100 tokens.  
- Label encoding of clause categories.  
- Early stopping to avoid overfitting.

---

## 📊 Evaluation Metrics
| Metric | Description |
|---------|--------------|
| **Accuracy** | Overall classification correctness |
| **Precision** | Correct positive predictions |
| **Recall** | Ability to find all relevant clauses |
| **F1-Score** | Balance between precision and recall |
| **ROC-AUC** | Class separation capability |
| **Confusion Matrix** | Visual performance per class |

---

## 🧾 Results Summary
| Model | Accuracy | Precision | Recall | F1-Score | ROC-AUC |
|--------|-----------|------------|----------|-----------|----------|
| **BiLSTM** | 0.7224 | 0.7318 | 0.6986 | 0.7007 | 0.9865 |
| **Attention Encoder** | 0.6038 | 0.5848 | 0.5838 | 0.5702 | 0.9844 |

**Observation:**  
The BiLSTM achieved higher accuracy and recall, showing stronger performance on legal clause semantics.

---


## 🧩 Tools & Environment
- **Language:** Python 3.10+  
- **Frameworks:** TensorFlow / Keras  
- **Environment:** Google Colab (T4 GPU)  
- **Libraries:** Pandas, NumPy, scikit-learn, Matplotlib  

