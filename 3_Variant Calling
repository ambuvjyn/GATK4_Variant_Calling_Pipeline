## GATK Mark Duplicates is from Picard : This tool locates and tags duplicate reads in a BAM or SAM file

`gatk MarkDuplicates -I S1_sorted_reads.bam -M S1_dedup_metrics.txt -O S1_sorted_dedup_reads.bam`

`gatk MarkDuplicates -I S2_sorted_reads.bam -M S2_dedup_metrics.txt -O S2_sorted_dedup_reads.bam`

`gatk MarkDuplicates -I S3_sorted_reads.bam -M S3_dedup_metrics.txt -O S3_sorted_dedup_reads.bam`

`gatk MarkDuplicates -I S4_sorted_reads.bam -M S4_dedup_metrics.txt -O S4_sorted_dedup_reads.bam`

`gatk MarkDuplicates -I S5_sorted_reads.bam -M S5_dedup_metrics.txt -O S5_sorted_dedup_reads.bam`

`gatk MarkDuplicates -I S6_sorted_reads.bam -M S6_dedup_metrics.txt -O S6_sorted_dedup_reads.bam`

------------

## picard Collect Alignment Summary Metrics : Produces a summary of alignment metrics from a SAM or BAM file

`picard CollectAlignmentSummaryMetrics R=Reference/reference.fa I=S1_sorted_dedup_reads.bam O=S1_alignment_metrics.txt`

`picard CollectAlignmentSummaryMetrics R=Reference/reference.fa I=S2_sorted_dedup_reads.bam O=S2_alignment_metrics.txt`

`picard CollectAlignmentSummaryMetrics R=Reference/reference.fa I=S3_sorted_dedup_reads.bam O=S3_alignment_metrics.txt`

`picard CollectAlignmentSummaryMetrics R=Reference/reference.fa I=S4_sorted_dedup_reads.bam O=S4_alignment_metrics.txt`

`picard CollectAlignmentSummaryMetrics R=Reference/reference.fa I=S5_sorted_dedup_reads.bam O=S5_alignment_metrics.txt`

`picard CollectAlignmentSummaryMetrics R=Reference/reference.fa I=S6_sorted_dedup_reads.bam O=S6_alignment_metrics.txt`

------------

## picard Collect Insert Size Metrics : This tool provides useful metrics for validating library construction including the insert size distribution and read orientation of paired-end libraries.

`picard CollectInsertSizeMetrics INPUT=S1_sorted_dedup_reads.bam OUTPUT=S1_insert_metrics.txt HISTOGRAM_FILE=S1_insert_size_histogram.pdf`

`picard CollectInsertSizeMetrics INPUT=S2_sorted_dedup_reads.bam OUTPUT=S2_insert_metrics.txt HISTOGRAM_FILE=S2_insert_size_histogram.pdf`

`picard CollectInsertSizeMetrics INPUT=S3_sorted_dedup_reads.bam OUTPUT=S3_insert_metrics.txt HISTOGRAM_FILE=S3_insert_size_histogram.pdf`

`picard CollectInsertSizeMetrics INPUT=S4_sorted_dedup_reads.bam OUTPUT=S4_insert_metrics.txt HISTOGRAM_FILE=S4_insert_size_histogram.pdf`

`picard CollectInsertSizeMetrics INPUT=S5_sorted_dedup_reads.bam OUTPUT=S5_insert_metrics.txt HISTOGRAM_FILE=S5_insert_size_histogram.pdf`

`picard CollectInsertSizeMetrics INPUT=S6_sorted_dedup_reads.bam OUTPUT=S6_insert_metrics.txt HISTOGRAM_FILE=S6_insert_size_histogram.pdf`

------------

## samtools depth – computes the read depth at each position or region

`samtools depth -a S1_sorted_dedup_reads.bam > S1_depth_out.txt`

`samtools depth -a S2_sorted_dedup_reads.bam > S2_depth_out.txt`

`samtools depth -a S3_sorted_dedup_reads.bam > S3_depth_out.txt`

`samtools depth -a S4_sorted_dedup_reads.bam > S4_depth_out.txt`

`samtools depth -a S5_sorted_dedup_reads.bam > S5_depth_out.txt`

`samtools depth -a S6_sorted_dedup_reads.bam > S6_depth_out.txt`

------------

## samtools index – indexes SAM/BAM/CRAM files

`samtools index S1_sorted_dedup_reads.bam`

`samtools index S2_sorted_dedup_reads.bam`

`samtools index S3_sorted_dedup_reads.bam`

`samtools index S4_sorted_dedup_reads.bam`

`samtools index S5_sorted_dedup_reads.bam`

`samtools index S6_sorted_dedup_reads.bam`

------------

## gatk HaplotypeCaller : It is capable of calling SNPs and indels simultaneously via local de-novo assembly of haplotypes in an active region.

`gatk HaplotypeCaller -R Reference/reference.fa -I S1_sorted_dedup_reads.bam -O S1_raw_variants.vcf`

`gatk HaplotypeCaller -R Reference/reference.fa -I S2_sorted_dedup_reads.bam -O S2_raw_variants.vcf`

`gatk HaplotypeCaller -R Reference/reference.fa -I S3_sorted_dedup_reads.bam -O S3_raw_variants.vcf`

`gatk HaplotypeCaller -R Reference/reference.fa -I S4_sorted_dedup_reads.bam -O S4_raw_variants.vcf`

`gatk HaplotypeCaller -R Reference/reference.fa -I S5_sorted_dedup_reads.bam -O S5_raw_variants.vcf`

`gatk HaplotypeCaller -R Reference/reference.fa -I S6_sorted_dedup_reads.bam -O S6_raw_variants.vcf`
