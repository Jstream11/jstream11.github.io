---
layout: post
title: Bioinformatic Data Analysis Application
date: 2023-12-17 00:00:00 +0300
description: Develop an RShiny application to analyze gene expression data, utilizing skills developed in R including data wrangling, counts data analysis, differential expression analysis, and gene set enrichment analysis.  (optional)
img: js-1.png # Add image post (optional)
tags: [Academic, R, RShiny, Differential Expression, GSEA] # add tag
---

The data used to develop this application:

[mRNA-Seq Expression profiling of human post-mortem BA9 brain tissue for Huntington’s Disease and neurologically normal individuals](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE64810)

![Screenshot 2024-01-13 134315.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/a025bc22-30d9-4acc-8823-78fd8b839151/6f06cd43-567f-40c5-93d2-76665730f68d/Screenshot_2024-01-13_134315.png)

[Bioinformatics_Data_Analysis_RShinyApp.mp4](https://prod-files-secure.s3.us-west-2.amazonaws.com/a025bc22-30d9-4acc-8823-78fd8b839151/36a749f5-d76f-4ebf-a4f9-93224649c2f1/Bioinformatics_Data_Analysis_RShinyApp.mp4)

### The Goal

---

Develop an RShiny application to analyze gene expression data, utilizing skills developed in R including data wrangling, counts data analysis, differential expression analysis, and gene set enrichment analysis. 

### The Design

---

**Sample Information Exploration**

This feature is focused on providing insights into the distinct values and distributions of sample information before delving into the analysis of corresponding sample data.

**Inputs**:

- *Sample Information Matrix*: Accepts CSV format files containing sample information.

**Shiny Functionalities**:

1. **Summary Tab**: Presents a comprehensive summary of the table, including an overview of the type and values in each column.
2. **Data Table Tab**: Offers a detailed data table displaying the sample information. The table is equipped with sortable columns, enhancing user interactivity.
3. **Visualization Tab**: Features density plots for continuous variables. This visual representation aids in a better understanding of the distribution patterns within the sample information.

**Counts Matrix Exploration**

This feature enables users to choose gene filtering thresholds, providing valuable insights into the effects of different filtering strategies on the counts matrix.

**Inputs**:

- *Normalized Counts Matrix*: Accepts CSV format files containing normalized counts data.
- *Input Controls*: Empowers users to filter genes based on statistical properties.
    - Slider to include genes with at least X percentile of variance.
    - Slider to include genes with at least X samples that are non-zero.

**Shiny Functionalities**:

1. **Filtering Summary Tab**: Provides a tabular summary of the filtering effects, including:
    - Number of samples.
    - Total number of genes.
    - Percentage of genes passing the current filter.
    - Percentage of genes not passing the current filter.
2. **Diagnostic Scatter Plots Tab**: Features scatter plots depicting the relationship between:
    - Median count vs variance (log scale considered).
    - Median count vs number of zeros.
    
    Genes passing filters are marked in a darker color, while filtered-out genes are lighter.
    
3. **Clustered Heatmap Tab**: Presents a clustered heatmap of counts remaining after filtering. 
4. **Principal Component Analysis (PCA) Scatter Plots Tab**: Includes a scatter plot of PCA projections. Users can select which principal components to plot in a scatter plot (e.g., PC1 vs PC2).

**Differential Expression Analysis**

This feature is designed to identify genes implicated in specific biological comparisons. This component enables users to load and explore a dataset resulting from a differential expression analysis.

**Inputs**:

- *Differential Expression Results*: Accepts CSV format files containing the results of a differential expression analysis.

**Shiny Functionalities**:

1. **Sortable Table Tab**: Presents a sortable table displaying differential expression results. Users can explore details such as gene names, log-fold changes, p-values, and adjusted p-values. Gene name search functionality is enabled.
2. **Diagnostic Plots Tab**: Users can select a desired plot:
    - Raw p-value histogram.
    - Log2 fold change histogram.
    - Volcano plot.
    
    Additionally, users can adjust the padj (adjusted p-value) threshold for enhanced customization and interpretation.
    

**Gene Set Enrichment Analysis (GSEA)**

This feature provides a comprehensive analysis, allowing users to visualize and explore enriched pathways based on their differential gene expression results.

**Input**:

- *File Upload Button*: Allows users to upload their fgsea results.

**Shiny Functionalities**:

1. **Top Pathways Tab**: Provides a ****barplot of fgsea Normalized Enrichment Scores (NES) for the top pathways filtered by padj (adjusted p-value) threshold by the user. Negatively enriched pathways are presented in red while positively enriched pathways are in blue.
2. **Data Table Tab:** Provides a sortable data table displaying the GSEA results, filtered by padj (adjusted p-value) threshold by the user. The user is also able to select positive, negative, or all NES pathways.  A download button to export the current filtered and displayed table results is available.
3. **Plots Tab:** Scatter plot depicting NES on the x-axis and -log10 adjusted p-value on the y-axis, filtered by padj (adjusted p-value) threshold by the user. Gene sets below the threshold are displayed in grey color.
