#  Computational Identification of Conserved HIV-1 p24 Epitope Candidates

> A fully reproducible, open-source computational pipeline for sequence-based prioritization of conserved T-cell and B-cell epitope candidates from HIV-1 p24.

---

## 🎯 Scientific Scope

This project demonstrates a **computational immunoinformatics workflow** for sequence-based prioritization of candidate epitopes.  
It does **not** establish immunogenicity, HLA binding, protective immunity, or vaccine efficacy.

**Goal:** Identify and rank conserved peptide candidates within HIV-1 p24 that are:
- ✅ Highly conserved across diverse HIV-1 strains
- ✅ Broadly represented in sequence datasets
- ✅ Supported by literature for B-cell evidence
- ✅ Prioritized using a reproducible multi-criteria scoring system

---

## 🧬 Pipeline Overview

```

NCBI GenBank (185 sequences)
↓
Quality Control (length filter, ambiguity removal)
↓
Multiple Sequence Alignment (MAFFT, 235 positions)
↓
Conservation Analysis (Shannon entropy)
↓
MHC-I Peptide Screening (9-mers)
↓
MHC-II Peptide Screening (15-mers)
↓
B-cell Evidence Mapping (literature-supported)
↓
Diversity-Aware Ranking (multi-criteria scoring)
↓
21 Prioritized Candidates

```

---

## 📊 Results

### Dataset Summary

| Feature | Value |
|---------|-------|
| **Total sequences analyzed** | 185 HIV-1 p24 sequences |
| **Alignment length** | 235 positions |
| **Total peptides screened** | 10,112 |
| **MHC-I (9-mer) unique peptides** | 3,557 |
| **MHC-II (15-mer) unique peptides** | 6,555 |
| **Final candidates** | 21 |

### Top 5 Candidates

| Rank | Peptide | Class | Score | Support (n/185) | Conservation |
|:----:|---------|:-----:|:-----:|:---------------:|:------------:|
| 1 | GPKEPFRDY | MHC-I | 0.590 | 182 | 0.976 |
| 2 | PKEPFRDYV | MHC-I | 0.590 | 182 | 0.974 |
| 3 | QGPKEPFRD | MHC-I | 0.589 | 182 | 0.973 |
| 4 | KEPFRDYVD | MHC-I | 0.589 | 182 | 0.973 |
| 5 | NKIVRMYSP | MHC-I | 0.589 | 181 | 0.976 |

### B-cell Epitope Candidate

| Peptide | Class | Score | Support (n/185) | Conservation |
|---------|:-----:|:-----:|:---------------:|:------------:|
| KVVEEKAFSPEVIPM | MHC-II | 0.480 | 41 | 0.974 |

### Ranking Criteria

| Criterion | Weight |
|-----------|:------:|
| Conservation | 40% |
| B-cell Evidence | 30% |
| Diversity Coverage | 20% |
| Sequence Support | 10% |

---

## 🛠️ Methods

### Data Acquisition
- **Source:** NCBI GenBank (db = nucleotide)
- **Date of retrieval:** 2026-08-20
- **Accessions:** All 185 accessions are available in `data/metadata/hiv_p24_metadata.csv`
- **Total:** 185 unique HIV-1 p24 sequences

### Quality Control
- **Length filter:** 200–260 amino acids
- **Ambiguous residue removal:** Sequences with >5% N, X, B, or Z were excluded
- **Deduplication:** Exact sequence deduplication performed

### Multiple Sequence Alignment
- **Tool:** MAFFT v7.490
- **Result:** 235 aligned positions
- **Command:** `mafft --auto --maxiterate 1000 --thread 2`

### Conservation Analysis
> Conservation was quantified using position-wise **Shannon entropy** across the aligned p24 sequences, with lower entropy indicating higher conservation.

- **Formula:** `Conservation = 1 - (Entropy / log₂(20))`
- **Threshold:** ≥ 0.7 considered conserved

### Peptide Screening
- **MHC-I:** All overlapping 9-mers
- **MHC-II:** All overlapping 15-mers
- **Total unique peptides:** 10,112

### B-cell Evidence
- Literature-supported peptides from peer-reviewed sources:
  - Los Alamos HIV Database
  - IEDB (Immune Epitope Database)
  - Published journal articles

### Ranking Formula

