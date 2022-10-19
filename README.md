# Severe COVID-19 is associated with molecular signatures of aging in the human brain
This repository provides instructions, code, and supplementary data files to reproduce results and figures from our COVID-19 brain aging paper 
> M Mavrikaki*, JD Lee*, IH Solomon, FJ Slack. Severe COVID-19 is associated with molecular signatures of aging
in the human brain, Nature Aging (2022). 

## Abstract

As COVID-19 and aging are both accompanied by cognitive decline, we hypothesized that COVID-19 might lead to molecular signatures similar to aging. We performed a whole-transcriptome analysis of frontal cortex, a critical area for cognitive function, in COVID-19 patients, age/sex-matched uninfected controls, and uninfected cases with ICU/ventilator treatment. Our findings indicate that severe COVID-19 is associated with molecular signatures of brain aging and emphasize the value of neurological follow-up in recovered individuals.

## Code information

The available [R markdown file](https://github.com/jonathandlee12/covid19-brain/blob/main/covid19_aging_rscripts_final.Rmd) contains R scripts used to generate all figures and data tables available with the current iteration of the manuscript. The code was last run 10/16/2022. 

## Resources for data preprocessing
- [SARS-CoV-2 reference genome](https://www.ncbi.nlm.nih.gov/nuccore/1798174254)
- [Ensembl v104 reference transcriptome](http://ftp.ensembl.org/pub/release-104/fasta/homo_sapiens/cdna/Homo_sapiens.GRCh38.cdna.all.fa.gz)
- [Calu-3 SARS-CoV-2- and mock-infected transcriptomes (.fastq)](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE147507), accession numbers GSM4462348-GSM4462353
- [Frontal cortex transcriptome profiles from this manuscript (.fastq)](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE188847)

## Resources for data analysis
- [Transcriptome alignment files from frontal cortex transcriptome profiles](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE188847) are required to reproduce this analysis
- [Cohort characteristics - COVID-19](https://github.com/jonathandlee12/covid19-brain/blob/main/TableS1_covid.csv) may also be found in Supplementary Table 1
- [Cohort characteristics - Aging](https://github.com/jonathandlee12/covid19-brain/blob/main/TableS1_aging.csv) may also be found in Supplementary Table 1
- [Processed aging datasets](https://github.com/jonathandlee12/covid19-brain/blob/main/master_aging_genesets.txt) may also be found in Supplementary Table 4a, original analysis files may be found below:
  - [Lu et al. 2004](https://static-content.springer.com/esm/art%3A10.1038%2Fnature02661/MediaObjects/41586_2004_BFnature02661_MOESM5_ESM.xls)
  - [Loerch et al. 2008](https://doi.org/10.1371/journal.pone.0003329.s007)
  - [ROSMAP (Supplementary Table 1 of Zullo et al.), Common Mind Consortium/CMC (Supplementary Table 3 of Zullo et al.), and Gibbs (Supplementary Table 5 of Zullo et al.)](https://static-content.springer.com/esm/art%3A10.1038%2Fs41586-019-1647-8/MediaObjects/41586_2019_1647_MOESM3_ESM.zip)
- [Transcript-to-gene mappings (from biomaRt)](https://github.com/jonathandlee12/covid19-brain/blob/main/tx2gene.txt)
- [ROSMAP preprocessed RNA-seq dataset](https://www.synapse.org/#!Synapse:syn8691134)
- [ROSMAP clinical annotation](https://www.synapse.org/Portal.html#!Synapse:syn3157322)
- [ROSMAP biospecimen metadata](https://www.synapse.org/Portal.html#!Synapse:syn3157322)

## Session Info from R

Analyses were run on a Macbook Pro (M1, 2020), Big Sur v11.2.3. 

sessionInfo() output is as follows:

R version 4.0.4 (2021-02-15)
Platform: x86_64-apple-darwin17.0 (64-bit)
Running under: macOS Big Sur 11.2.3

Matrix products: default
LAPACK: /Library/Frameworks/R.framework/Versions/4.0/Resources/lib/libRlapack.dylib

locale:
[1] en_US.UTF-8/en_US.UTF-8/en_US.UTF-8/C/en_US.UTF-8/en_US.UTF-8

attached base packages:
[1] parallel  stats4    stats     graphics  grDevices utils     datasets  methods   base     

other attached packages:
 [1] viridis_0.6.0               viridisLite_0.4.0           Rtsne_0.15                 
 [4] DESeq2_1.30.1               SummarizedExperiment_1.20.0 MatrixGenerics_1.2.1       
 [7] matrixStats_0.58.0          GenomicRanges_1.42.0        GenomeInfoDb_1.26.7        
[10] KEGGREST_1.30.1             tximport_1.18.0             pheatmap_1.0.12            
[13] reshape2_1.4.4              dplyr_1.0.5                 org.Hs.eg.db_3.12.0        
[16] biomaRt_2.46.3              fgsea_1.16.0                reactome.db_1.74.0         
[19] gProfileR_0.7.0             GO.db_3.12.1                AnnotationDbi_1.52.0       
[22] IRanges_2.24.1              S4Vectors_0.28.1            Biobase_2.50.0             
[25] BiocGenerics_0.36.1         ggrepel_0.9.1               ggplot2_3.3.3              
[28] stringr_1.4.0               limma_3.46.0                preprocessCore_1.52.1      

loaded via a namespace (and not attached):
 [1] colorspace_2.0-0       ellipsis_0.3.2         XVector_0.30.0         rstudioapi_0.13       
 [5] farver_2.1.0           bit64_4.0.5            mvtnorm_1.1-1          fansi_0.4.2           
 [9] apeglm_1.12.0          xml2_1.3.2             splines_4.0.4          cachem_1.0.4          
[13] geneplotter_1.68.0     knitr_1.33             jsonlite_1.7.2         annotate_1.68.0       
[17] dbplyr_2.1.1           png_0.1-7              readr_1.4.0            compiler_4.0.4        
[21] httr_1.4.2             assertthat_0.2.1       Matrix_1.3-4           fastmap_1.1.0         
[25] cli_2.5.0              htmltools_0.5.2        prettyunits_1.1.1      tools_4.0.4           
[29] coda_0.19-4            gtable_0.3.0           glue_1.4.2             GenomeInfoDbData_1.2.4
[33] rappdirs_0.3.3         fastmatch_1.1-0        Rcpp_1.0.7             bbmle_1.0.23.1        
[37] vctrs_0.3.8            Biostrings_2.58.0      nlme_3.1-152           xfun_0.31             
[41] lifecycle_1.0.0        XML_3.99-0.6           MASS_7.3-54            zlibbioc_1.36.0       
[45] scales_1.1.1           hms_1.0.0              RColorBrewer_1.1-2     yaml_2.2.1            
[49] curl_4.3.1             memoise_2.0.0          gridExtra_2.3          emdbook_1.3.12        
[53] bdsmatrix_1.3-4        stringi_1.5.3          RSQLite_2.2.7          genefilter_1.72.1     
[57] BiocParallel_1.24.1    rlang_0.4.11           pkgconfig_2.0.3        bitops_1.0-7          
[61] evaluate_0.14          lattice_0.20-44        purrr_0.3.4            labeling_0.4.2        
[65] bit_4.0.4              tidyselect_1.1.1       plyr_1.8.7             magrittr_2.0.1        
[69] R6_2.5.0               generics_0.1.0         DelayedArray_0.16.3    DBI_1.1.1             
[73] mgcv_1.8-35            pillar_1.6.0           withr_2.4.2            survival_3.2-11       
[77] RCurl_1.98-1.3         tibble_3.1.1           crayon_1.4.1           utf8_1.2.1            
[81] BiocFileCache_1.14.0   rmarkdown_2.14         progress_1.2.2         locfit_1.5-9.4        
[85] grid_4.0.4             data.table_1.14.0      blob_1.2.1             digest_0.6.27         
[89] xtable_1.8-4           numDeriv_2016.8-1.1    openssl_1.4.4          munsell_0.5.0         
[93] askpass_1.1  
