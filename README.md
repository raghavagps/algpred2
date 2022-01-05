# AlgPred2.0
# Introduction
AlgPred2.0 is developed for predicting, mapping and scanning allergen peptides. More information on AlgPred2.0 is available from its web server http://webs.iiitd.edu.in/raghava/. This page provides information about standalone version of AlgPred2.0. 

Minimum USAGE: Minimum ussage is "algpred2.py -i peptide.fa" where peptide.fa is an input fasta file. This will predict Allergenic peptides in fasta format. It will use other parameters by default. It will save output in "outfile.csv" in CSV (comma seperated variables).

Full Usage: Following is complete list of all options, you may get these options by "algpred2 -h" 

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


Input File: It allows users to provide input in two formats; i) FASTA format (standard) (e.g. peptide.fa) and ii) Simple Format. In case of simple format, file should have one one peptide sequence in a single line in single letter code (eg. peptide.seq). 

Output File: Program will save result in CSV format, in case user do not provide output file name, it will be stored in outfile.csv.

Threshold: User should provide threshold between 0 and 1, please note score is proportional to allergenic potential of peptide.

Models: In this program, two models have beeen incorporated;  i) Model1 for predicting given input peptide/protein sequence as Allergenic and Non-allergenic peptide/proteins using Random Forest based on amino-acid composition of the peptide/proteins; 

ii) Model2 for predicting given input peptide/protein sequence as Allergenic and Non-allergenic peptide/proteins using Hybrid approach, which is the ensemble of Random Forest+ BLAST+ MERCI. It combines the scores generated from machine learning (RF), MERCI, and BLAST as Hybrid Score, and the prediction is based on Hybrid Score.


AlgPred2.0 Package Files
=======================
It contain following files, brief descript of these files given below

INSTALLATION  	: Installation instructions

LICENSE       	: License information

envfile : This file provide the path information for BLAST and MERCI commands,and data required to run BLAST and MERCI

Database: This folder contains the BLAST database and IgE motif files

progs : This folder contains the program to run MERCI

README.md     	: This file provide information about this package

algpred2.py 	: Main python program 

rf_model        : Model file required for running Machine-learning model

peptide.fa	: Example file contain peptide sequences in FASTA format

peptide.seq	: Example file contain peptide sequences in simple format

protein.fa	: Example file contain protein sequences in FASTA format 



