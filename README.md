# Breast Cancer Tumor vs Normal — Differential Gene Expression Analysis

## Overview
This project analyzes gene expression differences between breast cancer tumor
tissue and normal breast tissue using a public microarray dataset from NCBI
GEO. The goal was to identify differentially expressed genes (DEGs) and
interpret their biological significance in the context of cancer.

## Dataset
- **Source:** NCBI Gene Expression Omnibus (GEO)
- **Accession:** GSE45827
- **Platform:** Affymetrix Human Genome U133 Plus 2.0 Array (GPL570)
- **Samples used:** 11 normal tissue samples vs. 36 tumor samples
  (Basal, HER2, Luminal A, Luminal B subtypes)
- **Citation:** Gruosso et al., EMBO Mol Med 2016 May;8(5):527-49

## Method
1. Retrieved the dataset from GEO and defined two sample groups (Tumor, Normal)
2. Ran differential expression analysis using **GEO2R**, which applies the
   limma package in R
3. Ranked genes by adjusted p-value (FDR) and log fold-change (logFC)
4. Selected top significant genes for biological
   ## Results

### Top Differentially Expressed Genes

| Gene | logFC | Direction | Function |
|------|-------|-----------|----------|
| ADIPOQ | -7.62 | Down in tumor | Anti-tumor adipokine, often lost in breast cancer |
| TNXB | -5.86 | Down in tumor | Extracellular matrix protein, loss linked to invasion |
| SCARA5 | -5.68 | Down in tumor | Tumor suppressor, silenced in aggressive cancers |
| SCD5 | -3.57 | Down in tumor | Fatty acid metabolism, altered in tumor lipid rewiring |
| TOP2A | +5.39 | Up in tumor | Proliferation marker, used clinically to grade tumors |
| SMC4 | +5.3 | Up in tumor | Chromosome organization during cell division |
| CDK1 | +5.06 | Up in tumor | Cell cycle driver, reflects uncontrolled growth |
| SQLE | +4.38 | Up in tumor | Cholesterol synthesis, fuels fast-growing cells |
| AURKA | +4.26 | Up in tumor | Drives cell division, overexpressed in cancer |
| MAPK1 | +3.49 | Up in tumor | Growth signaling, frequently hyperactive in cancer |
| RAD1 | +3.46 | Up in tumor | DNA damage checkpoint gene |
| KPNA1 | +3.23 | Up in tumor | Nuclear transport, often hijacked by cancer cells |

*(Full ranked gene list available in `/data/top_DEGs.csv`)*

### Visualization
Volcano plot showing significantly up- and down-regulated genes
(red = upregulated, blue = downregulated, black = not significant).

## Interpretation
The top differentially expressed genes cluster into two clear biological
themes:

1. **Loss of normal metabolic/structural genes** — ADIPOQ, SCD5, TNXB, and
   SCARA5 are all downregulated in tumor tissue. These genes are associated
   with healthy fat metabolism, tissue structure, and tumor-suppressive
   activity, and their loss is consistent with known breast cancer biology.

2. **Gain of cell-cycle/proliferation genes** — TOP2A, AURKA, CDK1, and SMC4
   are all upregulated in tumor tissue. These genes drive cell division and
   are well-established markers of tumor proliferation, reflecting the
   uncontrolled growth characteristic of cancer.

This pattern is consistent with established breast cancer molecular biology
and demonstrates a clear tumor-associated expression signature.

## Tools Used
- NCBI GEO / GEO2R (limma)
- Excel / Google Sheets for data organization

## Author
[Syed Mohd Zeeshan] — BSc Biology
