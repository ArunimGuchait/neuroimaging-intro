---
title: 'Introduction to Neuroimaging Data Analysis with Python: a beginner-friendly Jupyter learning module for fMRI'
tags:
  - Python
  - neuroimaging
  - fMRI
  - education
  - Nilearn
authors:
  - name: Arunim Guchait
    orcid: 0009-0002-8933-1932
    affiliation: 1
affiliations:
  - name: Institute of Cognitive Neuroscience, National Central University, Taiwan
    index: 1
date: 09 February 2026
bibliography: paper.bib
---

# Summary

Functional magnetic resonance imaging (fMRI) is widely used across cognitive neuroscience, clinical research, and data-driven behavioural science. Yet an educational barrier remains: learners often encounter neuroimaging concepts (brain organisation, experimental design, and statistical reasoning) without a clear, runnable pathway to open neuroimaging files, inspect voxel-wise signals, and produce interpretable outputs. This gap is amplified for beginners, because neuroimaging data formats and conventions are rarely explained alongside executable analysis steps.

*Introduction to Neuroimaging Data Analysis with Python* is an open, notebook-based computational learning module developed by the author to reduce this barrier. The module provides a short sequence of Jupyter notebooks that begins with essential Python foundations and progresses to neuroanatomical orientation, NIfTI-based data handling, exploratory region-of-interest (ROI) workflows, and a first-level task-based general linear model (GLM) analysis. The implementation uses widely adopted Python neuroimaging packages, particularly NiBabel and Nilearn, to support learning through executable examples and visual feedback [@nibabel; @nilearn].

# Statement of Need

Neuroimaging education frequently separates conceptual introductions from practical implementation. While this separation can be appropriate for advanced audiences, it often increases the perceived complexity of the field for newcomers and delays progression to independent practice. The present learning module addresses this gap by offering a single, incremental pathway designed for beginners, where computation supports learning of neuroimaging concepts rather than treating programming as the primary subject matter.

The module has been developed by the author according to the principle of “coding to learn”, with practical, hands-on tasks structured to enhance conceptual understanding through direct engagement with code. Introductory Python material is treated as enabling infrastructure for later neuroimaging learning, while subsequent notebooks focus on neuroimaging-specific representations (voxel grids and NIfTI containers), typical analysis ingredients (atlases, confounds, and design matrices), and an end-to-end first-level analysis. Public example datasets are accessed programmatically through community resources and standards [@markiewicz2021; @gorgolewski2016], enabling reproducible educational workflows without manual data distribution.

# Learning objectives

After completing the module, learners should be able to:

- Explain, at an introductory level, what a 4D fMRI dataset represents (3D space over time) and how voxel-wise signals are stored and indexed in NIfTI-like containers.
- Load, inspect, and visualise structural and functional neuroimaging data in Python, including slice views and statistical-map displays.
- Describe the purpose of atlases and confound regressors, and extract ROI time series from a standard parcellation (e.g., Harvard–Oxford) [@harvardoxford].
- Compute a basic ROI-to-ROI functional connectivity matrix and interpret it as an exploratory summary.
- Build a single-subject, single-run design matrix and fit a first-level GLM, including haemodynamic response function (HRF) convolution and nuisance regression [@friston1994; @nilearn_glm].
- Define contrasts, generate statistical maps, and apply introductory multiple-comparisons correction (e.g., false discovery rate).

# Module design and content

The author has organised the module as four Jupyter notebooks intended to be completed sequentially:

1. **Python foundations for neuroimaging**: core Python concepts (data types, control flow, functions), file/path handling, and light-weight use of NumPy and pandas to prepare learners for inspection and manipulation of neuroimaging-derived arrays and tables.
2. **Introduction to the human brain**: a practical orientation to major cortical and subcortical structures and functional systems, providing anatomical context for atlas-based reasoning and visualisation.
3. **Neuroimaging data analysis basics**: introduction to NIfTI data, voxel grids, and exploratory workflows; learners load example data, visualise images, extract ROI time series using an atlas, and perform a first connectivity analysis using public datasets accessed through Nilearn’s dataset interface [@nilearn_datasets].
4. **Task-based fMRI with the GLM**: a first-level, task-based analysis introducing experimental design, HRF-convolved regressors, contrast specification, and statistical inference in an end-to-end workflow suitable for teaching [@friston1994; @nilearn_glm; @spm12].

Across notebooks, learners are encouraged to run every cell, experiment with parameter values, and interpret both expected results and common errors. This instructional design treats trial-and-error as part of understanding, rather than a source of discouragement.

# Implementation, reproducibility, and adoption

The module has been designed by the author to be usable in typical teaching and self-learning environments. A local workflow is supported through a small set of widely available Python dependencies, and a browser-based workflow is supported through direct execution in Google Colab. To reduce friction in classroom settings, the notebooks rely on programmatic dataset fetching and caching so that each learner can reproduce analyses without manual data downloads; this also supports consistent teaching outcomes when the same example data are used across learners. Example data include the ICBM152 anatomical template, an OpenNeuro developmental fMRI sample (ds000228), and an auditory task dataset distributed with SPM, accessed via Nilearn's dataset fetchers [@nilearn_datasets; @markiewicz2021; @spm12].

The material is suitable for independent study by students entering neuroimaging from psychology, neuroscience, or adjacent data disciplines, and for short taught modules where an instructor wishes to provide a first practical experience with common file formats and baseline statistical workflows. The current scope is intentionally introductory: it provides a concrete first experience with neuroimaging files and single-subject modelling, while directing learners towards more advanced topics such as preprocessing pipelines, group-level inference, and more comprehensive quality control.

# Availability

The learning module is openly available in a public repository: [https://github.com/ArunimGuchait/neuroimaging-intro](https://github.com/ArunimGuchait/neuroimaging-intro). 

# References
