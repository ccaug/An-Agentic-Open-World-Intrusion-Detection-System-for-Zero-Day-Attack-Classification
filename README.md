# Hierarchical AI-Driven Security Management for Open-World Intrusion Detection

A hierarchical framework for detecting known and unknown network attacks. It combines a fine-tuned ModernBERT classifier, a FAISS-based RAG memory, and a calibrated two-signal novelty detector that selectively escalates only borderline samples to lightweight LLM specialist agents.

Target venue: NOMS 2027.

-------------------------------------------------------------------

WHAT IT DOES
-------------------------------------------------------------------

- Classifies nine known attack families
- Detects unknown / zero-day attacks
- Uses a calibrated decision policy to decide how much analysis each event needs
- Escalates only ~7.5% of samples to the LLM pool, saving latency and compute
- Evaluates on real UNSW-NB15 traffic held out of both training and retrieval

-------------------------------------------------------------------

RESULTS
-------------------------------------------------------------------

| Metric                        | Value                    |
|-------------------------------|--------------------------|
| Known attack accuracy         | 97.0%                    |
| Open-world accuracy           | 96.4% (95% CI: 95.1-97.5%) |
| Unknown detection rate        | 100% (500/500)           |
| ROC-AUC                       | 0.9997                   |
| Fast-path latency             | 60.9 ms                  |
| LLM latency                   | 1,636 ms                 |
| Memory footprint              | 2.41 GB                  |
| LLM escalation rate           | 7.5%                     |

-------------------------------------------------------------------

HOW TO RUN
-------------------------------------------------------------------

1. Open the notebook in Google Colab

2. Install dependencies:

   pip install transformers datasets scikit-learn pandas numpy matplotlib \
               seaborn tqdm torch sentence-transformers faiss-cpu psutil \
               scipy statsmodels ollama pyyaml

3. Install Ollama:

   sudo apt-get install -y zstd
   curl -fsSL https://ollama.com/install.sh | sh
   ollama pull llama3.2:1b

4. Run the notebook top-to-bottom

5. Upload the four datasets when prompted

-------------------------------------------------------------------

DATASETS
-------------------------------------------------------------------

| File                          | Role                     |
|-------------------------------|--------------------------|
| training_dataset.csv          | Fine-tune ModernBERT     |
| master_security_dataset.csv   | RAG memory               |
| sample_security_dataset.csv   | RAG memory               |
| UNSW_NB15_testing-set.csv     | Held-out unknown test set|

Note: UNSW is never used for training or RAG. It is used only for
evaluation.

-------------------------------------------------------------------

MODEL
-------------------------------------------------------------------

Trained ModernBERT model on Hugging Face:

https://huggingface.co/ccaug/Modernbert_Known_Model

Load it in a fresh environment:

    from transformers import AutoTokenizer, AutoModelForSequenceClassification

    tokenizer = AutoTokenizer.from_pretrained("ccaug/Modernbert_Known_Model")
    model = AutoModelForSequenceClassification.from_pretrained("ccaug/Modernbert_Known_Model")

-------------------------------------------------------------------

OUTPUT
-------------------------------------------------------------------

All figures, tables, and results are saved to:

    noms2027_outputs/
        figures/
        tables/
        results/
        models/

-------------------------------------------------------------------

PIPELINE SUMMARY
-------------------------------------------------------------------

    Event -> ModernBERT -> Two-Signal Novelty Score
                              |
                              v
                  Calibrated Management Policy
                              |
              +---------------+---------------+
              |               |               |
              v               v               v
         KNOWN ATTACK    BORDERLINE       ZERO-DAY
         (fast path)   (LLM escalation)     alert
