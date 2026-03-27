# Overfitting How to Detect and Fix It


[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Python 3.8+](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/)
[![scikit-learn](https://img.shields.io/badge/scikit--learn-1.x-orange.svg)](https://scikit-learn.org/)

---

## Overview

There is exactly one signal for overfitting: the gap between training performance and held-out performance. This tutorial treats overfitting as a **diagnostic problem** how to measure the gap, how to distinguish it from underfitting, and which of the five standard fixes to apply first.

**Datasets:** UCI Digits (1,797 images, 10 classes) + Wisconsin Breast Cancer (569 samples)  
**Technique:** Overfitting detection, diagnosis, and five standard fixes  
**Difficulty:** Advanced includes bias-variance decomposition

---

## What You Will Learn

- The **three regimes**: underfitting, good fit, overfitting and how to tell them apart
- How to plot and interpret **learning curves** (does more data help?)
- How to plot and interpret **validation curves** (is the model too complex?)
- The **bias-variance decomposition**: Expected error = Bias² + Variance + Irreducible noise
- **Five fixes in order**: more data → reduce complexity → regularisation → early stopping → cross-validation
- Real-world results on **UCI Digits** and **Wisconsin Breast Cancer**

---

## Repository Contents

```
overfitting-tutorial/
├── overfitting_tutorial.ipynb   ← Full Jupyter notebook (runnable)
├── Overfitting_Tutorial.docx    ← Tutorial document (Word)
├── figures_of/                  ← All generated figures (PNG, 180 dpi)
│   ├── fig1_three_regimes.png
│   ├── fig2_learning_validation_curves.png
│   ├── fig3_five_fixes.png
│   ├── fig4_bias_variance.png
│   └── fig5_diagnostic_flowchart.png
├── README.md
└── LICENSE
```

---

## Quick Start

```bash
git clone https://github.com/yourusername/overfitting-tutorial.git
cd overfitting-tutorial
pip install numpy matplotlib scikit-learn notebook
jupyter notebook overfitting_tutorial.ipynb
```

Run all cells in order. All figures saved to `figures_of/`. Expected runtime: ~2 minutes.

---

## Key Results

| Configuration | Train accuracy | CV accuracy | Gap |
|---|---|---|---|
| Overfit (depth=∞) | ~100% | ~95% | ~5% 🔴 |
| depth=5 | ~99% | ~96% | ~3% 🟡 |
| min_leaf=5 | ~98% | ~96% | ~2.3% 🟡 |
| n_est=20 ensemble | ~99% | ~96% | ~3% 🟡 |
| Best combo (RF tuned) | ~98% | ~96% | ~2% 🟢 |

**Key insight:** Limiting depth and minimum leaf size closes the gap without reducing test accuracy.

---

## Figures

All figures use the **Okabe-Ito colourblind-safe palette** with both colour and shape/hatch encoding no information conveyed by colour alone.

| Figure | Description |
|--------|-------------|
| Fig 1 | The three regimes — underfit, good fit, overfit on a curve-fitting problem |
| Fig 2 | Learning curve (UCI Digits) + validation curve (max_depth) |
| Fig 3 | Five fixes on Breast Cancer train vs CV accuracy and gap |
| Fig 4 | Bias-variance decomposition stacked plot and train/test error curves |
| Fig 5 | Diagnostic flowchart step-by-step decision guide |

---

## Accessibility

- **Colourblind-safe:** Okabe-Ito palette with hatch patterns for additional encoding
- **Alt-text:** All figures include descriptive alt-text in Word document metadata
- **Screen readers:** Strict H1→H2→H3 heading hierarchy
- **High contrast:** Code blocks >7:1 contrast ratio (WCAG AAA)
- **Plain language:** All maths spelled out in plain English

---

## References

1. Geman et al. (1992) Neural networks and the bias/variance dilemma. https://doi.org/10.1162/neco.1992.4.1.1
2. Hastie, Tibshirani & Friedman (2009) The Elements of Statistical Learning. Springer. https://hastie.su.domains/ElemStatLearn/
3. Domingos (2000) A unified bias-variance decomposition. ICML. https://homes.cs.washington.edu/~pedrod/papers/mlc00a.pdf
4. Srivastava et al. (2014) Dropout. JMLR, 15(56).
5. Bergstra & Bengio (2012) Random search for hyper-parameter optimisation. JMLR. https://www.jmlr.org/papers/v13/bergstra12a.html

---

