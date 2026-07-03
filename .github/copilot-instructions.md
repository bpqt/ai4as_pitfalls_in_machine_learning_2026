# Copilot Instructions for AI4AS Pitfalls in Machine Learning

## Project Overview

This repository contains Jupyter notebooks and course materials for the AI4AS Summer School on "Pitfalls in Machine Learning" in animal science. It's an educational project with exercise and solution notebooks, datasets, and documentation rendered via Quarto.

## Setup & Environment

**Python Version:** 3.12 (configured in `.devcontainer/devcontainer.json`)

**Install Dependencies:**
```bash
pip install -r requirements.txt
```

**Note:** `requirements.txt` is auto-generated from notebook imports using `99_update_requirements.ipynb`. Do not edit it manually—update it by running that notebook and committing the changes.

**Environment:** 
- Primary development environment: GitHub Codespaces with `.devcontainer` (Python 3.12, Jupyter)
- Alternatively: local virtual environment with Python 3.12

## Key Project Structure

```
├── notebooks_code/
│   ├── class_01_exercise.ipynb      # Student exercises
│   ├── class_02_exercise.ipynb
│   ├── class_03_exercise.ipynb
│   ├── class_01_solution.ipynb      # Reference solutions
│   ├── class_02_solution.ipynb
│   ├── class_03_solution.ipynb
│   └── 99_update_requirements.ipynb # Regenerates requirements.txt
├── data/
│   ├── raw/                         # Original datasets (CSV, XLSX, ZIP)
│   └── processed/                   # Processed data outputs
├── docs/                            # Slides and documentation
├── _quarto.yml                      # Quarto configuration
├── requirements.txt                 # Auto-generated from notebooks
└── .devcontainer/                   # Container configuration
```

## Working with Notebooks

**Opening & Running:**
- Open `.ipynb` files with Jupyter kernel (Python 3.12)
- In Codespaces, the kernel is configured automatically
- Install "Data Wrangler" extension in VS Code for visual data inspection

**Key Datasets:**
- `data/raw/ames_housing.csv` — Ames Housing dataset (ML regression examples)
- `data/raw/wang_et_al_2022.xlsx` — Wang et al. 2022 data (animal science application)
- `data/raw/rwu_275a_1_convert_10hz.zip` — RWU 275A accelerometer time series data (sensor data examples)

## Documentation & Rendering

**Quarto Configuration** (`_quarto.yml`):
- Output format: HTML (with table of contents) and Typst
- Code folding enabled, line numbers shown, code download available
- Uses default Quarto project type with `reports/` as output directory

**Build Documentation:**
```bash
quarto render
```
Output goes to `reports/` directory.

## Key Conventions

1. **Notebook Naming:** 
   - `class_NN_exercise.ipynb` — Student-facing with blank cells to fill
   - `class_NN_solution.ipynb` — Completed reference solution
   - `99_update_requirements.ipynb` — Utility for syncing dependencies

2. **Data Workflow:**
   - Raw datasets go in `data/raw/`
   - Processed outputs go in `data/processed/`
   - Notebooks read from raw, write to processed

3. **Git Workflow (from README):**
   - Fork the repository to your own account
   - Commit and push regularly (every 15–30 minutes) to avoid losing work
   - Use descriptive commit messages (e.g., "Exercise 1 finished")

4. **Libraries Used:**
   - Data: pandas, numpy, openpyxl
   - Visualization: matplotlib, seaborn
   - ML: scikit-learn, imbalanced-learn, Boruta
   - Statistics: statsmodels

## Common Tasks

**Updating Dependencies:**
1. Add import to the relevant notebook(s)
2. Run `99_update_requirements.ipynb`
3. Review changes to `requirements.txt`
4. Commit and push updated requirements.txt

**Adding Datasets:**
- Place raw data in `data/raw/`
- Document the source in the README
- If processing, save outputs to `data/processed/`

**Modifying Exercise/Solution Notebooks:**
- Keep exercise and solution versions in sync
- Exercise notebooks should have cells/sections for students to complete
- Solution notebooks should have complete working code
