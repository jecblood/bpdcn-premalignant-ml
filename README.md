Explainable Machine Learning Identifies Transcriptional Features of Premalignant and Malignant pDCs in BPDCN
<img width="2285" height="2819" alt="shap_summary" src="https://github.com/user-attachments/assets/ccad4512-1e7a-4b3b-acf7-2991d0722c03" />

Overview
Blastic plasmacytoid dendritic cell neoplasm (BPDCN) is a rare and aggressive hematologic malignancy that arises from plasmacytoid dendritic cells (pDCs). Using publicly available single-cell RNA-seq data from Griffin et al. (Nature, 2023), this project applies machine learning and explainable AI to identify transcriptional features associated with malignant transformation.
Models used:

Random Forest
XGBoost
SHAP (SHapley Additive exPlanations)

Goal:

Distinguish premalignant pDCs from malignant BPDCN cells
Identify genes consistently associated with transformation
Validate findings against published BPDCN transcriptional signatures


Dataset
Source

GEO: GSE227690
Griffin GK et al. Ultraviolet radiation shapes dendritic cell leukaemia transformation in the skin. Nature (2023)

Final machine learning dataset:
4,846 cells  2,000 highly variable genes
Cell populations analyzed:
Premalignant pDCs and Malignant BPDCN cells

Workflow
Metadata Processing        ↓pDC Identification        ↓Expression Matrix Construction        ↓Feature Filtering        ↓Random Forest        ↓XGBoost        ↓SHAP Analysis        ↓Gene Expression Validation

Key Findings
Genes consistently identified across Random Forest, XGBoost, and SHAP analyses:

ALOX5AP
ALKBH7
PDLIM1
HES6
SIGLEC6

Recovery of Published BPDCN Markers
The workflow independently recovered:

HES6
IGLL1

Both genes were reported in the original Nature study as components of a BPDCN transcriptional signature.
Candidate Transformation Markers

























Premalignant-EnrichedMalignant-EnrichedALOX5APPDLIM1ALKBH7HES6IGLL1SIGLEC6

SHAP Feature Importance
Top genes ranked by SHAP:

































GeneMean Absolute SHAPALOX5AP2.26PDLIM10.83HES60.58ALKBH70.46LAMP50.41SIGLEC60.30

Candidate Gene Validation

Differential expression analysis demonstrated significant expression differences between premalignant and malignant pDCs.
Example Findings

































GeneLog2 Fold ChangeALOX5AP-8.63ALKBH7-6.58PDLIM1+6.12HES6+5.70IGLL1+3.35SIGLEC6+2.85

SHAP Summary Plot


Repository Structure
Plain Textnotebooks/├── 06_build_expression_dataset.ipynb├── 07_feature_filtering.ipynb├── 08_random_forest.ipynb├── 09_xgboost.ipynb└── 11_gene_expression_validation.ipynbfigures/results/Show more lines

Results
Generated outputs include:
Plain Textresults/rf_feature_importance.csvxgb_feature_importance.csvshap_importance.csvcandidate_gene_validation.csvShow more lines

Limitations

Models were trained at the single-cell level.
Patient-level validation was limited by available count matrices.
Findings should be interpreted as hypothesis-generating and require additional biological validation.


Skills Demonstrated

Single-cell RNA-seq analysis
Machine learning
Random Forest
XGBoost
Explainable AI (SHAP)
Statistical testing
Data visualization
Reproducible research workflows
Python (pandas, scikit-learn, XGBoost, SHAP)


Citation
Griffin GK, Booth CAG, Togami K, et al.
Ultraviolet radiation shapes dendritic cell leukaemia transformation in the skin.
Nature. 2023;618:834–841.
