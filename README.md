# Amharic E-commerce Data Extractor

The **Amharic E-commerce Data Extractor** is a Natural Language Processing (NLP) project designed to extract structured information — such as product names, prices, and locations — from Amharic-language messages posted on Telegram e-commerce channels.

---

## Project Goals

- Build a robust pipeline for Amharic e-commerce text processing.
- Annotate product-related entities using BIO tagging (`B-Product`, `I-PRICE`, `B-LOC`, etc.).
- Train a Named Entity Recognition (NER) model to automate information extraction from raw messages.
- Enable future applications like product search, analytics, and recommendation systems.

---

## Dataset & Annotations

- **Source**: Real Telegram messages from Ethiopian e-commerce groups.
- **Size**: Over 200 messages collected; 50 labeled for training.
- **Annotation Format**: BIO tagging in CoNLL format (`labeled_data.conll`).
- **Entities**: Product, Price, and Location (including both beginning and continuation tags).

---




