# Sentence-Level Text Reuse in Multilingual Journalism

This repository accompanies a submission to EMNLP 2025 (under anonymity) that investigates sentence-level text reuse in multilingual newswire workflows. The study introduces a weakly supervised framework that detects content reuse between English-language articles from a national press organization, **X News Agency (XNA)**, and 15 **Foreign Agencies** in 7 languages.

---

## 📝 Project Overview

This work addresses the following research questions:

1. **Where in the article is reuse most likely to occur?**
2. **Which parts of foreign articles are most frequently reused?**
3. **How is content merged from multiple foreign sources?**

Our findings suggest that reused content is most often found in the middle or end of news articles, with many-to-many and paraphrased alignments being dominant. These insights contribute to understanding journalistic workflows and content transformation across languages.

---

## 📁 Repository Structure


```bash
project-root/
├── preprocessing.ipynb
├── experiment_with_wiki_corpus.ipynb
├── experiment_with_webis_paraphrase_corpus.ipynb
├── similarity_approach.ipynb
├── data/
│   ├── Webis-CPC-11_1000_sample.json
│   ├── wiki_test_corpus_full.json
│   ├── x_full_data.json

---
