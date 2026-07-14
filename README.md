# Explainable Machine Learning Identifies Transcriptional Features of Premalignant and Malignant pDCs in BPDCN

## Overview

Machine learning analysis of single-cell RNA-seq data from:

Griffin et al.
Nature 2023
"Ultraviolet radiation shapes dendritic cell leukaemia transformation in the skin"

using:

- Random Forest
- XGBoost
- SHAP

to distinguish:

- Premalignant pDCs
- Malignant BPDCN cells

## Dataset

GEO: GSE227690

## Workflow

Metadata
→ pDC identification
→ Expression matrix construction
→ Feature filtering
→ Random Forest
→ XGBoost
→ SHAP
→ Candidate gene validation

## Key Findings

Genes consistently identified across RF, XGBoost, and SHAP:

- ALOX5AP
- ALKBH7
- PDLIM1
- HES6
- SIGLEC6

Validation reproduced known BPDCN-associated genes reported in the original study:

- HES6
- IGLL1

## Results

(insert SHAP figure)

(insert validation panel)

## Limitations

Models were trained at the single-cell level.
Patient-level validation was limited by available count matrices.

## Citation

Griffin GK et al.
Nature 2023
