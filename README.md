# An-Agentic-Open-World-Intrusion-Detection-System-for-Zero-Day-Attack-Classification

## Overview

This repository contains a complete implementation of an **Agentic Intrusion Detection System (IDS)** for detecting, classifying, and analyzing both known and unknown network attacks using:

- **ModernBERT embeddings**
- **Prototype-based classification**
- **RAG-enhanced retrieval**
- **LLM specialist agents**
- **FAISS vector databases**
- **OOD-aware orchestration**
- **Novel attack detection and classification**

The system combines traditional embedding-based classification with a multi-agent architecture capable of reasoning over unknown attack behaviors using Retrieval-Augmented Generation (RAG) and LLM-based specialist agents.

This implementation was designed for advanced cybersecurity research and evaluation in **CNCC / LatinCom-style academic environments**.

---

## Key Features

### Core IDS Components

- **ModernBERT Fine-Tuning**
  - Trained on known attack classes
  - Embedding-based semantic classification
  - GPU-accelerated inference

- **OOD-Aware Detection**
  - Prototype similarity analysis
  - Confidence thresholding
  - Unknown attack rejection
  - Novel attack detection pipeline

- **FAISS Vector Databases**
  - Fast nearest-neighbor retrieval
  - RAG-based contextual similarity
  - Semantic memory for unknown attacks

- **Multi-Agent LLM Architecture**
  - Specialist agents for attack reasoning
  - LLM-enhanced attack classification
  - Coordinated orchestration system

- **Master Orchestrator**
  - Decision fusion engine
  - Dynamic routing between detectors
  - OOD-aware reasoning workflow

---

## Advanced Contributions

### Novel Attack Classification

The system supports:

- Detection of unseen attacks
- Semantic clustering of unknown behaviors
- LLM-assisted reasoning for attack attribution
- Classification of novel attacks into semantic categories

### Research-Oriented Evaluation

Includes:

- Comprehensive metrics evaluation
- ROC curve analysis
- Calibration analysis
- Confidence distribution analysis
- Confusion matrices
- Baseline comparisons
- Method distribution statistics

### Explainable Security Analysis

The framework provides:

- Similarity scores
- Confidence estimation
- Retrieval evidence
- LLM reasoning outputs
- Attack categorization explanations

---

## System Architecture

```text
Input Network Log
        ↓
ModernBERT Encoder
        ↓
Embedding Generation
        ↓
┌──────────────────────────────────────────────┐
│          OOD Detection Layer                 │
│  - Prototype Similarity                      │
│  - Confidence Thresholds                     │
│  - Novelty Estimation                        │
└──────────────────────────────────────────────┘
        ↓
 ┌───────────────┴────────────────┐
 ↓                                ↓
Known Attack                Unknown / Novel
Classification              Attack Detection
 ↓                                ↓
Direct Output              RAG Retrieval
                                    ↓
                           LLM Specialist Agents
                                    ↓
                           Master Orchestrator
                                    ↓
                        Final Attack Classification
```

---

## Notebook Structure

### Core Sections

| Section | Description |
|---|---|
| Section 1 | Imports and initial setup |
| Section 2 | Baseline detector implementations |
| Section 3 | Dataset loading and preprocessing |
| Section 4 | ModernBERT training on known attacks |
| Section 5 | Unknown dataset loading |
| Section 6 | FAISS RAG database construction |
| Section 7 | LLM specialist agents |
| Section 8 | Master orchestrator |
| Section 9 | Novel attack generation |
| Section 10 | Comprehensive evaluation |

### Advanced Analysis Sections

| Section | Description |
|---|---|
| Section 11 | Novel attack detection analysis |
| Section 12 | Baseline comparisons |
| Section 13 | Known attack confusion matrix |
| Section 14 | ROC curve analysis |
| Section 15 | Method distribution statistics |
| Section 16 | Confidence distribution |
| Section 17 | Calibration analysis |
| Section 18 | Final summary and export |

### Unknown Attack Classification Pipeline

| Section | Description |
|---|---|
| Section 19 | Specific unknown attack classification |
| Section 20 | Enhanced master orchestrator |
| Section 21 | Quick unknown attack testing |
| Section 22 | Batch unknown attack classification |
| Section 23 | Classification confusion matrices |
| Section 24 | Visualization and breakdown analysis |
| Section 25 | Unknown attack visualization |
| Section 26 | Final unknown attack summary |

---

## Dataset Requirements

The notebook expects multiple datasets containing network logs and attack labels.

### Expected Format

```csv
Log,Attack Type
"network log entry","Attack Name"
```

### Known Attack Training Dataset

Used for:

- Fine-tuning ModernBERT
- Prototype generation
- Known attack classification

### Unknown Attack Datasets

Used for:

- OOD evaluation
- RAG database construction
- Novel attack classification
- Semantic retrieval testing

---

## Installation

Install required dependencies:

```python
!pip install faiss-cpu sentence-transformers transformers datasets \
scikit-learn torch pandas numpy matplotlib seaborn tqdm \
psutil gputil ollama
```

---

## Technologies Used

### Machine Learning

- ModernBERT
- Sentence Transformers
- Prototype-based classification
- Cosine similarity scoring

### Vector Retrieval

- FAISS
- Dense embeddings
- Semantic nearest-neighbor search

### LLM & RAG

- Ollama
- RAG pipelines
- Multi-agent orchestration
- Retrieval-enhanced reasoning

### Visualization & Evaluation

- Matplotlib
- Seaborn
- ROC analysis
- Calibration curves
- Confusion matrices

---

## Evaluation Metrics

### Classification Metrics

- Accuracy
- Precision
- Recall
- F1-score
- Macro F1
- Weighted F1

### OOD Metrics

- Unknown detection accuracy
- False acceptance rate
- False rejection rate
- Novelty detection performance

### Calibration Metrics

- Confidence distributions
- Calibration curves
- Reliability analysis

---

## Output Files

### Evaluation Outputs

| File | Description |
|---|---|
| `evaluation_results.csv` | Complete evaluation metrics |
| `confusion_matrix.png` | Confusion matrix visualization |
| `roc_curves.png` | ROC curve analysis |
| `confidence_distribution.png` | Confidence analysis |
| `calibration_curve.png` | Calibration evaluation |
| `method_distribution.png` | Detection method statistics |

### Unknown Attack Outputs

| File | Description |
|---|---|
| `unknown_attack_results.csv` | Unknown classification outputs |
| `novel_attack_analysis.csv` | Novel attack detection results |
| `rag_retrieval_results.csv` | Retrieval evidence |
| `enhanced_classification_results.csv` | LLM-enhanced predictions |

---

## Usage

Run the notebook sequentially:

1. Install dependencies
2. Upload datasets
3. Train ModernBERT
4. Build FAISS databases
5. Initialize LLM agents
6. Run orchestrator
7. Evaluate IDS performance
8. Analyze unknown attacks
9. Export visualizations and reports

---

## Example Workflow

```text
Known Attack
→ ModernBERT Classification
→ Confidence Validation
→ Final Prediction

Unknown Attack
→ OOD Detection
→ FAISS Retrieval
→ LLM Specialist Analysis
→ Master Orchestrator
→ Semantic Attack Classification
```

---

## Research Contributions

This implementation contributes:

- OOD-aware intrusion detection
- Multi-agent cybersecurity reasoning
- RAG-enhanced IDS pipelines
- LLM-assisted novel attack classification
- Hybrid embedding + agentic security architectures

---

## Acknowledgments

- Hugging Face Transformers
- FAISS similarity search library
- Ollama LLM framework
- ModernBERT models
- Open-source cybersecurity datasets
