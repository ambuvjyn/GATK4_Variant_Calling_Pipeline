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

------------

# Isolating SNPs
## gatk Select Variants : Select a subset of variants from a VCF file

`gatk SelectVariants -R Reference/reference.fa -V S1_raw_variants.vcf --select-type-to-include SNP -O S1_raw_snps.vcf`

`gatk SelectVariants -R Reference/reference.fa -V S2_raw_variants.vcf --select-type-to-include SNP -O S2_raw_snps.vcf`

`gatk SelectVariants -R Reference/reference.fa -V S3_raw_variants.vcf --select-type-to-include SNP -O S3_raw_snps.vcf`

`gatk SelectVariants -R Reference/reference.fa -V S4_raw_variants.vcf --select-type-to-include SNP -O S4_raw_snps.vcf`

`gatk SelectVariants -R Reference/reference.fa -V S5_raw_variants.vcf --select-type-to-include SNP -O S5_raw_snps.vcf`

`gatk SelectVariants -R Reference/reference.fa -V S6_raw_variants.vcf --select-type-to-include SNP -O S6_raw_snps.vcf`

------------
# Isolating InDels

`gatk SelectVariants -R Reference/reference.fa -V S1_raw_variants.vcf --select-type-to-include INDEL -O S1_raw_indels.vcf`

`gatk SelectVariants -R Reference/reference.fa -V S2_raw_variants.vcf --select-type-to-include INDEL -O S2_raw_indels.vcf`

`gatk SelectVariants -R Reference/reference.fa -V S3_raw_variants.vcf --select-type-to-include INDEL -O S3_raw_indels.vcf`

`gatk SelectVariants -R Reference/reference.fa -V S4_raw_variants.vcf --select-type-to-include INDEL -O S4_raw_indels.vcf`

`gatk SelectVariants -R Reference/reference.fa -V S5_raw_variants.vcf --select-type-to-include INDEL -O S5_raw_indels.vcf`

`gatk SelectVariants -R Reference/reference.fa -V S6_raw_variants.vcf --select-type-to-include INDEL -O S6_raw_indels.vcf`

------------
# Filtering SNPs
## gatk Variant Filtration : Filter variant calls based on INFO and/or FORMAT annotations

`gatk VariantFiltration -R Reference/reference.fa -V S1_raw_snps.vcf -O S1_filtered_snps.vcf -filter-name "QD_filter" -filter "QD < 2.0" -filter-name "FS_filter" -filter "FS > 60.0" -filter-name "MQ_filter" -filter "MQ < 40.0" -filter-name "SOR_filter" -filter "SOR > 4.0"`

`gatk VariantFiltration -R Reference/reference.fa -V S2_raw_snps.vcf -O S2_filtered_snps.vcf -filter-name "QD_filter" -filter "QD < 2.0" -filter-name "FS_filter" -filter "FS > 60.0" -filter-name "MQ_filter" -filter "MQ < 40.0" -filter-name "SOR_filter" -filter "SOR > 4.0"`

`gatk VariantFiltration -R Reference/reference.fa -V S3_raw_snps.vcf -O S3_filtered_snps.vcf -filter-name "QD_filter" -filter "QD < 2.0" -filter-name "FS_filter" -filter "FS > 60.0" -filter-name "MQ_filter" -filter "MQ < 40.0" -filter-name "SOR_filter" -filter "SOR > 4.0"`

`gatk VariantFiltration -R Reference/reference.fa -V S4_raw_snps.vcf -O S4_filtered_snps.vcf -filter-name "QD_filter" -filter "QD < 2.0" -filter-name "FS_filter" -filter "FS > 60.0" -filter-name "MQ_filter" -filter "MQ < 40.0" -filter-name "SOR_filter" -filter "SOR > 4.0"`

`gatk VariantFiltration -R Reference/reference.fa -V S5_raw_snps.vcf -O S5_filtered_snps.vcf -filter-name "QD_filter" -filter "QD < 2.0" -filter-name "FS_filter" -filter "FS > 60.0" -filter-name "MQ_filter" -filter "MQ < 40.0" -filter-name "SOR_filter" -filter "SOR > 4.0"`

