# SyIDE-Tools: Synthetic Imaging Data Evaluation Tools

This repository implements a comprehensive evaluation framework for assessing the quality of synthetic medical imaging data, providing standardized metrics for congruence and coverage analysis as described in Zamzmi et al. (2025).

## Overview

The framework provides metric libraries to evaluate synthetic medical imaging datasets in terms of:

- **Congruence**: Quantifies similarity between synthetic and real patient medical data using distribution-based and image-level metrics
- **Coverage**: Measures diversity, entropy, and feature space coverage of synthetic datasets

## Installation

### Prerequisites

Install the required dependencies:

```
pip install -r requirements.txt
```

## Quick Start

### Usage

This tool contains three Jupyter notebooks which can be executed in the following order.

1. **Extract Features** 
   
FeatureExtraction.ipynb extracts statistical features from your medical images including:
   - Histogram-based features (mean, std, skewness, kurtosis, median)
   - Edge and texture features (edge density, average edge intensity)
   - Frequency domain features (low/high frequency energy)
   - Topological features (Betti numbers)

   The extracted features are saved in a CSV file.

2. **Calculate Congruence Metrics**
   
Congruence.ipynb computes similarity metrics between synthetic and real datasets:
   - Structural Similarity Index (SSIM)
   - Peak Signal-to-Noise Ratio (PSNR) 
   - Jensen-Shannon Divergence (JSD)
   - Earth Mover's Distance (EMD)
   - Cosine Similarity

3. **Calculate Coverage Metrics**
   
Coverage.ipynb computs diversity and variability of synthetic data:
   - Variance 
   - Entropy
   - Distance to centroid
   - Convex hull volume

## File Structure

```
├── requirements.txt # Python dependencies
├── FeatureExtraction.ipynb # Feature extraction (run first)
├── Congruence.ipynb # Congruence metrics calculation
├── Coverage.ipynb # Coverage metrics calculation
├── outputs/ 
│ ├── features/ # Extracted feature CSV files
│ ├── plots/ # Outputted plots
│ └── stats/ # Computed metric results 
└── README.md
```

## Metric Libraries

### Congruence Metrics

#### Image-Level Metrics
- **SSIM**: Structural similarity for pixel-level comparison
- **PSNR**: Peak signal-to-noise ratio for image quality assessment

#### Distribution-Level Metrics
- **Jensen-Shannon Divergence**: Measures distribution similarity
- **Earth Mover's Distance**: Wasserstein distance between feature distributions
- **Cosine Similarity**: Angular similarity between feature vectors

### Coverage Metrics

#### Diversity Measures
- **Variance**: Overall feature variability across dataset
- **Entropy**: Information content and diversity quantification
- **Distance to Centroid**: Average distance from feature space center
- **Convex Hull Volume**: Feature space coverage in reduced dimensions

### Supported Datasets
The framework has been tested on:
- **Real datasets**: VinDr, MIAS, DDSM, InBreast
- **Synthetic datasets**: MSYNTH (knowledge-based), HuggingFace, Mammo_medigan

### Output

Each metric calculation generates:
- Detailed scores per feature and dataset pair
- Summary CSV files with composite scores
- Visualization plots with confidence intervals

## Dependencies

The framework requires the following key packages:
- **Core computation**: numpy, scipy, pandas
- **Image processing**: scikit-image, imageio, pillow
- **Machine learning**: scikit-learn
- **Visualization**: matplotlib, seaborn
- **Topological analysis**: gudhi
- **Jupyter environment**: jupyter, ipython

See `requirements.txt` for complete dependency list with versions.

## Citation

Zamzmi G, Subbaswamy A, Sizikova E, Margerrison E, Delfino JG, Badano A. Scorecard for synthetic medical data evaluation. Commun Eng. 2025 Jul 21;4(1):130. doi: 10.1038/s44172-025-00450-1. PMID: 40691520; PMCID: PMC12280076.

## Contact

For questions, issues, or collaboration opportunities, please contact:

**Aldo Badano**  
Email: [Aldo.Badano@fda.hhs.gov](mailto:Aldo.Badano@fda.hhs.gov)

## Disclaimer

This software and documentation (the "Software") were developed at the Food and Drug Administration (FDA) by employees of the Federal Government in the course of their official duties. Pursuant to Title 17, Section 105 of the United States Code, this work is not subject to copyright protection and is in the public domain. Permission is hereby granted, free of charge, to any person obtaining a copy of the Software, to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, or sell copies of the Software or derivatives, and to permit persons to whom the Software is furnished to do so. FDA assumes no responsibility whatsoever for use by other parties of the Software, its source code, documentation or compiled executables, and makes no guarantees, expressed or implied, about its quality, reliability, or any other characteristic. Further, use of this code in no way implies endorsement by the FDA or confers any advantage in regulatory decisions. Although this software can be redistributed and/or modified freely, we ask that any derivative works bear some notice that they are derived from it, and any modified versions bear some notice that they have been modified.