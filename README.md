# SWYNEX-Biological-Dataset-Analysis

## Comparative Sequence and Physicochemical Profiling of the Mammalian Oxytocin Receptor Across Contrasting Social Phenotypes

**Internship Program:** SWYNEX Technologies — Bioinformatics Internship  
**Intern:** Sampriti Roy | B.Sc. Biotechnology, Panskura Banamali College

---

## Table of Contents
- **About the Project**
- **Research Question**
- **Why This Dataset Was Chosen**
- **Task 1 — Biological Dataset Selection and Provenance**
- **Task 2 — Data Cleaning, Physicochemical Profiling, and Homology Analysis**
- **Repository Structure**
- **Tools and Public Databases**
- **Author**

---

## About the Project
The **Oxytocin Receptor**, encoded by the **OXTR** gene, is a Class A G-protein-coupled receptor expressed in the central nervous system and peripheral tissues. It mediates the neuroendocrine signaling of the hypothalamic nonapeptide hormone **oxytocin**, which regulates social recognition, pair-bonding, maternal care, emotional regulation, and stress response modulation.

This repository hosts the open-access mammalian **OXTR** protein sequence dataset retrieved from the National Center for Biotechnology Information, along with cleaned canonical FASTA sequences, physicochemical property summaries, pairwise sequence homology metrics, and full documentation of data provenance and evolutionary rationale.

---

## Research Question
**How conserved are the primary amino acid sequence features and key physicochemical properties including molecular weight, theoretical isoelectric point, instability index, aliphatic index, and hydrophobic versus hydrophilic amino acid composition of the Oxytocin Receptor across mammalian species exhibiting contrasting social structures?**

---

## Why This Dataset Was Chosen
1. **Direct Molecular Bridge Between Hormones and Neuroscience:** OXTR translates endocrine oxytocin signals into neural circuit activity governing mammalian social bonding, maternal behavior, and stress buffering, making it an ideal target at the intersection of endocrinology and neurobiology.
2. **Purposeful Species Selection Based on Known Mammalian Behavior:** Rather than picking random organisms from NCBI, species selection was guided by well-established mammalian behavioral biology — comparing **highly social mammals** such as Human, Chimpanzee, and Bottlenose Dolphin, and **social rodent biomedical models** such as House Mouse and Guinea Pig, against a predominantly **solitary apex carnivore**, the Leopard. This comparative design enables systematic evaluation of conserved receptor regions alongside lineage-specific sequence variations.
3. **Open-Access Data Availability and Reproducibility:** Unlike restricted clinical phenotype cohorts in controlled-access repositories such as dbGaP that require formal institutional data-access requests, NCBI Protein RefSeq provides complete, curated, publicly downloadable FASTA sequences with zero access barriers.
4. **Appropriate Scale for In-Depth Sequence Analysis:** A six-species mammalian ortholog panel is broad enough to capture evolutionary divergence across primates, rodents, cetaceans, and carnivores while remaining focused enough for thorough residue-level inspection, physicochemical profiling, and comparative visualization.

---

## Task 1 — Biological Dataset Selection and Provenance

- **Workflow Step:** Retrieved mammalian OXTR protein batch records in FASTA format from NCBI Protein, verified RefSeq accession identifiers and exact amino acid sequence lengths, and documented dataset provenance and research scope.
- **Primary Public Repository:** National Center for Biotechnology Information — NCBI Protein and RefSeq Databases
- **Repository Web Portal:** https://www.ncbi.nlm.nih.gov/protein/
- **File Format:** Standard Multi-FASTA amino acid sequence files with `.fasta` extension
- **Total Raw Dataset Size:** **6 multi-FASTA files** containing **23 total protein sequence records** downloaded directly from NCBI Protein searches.
- **Primary Analysis Dataset Size:** **6 canonical mammalian OXTR ortholog sequences** — one representative full-length sequence per target species, ranging from **388 to 391 amino acids** in length.

### Target Mammalian OXTR Orthologs — Primary Analysis Set

