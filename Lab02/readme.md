# Lab 02 · NumPy for Numerical Computing

**Course:** CS-3105 Machine Learning Lab<br>
**Lab Instructor:** Engr. Muhammad Awais

*Use Python programming and tools to perform data handling and basic operations.*

## About this lab

This lab covers the core of NumPy: creating arrays, random numbers, reshaping, indexing and slicing, and vectorised computation on real datasets (Pakistan Census 2023, PMD climate normals, CPI inflation, class marks, and a small image). The rule throughout is **no Python loops where a NumPy function exists**.

## Repository structure

```
ML-Lab-2024-SE-34/
└── Lab02/
    ├── Lab02.ipynb    # completed notebook (all tasks)
    └── README.md      # this file
```

## How to run

1. Open [Google Colab](https://colab.research.google.com) (or Jupyter / VS Code).
2. Upload `Lab02.ipynb`.
3. Run the datasets cell first, then choose **Runtime → Restart and run all**.

Requirements: Python 3, NumPy. (`matplotlib` is optional, only for displaying the image in Task 10.)

---

## Tasks overview

| Task | Topic | Key NumPy functions |
|------|-------|---------------------|
| 1 | Setup | `import numpy as np`, `np.__version__` |
| 2 | Creating arrays | `zeros`, `ones`, `full`, `arange`, `reshape`, `eye` |
| 3 | Randomness and reproducibility | `random.seed`, `rand`, `randn`, `randint`, `unique` |
| 4 | Spacing and reshaping | `linspace`, `reshape`, `sum(axis=1)`, `argmax` |
| 5 | Indexing and slicing (exam hall) | `hall[2:, 1:]`, `sum`, `std` |
| 6 | Census 2023 | boolean masks, `argmax`, growth-rate formula |
| 7 | Climate of five cities | `mean(axis=...)`, `argmax`, `where`, column slicing |
| 8 | Inflation FY2024 vs FY2025 | `mean`, masks, nested `np.where` |
| 9 | Grace marks | `np.clip`, z-score |
| 10 | Image as an array | slicing, `[:, ::-1]`, `255 - img`, `np.clip` |
| 11 | Reflection | written summary |

---

## Key findings

**Census 2023 (Task 6).** Pakistan's total population across the seven units is about 247.5 million. Balochistan grew fastest between 2017 and 2023 (about 3.19 % per year), while AJK grew slowest (about 1.15 % per year), far below the other units.

**Climate (Task 7).** Quetta is the exception among the five cities: only about 6 % of its yearly rain falls in the monsoon (Jul–Sep), while Karachi gets about 74 % and Islamabad receives the most monsoon rain in absolute terms (about 763 mm).

**Inflation (Task 8).** Average year-on-year CPI inflation fell from about 26.2 % in FY2024 to about 4.9 % in FY2025 (Jul–Apr). The monthly drop ranged from about 17 to 26 points, with the biggest in January.

**Grace marks (Task 9).** After 5 grace marks (capped at 100), the pass rate is 90 %. Two students (indices 0 and 6) passed only because of the grace marks.

**Image (Task 10).** The 8 × 8 "7" is drawn with three slices:

```python
img = np.zeros((8, 8), dtype=int)
img[1, 1:7] = 255     # top bar
img[2:7, 5] = 255     # vertical stroke
img[4, 3:7] = 128     # grey crossbar
```

Flip, invert, crop and brighten are each one line of NumPy.

---

## Data sources

- **Census 2023:** Pakistan Bureau of Statistics, 7th Population and Housing Census.
- **Climate:** PMD / WMO 1991–2020 climate normals.
- **Inflation:** Pakistan Economic Survey 2024-25, Chapter 7, Fig 7.1 (PBS CPI, year-on-year %).
- **Marks:** sample lab-section marks.

## Concepts practised

- Vectorisation instead of loops
- Boolean masking and `np.where`
- `axis=0` (down columns) vs `axis=1` (across rows)
- Slicing with `[row, column]`, where the end index is excluded
- Reproducible randomness with `seed`
- Normalisation with z-scores

---

*Submitted for CS-3105 Machine Learning Lab · Lab 02.*
