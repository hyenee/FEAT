# 📚 FEAT: A Preference Feedback Dataset through a Cost-Effective Auto-Generation and Labeling Framework for English AI Tutoring

Teacher Feedback Preference Datasets for English AI Tutoring

Welcome to the official release of the **DIRECT** family of preference datasets! 🎉

These resources support research on learning‑to‑rank, preference learning, and feedback generation for intelligent tutoring systems.

---

## ✨ Key Features

* **Pairwise preference triples** `(prompt, chosen, rejected)` ready for RLHF‑style fine‑tuning.
* **Dual‑variant design** for *both* datasets:

  1. **base** – the canonical preference set built *within* each dialogue context.
  2. **mixed** – a harder set that pairs a *chosen* feedback from a different context as the `rejected` sample, encouraging cross‑context discrimination.
* **Criteria‑aware splits** – choose between **2‑criteria** (*Correct & Revealing*) and **5‑criteria** (*Correct, Revealing, Guidance, Diagnostic, Encouragement*) versions.
* **Simple JSON** format & clean train/test splits for painless loading.


> **📢 Note — DIRECT‑Manual (DIRECT-M):**
> 
> The **DIRECT‑M** is hosted in a separate repository:
> 
> **[https://github.com/DIRECTDataset/DIRECTManual](https://github.com/DIRECTDataset/DIRECTManual)**.
>
---

## 📦 Repository Structure

```text
datasets/
├── DIRECT-G/            
│   ├── base/
│   │   ├── train.criteria_2.json
│   │   ├── train.criteria_5.json
│   │   ├── test.criteria_2.json
│   │   └── test.criteria_5.json
│   └── mixed/
│       ├── train.criteria_2.json
│       ├── train.criteria_5.json
│       ├── test.criteria_2.json
│       └── test.criteria_5.json
└── DIRECT-M/   ← see: https://github.com/DIRECTDataset/DIRECTManual

```

Each JSON line follows:

```json
{
  "prompt": "<story>",
  "chosen": "<w/ criteria feedback>",
  "rejected": "<w/o criteria feedback>"
}
```

## 📝 File‑naming Convention

`<split>.criteria_<k>.json`

* **split** ∈ {`train`, `test`}
* **k** = `2` or `5` → number of feedback criteria:

  * **2** → *Correct* & *Revealing* only.
  * **5** → *Correct, Revealing, Guidance, Diagnostic, Encouragement*.

Example filenames: `train.criteria_2.json`, `test.criteria_5.json`.

---


## 📊 Dataset Size (pairs)

| Dataset  | Variant | Train   | Test  | 
| -------- | ------- | ------- | ----- | 
| DIRECT‑G | base    | 3,996   | 444   |
| DIRECT‑G | mixed   | 7,992   | 888   | 

---

## 📜 License

All files are released under the Creative Commons Attribution 4.0 International (CC BY 4.0) license unless stated otherwise.  🆓

---

## 📰 Citation

If you use DIRECT‑M or DIRECT‑G, please cite:

```bibtex
@inproceedings{seo2025feat,
  title     = {FEAT: A Preference Feedback Dataset through a Cost‑Effective Auto‑Generation and Labeling Framework for English AI Tutoring},
  author    = {Seo, Hyein and Hwang, Taewook and Lee, Yohan and Jung, Sangkeun},
  year      = {2025},
  booktitle = {Proceedings of the ACL}
}
```