| S/N | Common Name | Scientific Name | Known Behavioral Trait Used for Selection | Selected RefSeq Accession ID | Sequence Length | Raw File Name and Isoform Notes |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| 1 | **Human** | *Homo sapiens* | Highly social primate; reference benchmark | `NP_000907.2` | **389 aa** | `OXTR_Human.fasta` — Canonical isoform; identical sequence to isoforms `NP_001341582.1` through `NP_001341585.1` |
| 2 | **Chimpanzee** | *Pan troglodytes* | Close hominid relative with complex sociality | `XP_016795834.1` | **389 aa** | `OXTR_Chimpanzee.fasta` — Identical amino acid sequence to isoform `XP_063661372.1` |
| 3 | **House Mouse** | *Mus musculus* | Social and maternal rodent model organism | `NP_001074616.1` | **388 aa** | `OXTR_House Mouse.fasta` — Canonical isoform 1; identical sequence to isoform X1 `XP_036021816.1` |
| 4 | **Guinea Pig** | *Cavia porcellus* | Social caviomorph rodent model | `XP_013001788.1` | **390 aa** | `OXTR_Guinea Pig.fasta` — Isoform X2 matching canonical mammalian receptor length |
| 5 | **Leopard** | *Panthera pardus* | Predominantly solitary carnivore; behavioral contrast | `XP_019283838.2` | **388 aa** | `OXTR_Leopard.fasta` — Identical amino acid sequence to isoform `XP_019283837.2` |
| 6 | **Bottlenose Dolphin** | *Tursiops truncatus* | Marine mammal with high social intelligence | `XP_019800237.1` | **391 aa** | `OXTR_Dolphin.fasta` — Single full-length predicted RefSeq record |

### Raw Batch Records Filtered During Data Cleaning
Because NCBI Protein batch downloads include multiple predicted isoforms and related search hits, **17 redundant or non-target records** across the 6 raw FASTA files were cataloged and removed:

- **Redundant or Extended Isoforms — 8 records:** Human `NP_001341582.1`, `NP_001341583.1`, `NP_001341584.1`, and `NP_001341585.1` at 389 aa each; Chimpanzee `XP_063661372.1` at 389 aa; Mouse `XP_036021816.1` at 388 aa; Guinea Pig extended isoform X1 `XP_003464143.2` at 414 aa; and Leopard `XP_019283837.2` at 388 aa.
- **Truncated Partial Isoform — 1 record:** House Mouse OXTR isoform 2 `NP_001397175.1` at **75 aa**, lacking the N-terminal and transmembrane domains.
- **Non-Target Receptors and Neighboring Genes — 3 records:** Human melatonin receptor type 1B `NP_005950.1` at 362 aa, Human vasopressin V1a receptor `NP_000697.1` at 418 aa, and House Mouse inactive phospholipase C-like protein 2 `NP_038908.2` at 1128 aa.
- **Non-Target Species from Keyword Matches — 5 records:** Bonobo *Pan paniscus* `XP_054966873.1` at 389 aa, Clouded Leopard *Neofelis nebulosa* `XP_058582118.1` at 391 aa, Snow Leopard *Panthera uncia* `XP_049496864.1` at 390 aa, Leopard Cat *Prionailurus bengalensis* `XP_043443932.1` at 389 aa, and Northern Leopard Frog *Lithobates pipiens* `XP_077307700.1` at 384 aa.

---

## Task 2 — Data Cleaning, Physicochemical Profiling, and Homology Analysis

### 1. Sequence Quality Verification and Cleaning Workflow
- Filtered out all 17 redundant, truncated, and non-target records to retain one canonical full-length OXTR sequence per target species.
- Verified that all 6 retained sequences start with an initiator Methionine residue `M`, contain zero ambiguous or stop characters, and maintain uniform full-length open reading frames between 388 and 391 amino acids.
- Standardized all FASTA headers and compiled the cleaned dataset in `data/cleaned_fasta/OXTR_Cleaned_6Species.fasta`.

### 2. Physicochemical Characterization via ExPASy ProtParam
All six cleaned sequences were analyzed using **ExPASy ProtParam** and summarized statistically in Microsoft Excel:

