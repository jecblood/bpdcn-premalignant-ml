Explainable Machine Learning Identifies Transcriptional Features of Premalignant and Malignant pDCs in BPDCN

Overview
Blastic plasmacytoid dendritic cell neoplasm (BPDCN) is a rare and aggressive hematologic malignancy that arises from plasmacytoid dendritic cells (pDCs). Using publicly available single-cell RNA-seq data from Griffin et al. (Nature, 2023), this project applies machine learning and explainable AI to identify transcriptional features associated with malignant transformation.
<img width="2285" height="2819" alt="shap_summary" src="https://github.com/user-attachments/assets/e4ed58e0-bcbd-44ef-b6d4-20526397a966" />

### Interpreting the SHAP Summary Plot

Each point represents a single cell.

Blue points indicate low expression of a gene and red points indicate high expression.

Points positioned to the right increase the probability that a cell is classified as malignant BPDCN, while points positioned to the left increase the probability that a cell is classified as premalignant.

The model identified ALOX5AP and ALKBH7 as features associated with premalignant cells, whereas HES6, PDLIM1, and SIGLEC6 were associated with malignant BPDCN cells.

Notably, HES6 and IGLL1 were independently recovered and were also reported in the original Nature BPDCN transcriptional signature.

Models used:

Random Forest
XGBoost
SHAP (SHapley Additive exPlanations)

Goal:

Distinguish premalignant pDCs from malignant BPDCN cells
Identify genes consistently associated with transformation
Validate findings against published BPDCN transcriptional signatures


Dataset
GEO: GSE227690

Source

Griffin GK et al. Ultraviolet radiation shapes dendritic cell leukaemia transformation in the skin. Nature (2023)

Final machine learning dataset:
4,846 cells  2,000 highly variable genes
Cell populations analyzed:
Premalignant pDCs and Malignant BPDCN cells

Workflow
Metadata Processing        -->pDC Identification        -->Expression Matrix Construction        -->Feature Filtering        -->Random Forest        -->XGBoost        -->SHAP Analysis        -->Gene Expression Validation

Key Findings
Genes consistently identified across Random Forest, XGBoost, and SHAP analyses:

ALOX5AP
ALKBH7
PDLIM1
HES6
SIGLEC6
<img width="4169" height="2366" alt="candidate_gene_validation_panel" src="https://github.com/user-attachments/assets/0f9014a4-a115-4f24-9ee7-488f4e9ffa6d" />

Recovery of Published BPDCN Markers
The workflow independently recovered:

HES6
IGLL1

Both genes were reported in the original Nature study as components of a BPDCN transcriptional signature.

Differential expression analysis demonstrated significant expression differences between premalignant and malignant pDCs.
Example Findings


Gene       Log2 Fold Change
ALOX5AP     -8.63
ALKBH7      -6.58
PDLIM1      +6.12
HES6        +5.70
IGLL1       +3.35
SIGLEC6     +2.85


Repository Structure
notebooks/├── 06_build_expression_dataset.ipynb├── 07_feature_filtering.ipynb├── 08_random_forest.ipynb├── 09_xgboost.ipynb└── 11_gene_expression_validation.ipynbfigures/results/

Results
Generated outputs include:
results/rf_feature_importance.csvxgb_feature_importance.csvshap_importance.csvcandidate_gene_validation.csv

Limitations

Models were trained at the single-cell level.
Patient-level validation was limited by available count matrices.
Findings should be interpreted as hypothesis-generating and require additional biological validation.

Citation
Griffin GK, Booth CAG, Togami K, et al.
Ultraviolet radiation shapes dendritic cell leukaemia transformation in the skin.
Nature. 2023;618:834–841.
