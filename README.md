# Deepen the Understanding of WWL Graph Kernels

Original paper: [Wasserstein Weisfeiler-Lehman Graph Kernels](https://proceedings.neurips.cc/paper/2019/hash/73fed7fd472e502d8908794430511f4d-Abstract.html) (NeurIPS 2019)

The codes are adapted from the [the accompanying code](https://github.com/BorgwardtLab/WWL) for the above paper. Please follow the README of that repository to install the dependencies. 

Changes are made as follows:

1. Instead of manually downloading and decompressing the datasets, we use [the DGL python library](https://docs.dgl.ai/index.html) to fetch all the datasets that were used in the original paper. 

2. `main.py` are modified to repeat cross-validation 10 times and report the average accuracy, similar to what the original paper did.

3. Added an argument `--type`,  for users to choose whether run WWL
discrete version (`discrete`), continuous version (`continuous`) or WWLsquare (`both`).

|  | MUTAG | PTC-MR | NCI1 | PROTEINS | D&D | ENZYMES |
|----|----|----|----|----|----|----|
| WWL (from the paper) | 87.27±1.50 | 66.31±1.21 | 85.75±0.25 | 74.28±0.56 | 79.69±0.50 | 59.13±0.80 |
| WWL (our implementation) | 87.81±1.46 | 65.69±1.32 | |74.89±0.68 | 79.38±0.39 | 58.28±1.07 |


|  | ENZYMES | PROTEINS(_full) | BZR | COX2 | BZR_MD | COX2_MD |
|----|----|----|----|----|----|----|
| WWL (from the paper) | 73.25±0.87 | 77.91±0.80 | 84.42±2.03 | 78.29±0.47 | 69.76±0.94 | 76.33±1.02 |
| WWL (our implementation) | 73.58±0.63 | 77.80±0.65 | 79.05±0.23 | 78.24±0.29 | 71.23±0.04 | 68.22±3.75 |
| WWL^2 | 74.30±0.59 | 77.60±0.52 | 78.72±0.87 | 81.15±1.65 | 71.32±0.35 | 66.82±2.70 | 