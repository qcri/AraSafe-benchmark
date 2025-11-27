# AraSafe: Benchmarking Safety in Arabic LLMs

[![Paper](https://img.shields.io/badge/Check_Out_The%20Paper-blue?logo=data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSI2OCIgaGVpZ2h0PSI0NiIgdmVyc2lvbj0iMS4wIj48cGF0aCBkPSJNNDEuOTc4IDB2My4wMTZIMFY0Nmg2OFYzMC45OTRINTYuOTg4VjBoLTE1LjAxek0xNS4wMSAxNy45ODZoMjYuOTY4djEzLjAwOEgxNS4wMVYxNy45ODZ6IiBzdHlsZT0iZmlsbDojZWQxYzI0O2ZpbGwtb3BhY2l0eToxO2ZpbGwtcnVsZTpldmVub2RkO3N0cm9rZTpub25lO3N0cm9rZS13aWR0aDoxMi44OTU0MTE0OTtzdHJva2UtbGluZWNhcDpidXR0O3N0cm9rZS1saW5lam9pbjptaXRlcjtzdHJva2UtbWl0ZXJsaW1pdDo0O3N0cm9rZS1kYXNoYXJyYXk6bm9uZTtzdHJva2UtZGFzaG9mZnNldDowO3N0cm9rZS1vcGFjaXR5OjEiLz48L3N2Zz4=)](https://aclanthology.org/2025.findings-emnlp.529/)

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
cd AraSafe-benchmark
```

Directory structure:

```
AraSafe-benchmark/
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
