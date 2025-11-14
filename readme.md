# Fine-Tuning Transformer Models for Sentiment Analysis on Steam Reviews

This repository contains the code and report for the DSA4213 final project **“Fine-Tuning Transformer Models for Sentiment Analysis on Steam Reviews”**. The project systematically compares rule-based, recurrent, and transformer-based approaches for classifying **Steam game reviews** as **positive** or **negative**.

We focus on how different fine-tuning strategies on **DistilBERT** affect performance in an informal, sarcasm-rich domain like gaming reviews.

This is the dataset that we used https://www.kaggle.com/datasets/andrewmvd/steam-reviews

---

## 1. Project Overview

**Goal:**  
Given a Steam review, predict whether the review is **positive (recommended)** or **negative (not recommended)**.

**Key questions:**

- Does **domain-specific fine-tuning** of transformers outperform:
  - General-purpose / zero-shot transformers?
  - Lexicon-based tools like VADER?
  - Classical deep learning models (LSTM + Attention)?

**Main findings (test set):**

- Fully fine-tuned **DistilBERT** achieves the **best performance**:
  - **AP = 0.917**, **F1 = 0.826**, **Accuracy = 0.804**
- **LoRA** reaches **near-equivalent performance** (≈ 98% of F1) while updating only ~1% of parameters.
- Classical **LSTM + Attention** beats the rule-based baseline but is clearly behind transformers.
- **VADER** struggles with slang, sarcasm, and gaming-specific language.

:contentReference[oaicite:0]{index=0}

---

## 2. Repository Structure

A typical layout for this project:

```text
DSA4213-project/
├── project.ipynb
├── DSA4213 Final Project Report.docx
├── data/
│   └── steam_reviews.csv      # (Not included) Balanced 50k Steam review dataset
├── model/
│   └──attention_length.keras
├── .gitignore
├── requirements.txt
└── README.md
