# Dataset Documentation

## Data Source

This research uses publicly available gene expression data from the NCBI Gene Expression Omnibus (GEO).

**GEO Accession:** GSE174056

**Dataset:** https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE174056

The dataset was used to investigate gene co-expression patterns associated with Spinal Muscular Atrophy (SMA).

## Research Context

The study focuses on identifying potential SMA-associated molecular biomarkers through computational gene expression analysis.

Three reference biomarkers were considered:

- NfL
- HSPA7
- SMN2

These biomarkers served as reference points for investigating gene co-expression relationships.

## Data Preprocessing

The computational workflow involves:

1. Acquisition of publicly available gene expression data.
2. Preparation of gene expression profiles for computational analysis.
3. Selection of reference biomarkers.
4. Calculation of gene co-expression relationships.
5. Identification of biomarker-associated gene clusters.
6. Export of clustering results for interpretation.

## Data Analysis

The MATLAB workflow uses correlation-based analysis to investigate relationships between gene expression profiles.

Genes are grouped according to their co-expression relationships with individual biomarkers or combinations of biomarkers.

The resulting clusters are used to explore potential molecular signatures associated with SMA.

## Data Availability

The original dataset is publicly accessible through GEO accession GSE174056.

Example clustering results and exported gene lists are available in the repository's `results/` directory.

## Reproducibility

The MATLAB scripts are available in the `code/` directory.

The documented execution order is:

1. `01_compute_coexpression_by_biomarker.m`
2. `02_generate_biomarker_clusters.m`

Users should verify the required input data, preprocessing parameters, and file paths before executing the scripts.

## Research Reference

**Publication:** Identifying Biomarkers for Spinal Muscular Atrophy: A System Biology-Based Approach

**Conference:** BATS 2024, Rome, Italy
