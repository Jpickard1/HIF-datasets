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

## Datasets

**Note:** This section is currently under construction. The goal is to expand this repository into a larger, comprehensive database of hypergraph datasets.

At present, the collection includes approximately 200 hypergraphs primarily derived from gene enrichment analyses and regulatory network data.

## Data Storage

- The `/datasets` directory contains .hif files for each hypergraph dataset.

- The `/scripts` directory includes scripts and notebooks used to format and process the datasets.

For efficiency, .hif files larger than 50MB are split into multiple parts named as: `<dataset_name>_<part_number>of<total_parts>.hif`. The original file is split based on line count, and the resulting parts are not individually valid `.hif` files until they are reassembled.

When using `datasets.download()` or `datasets.load()`, the tool will automatically detect multi-part datasets, download all required parts, and reassemble them into a single .hif file. The reassembled file is validated against the HIF schema to ensure correctness.
