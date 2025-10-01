# A:  List of news categories and their abbreviations.

| category                     | abbreviation |
|------------------------------|--------------|
| arts and culture             | AC           |
| business and economy         | BE           |
| health, environment, science | HE           |
| politics                     | PO           |
| sports                       | SP           |


---

# B: Datasets statistics

### Distribution of news articles in the XNA dataset by category
| category | count |
|----------|-------|
| PO       | 648   |
| BE       | 312   |
| AC       | 107   |
| HE       | 103   |

---

### Distribution of news articles in the XNA and FA datasets by year
| dataset | year | count   |
|---------|------|---------|
| XNA     | 2023 | 544     |
| XNA     | 2025 | 749     |
| FA      | 2023 | 120,668 |
| FA      | 2025 | 116,883 |

---

### Distribution of news articles in the FA dataset by language
| language | count  |
|----------|--------|
| Italian  | 84,119 |
| English  | 49,545 |
| Polish   | 26,364 |
| French   | 25,482 |
| German   | 24,353 |
| Serbian  | 18,378 |
| Croatian | 9,310  |

---

# C: Testing of the similarity approach

### Similarity scores for the Webis-Wikipedia-Text-Reuse-18 corpus
| language | full text | different sentences | similar sentences | support |
|----------|-----------|----------------------|------------------|---------|
| English  | 0.72      | 0.37                 | 0.63             | 500     |
| German   | 0.73      | 0.35                 | 0.64             | 99      |
| French   | 0.69      | 0.35                 | 0.59             | 99      |
| Croatian | 0.71      | 0.37                 | 0.63             | 99      |
| Italian  | 0.74      | 0.37                 | 0.69             | 100     |
| Polish   | 0.69      | 0.35                 | 0.63             | 99      |
| Serbian  | 0.72      | 0.37                 | 0.69             | 99      |

---

### Similarity scores for the Webis-CPC-11
| paraphrased | full text | support |
|-------------|-----------|---------|
| no          | 0.78      | 500     |
| yes         | 0.81      | 500     |

---

# D: Alignment Classification

The alignment analysis followed a four-step process:

1. **Filtering**: Only sentence pairs matched with the earliest foreign article were selected to isolate reuse from the earliest known source.  
2. **Frequency Counting**: Each sentence from the XNA and each sentence from the foreign dataset was counted to determine sentence-level reuse frequency.  
3. **Alignment Typing**: Each pair was labeled based on these counts:  
   - `1:1` — both IDs appear once  
   - `1:many` — one XNA sentence maps to multiple FA sentences  
   - `many:1` — multiple XNA sentences map to one FA sentence  
   - `many:many` — reuse on both sides  
4. **Reuse Direction**: Each alignment type was disaggregated by the time match, indicating whether XNA reused FA (`True`) or FA reused XNA (`False`).  

---

# E: Data statistics

### Median number of reused sentences per day according to their position in XNA and foreign datasets
|          | XNA (median) | XNA (std) | FA (median) | FA (std) |
|----------|--------------|-----------|-------------|----------|
| beginning| 2            | 1.23      | 6           | 6.46     |
| middle   | 3            | 2.64      | 4           | 7.2      |
| end      | 2            | 1.45      | 7           | 3.68     |

---

### Reused sentences' alignment by position (FA-XNA)
|          | beginning | middle | end |
|----------|-----------|--------|-----|
| beginning| 31        | 217    | 135 |
| middle   | 130       | 204    | 144 |
| end      | 42        | 72     | 112 |

---

### Number of reused sentences by position in the XNA and FA datasets
|          | XNA | FA  |
|----------|-----|-----|
| beginning| 72  | 383 |
| middle   | 214 | 478 |
| end      | 101 | 226 |

---

### Significance testing for variables
| dataset       | Variable 1          | Variable 2        | Test                                | p-value |
|---------------|---------------------|------------------|-------------------------------------|---------|
| XNA           | position in text    | reused/not reused| χ² test with Monte Carlo simulation | <0.05   |
| XNA and FA    | position in text    | sentence          | χ² test with Monte Carlo simulation | <0.05   |
| FA            | position in text    | reused/not reused| χ² test                             | <0.05   |
| XNA and FA    | position in text XNA| position in text FA| χ² test                           | <0.05   |
