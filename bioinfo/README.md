---
sort: 3
---

# Bioinformatics and phylogenetics

source: `{{ page.path }}`

{% include list.liquid all=true %}


<span class="badge badge-info">A quick overview on phylogenetics</span>


:link: **Useful resources for molecular phylogenetics**

* [Sydney Phylo Workshop](https://github.com/simon-ho/SydneyPhyloWorkshop) by Simon Ho provides some excellent lecture notes and workshops with dataset
* [Phylogenetic Biology](https://github.com/Phylogenetics-Brown-BIOL1425/phylogeneticbiology) by Casey Dunn at Brown University is a great source of lecture and practical material. It also has a an extensive list of extra resources and useful links to reading material
* [RevBayes](https://github.com/revbayes) github page has a wealth of information specifically around the software but also includes some general phylogenetics material as well. Tutorial pages available [here](https://revbayes.github.io/tutorials/), a example of workshop page on molecular phylogenetics and fossil data available [here](http://phyloworks.org/revbayes-workshop2017/)
* [Taming the BEAST](https://taming-the-beast.org/tutorials/Introduction-to-BEAST2/) workshops around the use of BEAST software for Phylogenetics
* [Bayesian MCMC phylogenetics tutorial in R](https://github.com/thednainus/Bayesian_tutorial) - for those wanting an R interface for their Phylogenetics
* [Collection of tutorials on phylogenetics](https://github.com/mmatschiner/tutorials) by Michael Matschiner. This goes through the workflow from sequence analysis through to dating and more
* [Data Integration, Manipulation and Visualization of Phylogenetic Trees](https://yulab-smu.github.io/treedata-book/index.html)

Broadly conducting a phylogenetic analysis can be broken down in the following steps:

1. Obtain sequences (e.g. your own sequences - ensure you perform approriate QC methods, or reference sequences from Genbank etc)
    - [NCBI Genbank](https://www.ncbi.nlm.nih.gov/genbank/)
    - [NCBI Genome](https://www.ncbi.nlm.nih.gov/genome/)
    - [NCBI Protein](https://www.ncbi.nlm.nih.gov/protein/)
2. Align sequences
    - [MUSCLE, Edgar](https://drive5.com/muscle/)
    - [MAFFT](https://mafft.cbrc.jp/alignment/software/)
    - [Clustal](http://www.clustal.org/)
3. Decide on appropriate method and model - this will differ depending on your study question, data available, gene(s), length of sequence, type of data (i.e. nucleotide, amino acid etc)
    - You will likely need to use some program to help you decide on most appropriate model
    - Some examples:
            - ModelFinder available via IQ-TREE
            - Model Selection tool available via MEGA
            - PhyML
4. Conduct phylogeny reconstruction (with or without bootstrap/node support)
    - Depending on analysis examples include:
            - IQ-TREE
            - MEGA
            - MrBayes
5. Visualize and edit tree
    - View tree using:
            - [FigTree](http://tree.bio.ed.ac.uk/software/figtree/)
            - More tree views [here](http://www.treedyn.org/overview/editors.html)
    - In addition to edits available in tree vieiwng programs listed above may want to edit using general image editing software, such as:
            - [InkScape](https://inkscape.org/) - free open source graphics editor
