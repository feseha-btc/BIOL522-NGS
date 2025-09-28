Project\_README.md templatefor student projects 

Project Title

Analysis of RNA-Seq Data for Differential Expression in Yeast

\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

👤 Student Information

• Name: Alex Smith

• Email: alex.smith@email.edu

• GitHub Username: alexsmith22

\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

📖 Project Overview

This project analyzes RNA-Seq data from Saccharomyces cerevisiae under two conditions: control vs. stress treatment. The goal is to perform basic quality control, trimming, and read alignment to the reference genome to prepare for downstream differential expression analysis.

\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

🎯 Objectives

1\. Perform quality control on raw FASTQ reads.

2\. Trim adapters and low-quality bases.

3\. Align reads to the yeast reference genome.

4\. Summarize read mapping statistics.

5\. Document the workflow for reproducibility.

\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

🗂 Data

• Source: NCBI SRA, SRR1234567 (control), SRR1234568 (stress treatment)

• Type: Paired-end RNA-Seq FASTQ files (~5 GB total)

• Preprocessing: FastQC used to evaluate read quality before trimming

\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

⚙️ Methods \& Tools

• Linux shell on ACCESS-CI HPC

• FastQC v0.12.1

• Cutadapt v4.6

• BWA v0.7.17

• Samtools v1.16.1

• Python 3.10 + Biopython v1.83

• SLURM batch submission scripts

\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

🚀 Workflow

1\. Download raw FASTQ files using SRA toolkit (prefetch + fastq-dump).

2\. Run FastQC on all FASTQ files to check quality metrics:

3\. fastqc SRR1234567\_1.fastq SRR1234567\_2.fastq

4\. Trim adapters and low-quality bases with Cutadapt:

5\. cutadapt -a AGATCGGAAGAGC -A AGATCGGAAGAGC -q 20 -o trimmed\_1.fastq -p trimmed\_2.fastq SRR1234567\_1.fastq SRR1234567\_2.fastq

6\. Align trimmed reads to S. cerevisiae reference genome using BWA:

7\. bwa mem sacCer3.fa trimmed\_1.fastq trimmed\_2.fastq > aligned.sam

8\. Convert SAM → BAM, sort, and index with Samtools:

9\. samtools view -bS aligned.sam > aligned.bam

10\. samtools sort aligned.bam -o aligned\_sorted.bam

11\. samtools index aligned\_sorted.bam

12\. Generate mapping statistics:

13\. samtools flagstat aligned\_sorted.bam

\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

📂 Repository Structure

rna\_seq\_project/

├── data/       # Links to SRA files; raw FASTQ not stored due to size

├── scripts/    # Cutadapt trimming, BWA alignment, flagstat commands

├── results/    # FastQC reports, BAM files (if small subset), mapping stats

├── figures/    # Quality score plots from FastQC

└── README.md   # Project documentation

\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

📊 Results \& Figures

• FastQC Quality Summary: Average per-base quality > 30 across all reads.

• Trimming Summary: ~98% reads retained after adapter and quality trimming.

• Alignment Statistics:

o Total reads: 12,000,000

o Mapped reads: 11,400,000 (~95%)

o Properly paired: 92%

(Figures included in /figures/fastqc\_summary.png)

\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

📌 Discussion

• High-quality reads indicate that sequencing was successful.

• Trimming removed adapters with minimal loss of reads.

• Alignment rates are strong, suggesting reference genome is appropriate.

• Next steps: differential expression analysis using DESeq2 or edgeR.

\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

🔄 Reproducibility

• All commands executed on ACCESS-CI HPC using SLURM batch scripts in /scripts/.

• Python scripts for parsing FastQC outputs included in /scripts/parse\_fastqc.py.

• Software versions are documented above.

\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

📑 References

1\. FastQC: https://www.bioinformatics.babraham.ac.uk/projects/fastqc/

2\. Cutadapt: Martin, M. (2011). Cutadapt removes adapter sequences from high-throughput sequencing reads. EMBnet.journal.

3\. BWA: Li, H., \& Durbin, R. (2009). Fast and accurate short read alignment with Burrows–Wheeler transform. Bioinformatics.

4\. Samtools: Li, H., et al. (2009). The Sequence Alignment/Map format and SAMtools. Bioinformatics.

\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

End of Sample Project README