`gatk VariantFiltration -R Reference/reference.fa -V S6_raw_snps.vcf -O S6_filtered_snps.vcf -filter-name "QD_filter" -filter "QD < 2.0" -filter-name "FS_filter" -filter "FS > 60.0" -filter-name "MQ_filter" -filter "MQ < 40.0" -filter-name "SOR_filter" -filter "SOR > 4.0"`

------------

# Filtering InDels

`gatk VariantFiltration -R Reference/reference.fa -V S1_raw_indels.vcf -O S1_filtered_indels.vcf -filter-name "QD_filter" -filter "QD < 2.0" -filter-name "FS_filter" -filter "FS > 200.0" -filter-name "SOR_filter" -filter "SOR > 10.0"`

`gatk VariantFiltration -R Reference/reference.fa -V S2_raw_indels.vcf -O S2_filtered_indels.vcf -filter-name "QD_filter" -filter "QD < 2.0" -filter-name "FS_filter" -filter "FS > 200.0" -filter-name "SOR_filter" -filter "SOR > 10.0"`

`gatk VariantFiltration -R Reference/reference.fa -V S3_raw_indels.vcf -O S3_filtered_indels.vcf -filter-name "QD_filter" -filter "QD < 2.0" -filter-name "FS_filter" -filter "FS > 200.0" -filter-name "SOR_filter" -filter "SOR > 10.0"`

`gatk VariantFiltration -R Reference/reference.fa -V S4_raw_indels.vcf -O S4_filtered_indels.vcf -filter-name "QD_filter" -filter "QD < 2.0" -filter-name "FS_filter" -filter "FS > 200.0" -filter-name "SOR_filter" -filter "SOR > 10.0"`

`gatk VariantFiltration -R Reference/reference.fa -V S5_raw_indels.vcf -O S5_filtered_indels.vcf -filter-name "QD_filter" -filter "QD < 2.0" -filter-name "FS_filter" -filter "FS > 200.0" -filter-name "SOR_filter" -filter "SOR > 10.0"`

`gatk VariantFiltration -R Reference/reference.fa -V S6_raw_indels.vcf -O S6_filtered_indels.vcf -filter-name "QD_filter" -filter "QD < 2.0" -filter-name "FS_filter" -filter "FS > 200.0" -filter-name "SOR_filter" -filter "SOR > 10.0"`

------------
# Subsetting SNPs
## gatk SelectVariants : Select a subset of variants from a VCF file

`gatk SelectVariants --exclude-filtered -V S1_filtered_snps.vcf -O S1_bqsr_snps.vcf`

`gatk SelectVariants --exclude-filtered -V S2_filtered_snps.vcf -O S2_bqsr_snps.vcf`

`gatk SelectVariants --exclude-filtered -V S3_filtered_snps.vcf -O S3_bqsr_snps.vcf`

`gatk SelectVariants --exclude-filtered -V S4_filtered_snps.vcf -O S4_bqsr_snps.vcf`

`gatk SelectVariants --exclude-filtered -V S5_filtered_snps.vcf -O S5_bqsr_snps.vcf`

`gatk SelectVariants --exclude-filtered -V S6_filtered_snps.vcf -O S6_bqsr_snps.vcf`

------------

# Subsetting InDels

`gatk SelectVariants --exclude-filtered -V S1_filtered_indels.vcf -O S1_bqsr_indels.vcf`

`gatk SelectVariants --exclude-filtered -V S2_filtered_indels.vcf -O S2_bqsr_indels.vcf`

`gatk SelectVariants --exclude-filtered -V S3_filtered_indels.vcf -O S3_bqsr_indels.vcf`

`gatk SelectVariants --exclude-filtered -V S4_filtered_indels.vcf -O S4_bqsr_indels.vcf`

`gatk SelectVariants --exclude-filtered -V S5_filtered_indels.vcf -O S5_bqsr_indels.vcf`

`gatk SelectVariants --exclude-filtered -V S6_filtered_indels.vcf -O S6_bqsr_indels.vcf`

------------

## gatk Base Recalibrator : Generates recalibration table for Base Quality Score Recalibration (BQSR)

