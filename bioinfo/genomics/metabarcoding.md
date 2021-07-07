---
sort: 1
---

# Metabarcoding

source: `{{ page.path }}`

{% include list.liquid all=true %}

<span class="badge badge-info">Analysis of amplicon metabarcoding next generation sequencing data</span>


:link: **Useful resources**


- [Microbiome notes by Mikhail Dozmorov](https://github.com/mdozmorov/Microbiome_notes)
- [Metagenomics R packages](https://rdrr.io/category/biocview/Metagenomics/)
- [Introduction to the microbiome R package by Leo Lahti, Sudarshan Shetty et al.](https://microbiome.github.io/tutorials/), [core microbiome](https://microbiome.github.io/tutorials/Core.html) - Tools for microbiome analysis; with multiple example data sets from published studies; extending the phyloseq class. The package is in Bioconductor and aims to provide a comprehensive collection of tools and tutorials, with a particular focus on amplicon sequencing data.
- [How to give life to your microbiome data by Ruth Schmidt](https://towardsdatascience.com/how-to-give-life-to-your-microbiome-data-using-plotly-r-1892281183cf) - A tutorial on how to use Plotly’s R graphing library for microbiome data analysis and visualization. Also see [GitHub](https://github.com/ruthlys/) for more useful info.
- [omicplotR](https://github.com/dgiguer/omicplotR) - An R package to visualize high-throughput sequencing data.
- [MICrobial Community Analysis (micca)](https://micca.readthedocs.io/en/1.7.2/index.html) - software pipeline for the processing of amplicon sequencing data, from raw sequences to OTU tables, taxonomy classification and phylogenetic tree inference. The pipeline can be applied to a range of highly conserved genes/spacers, such as 16S rRNA gene, Internal Transcribed Spacer (ITS) 18S and 28S rRNA.
- [phyloseq tutoial by Daniel Vaulot](https://vaulot.github.io/tutorials/Phyloseq_tutorial.html#content) - This document explains the use of the phyloseq R library to analyze metabarcoding data.
-[Otago Uni eDNA GitHub page](https://github.com/otagoedna)
-[Amplicon analysis with QIIME2 - VL microbiome project by Rachael Lappan](https://rachaellappan.github.io/VL-QIIME2-analysis/)
- [Workflow for Microbiome Data Analysis: from raw reads to community analyses by Benjamin J Callahan](https://bioconductor.org/help/course-materials/2017/BioC2017/Day1/Workshops/Microbiome/MicrobiomeWorkflowII.html#abstract)
- [MicrobiomeR](https://microbiomer.vallenderlab.org/) - An R package for microbiome analysis that incorporates phyloseq, metacoder, taxa, and microbiome in order to standardize and simplify common microbiome workflows.
- [microeco: An R package for data mining in microbial community ecology by Chi Liu, Minjie Yao](https://chiliubio.github.io/microeco/)
- [ampvis2](https://madsalbertsen.github.io/ampvis2/index.html) - ampvis2 is an R-package to conveniently visualise and analyse 16S rRNA amplicon data in different ways.
- [microbiomeseq](https://github.com/umerijaz/microbiomeSeq) - This R package is developed to enhance the available statistical analysis procedures in R by providing more analysis produre and visualisation of results for microbial communities data obtained from 16S rRNA.
- [Analysis of Microbiome Community Data in R by Grunwald lab](https://grunwaldlab.github.io/analysis_of_microbiome_community_data_in_r/index.html)
- [MCSMRT Microbiome Classifier for SMRT PacBio data](https://github.com/jpearl01/mcsmrt) - a tool to cluster PacBio FL16S amplicon microbiome sequences into Operational Taxonomic Units (OTU) and assign species level taxonomic classifications. Outputs include a table of read counts assigned to each OTU centroid sequence (per sample) with corresponding taxonomic lineage, and a a table of read specific metrics (e.g., CCS count, expected error, length, primer matching result, etc.).
- [Bioplatforms Australia - Operational taxonomic unit (OTU) query system](https://github.com/BioplatformsAustralia/bpaotu) - BPA-OTU is a web-based portal into Operational Taxonomic Unit (OTU) data, developed to access data from the Australian Microbiome.
- [AusMicrobiome metagenome](https://github.com/martinostrowski/metagenome) - *In development* An assembly and annotation pipeline using standardised tools to characterise shotgun metagenomes produced by the Marine Microbes and Australian Microbiome Project.

## Additional analysis

- [decontam R package](https://benjjneb.github.io/decontam/vignettes/decontam_intro.html) - R package that outlines benchmarking, and demonstrates the benefits of `decontam`-inating your data for more accurate profiling of microbial communities.
- [The PR3 primer database](https://app.pr2-primers.org/) - A database of eukaryotic rRNA primers and primer sets for metabarcoding studies compiled from the literature.
- [Managing Batch Effects in Microbiome Data by Yiwen Wang, Kim-Anh Lê Cao](https://evayiwenwang.github.io/Managing_batch_effects/)

## RShiny

- [Biome-Shiny](https://github.com/Biodata-PT/Biome-Shiny) - A Shiny R app for microbiome visualization.
- [Dynamic Assessment of Microbial Ecology (DAME)](https://acnc-shinyapps.shinyapps.io/DAME/) - This R Shiny app is an open source platform that uses the R environment to perform microbial ecology data analyses (designed for QIIME1 output).
- [animalcules](https://compbiomed.github.io/animalcules-docs/index.html) - animalcules is an R package/R Shiny app for utilizing up-to-date data analytics, visualization methods, and machine learning models to provide users an easy-to-use interactive microbiome analysis framework.
- [An R package for the analysis and visualization of microbial communities by Janina Reeder ](https://github.com/zoecastillo/microbiomeExplorer) - The microbiomeExplorer package and the Shiny application contained with it provides methods and visualizations to explore the results of 16S rRNA amplicon sequencing experiment.

## Sample size calculator

Links to some useful resources for calculating power and sample size in microbiome studies. Good for grant and project proposals to show you have thought about sample size etc.

Some general points to consider

- What population should I target?
- How should I collect and store the samples? (CONTROLS!!!)
- What am I targeting and how should i extract?
- What sequencing approach should I use, amplicon or whole shotgun metagenome? Will there be PCR involved or do I want a pre-PCR library preparation method?
- How deeply should I sequence?

**References**

- Mattiello F, Verbist B, Faust K, Raes J, Shannon WD, Bijnens L, Thas O. A web application for sample size and power calculation in case-control microbiome studies. Bioinformatics. 2016 Jul 1;32(13):2038-40. doi: [10.1093/bioinformatics/btw099](https://doi.org/10.1093/bioinformatics/btw099)
- Kelly BJ, Gross R, Bittinger K, Sherrill-Mix S, Lewis JD, Collman RG, Bushman FD, Li H. Power and sample-size estimation for microbiome studies using pairwise distances and PERMANOVA. Bioinformatics. 2015 Aug 1;31(15):2461-8. doi: [10.1093/bioinformatics/btv183](https://doi.org/10.1093/bioinformatics/btv183)
- Casals-Pascual C, González A, Vázquez-Baeza Y, Song SJ, Jiang L, Knight R. Microbial Diversity in Clinical Microbiome Studies: Sample Size and Statistical Power Considerations. Gastroenterology. 2020 May;158(6):1524-1528. doi: [10.1053/j.gastro.2019.11.305](https://doi.org/10.1053/j.gastro.2019.11.305).
