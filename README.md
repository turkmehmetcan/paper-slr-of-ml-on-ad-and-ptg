# Repository for Materials of a Research Paper

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

## NOTE: Missing elements will be added upon acceptance of the paper

**Paper Title:** "Systematic Review of Machine Learning Applications in Anaerobic Digestion for Biological Methanation"

**Authors:** Mehmet Can Türk, Monisha Anand, Christian Otten, Michael Vedel Wegener Kofoed, Peter Gorm Larsen

**Journal:** [--PENDING--]

**Paper DOI:** [--PENDING--]

## Repository Structure

```text

├── [2] Query Files Filtered/        # Scopus exports (Q0–Q7, 8 CSV files)
├── [4] Scripts/
│   ├── [1] content_scorer.py        # Script for automated content scoring
│   ├── [2] paper_selector.py        # Script for automated paper selection suggestions
│   └── [3] figure_generator.ipynb   # Script for generating figures
├── [8] Figures/                     # Generated figures (PDF and TIFF)
├── [0] Master Sheet.xlsx            # Multi-sheet workbook with 73 selected papers
├── [1] Evaluation Sheet.xlsx        # Multi-sheet workbook used for paper selection process
├── [2] Input_CSV_Q0_List.csv        # Combined 2,160 candidate papers, used as input for script 1
├── [3] Input_CSV_Final_Ranks.csv    # Candidates with bibliometric scores, used as input for script 2
├── [5] Master Sheet.csv             # Final dataset: 73 papers × 27 fields, used as input for script 3
├── LICENSE                          # MIT License file for the repository
├── README.md                        # This file, providing an overview of the repository
└── requirements.txt                 # Python dependencies for the scripts

```

## Reproducing the Study Materials

This section outlines the workflow used to conduct the systematic literature review from initial queries to final figure generation.

### Prerequisites

- **Python 3.11.9** (or compatible version)
- Required packages listed in `requirements.txt`

```bash
# Clone the repository
git clone https://github.com/turkmehmetcan/paper-slr-of-ml-on-ad-and-ptg.git
cd paper-slr-of-ml-on-ad-and-ptg

# Install dependencies
pip install -r requirements.txt
```

### Workflow

1. **Database Query (Late May–Early June 2025)**
   Using the query texts provided in `[0] Master Sheet.xlsx`, execute the eight searches in the Scopus database. Download the CSV exports to create the folder `[2] Query Files Filtered`.

2. **Prepare Input Files**
   Generate `[2] Input_CSV_Q0_List.csv` and `[3] Input_CSV_Final_Ranks.csv` by exporting the relevant columns in `[1] Evaluation Sheet.xlsx`.

3. **Automated Scoring**
   Run the content scoring and paper selection scripts to update `[1] Evaluation Sheet.xlsx`:

   ```bash
   python "[4] Scripts/[1] content_scorer.py"
   python "[4] Scripts/[2] paper_selector.py"
   ```

4. **Paper Selection**
   Apply the detailed scoring system documented in `[1] Evaluation Sheet.xlsx` to rank and select papers for full-text analysis.

5. **Data Extraction**
   Read the selected papers in-depth and populate the relevant sheets in `[0] Master Sheet.xlsx`.

6. **Export Final Dataset**
   Export the completed data from `[0] Master Sheet.xlsx` as `[5] Master Sheet.csv`.

7. **Figure Generation**
   Run the figure generation notebook to create publication-ready plots:

   ```bash
   jupyter notebook "[4] Scripts/[3] figure_generator.ipynb"
   ```

## Citation

If you use this systematic review methodology, datasets, or scripts in your research, please cite:

```bibtex
@article{turk2026,
  title={Systematic Review of Machine Learning Applications in Anaerobic Digestion for Biological Methanation},
  author={Turk, Mehmet Can and Anand, Monisha and Otten, Christian and Kofoed, Michael Vedel Wegener and Larsen, Peter Gorm},
  journal={[--PENDING--]},
  doi={--PENDING--},
  year={2026}
}
```

## License

This work is licensed under the MIT License - see [LICENSE](LICENSE) for details.
