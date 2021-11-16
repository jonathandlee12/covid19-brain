# Severe COVID-19 induces molecular signatures of aging in the human brain
This repository provides instructions, code, and supplementary data files to reproduce results and figures from our COVID-19 brain aging paper 
> M Mavrikaki*, JD Lee*, IH Solomon, FJ Slack. Severe COVID-19 induces molecular signatures of aging in the human brain, bioRxiv (2021). 

## Abstract

Coronavirus disease 2019 (COVID-19) is predominantly an acute respiratory disease caused by severe acute respiratory syndrome coronavirus 2 (SARS-CoV-2) and remains a significant threat to public health. COVID-19 is accompanied by neurological symptoms and cognitive decline, but the molecular mechanisms underlying this effect remain unclear. As aging induces distinct molecular signatures in the brain associated with cognitive decline in healthy populations, we hypothesized that COVID-19 may induce molecular signatures of aging. Here, we performed whole transcriptomic analysis of human frontal cortex, a critical area for cognitive function, in 12 COVID-19 cases and age- and sex-matched uninfected controls. COVID-19 induces profound changes in gene expression, despite the absence of detectable virus in brain tissue. Pathway analysis shows downregulation of genes involved in synaptic function and cognition and upregulation of genes involved in immune processes. Comparison with five independent transcriptomic datasets of aging human frontal cortex reveals striking similarities between aged individuals and severe COVID-19 patients. Critically, individuals below 65 years of age exhibit profound transcriptomic changes not observed among older individuals in our patient cohort. Our data indicate that severe COVID-19 induces molecular signatures of aging in the human brain and emphasize the value of neurological follow-up in recovered individuals.

## Code information

