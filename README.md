# UrbanLPR-Dataset: A Large-Scale License Plate Recognition Dataset for Travel Time Prediction
Dataset and documentation for "Urban Road Network Travel Time Prediction Method Based on "Node-Link-Network" Spatiotemporal Reconstruction: A License Plate Data-Driven WGCN-BiLSTM Model"

[![License: CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-blue.svg)](https://creativecommons.org/licenses/by/4.0/)

This repository provides the documentation for the **UrbanLPR Dataset**, a large-scale dataset of license plate recognition data collected in Dongguan, China. This dataset was created to support our research paper:

### Paper Details
*   **Title:** Urban Road Network Travel Time Prediction Method Based on "Node-Link-Network'' Spatiotemporal Reconstruction: A License Plate Data-Driven WGCN-BiLSTM Model
*   **Authors:** Weiwei Qi*, Bin Rao*, and Jiabing Wu (* co-first authors)
*   **Journal:** **Measurement** (Accepted for publication)
*   **Corresponding Author:** Jiabing Wu (jiabinwu@fosu.edu.cn)

The dataset is designed to facilitate research in urban traffic analysis, travel time estimation, path reconstruction, and spatiotemporal data mining, especially in environments with sparse sensor coverage.

## Data Access (Coming Soon)

The full, anonymized dataset will be made publicly available through a permanent repository on Zenodo to ensure long-term access and proper academic citation.

*   **Zenodo Repository:** `[Link will be provided here upon data upload]`
*   **DOI for Citation:** `[DOI will be generated upon data upload]`

A small sample of the data will also be uploaded to this GitHub repository for quick preview purposes.

## Abstract

<details>
<summary><strong>Click to view the Abstract from the paper</strong></summary>

Accurate travel time prediction is critical for effective urban traffic management and route planning. However, few studies address travel time prediction in sparsely sensored regions. To address this gap, we propose a novel ``node-link-network'' framework for urban road network travel time prediction, which integrates sparse node data, path reconstruction, and network-level prediction. Using license plate data collected at intersections (node level), the framework employs a Path Reconstruction Random Forest (PRRF) model to innovatively reconstruct spatiotemporal path data (link level) with multi-factor features and quantify the weights of network spatial relationships. Leveraging these reconstructed paths, a Weighted Graph Convolutional Network with Bidirectional Long Short-Term Memory (WGCN-BiLSTM) employs dynamic weighted adjacency matrices to model spatiotemporal dependencies for accurate travel time prediction (network level). Results on the UrbanLPR dataset, collected in Dongguan, China demonstrate that our reconstruction model achieves a training time of 2.42 seconds, over 10 times faster than baseline models. Based on the reconstructed weighted matrices, our method reduces MAE by 23\% (to 6.46 seconds) compared to the second-best baseline, addressing travel time prediction in sparsely sensored regions and improving travel time prediction for urban traffic management.

</details>

## Dataset Details

*   **Location:** Dongguan, China
*   **Data Source:** License Plate Recognition (LPR) cameras at road intersections.
*   **Time Period:** March 1, 2023 to March 20, 2023 (20 consecutive days).
*   **Anonymization:** **All license plate numbers in the dataset have been fully anonymized.**

## File Structure and Schema (Preliminary)

The final dataset will be provided in the efficient **Parquet** format. The data will be split into manageable files (e.g., one file per day). The planned data schema is as follows:

| Column Name       | Data Type | Description                                               |
|-------------------|-----------|-----------------------------------------------------------|
| `vehicle_id`      | `string`  | Anonymized unique vehicle identifier.                     |
| `timestamp`       | `datetime`| The exact time a vehicle was detected.                    |
| `intersection_id` | `integer` | A unique ID for the intersection where the vehicle was seen. |
| `...`             | `...`     | *(More columns may be included, to be finalized soon)*    |

*This schema is preliminary and will be finalized upon data release.*

## How to Cite (Preliminary)

If you use this dataset or our methodology in your research, please cite our paper and the dataset itself.

**1. Paper Citation:**
```bibtex

