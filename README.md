# Introduction to Neuroimaging Data Analysis with Python

> **Repository:** [https://github.com/ArunimGuchait/neuroimaging-intro](https://github.com/ArunimGuchait/neuroimaging-intro)  
> **Last updated:** 2026-Feb-07

This folder contains **beginner-friendly Jupyter notebooks** that introduce neuroimaging (fMRI) data analysis in Python from scratch. The target is to reduce the initial fear of trying something completely new and complex. Every section is explained from the basics, assuming no prior knowledge.

## Contents

- **`introduction_python_for_neuroimaging.ipynb`** – **Chapter 01 (Prequel):** Python for complete beginners (variables, types, strings, lists, dicts, loops, functions, paths, NumPy, Pandas). No prior programming assumed.
- **`introduction_neuroimaging_analysis.ipynb`** – **Chapter 02 (Main):** neuroimaging (fMRI) from scratch—NIfTI, voxels, public data, visualization, ROI extraction, and a first connectivity analysis.
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
     - [Chapter 02: Neuroimaging Analysis](https://colab.research.google.com/github/ArunimGuchait/neuroimaging-intro/blob/main/introduction_neuroimaging_analysis.ipynb)
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

The notebook downloads a **small sample** of the public **development fMRI dataset** (OpenNeuro ds000228) the first time you run the download cell. Data is cached (e.g. in `~/nilearn_data`) so later runs are fast. No account or manual download is required.

## Suggested order

1. **New to Python?** Run **`introduction_python_for_neuroimaging.ipynb`** first (needs only Python + Jupyter; NumPy and Pandas are used in the second half).
2. **Then** run **`introduction_neuroimaging_analysis.ipynb`** (install deps from `requirements.txt` or the notebook's setup cell).

**Important:** We encourage you to **run all the cells yourself** and **play around with the code**—change values, try different parameters, and experiment! This hands-on approach will deepen your understanding far more than just reading. Don't worry about breaking things; that's part of the learning process.

## How to learn effectively

- **Run every cell** yourself, do not just read
- **Experiment** with the code: change numbers, file paths, plot parameters
- **Read error messages** carefully; they often tell you exactly what went wrong
- **Take your time**—neuroimaging is complex, but breaking it down step-by-step makes it manageable

## Audience

The neuroimaging notebook assumes **no prior knowledge** of neuroimaging or Python beyond basic concepts. It explains:

- What neuroimaging and fMRI are
- NIfTI files, voxels, and 4D data
- Using NiBabel and Nilearn to load, inspect, and plot data
- Confounds and atlases
- A first step in analysis (ROI time series and correlation matrix)

For more advanced topics (full preprocessing, GLM, group analysis), see the "Summary and next steps" section.

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

---

**Remember:** The goal of this course is to reduce the fear of trying something new and complex. Neuroimaging can seem intimidating, but by breaking it down into manageable steps and experimenting hands-on, you'll build confidence and understanding. Don't hesitate to explore, make mistakes, and learn from them!
