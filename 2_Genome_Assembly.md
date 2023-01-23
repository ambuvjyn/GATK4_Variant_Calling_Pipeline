# Table of contents

- [Indexing the reference of the sample using BWA](#indexing-the-reference-of-the-sample-using-bwa)
- [Local Alignment using BWA-MEM and mapping to the Reference genome](#local-alignment-using-bwa-mem-and-mapping-to-the-reference-genome)

# Indexing the reference of the sample using BWA

`bwa index reference.fa`

# Local Alignment using BWA-MEM and mapping to the Reference genome

*Readgroup info is provided with the -R flag. This information is key for downstream GATK functionality. GATK will not work without a read group tag.*

`bwa mem -M -K 100000000 -t 40 -Y -R '@RG\tID:Sample1_R1\tLB:Sample1_R1\tPL:ILLUMINA\tPM:HISEQ\tSM:Sample1_R1' Reference/reference.fa out.Sample1_R1.fq.gz out.Sample1_R2.fq.gz > Sample1_aligned_reads.sam`

`bwa mem -M -K 100000000 -t 40 -Y -R '@RG\tID:Sample2_R1\tLB:Sample2_R1\tPL:ILLUMINA\tPM:HISEQ\tSM:Sample2_R1' Reference/reference.fa out.Sample2_R1.fq.gz out.Sample2_R2.fq.gz > Sample2_aligned_reads.sam`

`bwa mem -M -K 100000000 -t 40 -Y -R '@RG\tID:Sample3_R1\tLB:Sample3_R1\tPL:ILLUMINA\tPM:HISEQ\tSM:Sample3_R1' Reference/reference.fa out.Sample3_R1.fq.gz out.Sample3_R2.fq.gz > Sample3_aligned_reads.sam`

`bwa mem -M -K 100000000 -t 40 -Y -R '@RG\tID:Sample4_R1\tLB:Sample4_R1\tPL:ILLUMINA\tPM:HISEQ\tSM:Sample4_R1' Reference/reference.fa out.Sample4_R1.fq.gz out.Sample4_R2.fq.gz > Sample4_aligned_reads.sam`

`bwa mem -M -K 100000000 -t 40 -Y -R '@RG\tID:Sample5_R1\tLB:Sample5_R1\tPL:ILLUMINA\tPM:HISEQ\tSM:Sample5_R1' Reference/reference.fa out.Sample5_R1.fq.gz out.Sample5_R2.fq.gz > Sample5_aligned_reads.sam`

`bwa mem -M -K 100000000 -t 40 -Y -R '@RG\tID:Sample6_R1\tLB:Sample5_R1\tPL:ILLUMINA\tPM:HISEQ\tSM:Sample6_R1' Reference/reference.fa out.Sample6_R1.fq.gz out.Sample6_R2.fq.gz > Sample6_aligned_reads.sam`

Sorting SAM file by cordinate and converting to BAM using Picard

`picard SortSam INPUT=Sample1_aligned_reads.sam OUTPUT=Sample1_sorted_reads.bam SORT_ORDER=coordinate`

`picard SortSam INPUT=Sample2_aligned_reads.sam OUTPUT=Sample2_sorted_reads.bam SORT_ORDER=coordinate`

`picard SortSam INPUT=Sample3_aligned_reads.sam OUTPUT=Sample3_sorted_reads.bam SORT_ORDER=coordinate`

`picard SortSam INPUT=Sample4_aligned_reads.sam OUTPUT=Sample4_sorted_reads.bam SORT_ORDER=coordinate`

`picard SortSam INPUT=Sample5_aligned_reads.sam OUTPUT=Sample5_sorted_reads.bam SORT_ORDER=coordinate`

`picard SortSam INPUT=Sample6_aligned_reads.sam OUTPUT=Sample6_sorted_reads.bam SORT_ORDER=coordinate`
