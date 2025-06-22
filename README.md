# Zero-Shot Named Entity Recognition (NER)

This repository presents a comprehensive, reproducible comparison of three state-of-the-art models for **zero-shot Named Entity Recognition (NER)**:

- **GPT-4o mini** (OpenAI, 2024)  
- **GLiNER** (Zaratiana et al., 2023)  
- **DistilBERT-NER** (Hugging Face)

## Overview

NER is a critical task in NLP that identifies and classifies named entities into categories such as person, organization, or location. In zero-shot learning, models must perform this task without being trained on labeled examples from the specific domain or dataset.

This project implements a standardized and reproducible pipeline to compare model performance in zero-shot settings using precision, recall, and F1 score as evaluation metrics.

## Models Compared

| Model          | Description                                                                          |
|----------------|--------------------------------------------------------------------------------------|
| GPT-4o mini    | Lightweight variant of GPT-4o; evaluated via OpenAI API using structured prompting   |
| GLiNER         | Span-based zero-shot NER model using BERT-like transformers with entity descriptions |
| DistilBERT-NER | Fine-tuned on CoNLL 2003; used as a strong baseline model for comparison             |

## Datasets Used

| Dataset       | Domain                  | Entity Types | Tagging Scheme |
|---------------|--------------------------|---------------|-----------------|
| CoNLL 2003    | News articles            | 4             | BIO             |
| WNUT 2017     | Social media posts       | 6             | BIO             |
| OntoNotes 5.0 | News, blogs, dialogue    | 18            | BIO             |

All datasets are accessed via the Hugging Face `datasets` library and undergo standardized pre-processing including tokenization and label alignment.


## How to Run

```bash
# Clone the repository
git clone https://github.com/yourusername/zero-shot-ner-comparison.git
cd zero-shot-ner-comparison

# Install dependencies
pip install datasets transformers scikit-learn gliner gliner-spacy openai

# Run experiments
jupyter notebook "Zero-shot Named Entity Recognition (NER)_CoNLL_final.ipynb"
