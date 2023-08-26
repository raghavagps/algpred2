# AlgPred2.0
# Introduction
AlgPred2.0 is developed for predicting, mapping and scanning allergen peptides. More information on AlgPred2.0 is available from its web server http://webs.iiitd.edu.in/raghava/algpred2/ . This page provides information about standalone version of AlgPred2.0. Please read/cite following paper for complete information including algorithm behind AlgPred 2.0.

## PIP installation
PIP version is also available for easy installation and usage of this tool. The following command is required to install the package 
```
pip install algpred2
```
To know about the available option for the pip package, type the following command:
```
algpred2 -h
```

**Minimum USAGE**: Minimum ussage is "algpred2.py -i peptide.fa" where peptide.fa is an input fasta file. 
This will predict Allergenic peptides in fasta format. It will use other parameters by default. It will save output in "outfile.csv" in CSV (comma seperated variables).

**Full Usage**: Following is complete list of all options, you may get these options by "algpred2.py -h" 

```
usage: algpred2.py [-h] -i INPUT [-o OUTPUT] [-t THRESHOLD] [-m {1,2}] [-d {1,2}]

Please provide following arguments

optional arguments:
  -h, --help            show this help message and exit
  -i INPUT, --input INPUT
                        Input: protein or peptide sequence in FASTA format or
                        single sequence per line in single letter code
  -o OUTPUT, --output OUTPUT
                        Output: File for saving results by default outfile.csv
  -t THRESHOLD, --threshold THRESHOLD
                        Threshold: Value between 0 to 1 by default 0.3
  -m {1,2}, -- model Model
                        Model: 1: AAC based RF, 2: Hybrid, by default 1
  -d {1,2}, --display {1,2}
                        Display: 1:Allergen peptide, 2: All peptides, by
                        default 1
```

**Input File**: It allows users to provide input in two formats; i) FASTA format (standard) (e.g. peptide.fa) and ii) Simple Format. In case of simple format, file should have one one peptide sequence in a single line in single letter code (eg. peptide.seq). 

**Output File**: Program will save result in CSV format, in case user do not provide output file name, it will be stored in outfile.csv.

**Threshold**: User should provide threshold between 0 and 1, please note score is proportional to allergenic potential of peptide.

**Models**: In this program, two models have beeen incorporated;  
  i) Model1 for predicting given input peptide/protein sequence as Allergenic and Non-allergenic peptide/proteins using Random Forest based on amino-acid composition of the peptide/proteins; 
   
   ii) Model2 for predicting given input peptide/protein sequence as Allergenic and Non-allergenic peptide/proteins using Hybrid approach, which is the ensemble of Random Forest+ BLAST+ MERCI. It combines the scores generated from machine learning (RF), MERCI, and BLAST as Hybrid Score, and the prediction is based on Hybrid Score.


AlgPred2.0 Package Files
=======================
It contains following files, brief description of these files given below

INSTALLATION  	: Installation instructions

LICENSE       	: License information

envfile : This file provides the path information for BLAST and MERCI commands,and data required to run BLAST and MERCI

Database: This folder contains the BLAST database and IgE motif files

progs : This folder contains the program to run MERCI

README.md     	: This file provides information about this package

algpred2.py 	: Main python program 

rf_model        : Model file required for running Machine-learning model

peptide.fa	: Example file contains peptide sequences in FASTA format

peptide.seq	: Example file contains peptide sequences in simple format

protein.fa	: Example file contains protein sequences in FASTA format 

# Reference
Sharma et al. (2021) AlgPred 2.0: an improved method for predicting allergenic proteins and mapping of IgE epitopes, <a href="https://academic.oup.com/bib/advance-article-abstract/doi/10.1093/bib/bbaa294/5985292?fbclid=IwAR1Q-60U7U7Kkzhmb7e-J4_641Y7KiH2fSaOq4bdnaRLxmyoe-rr8J1htjA">Briefings in Bioinformatics,22(4): bbaa294.</a> 

