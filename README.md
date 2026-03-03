# Expression Overlap Analysis

## Overview
This directory contains the pipeline and results for evaluating the expression overlap between human transcripts and mouse genes in the context of Schizophrenia research. The analysis matches human genes against mouse orthologs and computes similarities in expression directionality via multiple statistical tests to identify significant overlapping targets.

## Analysis Pipeline

### 1. Load Data
The pipeline begins by loading the summary statistics and lists of Differentially Expressed Genes (DEGs) for both human and mouse datasets.

### 2. Matching
To perform cross-species analysis, human genes are matched to their corresponding mouse orthologs.

### 3. Statistical Tests
The pipeline utilizes three primary statistical evaluations to identify significant overlaps:
*   **Hypergeometric Tests**: Evaluates if the degree of overlap between the human and mouse significant DEGs is greater than expected by chance.
*   **Spearman Correlation**: Measures the rank correlation of expression changes across the global set of matched genes.
*   **Rank-Rank Hypergeometric Overlap (RRHO)**: A threshold-free approach used to identify and visualize continuous patterns of overlap in gene expression profiles between the two species.

## Notebooks Overview
The core logic of the analysis is divided across three Jupyter Notebooks:
*   `stats_analysis.ipynb`: The main notebook containing the data loading, matching algorithms, and execution of the statistical tests (Hypergeometric, Spearman, RRHO).
*   `summary_VennDiagram.ipynb`: Generates Venn diagrams summarizing the overlapping significant genes across different datasets.
*   `signifance_evaluation.ipynb`: Used for follow-up and detailed significance evaluations based on the pipeline outputs.

## Results & Visualizations

The output of the mathematical analyses is saved in `results/overlap_results.csv`, which details the raw counts, statistical scores (Spearman rho, p-values), and significance flags for each target.

### Global Overlap
A global view of the sets of significantly overlapping genes:

![Summary Venn Diagram](/sample_results/venn_diagram_all.png)

### RRHO Heatmaps
The Rank-Rank Hypergeometric Overlap test produces heatmaps detailing the strength and directionality of the expression overlap. Below are a few selected examples from the results highlighting specific genes:

**SCYL1 (Transcript 201)**  
![SCYL1-201 RRHO Heatmap](/sample_results/SCYL1-201.png)

**RNASEH2C (Transcript 201)**  
![RNASEH2C-201 RRHO Heatmap](/sample_results/RNASEH2C-201.png)

**BANF1 (Transcript 201)**  
![BANF1-201 RRHO Heatmap](/sample_results/BANF1-201.png)

*(Note: Additional heatmaps for other gene targets can be found within the `sample_results` directory).*
