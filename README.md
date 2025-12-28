# Trio-Based Variant Calling Analysis Using NGS Data

## 📌 Project Overview
This project implements a **trio-based human variant calling pipeline** using next-generation sequencing (NGS) data from a **father–mother–proband** family. The workflow processes raw paired-end sequencing reads to identify **high-confidence genetic variants**, with a special focus on **de novo mutations**, which are commonly investigated in **rare inherited and neurodevelopmental disorders**.


## 🎯 Objectives
- Perform quality control of raw sequencing reads  
- Align reads to the human reference genome (hg19, chr8)  
- Process alignment files (filtering, sorting, duplicate removal)  
- Perform **joint variant calling** using trio information  
- Identify **candidate de novo variants** in the proband  
- Interpret biologically relevant findings  

---

## 🧬 Dataset Description
- **Samples:** Father, Mother, Proband (Trio)
- **Sequencing type:** Paired-end DNA sequencing
- **Reference genome:** hg19 (Chromosome 8 only)
- **Data source:** Public dataset (Zenodo)

---

## 🛠️ Tools & Software Used
The analysis was performed using a Conda-based environment with the following tools:

- **FastQC** – Raw read quality assessment  
- **MultiQC** – Aggregated quality control reporting  
- **BWA-MEM** – Read alignment to reference genome  
- **SAMtools** – BAM processing (filtering, sorting, duplicate removal)  
- **FreeBayes** – Variant calling  
- **BCFtools** – VCF processing and variant filtering  
- **bgzip / tabix** – VCF compression and indexing  

---

## 🔄 Workflow Summary
1. **Quality Control**
   - FASTQ files were assessed using FastQC and summarized with MultiQC.

2. **Read Alignment**
   - Reads were aligned to the hg19 chromosome 8 reference using BWA-MEM.
   - Alignment quality was evaluated using SAMtools.

3. **Post-alignment Processing**
   - Removal of unmapped and improperly paired reads  
   - Mate fixing, coordinate sorting, and duplicate removal  

4. **Joint Variant Calling**
   - Variants were jointly called across father, mother, and proband using FreeBayes.
   - A raw trio VCF file was generated.

5. **Inheritance-based Filtering**
   - Variants present exclusively in the proband were extracted as **candidate de novo variants**.

---

## 📊 Results Summary

| Category | Metric | Result |
|--------|--------|--------|
| Mapping Quality | Alignment Rate | **99.7%** |
| De novo Candidates | Variant Count | **52** |
| Variant Types | SNPs | **52** |
| Variant Types | Indels | **1** |
| Lead Candidate Gene | DLGAP2 | QUAL = **1222** |

---

## 🧠 Interpretation
- The high alignment rate (99.7%) indicates excellent sequencing and mapping quality.
- A biologically reasonable number of de novo variants were identified on chromosome 8.
- The variant spectrum was dominated by SNPs, consistent with known human mutation patterns.
- A high-confidence de novo variant was identified in **DLGAP2**, a gene involved in synaptic organization and neuronal signaling.
- This project demonstrates how trio-based sequencing enables inheritance-aware interpretation of genetic variants.

---

## 🧪 Biological Relevance
The analysis framework used in this project is commonly applied in studies of:
- **Rare inherited genetic disorders**
- **Neurodevelopmental disorders**
- **Congenital conditions with a genetic basis**


---

## 📂 Data Availability
Due to GitHub file size limitations and best practices for handling large genomic datasets, raw and processed sequencing files are **not stored directly in this repository**.

The full dataset is available for download via MEGA:

🔗 **MEGA Dataset Link:**  
https://mega.nz/folder/P8gxnDTY#nik3hHWBboep7_JYB4KRMg

The MEGA folder contains:
- BAM files for father, mother, and proband  
- BAM index files (.bai)  
- Joint trio VCF file  
- De novo candidate variants VCF  


## ✅ Conclusion
This project demonstrates a **complete and reproducible trio-based variant calling pipeline**, enabling the identification and interpretation of **high-confidence de novo genetic variants** from NGS data. The workflow reflects standard practices used in **clinical genomics and rare disease research**.


## 👤 Author
**Prashanth E**  
B-PHARMACY
MSc Bioinformatics 
prashantheprashanth584@gmail.com
