# Analysis of Differential Gene Expression in RNA-seq Data
This repository contains R scripts used to perform differential gene expression analysis in RNA-seq data. The dataset used comes from the study "Sugar coordinates plant defense signaling" (Yamada K, Mine A, Sci Adv 2024) and is available in the Gene Expression Omnibus (GEO) repository with the accession code GSE169473.

# Analysis Objective
The main objective of this analysis is to identify genes whose expression is modulated in response to sugar administration in plants. Different treatments and exposure times are explored to understand how metabolism signaling in plants is coordinated by the presence of sugars.

# Repository Structure
* Main Script: The main script, "analysis.R", contains the code used to load and process the data, perform differential gene expression analysis, and visualize the results.

* Count Tables: Count tables used in the analysis to represent gene abundance in different experimental conditions are included.

* Results: The analysis results are stored, including lists of differentially expressed genes and functional enrichment.

# Analysis Steps
* Data Loading: Gene expression data is obtained using the GEOquery library and organized into a suitable format for analysis.

* Data Preprocessing: Count tables are adjusted, and relevant subsets are selected for differential gene expression analysis.

* Differential Gene Expression Analysis (DESeq2): DESeq2 is used to identify genes whose expression significantly varies between different experimental conditions.

* Results Visualization: Graphs such as principal component analysis (PCA), GO enrichment analysis, and gene-specific visualizations are generated.

# Interactive Visualization
Interactive visualization is performed using the GOplot library, allowing detailed exploration of functional enrichment terms and graphical representation of gene expression.

For specific details about the analysis and its interpretation, refer to the main script and comments included in the code.

# Results

In pursuit of deciphering the complex tapestry of gene expression dynamics and metabolic pathway adaptations in response to sucrose addition, we executed a DESeq analysis on Col-0 genotype plants. This comprehensive investigation compared plants under non-sugar addition conditions with those treated with sucrose, each condition having three replicates. Out of a total of 32,833 genes examined, approximately 12% (4135 genes) exhibited up-regulation, while around 20% (6710 genes) displayed down-regulation. As a quality control measure, a Principal Component Analysis (PCA) was employed, revealing a distinct clustering pattern among replicates of the same treatments. 
![PCA](https://github.com/Bioinformaticareposit/RNA-seq-data-analysis/assets/115641732/b7e1a8bd-6f49-4bab-8e90-dde791edee4f)
![plotMA](https://github.com/Bioinformaticareposit/RNA-seq-data-analysis/assets/115641732/2e44b42d-beca-49f5-96e0-7e6d769b028f)

Following the DESeq analysis, we proceed with log-fold change shrinkage using lfcShrink for the specific comparison between plants treated with or without Sucrose conditions. Subsequently, genes are filtered based on significance and magnitude criteria (padj < 0.05 and |log2FoldChange| > 1). Finally, a Gene Ontology (GO) enrichment analysis is conducted, unveiling the biological processes, molecular functions, and cellular components associated with the differentially expressed genes.
![GO_analysis](https://github.com/Bioinformaticareposit/RNA-seq-data-analysis/assets/115641732/4e616c65-fea4-4496-bb9b-56827f68aefb)

Among the Gene Ontology groups, GO:0015979, associated with photosynthesis, stands out as particularly impacted, featuring a substantial alteration in 163 genes. A heatmap visualization distinctly reveals a prevalent downregulation trend among a significant proportion of these genes.
![heatmap photosyn](https://github.com/Bioinformaticareposit/RNA-seq-data-analysis/assets/115641732/ac79bbea-430b-4dc7-885c-f42722a5793a)

Through the use of ShinyGO, it becomes readily apparent that the majority of genes under GO:0015979 are closely associated with coding proteins of both photosystem I and II. 
![diagrama photo](https://github.com/Bioinformaticareposit/RNA-seq-data-analysis/assets/115641732/df214acb-b5fc-461c-9ccd-e6f8e60f18a8)
