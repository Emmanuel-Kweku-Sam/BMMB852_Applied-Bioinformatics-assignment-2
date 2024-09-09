# BMMB852_Applied-Bioinformatics-assignment-2

Analysis of GFF3 file for Ursus maritimus (Polar Bear):

Introduction:
The analysis focuses on the *Ursus maritimus* (Polar Bear) genome, using the GFF3 file provided by Ensembl. The genome data was downloaded using the following command:

   wget ftp://ftp.ensembl.org/pub/current_gff3/ursus_maritimus/Ursus_maritimus.UrsMar_1.0.112.gff3.gz

After downloading, the file was unzipped using the following command:

   gunzip Ursus_maritimus.UrsMar_1.0.112.gff3.gz

The GFF3 file corresponds to the genome assembly **UrsMar_1.0** and contains detailed annotations such as exons, genes, and other genomic features.

1. Number of features in the file:
   Command: grep -v "^#" Ursus_maritimus.UrsMar_1.0.112.gff3 | wc -l
   Output: 1,186,643

2. Number of sequence regions (chromosomes) in the file:
   Command: grep "##sequence-region" Ursus_maritimus.UrsMar_1.0.112.gff3 | wc -l
   Output: 28

3. Number of genes listed in the file:
   Command: grep -w "gene" Ursus_maritimus.UrsMar_1.0.112.gff3 | wc -l
   Output: 64,997

4. Top 10 most annotated feature types:
   Command: cut -f 3 Ursus_maritimus.UrsMar_1.0.112.gff3 | sort | uniq -c | sort -nr | head -10
   Output:
   - 352,135  exon
   - 147,293  CDS
   - 122,640  biological_region
   - 48,164   mRNA
   - 34,227   gene
   - 23,819   region
   - 5,817    five_prime_UTR
   - 3,744    three_prime_UTR
   - 5,292    rRNA_gene

Summary:
The GFF3 file for *Ursus maritimus* contains a total of 1,186,643 features across 28 sequence regions. The file lists 64,997 genes. The top feature types include exons, CDS, and biological regions, which indicate detailed gene structure annotation. This file appears to be well-annotated and complete based on the diversity and number of features.
