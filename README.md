# Sentence-Level Text Reuse in Multilingual Journalism

This repository accompanies a paper accepted to the SoCon-NLPSI 2026 workshop, co-located with LREC 2026. The work, titled “Rewrite the News: Tracing Editorial Reuse Across News Agencies,” investigates sentence-level text reuse in multilingual newswire workflows. It introduces a weakly supervised framework for detecting content reuse between English-language articles from the national press organization STA (Slovenian News Agency) and 15 Foreign Agencies across 7 languages.

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

```

## 📄 File Descriptions

| File | Description |
|------|-------------|
| `x_full_data.json` | The core aligned dataset containing sentence-level reuse instances between STA (Slovenian News Agency) and foreign agencies. Includes language, article IDs, sentence indices, and reuse labels. |
| `wiki_test_corpus_full.json` | A clean multilingual test set of Wikipedia article sentences used for evaluating paraphrase detection baselines. |
| `Webis-CPC-11_1000_sample.json` | A 1,000-example subset from the Webis Cross-lingual Paraphrase Corpus, used for benchmarking under noisy, multilingual conditions. |
| `similarity_approach.ipynb` | Main notebook for computing similarity scores using embedding-based model like Sentence-BERT. |
| `experiment_with_wiki_corpus.ipynb` | Evaluation using high-quality Wikipedia data to establish baseline performance. |
| `experiment_with_webis_paraphrase_corpus.ipynb` | Robustness evaluation on real-world paraphrases from noisy web sources. |
| `preprocessing.ipynb` | Data preparation pipeline: article filtering, sentence segmentation, alignment prep, and cleaning. |
---
## 📄 `x_full_data.json` Schema

Each entry in `x_full_data.json` represents a sentence with metadata. Fields include:

| Field | Description |
|-------|-------------|
| `sen_id` | Unique identifier for the sentence (UUID). |
| `article_id` | ID of the source article. |
| `seq_nr` | Sentence position in the article. |
| `lang` | Language of the sentence (e.g., `en`, `sl`). |
| `text` | Raw sentence text. |
| `reused` | Binary reuse label (1 = reused in foreign article, 0 = not reused). |
| `partner_id` | ID of the foreign article with reused content (if applicable). |
| `partner_sentence_id` | ID of the matched sentence in the foreign article (if applicable). |

---
## DISCLAIMER:

The data provided is intended solely for research and academic purposes. Any use of this data for commercial purposes, including but not limited to marketing, product development, or resale, is strictly prohibited. By accessing or using this data, you agree to abide by these terms and acknowledge that any unauthorized commercial use may result in legal action.
