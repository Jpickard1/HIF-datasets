# HIF-datasets (Hypergraph Interchange Format)

This repository hosts hypergraph datasets in the `.hif` format, following the [HIF standard](https://github.com/pszufe/HIF-standard/tree/main).

---

## Usage

You can retrieve and load datasets using the [`HAT`](https://github.com/Jpickard1/Hypergraph-Analysis-Toolbox) Python package:

```python
from HAT import Hypergraph, datasets

# Download a .hif file
file_path = datasets.download(<dataset_name>, <download_location>)

# Load the dataset as a HAT.Hypergraph object
HG = datasets.load(<dataset_name>)

# Example
HG = datasets.load("Azimuth_2023")
```

Alternatively, you can use this [this notebook](https://github.com/Jpickard1/HIF-datasets/blob/main/scripts/download_hif_datasets.ipynb) to manually download datasets without relying on HAT.

## Data Storage

- The `/datasets` directory contains .hif files for each hypergraph dataset.

- The `/scripts` directory includes scripts and notebooks used to format and process the datasets.

For efficiency, .hif files larger than 50MB are split into multiple parts named as: `<dataset_name>_<part_number>of<total_parts>.hif`. The original file is split based on line count, and the resulting parts are not individually valid `.hif` files until they are reassembled.

When using `datasets.download()` or `datasets.load()`, the tool will automatically detect multi-part datasets, download all required parts, and reassemble them into a single .hif file. The reassembled file is validated against the HIF schema to ensure correctness.

## Datasets

**Note:** This section is currently under construction. The goal is to expand this repository into a larger, comprehensive database of hypergraph datasets.

At present, the collection includes approximately 200 hypergraphs primarily derived from gene enrichment analyses and regulatory network data. Some summary information for selected hypergraphs is provided in the below table. *It is the plan to improve this table*

|    | Dataset                           |   Nodes |   Edges |
|---:|:----------------------------------|----------:|----------:|
|  0 | ARCHS4_Cell-lines                 |     23601 |       125 |
|  1 | COVID-19_Related_Gene_Sets        |     16979 |       205 |
|  2 | BioCarta_2016                     |      1348 |       237 |
|  3 | CORUM                             |      2741 |      1658 |
|  4 | CellMarker_2024                   |     12642 |      1692 |
|  5 | Aging_Perturbations_from_GEO_down |     16129 |       286 |
|  6 | BioCarta_2015                     |      1678 |       239 |
|  7 | Allen_Brain_Atlas_10x_scRNA_2021  |     12361 |       766 |
|  8 | COMPARTMENTS_Experimental_2025    |      5961 |        48 |
|  9 | CCLE_Proteomics_2020              |     11851 |       378 |
| 10 | Achilles_fitness_increase         |      4320 |       216 |
| 11 | BioPlanet_2019                    |      9813 |      1510 |
| 12 | BioPlex_2017                      |     10271 |      3915 |
| 13 | ARCHS4_IDG_Coexp                  |     20883 |       352 |
| 14 | CellMarker_Augmented_2021         |     14167 |      1097 |
| 15 | ARCHS4_Tissues                    |     21809 |       108 |
| 16 | COVID-19_Related_Gene_Sets_2021   |     16853 |       478 |
| 17 | Achilles_fitness_decrease         |      4271 |       216 |
| 18 | Aging_Perturbations_from_GEO_up   |     15309 |       286 |
| 19 | ARCHS4_TFs_Coexp                  |     25983 |      1724 |
| 20 | BioCarta_2013                     |      1295 |       249 |
| 21 | COMPARTMENTS_Curated_2025         |     12865 |      1015 |
| 22 | ARCHS4_Kinases_Coexp              |     19612 |       498 |
| 23 | Azimuth_Cell_Types_2021           |      1683 |       341 |
| 24 | Cancer_Cell_Line_Encyclopedia     |     15797 |       967 |
| 25 | Azimuth_2023                      |      3712 |      1425 |

