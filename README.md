# Team1-FunctionalAnnotation
#### Team Members: Maria Ahmad, Manasa Vegesna, Shuheng Gan, Hyeonjeong Cheon, Kenji Gerhardt
#### A pipeline for annotating the genes of *Escherichia coli.*
#### This pipeline clusters the genes, then performs both *ab-initio* and homology-based functional annotation on the genes.

## **Usearch**
#### Usearch is * insert description of usearch *
- insert parameter options etc.

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
#### InterProScan is * insert description of usearch *
- insert parameter options etc.

## **DeepARG**
#### DeepARG is * insert description of usearch *
- insert parameter options etc.

## **EggNOG**
#### EggNOG is * insert description of usearch *
- insert parameter options etc.

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
1. USearch citation
2. Armenteros, J. J. A., Tsirigos, K. D., Sønderby, C. K., Petersen, T. N., Winther, O., Brunak, S., ... & Nielsen, H. (2019). SignalP 5.0 improves signal peptide predictions using deep neural networks. Nature biotechnology, 37(4), 420-423.
3. Krogh, A., Larsson, B., Von Heijne, G., & Sonnhammer, E. L. (2001). Predicting transmembrane protein topology with a hidden Markov model: application to complete genomes. Journal of molecular biology, 305(3), 567-580.
4. Edgar, R.C. (2007) PILER-CR: fast and accurate identification of CRISPR repeats, BMC Bioinformatics, Jan 20;8:18.
5. InterProScan citation
6. DeepARG citation
7.  Fast genome-wide functional annotation through orthology assignment by eggNOG-mapper. Jaime Huerta-Cepas, Kristoffer Forslund, Luis Pedro Coelho, Damian Szklarczyk, Lars Juhl Jensen, Christian von Mering and Peer Bork.Mol Biol Evol (2017). [doi: 10.1093/molbev/msx148](https://doi.org/10.1093/molbev/msx148)

