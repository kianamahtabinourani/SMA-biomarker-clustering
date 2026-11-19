# SMA Biomarker Discovery and Gene Co-Expression Network Analysis

A systems-level computational framework integrating statistical signal processing, gene co-expression analysis, network-based clustering, and deep learning to identify potential molecular biomarkers associated with Spinal Muscular Atrophy (SMA).

**Research Publication:** *Identifying Biomarkers for Spinal Muscular Atrophy: A System Biology-Based Approach*

**Conference:** BATS 2024, Rome, Italy

**Research Areas:** Computational Genomics · Systems Biology · Gene Expression Analysis · Network Analysis · Machine Learning · Biomedical Engineering

---

## Overview

This repository accompanies the research paper:

**Identifying Biomarkers for Spinal Muscular Atrophy: A System Biology-Based Approach**

The study proposes a computational framework for identifying candidate SMA biomarkers by analyzing gene expression patterns relative to three established biomarkers: **NfL, HSPA7, and SMN2**.

The methodology integrates statistical gene filtering, Pearson correlation, biomarker-guided clustering, weighted gene co-expression network analysis, and network-based feature extraction.

A U-Net deep learning architecture was additionally investigated to analyze interaction patterns of prioritized biomarker candidates.

The study identified **CTDP1 and M6PR** as promising candidate biomarkers associated with control and SMA expression profiles, respectively.

These findings are computational and require further validation using independent clinical datasets.

## Research Objectives

1. Develop a computational framework for analyzing gene expression patterns associated with SMA.
2. Identify co-expressed genes relative to established SMA biomarkers.
3. Construct biomarker-guided gene clusters using statistical correlation.
4. Analyze gene interactions using weighted co-expression networks.
5. Extract network-based features to prioritize candidate biomarkers.
6. Investigate gene interaction patterns using U-Net-based deep learning.
7. Evaluate the biological relevance and potential detectability of candidate biomarkers.

## Dataset

**Source:** NCBI Gene Expression Omnibus (GEO)

**Accession:** [GSE174056](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE174056)

The research uses normalized RNA-seq exon-count data.

| Dataset Characteristic | Description |
|---|---|
| Initial gene set | 17,617 genes |
| Control samples | 5 |
| SMA samples | 5 |
| Total samples | 10 |
| Reference biomarkers | NfL, HSPA7, SMN2 |
| Genes retained after filtering | 7,358 |

Gene identifiers were mapped to their associated names and descriptions using Ensembl.

The limited number of biological samples represents an important constraint on statistical inference and generalizability.

## Computational Methodology

The proposed framework consists of six major computational stages.

### 1. Data Acquisition and Statistical Preprocessing

- Retrieval of normalized RNA-seq expression measurements
- Gene identifier mapping
- Separation of control and SMA expression matrices
- Calculation of gene-wise mean expression and variance
- Statistical filtering of low-information genes
- Preservation of reference biomarker identifiers during preprocessing

The filtering procedure retained 7,358 genes for subsequent analysis.

### 2. Correlation-Based Co-Expression Analysis

Pearson correlation coefficients were calculated between individual genes and the three reference biomarkers.

Control and SMA expression groups were analyzed separately.

The initial co-expression screening used an empirical Pearson correlation threshold of 0.7.

| Reference Biomarker | Control Co-Expressed Genes | SMA Co-Expressed Genes |
|---|---:|---:|
| NfL | 4,110 | 5,229 |
| HSPA7 | 159 | 945 |
| SMN2 | 1,083 | 843 |

Overlapping co-expression profiles between the control and SMA groups were also identified for further analysis.

### 3. Biomarker-Guided Gene Clustering

Genes were grouped according to their average correlation with individual biomarkers and biomarker combinations.

Seven cluster configurations were generated for each expression group, producing **14 clusters in total**.

Cluster configurations included:

- NfL
- HSPA7
- SMN2
- NfL + HSPA7
- NfL + SMN2
- HSPA7 + SMN2
- NfL + HSPA7 + SMN2

Genes were assigned to clusters when their average correlation with the corresponding biomarker configuration was at least 0.5.

### 4. Weighted Gene Co-Expression Network Analysis

Weighted gene co-expression networks were constructed to characterize relationships among genes within the generated clusters.

The analysis included:

