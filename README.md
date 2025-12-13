# **sc-seq analysis of bone marrow cells**

This repository contains a single-cell RNA-sequencing (scRNA-seq) analysis of human bone marrow. The project identifies major immune and hematopoietic cell populations, examines their biological functions, and interprets the immune landscape in the context of inflammation and infection. The analysis was performed using Scanpy, Decoupler, and PanglaoDB marker annotations.

## **Project Overview**

- **Dataset:  
    **<https://github.com/josoga2/sc/raw/refs/heads/main/bone_marrow.h5ad_(14,783> cells × 17,374 genes)  
    _
- **Tools & Libraries:  
    **Scanpy, Anndata, Decoupler, igraph, matplotlib  

- **Analysis Steps:  
    **
  - Quality control and filtering  

  - Normalization and log-transformation  

  - Highly variable gene selection  

  - PCA and UMAP for dimensionality reduction  

  - Clustering using the Leiden algorithm  

  - Cell type annotation using ULM scores with PanglaoDB markers  

  - Trajectory and pseudotime analysis using PAGA and DPT  

## **Identified Cell Types**

The following immune and hematopoietic cell types were identified:

- Neutrophils  

- Monocytes  

- Naïve B cells  

- Memory B cells  

- CD4⁺ T cells  

- CD8⁺ T cells  

- Natural killer (NK) cells  

- Plasma cells  

- Dendritic cells  

- Megakaryocytes  

- Erythroid progenitors  

## **Biological Roles of Identified Cell Types**

| **Cell Type** | **Function in Bone Marrow / Immunity** |
| --- | --- |
| Neutrophils | Short-lived phagocytes; first responders to infection |
| --- | --- |
| Monocytes | Precursors to macrophages and dendritic cells; innate immunity |
| --- | --- |
| Naïve B cells | Antigen-inexperienced B cells |
| --- | --- |
| Memory B cells | Antigen-experienced B cells enabling rapid recall responses |
| --- | --- |
| CD4⁺ T cells | Helper T cells coordinating immune responses |
| --- | --- |
| CD8⁺ T cells | Cytotoxic T cells targeting infected or abnormal cells |
| --- | --- |
| Natural killer cells | Innate cytotoxic lymphocytes mediating viral clearance |
| --- | --- |
| Plasma cells | Antibody-secreting terminal B cells |
| --- | --- |
| Dendritic cells | Antigen-presenting cells initiating adaptive immunity |
| --- | --- |
| Megakaryocytes | Platelet-producing cells involved in clotting |
| --- | --- |
| Erythroid<br><br>progenitors | Precursors of red blood cells |
| --- | --- |

## **Biological Interpretation of the Immune Landscape**

The single-cell RNA-seq analysis reveals a heterogeneous immune landscape composed of innate and adaptive immune populations alongside hematopoietic progenitors. The identified cell types and their relative abundances provide insight into immune activity but must be interpreted with caution.

### **Innate Immune Compartment**

- Neutrophils represent a major innate immune population. As professional phagocytes, they constitute the first line of defense against pathogens. Their relative enrichment is consistent with an acute inflammatory response, particularly in bacterial or viral infection contexts.
- Monocytes, a mononuclear phagocytic population, are prominently represented. These cells contribute to phagocytosis, cytokine production, and antigen presentation via MHC class II pathways. Increased monocyte abundance is commonly associated with systemic inflammation and innate immune activation.
- Dendritic cells, although less abundant, play a critical role in antigen processing and presentation, bridging innate and adaptive immunity.
- Natural killer (NK) cells exhibit activation-associated transcriptional profiles. NK cells are central to viral recognition and clearance, mediating cytotoxicity against infected or stressed cells in an antigen-independent manner.

### **Adaptive Immune Compartment**

The adaptive immune compartment includes CD4⁺ T cells, CD8⁺ T cells, and B cells, which together constitute the lymphoid fraction of peripheral blood mononuclear cells (PBMCs).

- CD4⁺ T cells coordinate immune responses through cytokine secretion.
- CD8⁺ T cells mediate cytotoxic killing of virus-infected cells.
- Naïve B cells represent antigen-inexperienced lymphocytes.
- Plasma cells, derived from activated B cells, function as antibody-secreting cells, indicating humoral immune activation and prior antigen exposure.

Pseudotime analysis reveals a differentiation trajectory from naïve B cells toward plasma cells, supporting ongoing or recent adaptive immune activation.

**Hematopoietic and Tissue Context**

The presence of erythroid progenitors and megakaryocytes strongly supports a bone marrow origin, as these populations are typically absent from peripheral blood. However, the relatively high abundance of mature mononuclear immune cells resembles a PBMC-like composition, suggesting possible marrow aspirate contamination or immune cell enrichment.

Notably, nuocytes (ILC2-like cells) were not clearly identified. Their absence may reflect biological rarity, limited sequencing depth, or marker overlap with other innate lymphoid populations.

### **Immune State and Health Inference**

While increased proportions of neutrophils, monocytes, NK cells, and plasma cells are consistent with an inflammatory or infectious immune response, cell-type proportions alone are insufficient to definitively determine patient health status. Immune composition may be influenced by:

- inter-individual variability  

- disease state or therapeutic intervention  

- sampling and technical biases

Therefore, the observed immune landscape should be interpreted as suggestive rather than diagnostic of an activated immune state.

## **Summary**

Overall, this dataset captures a coordinated immune response involving **phagocytosis**, **antigen presentation**, **viral recognition**, and **antibody production**, spanning both innate and adaptive arms of immunity. The findings align with an inflammatory immune environment but would benefit from validation across additional samples or conditions.

## **Analysis Pipeline Highlights**

- Quality filtering: removed cells with &lt;200 detected genes or &gt;10% mitochondrial reads  

- Normalization: total-count normalization followed by log1p transformation  

- Dimensionality reduction: PCA and UMAP  

- Clustering: Leiden algorithm (resolution = 1.0)  

- Cell type annotation: ULM enrichment using PanglaoDB markers  

- Trajectory analysis: PAGA graph construction and DPT pseudotime inference
