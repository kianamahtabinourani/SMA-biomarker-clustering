# MATLAB Computational Workflow

## Research Overview

This repository contains MATLAB scripts developed for the research project:

**Identifying Biomarkers for Spinal Muscular Atrophy: A System Biology-Based Approach**

**Conference:** BATS 2024, Rome, Italy

The computational framework investigates gene co-expression relationships associated with Spinal Muscular Atrophy (SMA), using selected reference biomarkers to identify potentially relevant gene clusters.

## Computational Pipeline

The repository documents two principal MATLAB processing stages.

### Stage 1: Gene Co-Expression Analysis

**MATLAB Script:** `01_compute_coexpression_by_biomarker.m`

**Objective:**

Investigate gene co-expression relationships relative to selected SMA biomarkers.

**Reference Biomarkers:**
- NfL
- HSPA7
- SMN2

**General Procedure:**

1. Load the prepared gene expression dataset.
2. Identify the reference biomarkers.
3. Calculate gene co-expression relationships.
4. Apply the correlation criteria defined in the MATLAB implementation.
5. Prepare the resulting gene associations for subsequent clustering.

### Stage 2: Biomarker-Guided Gene Clustering

**MATLAB Script:** `02_generate_biomarker_clusters.m`

**Objective:**

Organize genes into clusters according to their co-expression relationships with individual biomarkers and biomarker combinations.

**General Procedure:**

1. Load the co-expression analysis outputs.
2. Group genes according to the implemented clustering criteria.
3. Examine individual biomarker-associated gene groups.
4. Investigate gene groups associated with multiple reference biomarkers.
5. Generate clustering visualizations and export gene lists.

## Execution Order

Execute the MATLAB scripts in the following order:

1. `01_compute_coexpression_by_biomarker.m`
2. `02_generate_biomarker_clusters.m`

The second stage depends on the outputs generated during the first stage.

Before execution, verify that the required input files and directory paths are configured correctly.

## Example Outputs

The repository includes examples of generated results.

**Cluster Visualization:**

`results/SMA Clusters.jpg`

**Exported Gene List:**

`results/SMA_NfL+HSPA7+SMN2_ClusterGenes.csv`

These outputs illustrate the gene clustering results produced by the computational workflow.

## Interpretation

The computational analysis investigates co-expression relationships between genes and established SMA-associated reference biomarkers.

Individual biomarker clusters represent genes associated with a particular reference marker.

Multi-biomarker clusters represent genes satisfying the implemented association criteria for combinations of reference markers.

These relationships provide candidates for further biological investigation but do not independently establish causal regulatory interactions or validate new clinical biomarkers.

## Reproducibility Notes

The MATLAB scripts were developed as research components for the BATS 2024 study.

Successful execution requires:

- Access to the required gene expression data.
- Appropriate MATLAB software and any dependencies used by the scripts.
- Correct configuration of input and output paths.
- Consistent preprocessing and correlation parameters.

For information about the research dataset, see [Dataset Documentation](DATA.md).

## Research Reference

**Publication:** Identifying Biomarkers for Spinal Muscular Atrophy: A System Biology-Based Approach

**Conference:** BATS 2024, Rome, Italy
