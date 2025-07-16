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

The full dataset, including all auxiliary files, is permanently hosted on Hugging Face Datasets for fast and reliable access.

*   **Hugging Face Dataset Page:** 
    *   **[UrbanLPR-Dataset on Hugging Face](https://huggingface.co/datasets/abin1234/UrbanLPR-Dataset)** 
    *   (Visit this page to browse files, view the dataset card, and engage in community discussions.)

*   **Direct Download Link:** 
    *   **[Download UrbanLPR-Dataset_v1.0.zip (~1.2GB)](https://huggingface.co/datasets/abin1234/UrbanLPR-Dataset/blob/main/UrbanLPR-Dataset.zip)**
    *   (Use this link for a direct download of the complete dataset package.)

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

## Dataset Structure

The dataset is provided as a single compressed package (`UrbanLPR-Dataset_v1.0.zip`) which, when unzipped, contains the following file structure:

```text
UrbanLPR-Dataset_v1.0/
├── 2023-03-01.parquet
├── 2023-03-02.parquet
│   ...
├── 2023-03-20.parquet
├── distance.csv
├── intersection_map.jpg
└── vehicle_type_mapping.csv
```

### Main Data Files (`.parquet`)

The core of the dataset consists of 20 Parquet files, each containing the anonymized traffic data for a single day from March 1 to March 20, 2023. The schema for each file is as follows:

*   **`vehicle_id`** (`string`): Anonymized 64-character unique vehicle identifier, generated using a salted SHA-256 hash.
*   **`timestamp`** (`datetime`): The exact timestamp (YYYY-MM-DD HH:MM:SS) when a vehicle was detected.
*   **`intersection_id`** (`integer`): A unique integer ID for the intersection where the vehicle was detected.
*   **`vehicle_type`** (`integer`): A numeric ID representing the vehicle's type. Refer to `vehicle_type_mapping.csv` for a detailed description of each ID.

### Auxiliary Files

To facilitate analysis and ensure reproducibility, the dataset package also includes several essential auxiliary files:

*   **`distance.csv`**: A matrix file containing the road network distance (in meters) between every pair of intersections. The rows and columns are indexed by `intersection_id`. This file is crucial for any graph-based modeling or path reconstruction analysis.
*   **`intersection_map.jpg`**: A high-resolution map of the study area in Dongguan. Each traffic intersection used in this study is clearly marked and labeled with its corresponding `intersection_id`, providing a visual reference for the road network's topology.
*   **`vehicle_type_mapping.csv`**: A mapping table that translates the numeric `vehicle_type` IDs found in the main data files into human-readable descriptions. It includes columns for the ID (`vehicle_type`), the Chinese name (`type_name_zh`), and the English name (`type_name_en`).


## How to Cite (Preliminary)

If you use this dataset or our methodology in your research, please cite our paper and the dataset itself.

**1. Paper Citation:**
```bibtex

