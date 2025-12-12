# **sc-seq analysis of bone marrow cells**

This repository contains a single-cell RNA-seq analysis of human bone marrow. The project identifies major immune and hematopoietic cell types, examines their biological roles, and interprets the health status of the donor. Analysis was performed using Scanpy, Decoupler, and PanglaoDB marker annotations.

## **Project Overview**

- Dataset: <https://github.com/josoga2/sc/raw/refs/heads/main/bone_marrow.h5ad> (14,783 cells, 17,374 genes)  

- Tools & Libraries: Scanpy, Anndata, Decoupler, igraph, matplotlib  

- Analysis steps:  
  - Quality control and filtering  

  - Normalization and log-transformation  

  - Highly variable gene selection  

  - PCA and UMAP for dimensionality reduction  

  - Clustering using leiden algorithm  

  - Cell type annotation using ULM scores with PanglaoDB markers  

  - Trajectory/pseudotime analysis using PAGA and DPT  

## **Identified Cell Types**

The analysis identified the following cell types:

- Neutrophils  

- Monocytes  

- B cells naive  

- B cells memory  

- T cells CD4+  

- T cells CD8+  

- Natural Killer cells  

- Plasma cells  

- Dendritic cells  

- Megakaryocytes  

- Erythroid progenitors  

## 2\. Biological Roles

| Cell Type | Function in Bone Marrow / Immunity |
| --- | --- |
| Neutrophils | Short-lived phagocytes, first responders to infection |
| --- | --- |
| Monocytes | Precursors to macrophages/dendritic cells; innate immunity |
| --- | --- |
| B cells naive | Immature B cells, antigen-inexperienced |
| --- | --- |
| B cells memory | Antigen-experienced B cells, rapid response upon re-exposure |
| --- | --- |
| T cells CD4+ | Helper T cells; orchestrate immune responses |
| --- | --- |
| T cells CD8+ | Cytotoxic T cells; kill virus-infected or abnormal cells |
| --- | --- |
| Natural Killer cells | Innate cytotoxic lymphocytes; kill stressed or infected cells |
| --- | --- |
| Plasma cells | Antibody-producing terminal B cells |
| --- | --- |
| Dendritic cells | Antigen-presenting cells; initiate adaptive immunity |
| --- | --- |
| Megakaryocytes | Platelet-producing cells; support clotting |
| --- | --- |
| Erythroid progenitors | Early red blood cell precursors |
| --- | --- |

## **Tissue Source Justification**

- Presence of erythroid progenitors and megakaryocytes supports bone marrow origin.  

- Mature lymphocytes, neutrophils, and monocytes are expected in both blood and marrow; progenitor populations confirm marrow.  

- Caveat: Some skew toward mature lymphocytes may indicate peripheral blood contamination.  

Conclusion: Likely bone marrow tissue, with minor peripheral contribution.

## **Health Status Interpretation**

- Neutrophils & monocytes: Elevated proportions indicate an active immune response.  

- Natural Killer cells: High activation states support infection detection.  

- B & plasma cells: Differentiation from naive B cells toward plasma cells suggests recent antigen exposure.  

Inference: The patient is likely experiencing an infection or immune challenge, as evidenced by shifts in immune cell populations and trajectory analysis.

## **Analysis Pipeline Highlights**

- Quality filtering: Removed cells with &lt;200 genes or &gt;10% mitochondrial reads  

- Normalization: Total-count normalization and log1p transformation  

- Dimensionality reduction: PCA and UMAP  

- Clustering: Leiden algorithm (resolution=1.0)  

- Cell type annotation: ULM scores from PanglaoDB markers  

- Trajectory analysis: PAGA graph and DPT pseudotime
