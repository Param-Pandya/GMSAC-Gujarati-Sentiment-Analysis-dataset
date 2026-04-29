# GMSAC: A Large-Scale Gujarati Multi-Domain Sentiment Analysis Dataset

---

## Dataset Description

GMSAC (Gujarati Multi-domain Sentiment Analysis Corpus) is a large-scale, manually annotated dataset designed for sentiment classification in Gujarati, a low-resource and morphologically rich language.

The dataset contains 16,998 text samples collected from multiple social media platforms, including Twitter, YouTube, and Reddit. Each sample is labeled into one of three sentiment categories: positive, neutral, or negative.

The dataset is designed to support research in Gujarati NLP and provide a strong benchmark for sentiment analysis tasks.

---

## Value of the Data

- Addresses the lack of large-scale Gujarati sentiment datasets
- Supports both classical machine learning and transformer-based models
- Captures real-world linguistic diversity, including informal and code-mixed text
- Provides high annotation reliability (Fleiss’ Kappa = 0.897)
- Enables benchmarking for low-resource language research

---

## Data Specifications

- Dataset Name: GMSAC
- Language: Gujarati
- Total Samples: 16,998
- Domains: Twitter, YouTube, Reddit
- Annotation Type: Manual
- Labels: Positive, Neutral, Negative
- Annotation Agreement: Fleiss’ Kappa = 0.897
- Format: CSV
- Encoding: UTF-8

---

## Dataset Structure

dataset/
├── train.csv   (70%)
├── val.csv     (10%)
├── test.csv    (20%)

Each file contains:

- text: Gujarati text sample
- label: sentiment category (positive / neutral / negative)

---

## Class Distribution

- Positive: 6,040 (35.53%)
- Neutral: 5,887 (34.63%)
- Negative: 5,071 (29.83%)

The dataset is relatively well-balanced, which helps reduce bias during model training.

---

## Experimental Design, Materials and Methods

### Data Collection

Data was collected from the following platforms:
- Twitter
- YouTube
- Reddit

These sources were selected to capture diverse linguistic patterns, including informal and real-world user-generated content.

---

### Data Preprocessing

The following preprocessing steps were applied:

- Removal of URLs, mentions, and special characters
- Text normalization and whitespace cleaning
- Removal of duplicate and very short samples
- Unicode normalization (encoding correction)
- Removal of irrelevant trailing English tokens

---

### Annotation Procedure

- Manual annotation into:
  - Positive
  - Neutral
  - Negative

- Annotation considered:
  - Context and semantics
  - Sarcasm and ambiguity
  - Informal language usage

- Annotation quality:
  - Fleiss’ Kappa = 0.897 (near-perfect agreement)

---

### Data Splitting

- Training: 70%
- Validation: 10%
- Testing: 20%

This split ensures robust model training and unbiased evaluation.

---

## Benchmark Results

### Classical Machine Learning Models (Macro F1)

- Naive Bayes: ~0.73
- Logistic Regression: ~0.79
- SVM: ~0.79
- Random Forest: ~0.79

---

### Transformer-Based Models (Macro F1)

- mBERT: 0.8662
- XLM-RoBERTa: 0.8896
- XLM-T: 0.8890
- GujaratiBERT: 0.8935
- IndicBERTv2: 0.9007

Transformer-based models significantly outperform classical approaches.

---

## Data Characteristics

- Multi-domain dataset
- Contains code-mixed Gujarati-English text
- Includes informal and colloquial language
- Reflects real-world sentiment usage
- Suitable for both ML and deep learning models

---

## Limitations

- Primarily based on social media data (domain bias)
- Contains noisy and code-mixed text
- Smaller compared to datasets for high-resource languages

---

## Future Work

- Expand dataset to additional domains (news, reviews)
- Introduce aspect-based sentiment annotations
- Explore cross-lingual and multilingual approaches
- Extend to multimodal sentiment analysis

---

## Ethical Considerations

- Data collected from publicly available sources
- No personally identifiable information intentionally included
- Intended for research purposes only

---

## Usage Example

```python
import pandas as pd

df = pd.read_csv("train.csv")
print(df.head())
