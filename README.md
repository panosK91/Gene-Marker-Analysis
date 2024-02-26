# Data Analysis Overview

We utilized data sourced from scREAD focusing on the human species and examining four critical areas of the brain to understand the cellular and molecular underpinnings of Alzheimer's Disease (AD). The data encompasses both control and disease groups across these regions detailed as follows:

## 1. Entorhinal Cortex

- **Control Group:** Includes datasets AD00202 and AD00201 representing healthy subjects.
- **Disease Group:** Comprises datasets AD00203, AD00204, AD00205, and AD00206 representing subjects diagnosed with Alzheimer's Disease.

## 2. Prefrontal Cortex

- **Control Group:** Contains datasets AD01101 and AD01102 representing healthy subjects.
- **Disease Group:** Includes datasets AD01103 and AD01104 representing subjects diagnosed with Alzheimer's Disease.

## 3. Superior Frontal Gyrus

- **Control Group:** Features dataset AD00801 representing healthy subjects.
- **Disease Group:** Encompasses datasets AD00802 and AD00803 representing subjects diagnosed with Alzheimer's Disease.

## 4. Superior Parietal Lobe

- **Control Group:** Comprises datasets AD01201 and AD01202 representing healthy subjects.
- **Disease Group:** Contains datasets AD01203, AD01204, AD01205, and AD01206 representing subjects diagnosed with Alzheimer's Disease.

# Approach Followed

## Step 1: Organizing the Data

- **Control Group Compilation:** We collected data from healthy individuals' brain cells pooling this information into a unified dataset known as an AnnData object.
- **Disease Group Compilation:** Similarly, we gathered data from individuals diagnosed with Alzheimer's amalgamating this into another AnnData object.

## Step 2: Integrating Data for Comparative Analysis

- **Merging Datasets:** The next critical step involved combining the control and disease group datasets into one integrated AnnData object.

## Step 3: Identifying Genetic Discrepancies

- **Differential Gene Expression Analysis:** With a comprehensive dataset at our disposal, we conducted an analysis to discern genes that were either upregulated or downregulated in Alzheimer's affected brain cells compared to healthy ones.

# Preparing Your Dataset

## Data Collection and Initial Setup

- **Rationale:** Start with high-quality scRNA-seq data from various brain regions.
- **Action:** Ensure datasets are annotated with metadata including sample origin, condition, and any known batch factors.

## Quality Control and Outlier Removal

- **Rationale:** Quality control is essential to remove low-quality cells and genes.
- **Action:** Use the median absolute deviation (MAD) method to identify and exclude cells with abnormal gene expression patterns.

## Data Processing and Integration

### Normalization and Log Transformation

- **Rationale:** Normalization equilibrates gene expression levels across cells.
- **Action:** Apply a normalization method targeting a specific total RNA count per cell followed by log transformation.

### Batch Effect Annotation and Correction

- **Rationale:** Batch effects can introduce significant technical variability.
- **Action:** Annotate batches based on known variables and employ statistical models to adjust the data.

## Advanced Data Analysis

### Identification of Highly Variable Genes (HVGs)

- **Rationale:** Focusing on HVGs helps to highlight genes that contribute most to cellular heterogeneity.
- **Action:** Use variance-mean ratio (VMR) criteria to select HVGs for downstream analysis.

### Dimensionality Reduction and Clustering

- **Rationale:** Dimensionality reduction simplifies data interpretation.
- **Action:** Perform PCA followed by UMAP for visualization. Apply clustering algorithms like Leiden to define cell populations.

## Interpretation

### Differential Expression Analysis

- **Rationale:** This analysis identifies genes whose expression levels significantly differ between conditions.
- **Action:** Compare gene expression across identified clusters or conditions using statistical tests.

### Pathway Enrichment Analysis

- **Rationale:** Enrichment analysis links differentially expressed genes to known biological pathways.
- **Action:** Use tools like GSEA or Enrichr to identify pathways enriched in the gene lists derived from differential expression analysis.
