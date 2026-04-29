# Phonological Feature Probing in wav2vec Models

## Overview

This project studies how self-supervised speech models, specifically wav2vec 2.0 and its multilingual variants, encode phonological features across languages. The focus is on features such as voicing and manner of articulation, and whether these are represented in a language-independent way.

---

## Project Goals

* Evaluate how phonological features are encoded in wav2vec representations
* Compare monolingual and multilingual models
* Analyze cross-lingual transfer of phonological features
* Identify which model layers encode phonology most strongly

---

## Background

wav2vec 2.0 is a self-supervised model that learns speech representations directly from raw audio. Multilingual variants such as XLSR-53 and XLS-R extend this approach across multiple languages and enable cross-lingual transfer.

---

## Methodology

### Pipeline

```
Audio → wav2vec → Hidden States → Embeddings
       ↓
Transcription → Phonological Features
       ↓
Linear Classifier → Prediction → Evaluation
```

### Key Components

**Feature Extraction**

* Extract hidden representations from wav2vec models
* Apply mean pooling to obtain fixed-size embeddings

**Phonological Feature Labeling**

* Use a simple grapheme-to-phoneme approximation
* Extract:

  * voicing (voiced / voiceless)
  * manner of articulation (stop, fricative, nasal, etc.)

**Probing**

* Train logistic regression classifiers
* Evaluate whether phonological features are recoverable from embeddings

---

## Experiments

**Cross-Lingual Transfer**

* Train on English
* Test on German and Spanish
* Measures language-independent representations

**Layer Analysis**

* Compare representations across different layers
* Identifies where phonological information is encoded

**Language Comparison**

* Train and test within each language
* Measures language-specific encoding

---



## Dataset

The project uses the FLEURS dataset, a multilingual speech dataset containing audio recordings and transcriptions across many languages.

---


## Usage



---

## Output

* Extracted features: `./extracted_features/*.pkl`
* Experiment results: `experiments_results.csv`

---


## Author

Muhammad Haider
MSc Artificial Intelligence
