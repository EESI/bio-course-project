# bio-course-projecct

Course project for the Bioinformatics course.    

## Background
The novel coronavirus responsible for COVID-19, SARS-CoV-2, expanded to reportedly over 30.6 million confirmed cases worldwide by September  20, 2020. The global SARS-CoV-2 pandemic highlights the importance of tracking viral transmission dynamics in real-time. Through September 2020, researchers have obtained genetic sequences of SARS-CoV-2 from over 100 thousand samples from infected individuals worldwide. Since the virus readily mutates, each sequence of an infected individual contains useful mutational signature information linked to the virus subtypes. But, there are over 30,000 bases in the full SARS-CoV-2 genome, so tracking genetic variants on a whole-sequence basis becomes unwieldy. [EESI laboratory](https://drexeleesi.com/) led by Dr. Gail Rosen has developed an efficient tool to quickly idenitfy and label genetic variants, a.k.a., "subtypes" of SARS-CoV-2 sequences. This method defines a compact set of nucleotide sites that characterize the most variable (and thus most informative) positions in the viral genomes sequenced from different individuals, called an Informative Subtype Marker or *ISM*. This tool defines viral subtypes for each ISM, and analyze the regional distribution of subtypes to track the progress of the pandemic.
ncov_ism (Novel Coronavirus Informative Subtype Marker) is an efficient framework for genetic subtyping of a pandemic virus and implement it for SARS-CoV-2, the novel coronavirus that causes COVID-19. For detailed information about this method, please refer to the manuscript pubilished in PLOS Computational Biology, [Genetic grouping of SARS-CoV-2 coronavirus sequences using informative subtype markers for pandemic spread visualization](https://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1008269). A command line tool, *ncov-ism*, based on the method described in the paper is made available at [here](https://github.com/EESI/ncov_ism). Scientists have detected SARS-CoV-2 virus in the wastewater in California (see the preprint [here](https://www.medrxiv.org/content/10.1101/2020.09.13.20193805v1.full.pdf)). And in their preprint, the results indicates that their wastewater sequencing can provide evidence for recent introductions of viral lineages before they are detected by local clinical sequencing. Their method mainly considered single nucleotide variant (SNV). The goal of this project is to use *ncov-ism* method developed by EESI laboratory to label SARS-CoV-2 subtypes and compare them with subtypes identified worldwide.

## Procedures
1. Register for an account at [GISAID website](https://www.gisaid.org/) to download the latest sequence data (e.g., msa_0920 and nextmeta files from the *Downloads* tab). 

2. On [Proteus](https://proteusmaster.urcf.drexel.edu/urcfwiki/index.php/Main_Page),  install and run the default [*ncov_ism*](https://github.com/EESI/ncov_ism). This process will generate ISM positions in *ISM_annotation.txt* file and ISM subtypes for all sequences in *ISM_df_with_correction.csv* file.

3. Align the consensus SARS-CoV-2 sequences from [wastewater project](https://github.com/alexcritschristoph/wastewater_sarscov2/blob/master/data/wastewater/wastewater.fasta) to the reference sequence [NC_045512.2](https://www.ncbi.nlm.nih.gov/nuccore/NC_045512.2/) and then extract the nucleotides at ISM hotspots according to *ISM_annotation.txt* file from step 2.

4. Perform exploratory analysis to answer the following questions:
    - What subtype is each sample assigned to? 
    - Which region/country in the world does this subtype found most abundant?
    - These samples are collected in California in different dates. What are the most abundant subtype in California at those dates according to the *ISM_df_with_correction.csv* file?

5. The *ISM_df_with_correction.csv* file can be used to make ordination to reveal the ISM distribution similarity across different regions in the world ([Fig]( https://journals.plos.org/ploscompbiol/article/figure?id=10.1371/journal.pcbi.1008269.g007)). Please make such PCA plots for data collected by each months from 2020-1 to 2020-9 to show how the similarity of different regions change over time.

## Useful links
1. [GISAID](https://www.gisaid.org/)
2. [ISM](https://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1008269)
3. [*ncov_ism*](https://github.com/EESI/ncov_ism)
4. [wastewater](https://www.medrxiv.org/content/10.1101/2020.09.13.20193805v1.full.pdf)
5. [Proteus](https://proteusmaster.urcf.drexel.edu/urcfwiki/index.php/Main_Page)
6. [NC_045512.2](https://www.ncbi.nlm.nih.gov/nuccore/NC_045512.2/)