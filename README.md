# Single-Cell Hypoxia Classification

**Machine learning on single-cell RNA sequencing (scRNA-seq) data** to distinguish hypoxic from normoxic cells across two human breast cancer cell lines, **MCF7** and **HCC1806**, and two sequencing technologies, **Smart-Seq** and **Drop-Seq**.

## Overview

This project explores how oxygen conditions are reflected in single-cell gene-expression profiles. It combines exploratory data analysis, quality-control investigations, dimensionality reduction, unsupervised learning, and supervised classification.

The original analysis was developed as an academic AI laboratory project. The notebook is provided as a record of the analysis, including its original code and outputs.

## Methodology

- **Data exploration and quality control:** examine count-matrix sparsity, read depth, genes detected per cell, mitochondrial expression, and filtering criteria.
- **Visualization and unsupervised learning:** PCA, UMAP, K-means, and hierarchical clustering to explore cell populations and differences between assay platforms.
- **Supervised learning:** regularized logistic regression and tree ensembles on Smart-Seq data; PCA-based feature selection and multilayer perceptrons on Drop-Seq data.
- **Evaluation:** held-out validation, cross-validation, log-loss, accuracy, learning curves, and permutation tests.

## Results reported in the notebook

| Dataset | Selected approach | Reported validation accuracy |
| --- | --- | ---: |
| MCF7 · Smart-Seq | L2-regularized logistic regression | 100% |
| HCC1806 · Smart-Seq | Calibrated ExtraTrees | 100% |
| MCF7 · Drop-Seq | Tuned multilayer perceptron | ~97% |
| HCC1806 · Drop-Seq | Tuned multilayer perceptron | ~94–95% |

These figures are **reported in the original notebook** and have not been independently reproduced for this repository. Results depend on the supplied dataset and experimental splits; they should not be interpreted as clinical validation.

## Repository structure

```text
single-cell-hypoxia-classification/
├── README.md
├── requirements.txt
├── .gitignore
├── notebooks/
│   └── AI_lab_project.ipynb
└── docs/
    └── AI_lab_project.html
```

The [Jupyter notebook](notebooks/AI_lab_project.ipynb) contains the full analysis. The [HTML export](docs/AI_lab_project.html) provides a static version with rendered outputs (download and open locally if GitHub does not preview it).

## Running the notebook

1. Create a Python environment and install dependencies: `pip install -r requirements.txt`.
2. Obtain the **original single-cell datasets** separately. They are **not included** in this repository.
3. Update the **machine-specific absolute file paths** in the notebook's data-loading cells to point to your local copies of the datasets.
4. Open `notebooks/AI_lab_project.ipynb` in Jupyter and run cells in order.

**Reproducibility note:** the notebook currently contains absolute paths from the original development machines, so it will not run out of the box. Some steps may be computationally intensive. The original code is intentionally preserved rather than silently rewritten.

## Technologies

Python · pandas · NumPy · scikit-learn · Matplotlib · Seaborn · UMAP · SciPy · Jupyter

## Project context

Academic group project. Credit should be shared with the original contributors where applicable. No original sequencing datasets are redistributed here.
