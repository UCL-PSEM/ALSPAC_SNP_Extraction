# ALSPAC SNP Extractor

This pipeline allows researchers to rapidly extract specified SNPs of interest from ALSPAC genotyped data to use in analyses such as Mendelian Randomization, Polygenic Risk Scores, etc. 

It has been adapted from code created to perform a similar task in UK Biobank which can be found at https://github.com/asalzy/MRPipeline. It has been written to work on UCL's Myriad cluster but could easily be adapted for other environments. 

## Requirements

1) ALSPAC Genome-wide HRC Imputed Dataset - This consists of individual autosomal chromosome .bgen files supplied by ALSPAC with the naming convention 'filtered_01.bgen' to 'filtered_22.bgen'.

2) SNP List - A list of the desired SNPS for extraction. 

3) params file - A text file that allows the user to specify the desired directories for inputs/outputs/etc.

4) ALSPAC_SNP_Extraction.sh - The script to run the programme.

## How To Use

### 1) Create SNP List

The pipeline requires a list of SNPs provided as a single column in a text file. ALSPAC bgen files list SNPs by chr:pos, which are located by the script using the -incl-range function. As such, each SNP in the text file needs to be in the format of XX:xxxxxx-XX:xxxxxx, where the XX is the chromosome number and the xxxxxx is the same BP position (e.g. 02:123456-02:123456). If extracting SNPs from a table of summary statistics, this text file can easily be created in one step using an awk command similar to the following:

`awk 'NR>1 {chr_bp = ($2 < 10 ? "0"$2 : $2) ":" $3; print chr_bp "-" $3}' /path/to/your/summary_stats.txt > /path/to/your/SNP_list.txt`

### 2) Modify Params File

This file tells the script where to find the QCed dataset, where to find the SNP list, and where to output the results. It can be easily accessed and altered using a command such as vim.

### 3) Install and Run Script

1) Clone this GitHub repo into your directory of choice using the command

```
git clone https://github.com/scottchiesa/ALSPAC_SNP_Extraction/
```

2) Run the script usng the command

```
sh ./ALSPAC_SNP_Extraction.sh -b
````

If you have updated the params file with all of the necessary information, this will create a single .bgen file containing only the desired SNPS. If you want a .gen file, use -g instead of -b. If you haven't set the params file, you can manually set the required parameters using a command such as

```
sh ./ALSPAC_SNP_Extraction.sh -b -s path/to/SNP_list.txt -o path/to/output_directory -n filename_for_output_file
```