`gatk BaseRecalibrator -R Reference/reference.fa -I S1_sorted_dedup_reads.bam --known-sites S1_bqsr_snps.vcf --known-sites S1_bqsr_indels.vcf -O S1_recal_data.table`

`gatk BaseRecalibrator -R Reference/reference.fa -I S2_sorted_dedup_reads.bam --known-sites S2_bqsr_snps.vcf --known-sites S2_bqsr_indels.vcf -O S2_recal_data.table`

`gatk BaseRecalibrator -R Reference/reference.fa -I S3_sorted_dedup_reads.bam --known-sites S3_bqsr_snps.vcf --known-sites S3_bqsr_indels.vcf -O S3_recal_data.table`

`gatk BaseRecalibrator -R Reference/reference.fa -I S4_sorted_dedup_reads.bam --known-sites S4_bqsr_snps.vcf --known-sites S4_bqsr_indels.vcf -O S4_recal_data.table`

`gatk BaseRecalibrator -R Reference/reference.fa -I S5_sorted_dedup_reads.bam --known-sites S5_bqsr_snps.vcf --known-sites S5_bqsr_indels.vcf -O S5_recal_data.table`

`gatk BaseRecalibrator -R Reference/reference.fa -I S6_sorted_dedup_reads.bam --known-sites S6_bqsr_snps.vcf --known-sites S6_bqsr_indels.vcf -O S6_recal_data.table`

------------

## gatk Apply BQSR - Apply base quality score recalibration

`gatk ApplyBQSR -R Reference/reference.fa -I S1_sorted_dedup_reads.bam -bqsr S1_recal_data.table -O S1_recal_reads.bam`

`gatk ApplyBQSR -R Reference/reference.fa -I S2_sorted_dedup_reads.bam -bqsr S2_recal_data.table -O S2_recal_reads.bam`

`gatk ApplyBQSR -R Reference/reference.fa -I S3_sorted_dedup_reads.bam -bqsr S3_recal_data.table -O S3_recal_reads.bam`

`gatk ApplyBQSR -R Reference/reference.fa -I S4_sorted_dedup_reads.bam -bqsr S4_recal_data.table -O S4_recal_reads.bam`

`gatk ApplyBQSR -R Reference/reference.fa -I S5_sorted_dedup_reads.bam -bqsr S5_recal_data.table -O S5_recal_reads.bam`

`gatk ApplyBQSR -R Reference/reference.fa -I S6_sorted_dedup_reads.bam -bqsr S6_recal_data.table -O S6_recal_reads.bam`

------------

## gatk Base Recalibrator : Generates recalibration table for Base Quality Score Recalibration (BQSR)

`gatk BaseRecalibrator -R Reference/reference.fa -I S1_recal_reads.bam --known-sites S1_bqsr_snps.vcf --known-sites S1_bqsr_indels.vcf -O S1_post_recal_data.table`

`gatk BaseRecalibrator -R Reference/reference.fa -I S2_recal_reads.bam --known-sites S2_bqsr_snps.vcf --known-sites S2_bqsr_indels.vcf -O S2_post_recal_data.table`

`gatk BaseRecalibrator -R Reference/reference.fa -I S3_recal_reads.bam --known-sites S3_bqsr_snps.vcf --known-sites S3_bqsr_indels.vcf -O S3_post_recal_data.table`

`gatk BaseRecalibrator -R Reference/reference.fa -I S4_recal_reads.bam --known-sites S4_bqsr_snps.vcf --known-sites S4_bqsr_indels.vcf -O S4_post_recal_data.table`

`gatk BaseRecalibrator -R Reference/reference.fa -I S5_recal_reads.bam --known-sites S5_bqsr_snps.vcf --known-sites S5_bqsr_indels.vcf -O S5_post_recal_data.table`

`gatk BaseRecalibrator -R Reference/reference.fa -I S6_recal_reads.bam --known-sites S6_bqsr_snps.vcf --known-sites S6_bqsr_indels.vcf -O S6_post_recal_data.table`

## gatk Analyze Covariates : Evaluate and compare base quality score recalibration (BQSR) tables

`gatk AnalyzeCovariates -before S1_recal_data.table -after S1_post_recal_data.table -plots S1_recalibration_plots.pdf`

