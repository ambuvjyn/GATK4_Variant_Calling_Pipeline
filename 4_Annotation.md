# Annotation using snpEff
Here we have to specify the sample_name which corresponds to your sample from snpEff database.

`java -jar ../snpEff.jar -v sample_name S1_filtered_snps_final.vcf > S1_filtered_snps_final.ann.vcf`

`java -jar ../snpEff.jar -v sample_name S2_filtered_snps_final.vcf > S2_filtered_snps_final.ann.vcf`

`java -jar ../snpEff.jar -v sample_name S3_filtered_snps_final.vcf > S3_filtered_snps_final.ann.vcf`

`java -jar ../snpEff.jar -v sample_name S4_filtered_snps_final.vcf > S4_filtered_snps_final.ann.vcf`

`java -jar ../snpEff.jar -v sample_name S5_filtered_snps_final.vcf > S5_filtered_snps_final.ann.vcf`

`java -jar ../snpEff.jar -v sample_name S6_filtered_snps_final.vcf > S6_filtered_snps_final.ann.vcf`

------------

## gatk Variants To Table : Extract fields from a VCF file to a tab-delimited table

### Extracting chromosome name and annotation from the result

`gatk VariantsToTable -V S1_filtered_snps_final.ann.vcf -F CHROM -F ANN -O S1_CHROM_ANN.table`

`gatk VariantsToTable -V S2_filtered_snps_final.ann.vcf -F CHROM -F ANN -O S2_CHROM_ANN.table`

`gatk VariantsToTable -V S3_filtered_snps_final.ann.vcf -F CHROM -F ANN -O S3_CHROM_ANN.table`

`gatk VariantsToTable -V S4_filtered_snps_final.ann.vcf -F CHROM -F ANN -O S4_CHROM_ANN.table`

`gatk VariantsToTable -V S5_filtered_snps_final.ann.vcf -F CHROM -F ANN -O S5_CHROM_ANN.table`

`gatk VariantsToTable -V S6_filtered_snps_final.ann.vcf -F CHROM -F ANN -O S6_CHROM_ANN.table`

### Extracting only chromosome name from the result

`gatk VariantsToTable -V S1_filtered_snps_final.ann.vcf -F CHROM -O S1_CHROM.table`

`gatk VariantsToTable -V S2_filtered_snps_final.ann.vcf -F CHROM -O S2_CHROM.table`

`gatk VariantsToTable -V S3_filtered_snps_final.ann.vcf -F CHROM -O S3_CHROM.table`

`gatk VariantsToTable -V S4_filtered_snps_final.ann.vcf -F CHROM -O S4_CHROM.table`

`gatk VariantsToTable -V S5_filtered_snps_final.ann.vcf -F CHROM -O S5_CHROM.table`

`gatk VariantsToTable -V S6_filtered_snps_final.ann.vcf -F CHROM -O S6_CHROM.table`

------------


### Extracting chromosome name, position, ID, reference and the alternate aminoacid of SNP, quality, filter and information if its passed as SNP or not from the result

`gatk VariantsToTable -V S1_filtered_snps_final.vcf -F CHROM -F POS -F ID -F REF -F ALT -F QUAL -F FILTER -F INFO -O S1_vep.vcf`

`gatk VariantsToTable -V S2_filtered_snps_final.vcf -F CHROM -F POS -F ID -F REF -F ALT -F QUAL -F FILTER -F INFO -O S2_vep.vcf`

`gatk VariantsToTable -V S3_filtered_snps_final.vcf -F CHROM -F POS -F ID -F REF -F ALT -F QUAL -F FILTER -F INFO -O S3_vep.vcf`

`gatk VariantsToTable -V S4_filtered_snps_final.vcf -F CHROM -F POS -F ID -F REF -F ALT -F QUAL -F FILTER -F INFO -O S4_vep.vcf`

`gatk VariantsToTable -V S5_filtered_snps_final.vcf -F CHROM -F POS -F ID -F REF -F ALT -F QUAL -F FILTER -F INFO -O S5_vep.vcf`

`gatk VariantsToTable -V S6_filtered_snps_final.vcf -F CHROM -F POS -F ID -F REF -F ALT -F QUAL -F FILTER -F INFO -O S6_vep.vcf`

*edit the heading of all vep.vcf files and add :*
`##fileformat=VCFv4.0`
`#CHROM.......`
*and rename as samplename_vep.vcf*

------------
## VEP determines the effect of your variants (SNPs, insertions, deletions, CNVs or structural variants) on genes, transcripts, and protein sequence, as well as regulatory regions.

*Here we have to specify the sample_name which corresponds to your sample from VEP database.*

`vep -i S1_vep.vcf -o S1_vep_res.txt --species sample_name --cache --genome --cache_version 55 --dir_cache ./`

`vep -i S2_vep.vcf -o S2_vep_res.txt --species sample_name --cache --genome --cache_version 55 --dir_cache ./`

`vep -i S3_vep.vcf -o S3_vep_res.txt --species sample_name --cache --genome --cache_version 55 --dir_cache ./`

`vep -i S4_vep.vcf -o S4_vep_res.txt --species sample_name --cache --genome --cache_version 55 --dir_cache ./`

`vep -i S5_vep.vcf -o S5_vep_res.txt --species sample_name --cache --genome --cache_version 55 --dir_cache ./`

`vep -i S6_vep.vcf -o S6_vep_res.txt --species sample_name --cache --genome --cache_version 55 --dir_cache ./`

