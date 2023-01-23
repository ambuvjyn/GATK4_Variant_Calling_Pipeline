
# Quality Check of fastq sequences using fastqc
*Prerequisites : Miniconda/Anaconda* , Mamba (Better handling of installation than native conda)
## Create a conda environment with fastqc

`mamba create -n fastqc -c bioconda fastqc -y`

`conda activate fastqc`

### Running Fastqc for multiple samples

`fastqc -f fastq Sample1_R1.fastq.gz Sample1_R2.fastq.gz Sample2_R1.fastq.gz Sample2_R2.fastq.gz Sample3_R1.fastq.gz Sample3_R2.fastq.gz Sample4_R1.fastq.gz Sample4_R2.fastq.gz Sample5_R1.fastq.gz Sample5_R2.fastq.gz Sample6_R1.fastq.gz Sample6_R2.fastq.gz -o FastQC_output`

# Pre-processing of fastq sequences using fastp
## Create a conda environment with fastp

`mamba create -n fastp -c bioconda fastp -y`

`conda activate fastp`

### Running Fastp

`fastp --detect_adapter_for_pe --overrepresentation_analysis -i ../Sample1_R1.fastq.gz -I ../Sample1_R2.fastq.gz -o out.Sample1_R1.fq.gz -O out.Sample1_R2.fq.gz -j Sample1.json -h Sample1.html`

`fastp --detect_adapter_for_pe --overrepresentation_analysis -i ../Sample2_R1.fastq.gz -I ../Sample2_R2.fastq.gz -o out.Sample2_R1.fq.gz -O out.Sample2_R2.fq.gz -j Sample2.json -h Sample2.html`

`fastp --detect_adapter_for_pe --overrepresentation_analysis -i ../Sample3_R1.fastq.gz -I ../Sample3_R2.fastq.gz -o out.Sample3_R1.fq.gz -O out.Sample3_R2.fq.gz -j Sample3.json -h Sample3.html`

`fastp --detect_adapter_for_pe --overrepresentation_analysis -i ../Sample4_R1.fastq.gz -I ../Sample4_R2.fastq.gz -o out.Sample4_R1.fq.gz -O out.Sample4_R2.fq.gz -j Sample4.json -h Sample4.html`

`fastp --detect_adapter_for_pe --overrepresentation_analysis -i ../Sample5_R1.fastq.gz -I ../Sample5_R2.fastq.gz -o out.Sample5_R1.fq.gz -O out.Sample5_R2.fq.gz -j Sample5.json -h Sample5.html`

`fastp --detect_adapter_for_pe --overrepresentation_analysis -i ../Sample6_R1.fastq.gz -I ../Sample6_R2.fastq.gz -o out.Sample6_R1.fq.gz -O out.Sample6_R2.fq.gz -j Sample6.json -h Sample6.html`

# Interactive MultiQC report from fastqc
## Create a conda environment with multiqc

`mamba create -n multiqc -c bioconda multiqc -y`

`conda activate multiqc`

### Running MultiQC for combining fastqc results into a interactive form

`multiqc . -o MultiQC`

*MultiQC Result doesnot show fastp as there is no adapters present.*
