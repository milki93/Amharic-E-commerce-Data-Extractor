# Amharic E-commerce Vendor Scorecard for FinTech Micro-Lending

## Overview

This project presents a full pipeline for analyzing informal e-commerce vendors in Ethiopia who operate on **Telegram**. It combines **Natural Language Processing (NLP)**, **multilingual NER**, and **business analytics** to support micro-lending decisions for FinTech institutions.

It enables:
- Real-time data scraping and structuring from Telegram channels.
- Training and interpretation of **NER models** to extract key entities from Amharic messages.
- Generation of detailed vendor performance metrics.
- Calculation of a **Lending Scorecard** to rank vendors based on business activity and engagement.

Designed for **FinTech lenders**, the system helps assess digital vendors who lack formal business profiles but demonstrate potential through online engagement.

---

## Project Structure

```bash
Amharic-E-commerce-Data-Extractor/
│
├── data/
│   ├── telegram_data.csv         # Cleaned Telegram posts with metadata
│   └── labeled_data.conll        # CoNLL-annotated dataset for NER training
│
├── notebook/
│   ├── 1_data_scraper.ipynb      # Scrape Telegram messages and metadata
│   ├── 2_data_labeling.ipynb     # Manual entity tagging (CoNLL format)
│   ├── 3_model_training.ipynb    # Fine-tune AfroXLM-R on Amharic NER task
│   ├── 4_model_comparison.ipynb  # Evaluate multiple multilingual models
│   ├── 5_model_interpretability.ipynb  # Explain predictions via SHAP & LIME
│   └── 6_vendor_scorecard.ipynb # Compute vendor metrics and lending score
│
├── models/
│   └── checkpoint-xx/            # Fine-tuned NER model outputs
│
├── vendor_scorecard.csv         # Final ranked scorecard of vendors
└── README.md
```
---

## Features

- **Amharic NER**: Fine-tuned AfroXLM-R to extract `Product`, `Price`, and `Location` from mixed-language Telegram posts.
- **Vendor Analytics Engine**: Automatically computes business metrics per vendor (posts/week, views, prices).
- **Lending Scorecard**: Ranks vendors with a weighted score for lending decisions.
- **Model Explainability**: Visual explanations via SHAP & LIME to validate and trust NER outputs.
- **Modular Colab Notebooks**: Reproducible step-by-step workflow for end-to-end execution.

---

## Project Workflow

- **Telegram Scraper**
A Python script fetches messages, views, and timestamps from selected Amharic e-commerce Telegram channels.

- **Manual Annotation**
A subset of posts is labeled in **CoNLL** format to train the NER model for Amharic.

- **NER Model Training**
The `Davlan/afro-xlmr-base` model is fine-tuned on the custom Amharic data using Hugging Face's **Trainer API**.

- **Model Comparison**
Competing models (e.g., **XLM-R**, **mBERT**) are evaluated for **accuracy**, **speed**, and **robustness**.

- **Interpretability**
**SHAP** and **LIME** are used to explain which tokens influence entity classification most, ensuring transparency and trust.

- **Vendor Scoring**
- scoring engine computes:
- Posting frequency  
- Average views per post  
- Average product price  
- Top-performing product  
- Lending score  

--- 

## Requirements

- Python 3.8+
- PyTorch
- Hugging Face Transformers
- SHAP
- LIME
- Pandas
- NumPy
- Google Colab (recommended for training + GPU)

---

## Future Work

- Expand the labeled dataset for better NER generalization.
- Develop a **domain-specific Amharic tokenizer**.
- Integrate image analysis (e.g., using **CLIP**) to analyze product visuals.
- Deploy the full pipeline on cloud for **real-time vendor scoring**.
- Build a dashboard using **Streamlit** or **Dash** for interactive exploration.
