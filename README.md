# AraSafe: Benchmarking Safety in Arabic LLMs

This repository contains the datasets released with the EMNLP 2025 paper
**AraSafe: Benchmarking Safety in Arabic LLMs**.

AraSafe is the first large-scale, **native Arabic safety benchmark** designed to evaluate and improve the safety of Arabic large language models (LLMs). It combines real human-written prompts with high-quality synthetic examples to reveal and mitigate safety blind spots in Arabic NLP systems.

---

## Contents

### 1. Human-Written Safety Benchmark

* **Size:** ~12,000 naturally occurring Arabic prompts
* **Coverage:** Modern Standard Arabic and multiple Arabic dialects
* **Annotation:** Two expert annotators independently labeled each prompt as *Safe* or as one of **eight fine-grained harmful categories**:

  * Illegal Activities
  * Violence or Harm
  * Privacy Violation
  * Terrorism or Extremism
  * Hate Speech
  * Explicit Content
  * Misinformation
  * Other Harmful Content

* **Format:** JSONL with prompt text and final label.

### 2. Synthetic Harmful Prompts

* **Size:** ~12,000 prompts
* **Source:** Generated with GPT-4o to complement the human-written data and enhance representation of rare or high-severity harmful content.
* **Format:** JSONL with prompt text and category label.

---

## Getting Started

Clone the repository:

```bash
git clone https://github.com/qcri/AraSafe-dataset.git
cd AraSafe-dataset
```

Directory structure:

```
AraSafe-dataset/
│
├─ human_written/      # 12K gold-annotated prompts
└─ synthetic/          # 12K GPT-4o–generated harmful prompts
```

---

## Usage Example

Load the data in Python:

```python
import json

with open('human_written/arasafe_natural_prompts.jsonl', 'r', encoding='utf-8') as f:
    human_prompts = [json.loads(line) for line in f]

with open('synthetic/arasafe_synthetic_prompts.jsonl', 'r', encoding='utf-8') as f:
    synthetic_prompts = [json.loads(line) for line in f]
```

You can then train classifiers, evaluate Arabic LLMs, or perform safety analyses using these datasets.

---

## Citation

If you use AraSafe in your research, please cite:

```
@inproceedings{mubarak2025arasafe,
  title     = {AraSafe: Benchmarking Safety in Arabic LLMs},
  author    = {Mubarak, Hamdy and Mohamed, Abubakr and Hawasly, Majd},
  booktitle = {Proceedings of the 2025 Conference on Empirical Methods in Natural Language Processing},
  year      = {2025}
}
```
