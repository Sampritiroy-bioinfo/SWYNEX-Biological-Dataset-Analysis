#  SWYNEX-Biological-Dataset-Analysis

## Comparative Sequence and Physicochemical Profiling of the Mammalian Oxytocin Receptor Across Contrasting Social Phenotypes

**Internship Program:** SWYNEX Technologies — Bioinformatics Internship  
**Intern:** Sampriti Roy | B.Sc. Biotechnology

---

## Table of Contents
- **About the Project**
- **Research Question**
- **Why This Dataset Was Chosen**
- **Dataset Source, Size, and Accession Inventory**
- **Repository Structure**
- **Tools and Public Databases**
- **Internship Workflow**
- **Author**

---

## About the Project
The **Oxytocin Receptor**, encoded by the **OXTR** gene, is a Class A G-protein-coupled receptor expressed in the central nervous system and peripheral tissues. It mediates the neuroendocrine signaling of the hypothalamic nonapeptide hormone **oxytocin**, which regulates social recognition, pair-bonding, maternal care, emotional regulation, and stress response modulation.

This repository hosts the open-access mammalian **OXTR** protein sequence dataset retrieved from the National Center for Biotechnology Information, along with complete documentation of data provenance, dataset size, sequence accession identifiers, and evolutionary rationale.

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

## Dataset Source, Size, and Accession Inventory

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

### Raw Batch Records Documented for Filtering in future 
Because NCBI Protein batch downloads include multiple predicted isoforms and related search hits, the remaining **17 records** across the 6 raw FASTA files are cataloged transparently for removal during **Data Cleaning and Basic Analysis**:

- **Redundant or Extended Isoforms — 8 records:** Human `NP_001341582.1`, `NP_001341583.1`, `NP_001341584.1`, and `NP_001341585.1` at 389 aa each; Chimpanzee `XP_063661372.1` at 389 aa; Mouse `XP_036021816.1` at 388 aa; Guinea Pig extended isoform X1 `XP_003464143.2` at 414 aa; and Leopard `XP_019283837.2` at 388 aa.
- **Truncated Partial Isoform — 1 record:** House Mouse OXTR isoform 2 `NP_001397175.1` at **75 aa**, lacking the N-terminal and transmembrane domains.
- **Non-Target Receptors and Neighboring Genes — 3 records:** Human melatonin receptor type 1B `NP_005950.1` at 362 aa, Human vasopressin V1a receptor `NP_000697.1` at 418 aa, and House Mouse inactive phospholipase C-like protein 2 `NP_038908.2` at 1128 aa.
- **Non-Target Species from Keyword Matches — 5 records:** Bonobo *Pan paniscus* `XP_054966873.1` at 389 aa, Clouded Leopard *Neofelis nebulosa* `XP_058582118.1` at 391 aa, Snow Leopard *Panthera uncia* `XP_049496864.1` at 390 aa, Leopard Cat *Prionailurus bengalensis* `XP_043443932.1` at 389 aa, and Northern Leopard Frog *Lithobates pipiens* `XP_077307700.1` at 384 aa.

---

## Repository Structure 
This repository is organized to support gradual development throughout the internship 

```text
SWYNEX-Biological-Dataset-Analysis/
├── data/
│   ├── raw_fasta/              # Task 1: Unmodified NCBI multi-FASTA files for all 6 species
│   └── cleaned_fasta/          # Task 2: Deduplicated canonical OXTR FASTA sequences
├── analysis/                   # Task 2 and Task 3: ExPASy ProtParam tables, BLAST outputs, and Excel charts
├── report/                     # Task 4: Final complete bioinformatics internship report in Word format
└── README.md                   # Complete project overview, research question, rationale, and metadata
