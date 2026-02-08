# Introduction to Neuroimaging Data Analysis with Python

> **Repository:** [https://github.com/ArunimGuchait/neuroimaging-intro](https://github.com/ArunimGuchait/neuroimaging-intro)  
> **Last updated:** 2026-Feb-08

This folder contains **beginner-friendly Jupyter notebooks** that introduce neuroimaging (fMRI) data analysis in Python from scratch. The target is to reduce the initial fear of trying something completely new and complex. Every section is explained from the basics, assuming no prior knowledge.

## Contents

- **`introduction_python_for_neuroimaging.ipynb`** – **Chapter 01:** Python for complete beginners (variables, types, strings, lists, dicts, loops, functions, paths, NumPy, Pandas).
- **`introduction_to_human_brain.ipynb`** – **Chapter 02:** The human brain — basic anatomy, major cortical and subcortical structures, and functional systems overview.
- **`introduction_neuroimaging_analysis.ipynb`** – **Chapter 03:** Neuroimaging (fMRI) basics—NIfTI files, voxels, public data, visualization, ROI extraction, and a first connectivity analysis.
- **`task_based_fmri_analysis.ipynb`** – **Chapter 04:** Task-based fMRI analysis with the General Linear Model (GLM), hemodynamic response function (HRF), contrasts, statistical maps, and multiple comparisons correction.
- **`requirements.txt`** – Python dependencies (nibabel, nilearn, numpy, pandas, matplotlib, jupyter).

## Setup

### Why use a virtual environment?

A **virtual environment** keeps your project dependencies isolated and avoids conflicts with other Python projects. We strongly recommend using one.

### Option 1: Run locally (venv or conda)

1. Create a virtual environment (recommended):
   ```bash
   python -m venv neuro-env
   neuro-env\Scripts\activate   # Windows
   # source neuro-env/bin/activate  # Linux/macOS
   ```

2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Start Jupyter and open the notebook:
   ```bash
   jupyter notebook introduction_neuroimaging_analysis.ipynb
   ```
   Or open the `.ipynb` file from Jupyter Lab, VS Code, or Cursor.


### Option 2: Run on Google Colab (no local install)

Good for students who prefer a browser-based environment or don’t want to install Python locally.

1. **Open the notebook in Colab**
   - **From GitHub:** Go to [Google Colab](https://colab.research.google.com), then **File → Open notebook → GitHub**, and enter `https://github.com/ArunimGuchait/neuroimaging-intro`. Select the notebook you want to run.
    - **Direct links:**
       - [Chapter 01: Python for Neuroimaging](https://colab.research.google.com/github/ArunimGuchait/neuroimaging-intro/blob/main/introduction_python_for_neuroimaging.ipynb)
       - [Chapter 02: Introduction to the Human Brain](https://colab.research.google.com/github/ArunimGuchait/neuroimaging-intro/blob/main/introduction_to_human_brain.ipynb)
       - [Chapter 03: Neuroimaging Analysis](https://colab.research.google.com/github/ArunimGuchait/neuroimaging-intro/blob/main/introduction_neuroimaging_analysis.ipynb)
       - [Chapter 04: Task-Based fMRI Analysis](https://colab.research.google.com/github/ArunimGuchait/neuroimaging-intro/blob/main/task_based_fmri_analysis.ipynb)
   - **If you have the file locally:** go to [Google Colab](https://colab.research.google.com), then **File → Upload notebook**, and choose the `.ipynb` file.

2. **Install dependencies**  
   Run the **“Environment setup”** cell that detects Colab and runs `pip install` for the required packages (nibabel, nilearn, etc.). You only need to run it once per Colab session.

3. **Run the rest of the notebook**  
   Run the remaining cells in order. The first time you run the data-download cell, the dataset will be fetched; this may take a few minutes.

**Colab notes:**
- A **CPU runtime** is enough; no GPU is required for this tutorial.
- The downloaded data is stored in the Colab VM. If the runtime disconnects or is recycled, you’ll need to re-run the notebook and the data will download again.
- To avoid re-downloading every session, you can mount Google Drive and set the Nilearn data directory to a folder on Drive (the notebook explains this in the Colab setup cell).

## Data

This collection of notebooks downloads and uses small, public example datasets (via Nilearn) to make the exercises reproducible and easy to run. Files are downloaded the first time a notebook calls the corresponding `nilearn.datasets` fetcher and are cached on disk for later runs.

Datasets used by chapter:

- Chapter 02 (`introduction_to_human_brain.ipynb`): ICBM152 T1 anatomical template (fetched with `nilearn.datasets.fetch_icbm152_2009()`) — used for slice visualization and basic image inspection.
- Chapter 03 (`introduction_neuroimaging_analysis.ipynb`): development fMRI sample (OpenNeuro **ds000228**) fetched with `nilearn.datasets.fetch_development_fmri(...)` (the notebook uses `n_subjects=2` for speed). Also fetches atlases such as the Harvard–Oxford atlas via `nilearn.datasets.fetch_atlas_harvard_oxford()` for ROI extraction.
- Chapter 04 (`task_based_fmri_analysis.ipynb`): SPM auditory task dataset (classic task-based example) fetched with `nilearn.datasets.fetch_spm_auditory()` — used for the first-level GLM demo.

Where data is cached

- By default Nilearn stores downloaded datasets in a cache directory (commonly `~/nilearn_data` on Linux/macOS or `%USERPROFILE%\\nilearn_data` on Windows). This keeps downloads small and makes repeated runs fast.

Controlling the cache location

Set the `NILEARN_DATA` environment variable before running the notebooks to change the cache location. Examples:

```bash
# Linux / macOS (bash)
export NILEARN_DATA=~/nilearn_data

# Windows (PowerShell)
$env:NILEARN_DATA = "$HOME\\nilearn_data"
```

On Google Colab, runtime storage is ephemeral. To persist the cache between sessions mount Google Drive and set `NILEARN_DATA` to a folder on Drive (the notebooks include an optional Colab setup cell you can run to do this). Example (in a notebook cell):

```python
from google.colab import drive
drive.mount('/content/drive')
import os
os.environ['NILEARN_DATA'] = '/content/drive/MyDrive/nilearn_data'
```

If you prefer not to set `NILEARN_DATA`, Nilearn will use its default cache location. Ensure the chosen location has sufficient disk space for the datasets you intend to download.

## Suggested order

1. **New to Python?** Run **`introduction_python_for_neuroimaging.ipynb`** (Chapter 01) first (needs only Python + Jupyter; NumPy and Pandas are used in the second half).
2. **Then** run **`introduction_to_human_brain.ipynb`** (Chapter 02) to learn core neuroanatomy and brain organization.
3. **Next** run **`introduction_neuroimaging_analysis.ipynb`** (Chapter 03) to learn neuroimaging basics (install deps from `requirements.txt` or the notebook's setup cell).
4. **Finally** run **`task_based_fmri_analysis.ipynb`** (Chapter 04) to learn task-based fMRI analysis with the General Linear Model.

**Important:** We encourage you to **run all the cells yourself** and **play around with the code**—change values, try different parameters, and experiment! This hands-on approach will deepen your understanding far more than just reading. Don't worry about breaking things; that's part of the learning process.

## How to learn effectively

- **Run every cell** yourself, do not just read
- **Experiment** with the code: change numbers, file paths, plot parameters
- **Read error messages** carefully; they often tell you exactly what went wrong
- **Take your time**—neuroimaging is complex, but breaking it down step-by-step makes it manageable

## Audience

These notebooks assume **no prior knowledge** of neuroimaging or advanced Python. The series progressively builds from basics to statistical analysis:

**Chapter 01** (Python Basics):
- Core Python: variables, types, strings, lists, dictionaries, loops, functions
- Working with files and paths
- NumPy arrays and Pandas DataFrames

**Chapter 02** (Neuroimaging Basics):
- What neuroimaging and fMRI are
- NIfTI files, voxels, and 4D data
- Using NiBabel and Nilearn to load, inspect, and plot data
- Confounds, atlases, and ROI time series extraction
- Spatial smoothing and basic preprocessing

**Chapter 03** (Statistical Modeling):
- Task-based fMRI experimental design
- General Linear Model (GLM) for fMRI statistics
- Hemodynamic Response Function (HRF)
- Contrasts and statistical maps (z-scores, t-statistics)
- Multiple comparisons correction (FDR, FWE)

For even more advanced topics (group-level analysis, advanced preprocessing pipelines), see the "Summary and next steps" sections in each notebook.

## Questions or Ideas?

Have a question? Want to share how you're using this? **[Start a Discussion](https://github.com/ArunimGuchait/neuroimaging-intro/discussions)!**

This is the best place to:
- Ask for help with setup or understanding the code
- Share projects you've built using this tutorial
- Suggest improvements or new examples
- Connect with other learners

We monitor discussions regularly and are happy to help. Don't hesitate to ask—every question helps improve this resource!

## Contributing

**Suggestions and comments are always welcome!** If you find issues, have ideas for improvement, or want to contribute examples, please:

- Open an issue on GitHub
- Submit a pull request
- Share your feedback in [Discussions](https://github.com/ArunimGuchait/neuroimaging-intro/discussions)

Your input helps us improve this resource for everyone.

## Additional curated resources

- **fmri-analysis-resources**: A curated collection of tutorials, videos, and tools focused on fMRI analysis maintained by me. It complements this tutorial with deeper guides on FSL, fMRIPrep, Nilearn, NiBabel, and practical walkthroughs. Repository: https://github.com/ArunimGuchait/fmri-analysis-resources

---


**Remember:** The goal of this course is to reduce the fear of trying something new and complex. Neuroimaging can seem intimidating, but by breaking it down into manageable steps and experimenting hands-on, you'll build confidence and understanding. Don't hesitate to explore, make mistakes, and learn from them!
