# RNA-seq-data-analysis-DEMO
## Overview
It's a common strategy to analyze RNA-seq data of samples with different treatments (_e.g._ Resistance vs Susceptible) to identify gene expression profile, find key genes and biological pathways. Here, a simple case of mining resistance-related genes and pathways using RNA-seq data of _Tetranychus urticae_ is presented. 

## Workflow
<img src="https://github.com/TK-CamBaz/RNA-seq-data-analysis-DEMO/blob/main/FigureTable/flowchart.png" width="400">

## Results
(1). "With exposure" samples is similar to "Without exposure" ones, while "Reference" ones show different pattern compared to the others (see Figiure 1, 2 and 3).
(2).  Differential expressed genes 

BACK domain-containing protein: cullin-RING ubiquitin ligase adaptors that facilitate the ubiquitination of target substrates.
Lipocalin/cytosolic fatty-acid binding domain-containing protein: transport small hydrophobic molecules such as steroids, bilins, retinoids, and lipids.
Proteasome assembly chaperone 2: proteasome mediates ubiquitin-dependent proteolysis in eukaryotic cells.
Sodium/calcium exchanger membrane region: regulate intracellular Ca2+ concentrations in many cells
Nephrin: are expressed in the nephrocyte (filtration function)
Cytochrom P450s: the main detoxification enzymes employed by insects to combat the chemical defenses
Partial AB-hydrolase lipase domain-containing protein: hydrolase activity, acting on ester bonds.
Intradiol ring-cleavage dioxygenases domain-containing protein: to cleave catechol between two hydroxyl-groups using atmospheric dioxygen.

Thioredoxin-dependent peroxiredoxin: catalyzes the reduction of hydrogen peroxide and organic hydroperoxides to water and alcohols, respectively.
Cystatin domain-containing protein: inhibit peptidases.
Glycosyl transferase family 1 domain-containing protein: transfer UDP, ADP, GDP or CMP linked sugars to a variety of substrates.




In Figiure 1, the expression profiles in hierarchical and K-means clustering indicate that "With exposure" samples is similar to "Without exposure" ones, while "Reference" ones show different pattern compared to the others. After filtering (FDR < 0.05 & log(FC) > 2) and ranking (descending by log(FC)) the genes by statistical threshold , several genes are display due to its high expression level and siginificance (see Figure 2). Numbers of differential expressed genes in "With exposure" - "Without exposure" are extremely fewer than other two comparisons. It is probably caused by the high similarity between "With exposure" and "Without exposure".

### Figure 1. Heatmap
Hierarchical clustering    |  K-means clustering
:-------------------------:|:-------------------------:
<img src="https://github.com/TK-CamBaz/RNA-seq-data-analysis-DEMO/blob/main/FigureTable/heatmap_H.png"  height=250>|<img src="https://github.com/TK-CamBaz/RNA-seq-data-analysis-DEMO/blob/main/FigureTable/heatmap_K.png" height=250>

### Figure 2. Differential expressed genes bar chart
<img src="https://github.com/TK-CamBaz/RNA-seq-data-analysis-DEMO/blob/main/FigureTable/sig_gene_stats.png"  width=300>

### Figure 3. Volcano plot
Without Exposure vs Reference   |  With Exposure vs Without Exposure   |  With Exposure vs Reference 
:-------------------------:|:-------------------------:|:-------------------------:
<img src="https://github.com/TK-CamBaz/RNA-seq-data-analysis-DEMO/blob/main/FigureTable/volcano_plot_woe_ref.png">|<img src="https://github.com/TK-CamBaz/RNA-seq-data-analysis-DEMO/blob/main/FigureTable/volcano_plot_we_woe.png">|<img src="https://github.com/TK-CamBaz/RNA-seq-data-analysis-DEMO/blob/main/FigureTable/volcano_plot_we_ref.png">

### Table 1. Top 5 up/down regulated differential expressed genes for each comparison
<img src="https://github.com/TK-CamBaz/RNA-seq-data-analysis-DEMO/blob/main/FigureTable/top5function_for_updown.png" width=300>
Ranked by log(Fold change).

### Table 1. Up/down regulated pathways for each comparison
Over-representation analysis    |  Gene set enrichment analysis
:-------------------------:|:-------------------------:
<img src="https://github.com/TK-CamBaz/RNA-seq-data-analysis-DEMO/blob/main/FigureTable/pathway_ora.png" height=150>|<img src="https://github.com/TK-CamBaz/RNA-seq-data-analysis-DEMO/blob/main/FigureTable/pathway_gesa.png" height=150>


## Details of each step of flow chart
The design of RNA-seq data contains 3 treatments, including "With exposure", "Without exposure" and "Reference". The procedure of analysis consist of 5 steps: (1) Download from database / custom data, (2) Quality control, (3) Reference genome indexing, (4) Mapping to genome, (5) Read counts calculation and (6) DEG & enrichment analysis.

## Note
In this demo, I use three packages/web tools to improve the workflow of the analysis: 
1. Trimming sequence and generate QC report by **AfterQC** due to its versatility in quality control,
 data filtering, error profiling and base correction automatically. 
2. Annotating sequence by **eggNOG-mapper** which is a powerful function annotation and prediction web tool. 
3. Analyzing the gene counts matrix by **iDEP**, a web application with easy-to-use GUI for differential expression and pathway analysis, which saving a lot of time to understand R codes and debug.

## Reference
