# Variant Calling Pipeline using GATK4
*FASTQ to SNPs and INDELs using GATK4*

Identifying genomic variants, including single nucleotide polymorphisms (SNPs) and DNA insertions and deletions (indels), from next generation sequencing data is an important part of scientific discovery.

To facilitate this research, a bioinformatics pipeline has been developed to enable researchers to accurately and rapidly identify, and annotate, sequence variants.

The pipeline employs the Genome Analysis Toolkit 4 (GATK4) to perform variant calling and is based on the best practices for variant discovery analysis outlined by the Broad Institute. 

*Once SNPs have been identified, SnpEff is used to annotate, and predict, variant effects.*

Base Quality Score Recalibration (BQSR) is an important step for accurate variant detection that aims to minimize the effect of technical variation on base quality scores (measured as Phred scores). As with the original pipeline (link), this pipeline assumes that a ‘gold standard’ set of SNPS and indels are not available for BQSR.  In the absence of a gold standard the pipeline performs an initial step detecting variants without performing BQSR, and then uses the identified SNPs as input for BQSR before calling variants again. This process is referred to as bootstrapping and is the procedure recommended by the Broad Institute’s best practices for variant discovery analysis when a gold standard is not available.

1. [Quality Control](https://github.com/ambuvjyn/GATK4_Variant_Calling_Pipeline/blob/main/1_Quality_Control.md)

2. [Genome Assembly](https://github.com/ambuvjyn/GATK4_Variant_Calling_Pipeline/blob/aaa9fc25009f73856b90c3b91bb7b98a713d96b4/2_Genome_Assembly.mdhttp:// "Genome Assembly")

3. [Variant Calling](https://github.com/ambuvjyn/GATK4_Variant_Calling_Pipeline/blob/aaa9fc25009f73856b90c3b91bb7b98a713d96b4/3_Variant%20Calling.mdp:// "Variant Calling")

4. [Annotation](https://github.com/ambuvjyn/GATK4_Variant_Calling_Pipeline/blob/aaa9fc25009f73856b90c3b91bb7b98a713d96b4/4_Annotation.md:// "Annotation")