The available [R markdown file](https://github.com/jonathandlee12/covid19-brain/blob/main/covid19_aging_rscripts_final.Rmd) contains R scripts used to generate all figures and data tables available with the current iteration of the manuscript. The code was last run 11/15/2021. 

## Resources for data preprocessing
- [SARS-CoV-2 reference genome](https://www.ncbi.nlm.nih.gov/nuccore/1798174254)
- [Ensembl v104 reference transcriptome](http://ftp.ensembl.org/pub/release-104/fasta/homo_sapiens/cdna/Homo_sapiens.GRCh38.cdna.all.fa.gz)
- [Calu-3 SARS-CoV-2- and mock-infected transcriptomes (.fastq)](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE147507), accession numbers GSM4462348-GSM4462353
- [Frontal cortex transcriptome profiles from this manuscript (.fastq)](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE188847)

## Resources for data analysis
- [Transcriptome alignment of frontal cortex transcriptome profiles (.sf)](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE188847)
- [Cohort characteristics](https://github.com/jonathandlee12/covid19-brain/blob/main/TableS1_patient_info.csv) may also be found in Supplementary Table 1
- [Processed aging datasets](https://github.com/jonathandlee12/covid19-brain/blob/main/master_aging_genesets.txt) may also be found in Supplementary Table 4a, original analysis files may be found below:
  - [Lu et al. 2004](https://static-content.springer.com/esm/art%3A10.1038%2Fnature02661/MediaObjects/41586_2004_BFnature02661_MOESM5_ESM.xls)
  - [Loerch et al. 2008](https://doi.org/10.1371/journal.pone.0003329.s007)
  - [ROSMAP (Supplementary Table 1 of Zullo et al.), Common Mind Consortium/CMC (Supplementary Table 3 of Zullo et al.), and Gibbs (Supplementary Table 5 of Zullo et al.)](https://static-content.springer.com/esm/art%3A10.1038%2Fs41586-019-1647-8/MediaObjects/41586_2019_1647_MOESM3_ESM.zip)
- [Transcript-to-gene mappings (from biomaRt)](https://github.com/jonathandlee12/covid19-brain/blob/main/tx2gene.txt)

## Session Info from R

Analyses were run on a Macbook Pro (M1, 2020), Big Sur v11.2.3. 

sessionInfo() output is as follows:

R version 4.0.4 (2021-02-15)
Platform: x86_64-apple-darwin17.0 (64-bit)
Running under: macOS Big Sur 10.16

Matrix products: default
LAPACK: /Library/Frameworks/R.framework/Versions/4.0/Resources/lib/libRlapack.dylib

locale:
[1] en_US.UTF-8/en_US.UTF-8/en_US.UTF-8/C/en_US.UTF-8/en_US.UTF-8

attached base packages:
[1] parallel  stats4    stats     graphics  grDevices utils     datasets  methods   base     

other attached packages:
 [1] viridis_0.6.0               viridisLite_0.4.0           Rtsne_0.15                  DESeq2_1.30.1              
 [5] SummarizedExperiment_1.20.0 MatrixGenerics_1.2.1        matrixStats_0.58.0          GenomicRanges_1.42.0       
 [9] GenomeInfoDb_1.26.7         KEGGREST_1.30.1             tximport_1.18.0             pheatmap_1.0.12            
[13] reshape2_1.4.4              dplyr_1.0.5                 org.Hs.eg.db_3.12.0         biomaRt_2.46.3             
[17] fgsea_1.16.0                reactome.db_1.74.0          gProfileR_0.7.0             GO.db_3.12.1               
[21] AnnotationDbi_1.52.0        IRanges_2.24.1              S4Vectors_0.28.1            Biobase_2.50.0             
[25] BiocGenerics_0.36.1         ggrepel_0.9.1               ggplot2_3.3.3               stringr_1.4.0              
[29] limma_3.46.0                preprocessCore_1.52.1      

loaded via a namespace (and not attached):
 [1] bitops_1.0-7           bit64_4.0.5            RColorBrewer_1.1-2     progress_1.2.2         httr_1.4.2            
 [6] tools_4.0.4            utf8_1.2.1             R6_2.5.0               DBI_1.1.1              colorspace_2.0-0      
[11] withr_2.4.2            tidyselect_1.1.1       gridExtra_2.3          prettyunits_1.1.1      bit_4.0.4             
[16] curl_4.3.1             compiler_4.0.4         cli_2.5.0              xml2_1.3.2             DelayedArray_0.16.3   
[21] labeling_0.4.2         scales_1.1.1           readr_1.4.0            genefilter_1.72.1      askpass_1.1           
[26] rappdirs_0.3.3         digest_0.6.27          rmarkdown_2.7          XVector_0.30.0         htmltools_0.5.1.1     
[31] pkgconfig_2.0.3        dbplyr_2.1.1           fastmap_1.1.0          rlang_0.4.11           rstudioapi_0.13       
[36] RSQLite_2.2.7          farver_2.1.0           generics_0.1.0         jsonlite_1.7.2         BiocParallel_1.24.1   
[41] RCurl_1.98-1.3         magrittr_2.0.1         GenomeInfoDbData_1.2.4 Matrix_1.3-4           Rcpp_1.0.7            
[46] munsell_0.5.0          fansi_0.4.2            lifecycle_1.0.0        yaml_2.2.1             stringi_1.5.3         
[51] zlibbioc_1.36.0        plyr_1.8.6             BiocFileCache_1.14.0   grid_4.0.4             blob_1.2.1            
[56] crayon_1.4.1           lattice_0.20-44        splines_4.0.4          Biostrings_2.58.0      annotate_1.68.0       
[61] hms_1.0.0              locfit_1.5-9.4         knitr_1.33             pillar_1.6.0           geneplotter_1.68.0    
[66] fastmatch_1.1-0        XML_3.99-0.6           glue_1.4.2             evaluate_0.14          data.table_1.14.0     
[71] vctrs_0.3.8            png_0.1-7              gtable_0.3.0           openssl_1.4.4          purrr_0.3.4           
[76] assertthat_0.2.1       cachem_1.0.4           xfun_0.22              xtable_1.8-4           survival_3.2-11       
[81] tibble_3.1.1           memoise_2.0.0          ellipsis_0.3.2        