- Gene-gene correlation matrices
- Weighted adjacency matrix construction
- Network connectivity analysis
- Cosine similarity calculations
- Intra-cluster connectivity measurements
- Differential expression comparisons

These network-derived measurements were integrated to evaluate and rank candidate genes.

### 5. Candidate Biomarker Identification

Candidate genes were prioritized using network similarity, connectivity, and differential expression characteristics.

Following cluster refinement, the top 20 ranked genes from each cluster were selected for further investigation.

**CTDP1** emerged as a candidate associated predominantly with control expression profiles.

**M6PR** emerged as a candidate associated with increased expression in SMA samples.

Biological relevance and potential blood detectability were investigated using external resources, including Reactome, GTEx, and the Human Protein Atlas.

### 6. U-Net-Based Network Interaction Analysis

A U-Net architecture was investigated to characterize network interaction patterns of prioritized candidate biomarkers.

The methodology included:

- Conversion of gene-network adjacency matrices into two-dimensional representations
- Resizing network representations to 64 × 64 pixels
- Normalization of network-image values
- Encoder-decoder-based feature extraction and reconstruction
- Evaluation of reconstruction performance using mean squared error (MSE)

The reported average reconstruction MSE values included:

| Expression Group | Candidate Gene | Average MSE |
|---|---|---:|
| Control | CTDP1 | 0.0227 |
| SMA | M6PR | 0.0268 |

These results describe reconstruction behavior and should not be interpreted as clinical biomarker validation.

## Research Framework and Visualizations

### Biomarker-Based Gene Clustering

The following visualization illustrates gene clusters constructed from individual reference biomarkers and their combinations.

![SMA Biomarker Clusters](results/SMA%20Clusters.jpg)

**Figure 1.** Biomarker-guided co-expression clusters generated for the SMA analysis.

### Example Exported Gene List

An example gene list generated from the clustering workflow is available below.

[View Cluster Gene List](results/SMA_NfL+HSPA7+SMN2_ClusterGenes.csv)

## Experimental Results

The computational analysis identified distinct co-expression profiles between control and SMA samples.

**Key findings:**

- Statistical filtering reduced the original gene set from 17,617 to 7,358 genes.
- Biomarker-guided clustering generated 14 cluster configurations across control and SMA expression groups.
- Network analysis enabled candidate gene ranking using similarity, connectivity, and differential expression.
- CTDP1 and M6PR were identified as promising candidate biomarkers for further investigation.
- U-Net-based reconstruction provided an additional computational assessment of candidate network interaction patterns.

## Repository Structure

| Directory | Description |
|---|---|
| `code/` | MATLAB scripts for computational analysis |
| `results/` | Exported gene lists and research outputs |
| `figures/` | Research visualizations (planned) |
| `docs/` | Dataset and workflow documentation (planned) |

## Running the Available Clustering Scripts

The existing repository includes MATLAB scripts for the initial co-expression and clustering stages.

Run the scripts in the following order:

1. `01_compute_coexpression_by_biomarker.m`
2. `02_generate_biomarker_clusters.m`

The available scripts generate co-expression and clustering outputs.

The broader WGCN, biomarker-ranking, and U-Net methodologies are described in the accompanying publication. Their implementation availability should be verified separately from the published methodology.

## Research Limitations

The study presents an exploratory computational framework rather than a clinically validated diagnostic system.

Important limitations include:

- Small sample size (five control and five SMA samples)
- Empirically selected correlation thresholds
- Potential instability of gene correlation estimates with limited biological replicates
- Lack of independent clinical validation of the proposed biomarkers
- Need for additional evaluation of candidate biomarker specificity and reproducibility

Future work should investigate larger independent cohorts, sensitivity analysis, external validation, and integration of additional molecular datasets.

## Publication

**Mahtabi Nourani, K., Demirel, H., and Seytanoglu, A.**

*Identifying Biomarkers for Spinal Muscular Atrophy: A System Biology-Based Approach.*

BATS 2024, Rome, Italy.

## Author and Contact

**Kiana Mahtabi Nourani**

MSc Candidate, Electrical and Electronic Engineering

Eastern Mediterranean University

**Research Interests:** Artificial Intelligence, Machine Learning, Computational Genomics, Systems Biology, and Biomedical Engineering.

[GitHub](https://github.com/kianamahtabinourani)