`gatk AnalyzeCovariates -before S1_recal_data.table -after S1_post_recal_data.table -plots S1_recalibration_plots.pdf`

`gatk AnalyzeCovariates -before S1_recal_data.table -after S1_post_recal_data.table -plots S1_recalibration_plots.pdf`

`gatk AnalyzeCovariates -before S1_recal_data.table -after S1_post_recal_data.table -plots S1_recalibration_plots.pdf`

`gatk AnalyzeCovariates -before S1_recal_data.table -after S1_post_recal_data.table -plots S1_recalibration_plots.pdf`

`gatk AnalyzeCovariates -before S1_recal_data.table -after S1_post_recal_data.table -plots S1_recalibration_plots.pdf`

------------

## gatk Haplotype Caller : Call germline SNPs and indels via local re-assembly of haplotypes

`gatk HaplotypeCaller -R Reference/reference.fa -I S1_recal_reads.bam -O S1_raw_variants_recal.vcf`

`gatk HaplotypeCaller -R Reference/reference.fa -I S2_recal_reads.bam -O S2_raw_variants_recal.vcf`

`gatk HaplotypeCaller -R Reference/reference.fa -I S3_recal_reads.bam -O S3_raw_variants_recal.vcf`

`gatk HaplotypeCaller -R Reference/reference.fa -I S4_recal_reads.bam -O S4_raw_variants_recal.vcf`

`gatk HaplotypeCaller -R Reference/reference.fa -I S5_recal_reads.bam -O S5_raw_variants_recal.vcf`

`gatk HaplotypeCaller -R Reference/reference.fa -I S6_recal_reads.bam -O S6_raw_variants_recal.vcf`

------------

# Subsetting SNPs
## gatk Select Variants : Select a subset of variants from a VCF file

`gatk SelectVariants -R Reference/reference.fa -V S1_raw_variants_recal.vcf --select-type-to-include SNP -O S1_raw_snps_recal.vcf`

`gatk SelectVariants -R Reference/reference.fa -V S2_raw_variants_recal.vcf --select-type-to-include SNP -O S2_raw_snps_recal.vcf`

`gatk SelectVariants -R Reference/reference.fa -V S3_raw_variants_recal.vcf --select-type-to-include SNP -O S3_raw_snps_recal.vcf`

`gatk SelectVariants -R Reference/reference.fa -V S4_raw_variants_recal.vcf --select-type-to-include SNP -O S4_raw_snps_recal.vcf`

`gatk SelectVariants -R Reference/reference.fa -V S5_raw_variants_recal.vcf --select-type-to-include SNP -O S5_raw_snps_recal.vcf`

`gatk SelectVariants -R Reference/reference.fa -V S6_raw_variants_recal.vcf --select-type-to-include SNP -O S6_raw_snps_recal.vcf`

------------

# Subsetting InDels

`gatk SelectVariants -R Reference/reference.fa -V S1_raw_variants.vcf --select-type-to-include INDEL -O S1_raw_indels_recal.vcf`

`gatk SelectVariants -R Reference/reference.fa -V S2_raw_variants.vcf --select-type-to-include INDEL -O S2_raw_indels_recal.vcf`

`gatk SelectVariants -R Reference/reference.fa -V S3_raw_variants.vcf --select-type-to-include INDEL -O S3_raw_indels_recal.vcf`

`gatk SelectVariants -R Reference/reference.fa -V S4_raw_variants.vcf --select-type-to-include INDEL -O S4_raw_indels_recal.vcf`

`gatk SelectVariants -R Reference/reference.fa -V S5_raw_variants.vcf --select-type-to-include INDEL -O S5_raw_indels_recal.vcf`

`gatk SelectVariants -R Reference/reference.fa -V S6_raw_variants.vcf --select-type-to-include INDEL -O S6_raw_indels_recal.vcf`

------------

# Filtering SNPs
## gatk Variant Filtration : Filter variant calls based on INFO and/or FORMAT annotations

`gatk VariantFiltration -R Reference/reference.fa -V S1_raw_snps_recal.vcf -O S1_filtered_snps_final.vcf -filter-name "QD_filter" -filter "QD < 2.0" -filter-name "FS_filter" -filter "FS > 60.0" -filter-name "MQ_filter" -filter "MQ < 40.0" -filter-name "SOR_filter" -filter "SOR > 4.0"`