```

Final Score = (0.40 × Conservation)
+ (0.30 × B-cell Support)
+ (0.20 × Diversity Coverage)
+ (0.10 × Sequence Support)

```

### Sensitivity Analysis

A preliminary sensitivity analysis was performed by testing alternative weight configurations:
- **B-cell weight increased** from 0% to 40% (CELL 4c)
- **B-cell weight increased** to 60% (CELL 4d, extreme condition)

The top candidate (`GPKEPFRDY`) remained stable across all tested configurations, indicating robust prioritization.

### Random Seed
- **Random seed:** `42` (used for all stochastic processes)
- **Reproducibility:** All random operations are seeded for exact reproducibility.

---

## 📁 Project Structure

```

HIV1-p24-Epitope-Analysis/
│
├── data/
│   ├── raw/              # Raw FASTA sequences
│   ├── processed/        # Cleaned sequences
│   └── metadata/         # Metadata with accessions (CSV)
│
├── results/
│   ├── tables/           # All CSV results
│   ├── figures/          # 5 key figures
│   └── reports/          # Research reports
│
├── notebooks/            # Analysis notebooks
├── README.md
└── requirements.txt

```

---

## 📊 Figures

| Figure | Description |
|--------|-------------|
| `conservation_profile.png` | Shannon entropy profile across p24 |
| `support_distribution.png` | Top 30 peptides by support |
| `score_distribution.png` | Score distribution by class |
| `conservation_vs_support.png` | Conservation vs support correlation |
| `shortlist_table.png` | Final shortlist summary |

---

## 🧪 Reproducibility

All analyses were performed using **Python** and **MAFFT**.  
Raw and processed sequence data, metadata, intermediate tables, figures, and final rankings are provided in this repository.

### Environment

| Component | Version |
|-----------|---------|
| **Python** | 3.10.12 |
| **Biopython** | 1.83 |
| **Pandas** | 2.0.3 |
| **NumPy** | 1.24.3 |
| **Matplotlib** | 3.7.2 |
| **Seaborn** | 0.12.2 |
| **Scikit-learn** | 1.3.0 |
| **MAFFT** | 7.490 |

### Installation

```bash
# Install dependencies
pip install -r requirements.txt

# Install MAFFT (Ubuntu/Debian)
sudo apt-get install mafft
```

Dependencies

```
biopython>=1.81
pandas>=2.0.0
numpy>=1.24.0
matplotlib>=3.7.0
seaborn>=0.12.0
scipy>=1.10.0
scikit-learn>=1.3.0
requests>=2.31.0
```

---

⚠️ Limitations & Reproducibility Statement

1. HLA-restricted prediction was NOT performed
      MHC-I/MHC-II assignment is based on peptide length (9-mer/15-mer) and conservation, not NetMHCpan or similar tools.
2. B-cell epitopes are literature-supported
      Not experimentally validated in this study.
3. In-silico prioritization only
      All results require experimental validation.
4. Single protein target
      Only HIV-1 p24 was analyzed.
5. No experimental validation
      No wet-lab validation was performed. This is a purely computational study.
6. Reproducibility
      All code, data, and parameters are provided. The analysis can be fully reproduced by running the notebooks in order with the provided data.

---

🧬 Scientific Scope

This project demonstrates a computational immunoinformatics workflow for sequence-based prioritization of candidate epitopes.
It does not establish immunogenicity, HLA binding, protective immunity, or vaccine efficacy.

---

📋 Recommended Next Steps

1. 🧪 Experimental validation of top 5 candidates
2. 🧬 HLA binding assays (ELISPOT, MHC multimer)
3. 🧫 B-cell epitope validation (ELISA, peptide microarray)
4. 🔬 Expand analysis to other HIV-1 proteins (Env, Nef, etc.)

---

📝 Citation

```
Computational Identification of Conserved HIV-1 p24 Epitope Candidates.
Moafi, Sepideh, 2026. GitHub Repository.
```

---

👤 Author

Sepideh Moafi 
---

📄 License

This project is provided for research and educational purposes only.

---

🙏 Acknowledgments

· NCBI GenBank for sequence data
· MAFFT for multiple sequence alignment
· IEDB and Los Alamos HIV Database for reference epitopes

---

🏁 Status

✅ Complete computational analysis and reproducible research package

---

This is an in-silico prioritization study. Results require experimental validation.

```
