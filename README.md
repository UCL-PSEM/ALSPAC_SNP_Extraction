# PSEM ALSPAC SNP Extractor

This pipeline allows researchers working in the UCL Department of Population Science and Experimental Medicine to rapidly extract specified SNPs of interest from ALSPAC Genetic Data for future use in a range of analyses such as Mendelian Randomization, creation of Polygenic Risk Scores, etc. 

## Getting Started

The pipeline is written to work within the UCL Myriad HPC using the ALSPAC Genome-wide - HRC Imputed Dataset, which consists of individual chromosome .bgen files named 'filtered_01.bgen' to 'filtered_22.bgen'.

It requires the following files to operate:

ALSPAC_SNP_Extraction.sh - The code to run the programme.

params - A text file that allows the user to specify the necessary directories on their operating system.

SNP List - A list of the desired SNPS for extraction. 

