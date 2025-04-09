# ALSPAC SNP Extractor

This pipeline allows researchers to rapidly extract specified SNPs of interest from ALSPAC genotyped data to use in analyses such as Mendelian Randomization, creation of Polygenic Risk Scores, etc. 

It has been adapted from code created to perform a similar task in UK Biobank - available here https://github.com/asalzy/MRPipeline.  It has been written to work UCL's Myriad cluster, but could easily be adapted for other environments. 

## Requirements

ALSPAC Genome-wide HRC Imputed Dataset - This consists of individual chromosome .bgen files supplied by ALSPAC with the naming convention 'filtered_01.bgen' to 'filtered_22.bgen'.

SNP List - A list of the desired SNPS for extraction. 

params - A text file that allows the user to specify the desired directories for inputs/outputs/etc.

ALSPAC_SNP_Extraction.sh - The script to run the programme.







