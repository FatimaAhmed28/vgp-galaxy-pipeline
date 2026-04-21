🧬 Vertebrate Genome (VGP) Assembly Pipeline using Galaxy
This repository documents the implementation of the Vertebrate Genome Project (VGP) genome assembly pipeline using the Galaxy platform to generate a high-quality, chromosome-level genome assembly.

________________________________________
📌 Overview
This project focuses on assembling the genome of Saccharomyces cerevisiae (S288C strain) using a multi-technology approach:
•	PacBio HiFi reads (long, high accuracy)
•	Hi-C sequencing (chromosome structure)
•	Bionano optical maps (structural validation)
The pipeline integrates these datasets to produce a highly contiguous, phased, and accurate genome assembly.
________________________________________
🧪 Pipeline Workflow
Input Data (HiFi + Hi-C + Bionano)
        ↓
Read Cleaning (Cutadapt)
        ↓
K-mer Analysis (Meryl + GenomeScope2)
        ↓
Genome Assembly (Hifiasm)
        ↓
Scaffolding (Hi-C + Bionano)
        ↓
Validation (BUSCO + Merqury)
        ↓
Chromosome-level Genome Output
________________________________________
📂 Input Data
1. HiFi Reads
•	PacBio SMRT sequencing
•	Read length: ~10–25 kb
•	Accuracy: >99%
•	Used for primary assembly
2. Hi-C Reads
•	Illumina paired-end sequencing
•	Provides chromatin interaction data
•	Enables scaffolding & phasing
3. Bionano Optical Maps
•	Long DNA molecule mapping
•	Supports structural organization
________________________________________
⚙️ Methodology
🔹 Data Preprocessing
•	Tool: Cutadapt
•	Adapter-contaminated reads removed (not trimmed)
•	Output: Clean high-quality reads
________________________________________
🔹 Genome Characterization
•	Meryl → k-mer counting (k=31)
•	GenomeScope2 → genome estimation
Results:
•	Genome size: ~11.7 Mb
•	Heterozygosity: ~0.58%
•	Unique content: ~93.8%
•	Error rate: very low
________________________________________
🔹 De Novo Assembly
•	Tool: Hifiasm
•	Graph-based assembly
•	Haplotypes separated using Hi-C
Outputs:
•	Haplotype 1 (Hap1)
•	Haplotype 2 (Hap2)
________________________________________
🔹 Assembly Statistics
•	Tool: Gfastats
•	Contigs: 16–17
•	Largest contig: ~1.5 Mb
•	N50: ~922 kb
________________________________________
📊 Quality Assessment
🧬 BUSCO (Completeness)
•	Hap1: 95.9% (High quality)
•	Hap2: 89.0% (Moderate quality)
➡️ Hap1 is more complete; Hap2 is slightly lower (expected in diploid assemblies)
________________________________________
🔬 Merqury (Reference-free)
•	Completeness: 99.9999%
•	Haplotype separation: Clear
➡️ Indicates near-perfect assembly with minimal errors
________________________________________
🧱 Structural Scaffolding
Bionano Hybrid Scaffolding
•	Improves genome organization
•	Produces larger scaffolds
Hi-C Scaffolding (YaHS)
•	Maps interaction frequencies
•	Assembles chromosome-level scaffolds
________________________________________
🔍 Validation (Hi-C Contact Maps)
Before Scaffolding
•	Thin diagonal pattern
➡️ Correct contigs but unorganized
After Scaffolding
•	Clear block structures
➡️ Each block represents a chromosome
✅ Confirms correct ordering and orientation
________________________________________
📈 Results and Performance
Metric	Value	Assessment
Genome Size	~11.7 Mb	Accurate
N50	~922 kb	Excellent
BUSCO	95.9%	High
Merqury	99.9999%	Outstanding
Phasing	Clear	Excellent
________________________________________
🧬 Biological Significance
•	Accurate representation of both haplotypes
•	Minimal duplication errors
•	Reliable chromosome structure
________________________________________
✅ Strengths
•	Integrates multiple technologies
•	Produces high-resolution assemblies
•	Enables haplotype phasing
•	Fully reproducible in Galaxy
________________________________________
⚠️ Limitations
•	High computational requirements
•	Requires multiple datasets
•	Some manual curation needed
________________________________________
🏁 Conclusion
This project demonstrates a successful implementation of the VGP pipeline, producing:
•	Near-complete genome assembly
•	Chromosome-level scaffolding
•	High structural accuracy
•	Correct haplotype resolution
👉 Overall, this pipeline represents a gold standard for modern genome assembly and is suitable for:
•	Genomics research
•	Evolutionary studies
•	Precision biology
________________________________________
🛠️ Tools Used
•	Cutadapt
•	Meryl
•	GenomeScope2
•	Hifiasm
•	Gfastats
•	BUSCO
•	Merqury
•	YaHS
•	Galaxy Platform
________________________________________
📎 Author
Fatima Ahmed
MS Bioinformatics
National University of Sciences and Technology
________________________________________
