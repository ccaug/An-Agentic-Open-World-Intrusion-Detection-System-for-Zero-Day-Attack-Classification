
---

## What changed vs. the original README

| Aspect | Original | NOMS Version |
|--------|----------|--------------|
| **Title** | "An-Agentic-Open-World-Intrusion-Detection-System-for-Zero-Day-Attack-Classification" | "Hierarchical AI-Driven Security Management..." — management framing |
| **Overview** | Component list (ModernBERT, RAG, LLM, FAISS) | Management problem framing + contributions |
| **Framing** | "Agentic IDS" | "Hierarchical security-analysis service" |
| **Key Results** | None | Full metrics table with CIs |
| **Dataset layout** | Not specified | Explicit 4-way partitioning table (critical for reproducibility) |
| **RAG corpus** | 439,873 vectors | 361,141 vectors (correctly excludes UNSW) |
| **Calibration** | Not mentioned | Documented as LOFO + disagreement |
| **Architecture** | Component diagram | Three-plane (Monitoring / Analysis / Management) |
| **Notebook sections** | "Sections 1–26" (generic) | Precise 23-section listing with 8.5/8.6 calibration |
| **HuggingFace** | Not mentioned | Full model reload recipe + file manifest |
| **Ollama setup** | One-line pip install | Complete install with zstd prerequisite |
| **New experiments** | Not documented | Baseline, threshold, trade-off, ablation, workload, edge/cloud |
| **Citation** | None | BibTeX entry |
| **Metrics** | Generic list | Categorized: Classification / Open-World / Management / Statistical |

## To use it

1. **Copy the entire README** into your GitHub repository
2. **Push the trained model** to HuggingFace as `ccaug/Modernbert_Known_Model` (already done — the README references it correctly)
3. **Update the GitHub repo** with the corrected notebook
4. **Add the 12 figures** as a preview in the README if you want a visual index (optional)

The README is now accurate, honest, and framed for the NOMS 2027 audience. Anyone reading it will immediately understand:
- **What problem** the work solves (management of security-analysis resources)
- **How** the framework works (three planes + calibrated policy)
- **What results** it achieves (with confidence intervals)
- **What makes it novel** (calibration without unknowns + selective escalation)
- **How to reproduce** it (dataset partitioning + notebook sections)
