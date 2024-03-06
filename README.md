#Analysis of Differential Gene Expression in RNA-seq Data
This repository contains R scripts used to perform differential gene expression analysis in RNA-seq data. The dataset used comes from the study "Sugar coordinates plant defense signaling" (Yamada K, Mine A, Sci Adv 2024) and is available in the Gene Expression Omnibus (GEO) repository with the accession code GSE169473.

#Analysis Objective
The main objective of this analysis is to identify genes whose expression is modulated in response to sugar administration in plants. Different treatments and exposure times are explored to understand how defense signaling in plants is coordinated by the presence of sugars.

#Repository Structure
*Main Script: The main script, "analysis.R", contains the code used to load and process the data, perform differential gene expression analysis, and visualize the results.

*Count Tables: Count tables used in the analysis to represent gene abundance in different experimental conditions are included.

*Results: The analysis results are stored, including lists of differentially expressed genes and functional enrichment.

#Analysis Steps
*Data Loading: Gene expression data is obtained using the GEOquery library and organized into a suitable format for analysis.

*Data Preprocessing: Count tables are adjusted, and relevant subsets are selected for differential gene expression analysis.

*Differential Gene Expression Analysis (DESeq2): DESeq2 is used to identify genes whose expression significantly varies between different experimental conditions.

*Results Visualization: Graphs such as principal component analysis (PCA), GO enrichment analysis, and gene-specific visualizations are generated.

#Interactive Visualization
Interactive visualization is performed using the GOplot library, allowing detailed exploration of functional enrichment terms and graphical representation of gene expression.

For specific details about the analysis and its interpretation, refer to the main script and comments included in the code.