`gatk VariantFiltration -R Reference/reference.fa -V S2_raw_snps_recal.vcf -O S2_filtered_snps_final.vcf -filter-name "QD_filter" -filter "QD < 2.0" -filter-name "FS_filter" -filter "FS > 60.0" -filter-name "MQ_filter" -filter "MQ < 40.0" -filter-name "SOR_filter" -filter "SOR > 4.0"`

`gatk VariantFiltration -R Reference/reference.fa -V S3_raw_snps_recal.vcf -O S3_filtered_snps_final.vcf -filter-name "QD_filter" -filter "QD < 2.0" -filter-name "FS_filter" -filter "FS > 60.0" -filter-name "MQ_filter" -filter "MQ < 40.0" -filter-name "SOR_filter" -filter "SOR > 4.0"`

`gatk VariantFiltration -R Reference/reference.fa -V S4_raw_snps_recal.vcf -O S4_filtered_snps_final.vcf -filter-name "QD_filter" -filter "QD < 2.0" -filter-name "FS_filter" -filter "FS > 60.0" -filter-name "MQ_filter" -filter "MQ < 40.0" -filter-name "SOR_filter" -filter "SOR > 4.0"`

`gatk VariantFiltration -R Reference/reference.fa -V S5_raw_snps_recal.vcf -O S5_filtered_snps_final.vcf -filter-name "QD_filter" -filter "QD < 2.0" -filter-name "FS_filter" -filter "FS > 60.0" -filter-name "MQ_filter" -filter "MQ < 40.0" -filter-name "SOR_filter" -filter "SOR > 4.0"`

`gatk VariantFiltration -R Reference/reference.fa -V S6_raw_snps_recal.vcf -O S6_filtered_snps_final.vcf -filter-name "QD_filter" -filter "QD < 2.0" -filter-name "FS_filter" -filter "FS > 60.0" -filter-name "MQ_filter" -filter "MQ < 40.0" -filter-name "SOR_filter" -filter "SOR > 4.0"`

# Filtering InDels

`gatk VariantFiltration -R Reference/reference.fa -V S1_raw_indels_recal.vcf -O S1_filtered_indels_final.vcf -filter-name "QD_filter" -filter "QD < 2.0" -filter-name "FS_filter" -filter "FS > 200.0" -filter-name "SOR_filter" -filter "SOR > 10.0"`

`gatk VariantFiltration -R Reference/reference.fa -V S2_raw_indels_recal.vcf -O S2_filtered_indels_final.vcf -filter-name "QD_filter" -filter "QD < 2.0" -filter-name "FS_filter" -filter "FS > 200.0" -filter-name "SOR_filter" -filter "SOR > 10.0"`

`gatk VariantFiltration -R Reference/reference.fa -V S3_raw_indels_recal.vcf -O S3_filtered_indels_final.vcf -filter-name "QD_filter" -filter "QD < 2.0" -filter-name "FS_filter" -filter "FS > 200.0" -filter-name "SOR_filter" -filter "SOR > 10.0"`

`gatk VariantFiltration -R Reference/reference.fa -V S4_raw_indels_recal.vcf -O S4_filtered_indels_final.vcf -filter-name "QD_filter" -filter "QD < 2.0" -filter-name "FS_filter" -filter "FS > 200.0" -filter-name "SOR_filter" -filter "SOR > 10.0"`

`gatk VariantFiltration -R Reference/reference.fa -V S5_raw_indels_recal.vcf -O S5_filtered_indels_final.vcf -filter-name "QD_filter" -filter "QD < 2.0" -filter-name "FS_filter" -filter "FS > 200.0" -filter-name "SOR_filter" -filter "SOR > 10.0"`

`gatk VariantFiltration -R Reference/reference.fa -V S6_raw_indels_recal.vcf -O S6_filtered_indels_final.vcf -filter-name "QD_filter" -filter "QD < 2.0" -filter-name "FS_filter" -filter "FS > 200.0" -filter-name "SOR_filter" -filter "SOR > 10.0"`

