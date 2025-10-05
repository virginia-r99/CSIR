# Code-Switching IR Evaluation Repository

This repository contains resources, data, and experiments for **evaluating cross-lingual and code-switching information retrieval (CS-IR)** systems.  
It includes datasets, formal ontologies, evaluation scripts, and result summaries for various embedding and LLM-based retrieval models.

> **Note:** Replace variables with your own values wherever applicable (e.g., repository name, author, contact email, environment names, and file paths).

---

## 📂 Repository Structure

```
|   LICENSE
|   README.md
|   requirements.txt
|
+---code
|   +---data_adaptation
|   |       CS_dataset_adaptation_ES.ipynb
|   |       CS_dataset_adaptation_ZH-ES.ipynb
|   |       CS_dataset_adaptation_ZH.ipynb
|   |
|   \---evaluation
|           CS-IR_EM_Alignment_Evaluation.ipynb
|           CS-IR_EM_Evaluation.ipynb
|           CS-IR_LLM_Evaluation.ipynb
|
+---data
|       docs_subset.jsonl
|       qrels_subset.jsonl
|       queries_subset.jsonl
|
+---formalisation
|       csir-adapt.ttl
|       csir-data.ttl
|       csir-exec.ttl
|       csir-metric.ttl
|       csir-model.ttl
|       csir-scenario.ttl
|       csir-task.ttl
|
\---results
    |   CS-IR_summary_alignment.xlsx
    |   CS-IR_summary_EMs.xlsx
    |   CS-IR_summary_LLMs.xlsx
    |
    +---EM_evaluation_results
    |   ├── Alibaba-NLP__gte-multilingual-base/
    |   ├── intfloat__multilingual-e5-base/
    |   ├── intfloat__multilingual-e5-large/
    |   ├── intfloat__multilingual-e5-small/
    |   ├── jinaai__jina-embeddings-v3/
    |   └── upskyy__bge-m3-korean/
    |
    └---LLM_evaluation_results
        ├── meta-llama__Llama-3.1-8B-Instruct/
        ├── meta-llama__Llama-3.2-1B-Instruct/
        ├── microsoft__Phi-3-mini-4k-instruct/
        ├── Qwen__Qwen2.5-3B-Instruct/
        └── Qwen__Qwen2.5-7B-Instruct/
```

---

## 🧩 Contents Description

### **Root Files**
- **LICENSE** — Open-source license governing use of this repository.  
- **README.md** — This documentation file.  
- **requirements.txt** — Python dependencies required to run the notebooks and scripts.

---

### **`code/`**
Contains the Jupyter notebooks used for data adaptation and evaluation.

#### ▸ `data_adaptation/`
Notebooks for preparing datasets in different languages and code-switching scenarios:
- `CS_dataset_adaptation_ES.ipynb` — Spanish dataset adaptation.
- `CS_dataset_adaptation_ZH.ipynb` — Chinese dataset adaptation.
- `CS_dataset_adaptation_ZH-ES.ipynb` — Mixed Chinese–Spanish adaptation.

#### ▸ `evaluation/`
Evaluation scripts and analysis notebooks:
- `CS-IR_EM_Evaluation.ipynb` — Embedding model evaluation.
- `CS-IR_EM_Alignment_Evaluation.ipynb` — Alignment evaluation across embeddings.
- `CS-IR_LLM_Evaluation.ipynb` — LLM-based evaluation of retrieval performance.

---

### **`data/`**
Contains lightweight subsets of the CS-IR dataset used in experiments:
- `docs_subset.jsonl` — Document collection.
- `qrels_subset.jsonl` — Relevance judgments.
- `queries_subset.jsonl` — Query set.

---

### **`formalisation/`**
Semantic representations (RDF/Turtle) defining the CS-IR formalisation and metadata:
- `csir-adapt.ttl` — Adaptation and preprocessing formalisation.
- `csir-data.ttl` — Dataset description.
- `csir-exec.ttl` — Execution and evaluation process.
- `csir-metric.ttl` — Metrics used for evaluation.
- `csir-model.ttl` — Model specifications.
- `csir-scenario.ttl` — Experimental configurations.
- `csir-task.ttl` — Task and benchmark formalisation.

---

### **`results/`**
Aggregated outputs and evaluation metrics.  
**Note:** This directory includes **all resulting files produced by our executions**, including raw per-query CSVs and aggregated summaries.

#### ▸ Summary files
- `CS-IR_summary_alignment.xlsx` — Alignment results across embedding models.
- `CS-IR_summary_EMs.xlsx` — Summary of embedding model performance.
- `CS-IR_summary_LLMs.xlsx` — Summary of LLM-based evaluation results.

#### ▸ `EM_evaluation_results/`
Detailed CSV evaluation outputs for **embedding models**:  
Each subfolder corresponds to a model (e.g., `intfloat__multilingual-e5-base`), containing multiple datasets:
- `D_ALL_GT3L/` — Combined multilingual dataset.
- `D_en/`, `D_es/`, `D_zh/` — Monolingual datasets for English, Spanish, and Chinese.

Each folder contains per-query evaluation results (e.g., `Q_en.csv`, `Q_es__to__zh.csv`, etc.) covering both monolingual and cross-lingual retrieval.

#### ▸ `LLM_evaluation_results/`
Detailed evaluation results for **large language models** used as retrieval evaluators:  
Each subfolder (e.g., `meta-llama__Llama-3.1-8B-Instruct`, `Qwen__Qwen2.5-7B-Instruct`) contains the same multilingual dataset structure as embedding model results.

---

## ⚙️ Setup & Usage

1. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

2. **Run notebooks**
   Open the notebooks in `code/` and execute sequentially (e.g., data adaptation → embedding evaluation → LLM evaluation).

3. **View results**
   - Summary metrics: see `/results/*.xlsx`
   - Per-model evaluations: explore `/results/EM_evaluation_results/` and `/results/LLM_evaluation_results/`

---

## 📜 License
This repository is distributed under the terms specified in the `LICENSE` file.

---

## 📧 Contact
For questions or collaboration, please open an issue or email **virginia.ramon@upm.es**.  