| Species | RefSeq Accession | Length | Molecular Weight Da | Theoretical pI | Asp and Glu Count | Arg and Lys Count | Instability Index | Stability Status | Aliphatic Index | GRAVY Score | Hydrophobic Residues Percent |
| :--- | :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| **Human** — *Homo sapiens* | `NP_000907.2` | 389 aa | 42771.57 | 9.63 | 20 | 39 | 40.18 | Unstable | 109.67 | 0.520 | 52.70% |
| **Chimpanzee** — *Pan troglodytes* | `XP_016795834.1` | 389 aa | 42833.64 | 9.63 | 20 | 39 | 40.04 | Unstable | 109.15 | 0.524 | 52.70% |
| **House Mouse** — *Mus musculus* | `NP_001074616.1` | 388 aa | 42804.68 | 9.63 | 20 | 39 | 43.17 | Unstable | 110.39 | 0.533 | 51.80% |
| **Guinea Pig** — *Cavia porcellus* | `XP_013001788.1` | 390 aa | 43290.00 | 9.38 | 22 | 37 | 40.73 | Unstable | 107.33 | 0.473 | 51.80% |
| **Leopard** — *Panthera pardus* | `XP_019283838.2` | 388 aa | 42717.37 | 9.55 | 20 | 37 | 37.51 | Stable | 108.14 | 0.500 | 51.80% |
| **Bottlenose Dolphin** — *Tursiops truncatus* | `XP_019800237.1` | 391 aa | 43019.87 | 9.22 | 24 | 38 | 39.19 | Stable | 109.34 | 0.536 | 52.40% |
| **Mean Across 6 Species** | — | **389.17 aa** | **42906.19** | **9.51** | **21.00** | **38.17** | **40.14** | — | **109.00** | **0.514** | **52.20%** |
| **Standard Deviation** | — | **1.17 aa** | **214.28** | **0.17** | **1.67** | **0.98** | **1.86** | — | **1.10** | **0.024** | **0.45%** |

**Key Physicochemical Observations:**
- **Membrane-Bound Hydrophobicity:** All six orthologs show consistently positive GRAVY scores from **0.473 to 0.536** and high hydrophobic amino acid proportions from **51.80% to 52.70%**, reflecting the seven hydrophobic transmembrane alpha-helices required for membrane integration as a Class A GPCR.
- **Basic Isoelectric Point:** Theoretical pI values remain tightly basic across all mammals from **9.22 to 9.63** due to an excess of positively charged Arg and Lys residues over negatively charged Asp and Glu residues, supporting electrostatic interactions at intracellular G-protein coupling loops.
- **High Thermal Stability:** Aliphatic index values range from **107.33 to 110.39**, indicating strong structural thermostability across diverse mammalian body temperatures.

### 3. Pairwise Sequence Homology Against Human OXTR via NCBI BLASTp
All six cleaned sequences were aligned against the Human OXTR reference sequence `NP_000907.2` using NCBI BLASTp:

| Subject Species | RefSeq Accession | Subject Length | Max Score | Query Cover | E-value | Percent Identity | Evolutionary Conservation Note |
| :--- | :--- | :---: | :---: | :---: | :---: | :---: | :--- |
| **Human** — *Homo sapiens* | `NP_000907.2` | 389 aa | 786 | 100% | 0.0 | 100.00% | Self-alignment baseline reference |
| **Chimpanzee** — *Pan troglodytes* | `XP_016795834.1` | 389 aa | 781 | 100% | 0.0 | 98.97% | Closest primate ortholog |
| **Leopard** — *Panthera pardus* | `XP_019283838.2` | 388 aa | 650 | 96% | 0.0 | 93.03% | Solitary carnivore ortholog |
| **House Mouse** — *Mus musculus* | `NP_001074616.1` | 388 aa | 659 | 96% | 0.0 | 91.96% | Social rodent model ortholog |
| **Bottlenose Dolphin** — *Tursiops truncatus* | `XP_019800237.1` | 391 aa | 693 | 100% | 0.0 | 91.03% | Social marine mammal ortholog |
| **Guinea Pig** — *Cavia porcellus* | `XP_013001788.1` | 390 aa | 674 | 96% | 0.0 | 89.04% | Caviomorph rodent ortholog |

**Key Homology Observations:**
- All mammalian orthologs achieved an **E-value of 0.0** and **Max Scores between 650 and 786**, confirming high evolutionary conservation of OXTR across mammalian orders.
- Query coverage is **100%** in primates and dolphin and **96%** in rodents and leopard, demonstrating that minor sequence variation is localized to the N-terminal extracellular tail while the core transmembrane and ligand-binding domains remain strongly conserved.

---

## Repository Structure
```text
SWYNEX-Biological-Dataset-Analysis/
├── data/
│   ├── raw_fasta/
│   │   ├── OXTR_Chimpanzee.fasta
│   │   ├── OXTR_Dolphin.fasta
│   │   ├── OXTR_Guinea Pig.fasta
│   │   ├── OXTR_House Mouse.fasta
│   │   ├── OXTR_Human.fasta
│   │   └── OXTR_Leopard.fasta
│   └── cleaned_fasta/
│       └── OXTR_Cleaned_6Species.fasta
├── analysis/
│   └── OXTR_Task2_Cleaning & Summery.xlsx
└── README.md
