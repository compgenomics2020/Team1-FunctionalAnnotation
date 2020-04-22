# Team1-FunctionalAnnotation
#### Team Members: Maria Ahmad, Manasa Vegesna, Shuheng Gan, Hyeonjeong Cheon, Kenji Gerhardt
#### A pipeline for annotating the genes of *Escherichia coli.*
#### This pipeline clusters the genes, then performs both *ab-initio* and homology-based functional annotation on the genes.

## **Usearch**
#### USearch performs sequence clustering using a greedy agglomerative algorithm, meaning it creates clusters and assigns cluster identity in the order of input sequences. Identity is calculated through the use of kmers in a heuristic manner.
* Input: Identified Gene sequences in FASTA format
* Output: FASTA format file with representative sequences of each indentified cluster. 

## **SignalP**
#### SignalP is a Signal Peptide Prediction Tool which identifies signal peptides from protein fasta files
* Version: 5.0 
* The path to the directory of where the executable script of the tool should be provided if the tool is not your path.
* output path should be provided 
* output is produced in gff3 format

## **TMHMM**
#### TMHMM is a Transmembrane Prediction Tool which identifies transmembrane proteins from protein fasta files
* Version: 2.0
* The path to the directory of where the executable script of the tool should be provided if the tool is not your path.
* output path should be provided 

## **PilerCR**
#### PilerCR is an *ab-initio* based tool which scans the assembled genome (not the genes) for CRISPR repeats.
- -in inputFile
- -out outputFile
- -noinfo
...This option stops the program from printing extra information in the report file.

#### The output files are in GFF format. 

## **InterProScan**
#### InterProScan is a function annotation tool that scans sequences against InterPro protein signature databases. It classifies proteins into families and predict domains and important sites. Signatures are predictive models constructed from multiple sequence alignments that can be used to classify proteins. Using protein signatures is often a more sensitive way of identifying protein function than pairwise sequence similarity searches, such as BLAST. InterPro combines four types of protein signatures (patterns, profiles, fingerprints and HMMs) from multiple databases.
* Version: 5.42
* Requirement: 
  - Perl 5.22
  - Python 3
  - Java 11
* input: centroid.fa (protein sequence)
* output: *.gff3 *.tsv *.xml

## **DeepARG**
#### DeepARG is a deep learning tool that annotate antibiotic resistance genes in metagenomes. It is composed of two models for two types of input: DeepARG-SS for short sequence reads from Next Generation Sequencing (NGS) technologies such as Ilummina and DeepARG-LS for long gene-like sequences from assembled samples.
* Requirement: Python 2.7
* input: centroid.fa (protein sequence)
* output:
  - output_file_name.align.daa, DIAMOND alignment archive
  - output_file_name.align.daa.tsv, tabular format. Default: qseqid sseqid pident length mismatch gapopen qstart qend sstart send evalue bitscore
  - output_file_name.mapping.ARG, contains the sequences with a probability >= --prob (0.8 default)
  - output_file_name.mapping.potential.ARG, contains the sequences with a probability < --prob (0.8 default)

## **EggNOG**
#### EggNOG-mapper is a fast functional annotation tool for genes and proteins. It uses precomputed orthologous groups and phylogenies from the eggNOG database which consists of Orthologous Groups( OGs) of proteins at taxonomic levels.
* Version: 2.0
* input: FASTA file
* -d database(bacterial: bact/ eukaryotic: euk/ archeal: arch)
* -m mode(HMMER/Diamond)
* -i inputFile
* --output outputFile
* -o ouptutDirectory

## Usage
* -i : specify clustering identity; default = 0.7
* -f : path to protein sequences directory
* -p : used to specify if the sequences are protein sequences or not
* -u : Usearch tool path
* -o : Output file path
* -s : Interproscan absolute path
* -d : DeepARG absolute path
* -e : EggNOG absolute path
* -p : SignalP Directory Path
* -t : TMHMM Directory Path
* -r : PilerCR Output Path (Must end in "/")

Execution: 

## Requirements 
This pipeline assumes all tools listed below and their dependencies have already been installed.

* [USEARCH](https://www.drive5.com/usearch/download.html)
* [SignalP](https://services.healthtech.dtu.dk/service.php?SignalP-5.0)
* [TMHMM](https://services.healthtech.dtu.dk/service.php?TMHMM-2.0)
* [PilerCR](https://www.drive5.com/pilercr/)
* [InterProScan](http://www.ebi.ac.uk/interpro/download/)
* [DeepARG](https://bench.cs.vt.edu/deeparg)
* [EggNOG-Mapper](https://github.com/eggnogdb/eggnog-mapper)

## Citations
1. Edgar,RC (2010) Search and clustering orders of magnitude faster than BLAST, Bioinformatics 26(19), 2460-2461.
doi: 10.1093/bioinformatics/btq461
2. Armenteros, J. J. A., Tsirigos, K. D., Sønderby, C. K., Petersen, T. N., Winther, O., Brunak, S., ... & Nielsen, H. (2019). SignalP 5.0 improves signal peptide predictions using deep neural networks. Nature biotechnology, 37(4), 420-423.
3. Krogh, A., Larsson, B., Von Heijne, G., & Sonnhammer, E. L. (2001). Predicting transmembrane protein topology with a hidden Markov model: application to complete genomes. Journal of molecular biology, 305(3), 567-580.
4. Edgar, R.C. (2007) PILER-CR: fast and accurate identification of CRISPR repeats, BMC Bioinformatics, Jan 20;8:18.
5. Jones, Philip, et al. "InterProScan 5: genome-scale protein function classification." Bioinformatics 30.9 (2014): 1236-1240.
6. Arango-Argoty, Gustavo, et al. "DeepARG: a deep learning approach for predicting antibiotic resistance genes from metagenomic data." Microbiome 6.1 (2018): 1-15.
7.  Fast genome-wide functional annotation through orthology assignment by eggNOG-mapper. Jaime Huerta-Cepas, Kristoffer Forslund, Luis Pedro Coelho, Damian Szklarczyk, Lars Juhl Jensen, Christian von Mering and Peer Bork.Mol Biol Evol (2017). [doi: 10.1093/molbev/msx148](https://doi.org/10.1093/molbev/msx148)
8. Fast genome-wide functional annotation through orthology assignment by eggNOG-mapper. Jaime Huerta-Cepas, Damian Szklarczyk, Lars Juhl Jensen, Christian von Mering and Peer Bork. Submitted (2016).

