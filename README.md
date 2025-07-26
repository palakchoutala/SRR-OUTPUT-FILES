# SRR-OUTPUT-FILES
# 🧬 From Raw Reads to Gene Insights  
**RNA-Seq Analysis of Human Lymphoblastoid Cell Line (YRI – SRR19762473)**  
_Comprehensive transcriptome analysis pipeline using public NGS data_

---

## 📌 Project Overview

This project demonstrates a complete RNA-Seq data analysis pipeline, applied to the sample `SRR19762473` from Yoruba individuals in the **1000 Genomes Project**. The analysis focuses on quality assessment, read trimming, alignment, variant calling, and visualization, aimed at extracting biological insights from raw sequencing data.

---

## 🧬 Dataset Information

- **Organism:** *Homo sapiens* (Human)  
- **Sample:** Lymphoblastoid Cell Line (YRI)  
- **SRA Run ID:** SRR19762473  
- **SRA Project ID:** PRJNA207555  
- **Read Type:** Paired-end RNA-Seq  
- **Source:** [NCBI SRA]
---

## 🧪 Workflow Summary

1. **Data Download**
   - `prefetch SRR19762473`
   - `fasterq-dump --split-files SRR19762473.sra`

2. **Quality Control**
   - Tool: `FastQC`
   - Output: HTML quality reports

3. **Trimming**
   - Tool: `Trimmomatic`
   - Removed Illumina adapters and low-quality bases

4. **Alignment**
   - Tool: `BWA-MEM` aligned to hg38 reference genome
   - Output: `.sam` and sorted `.bam` files

5. **Post-Processing**
   - Tool: `SAMtools`
   - Conversion, sorting, and indexing of BAM files

6. **Variant Calling**
   - Tool: `BCFtools`
   - Variant discovery and filtering (QUAL > 30, DP > 10)

7. **Visualization**
   - Tool: `IGV`
   - Genome browser view of alignments and variants

---

## 📂 Repository Contents

```bash
├── data/                   # Raw FASTQ files
├── trimmed_reads/          # Trimmed FASTQ outputs
├── qc_reports/             # FastQC HTML reports
├── alignment/              # SAM/BAM/BAM.BAI files
├── variants/               # VCF and filtered VCF files
├── igv_snapshots/          # IGV visualizations (PNG/SVG)
├── run_commands.sh         # All shell commands used
└── README.md               # This file

