---
reference-section-title: References
link-citations: true
# title: Open Ocean Data Collection for AI and ML
author: Inria Challenge OcéanIA Project
documentclass: scrartcl
# header-includes: \usepackage{inconsolata}
# [![Awesome](https://cdn.rawgit.com/sindresorhus/awesome/d7305f38d29fed78fa85652e3a63e154dd8e8829/media/badge.svg)](https://github.com/Inria-Chile/awesome)
---

# Open Ocean Data Collection for AI and ML bubu [![Awesome](https://cdn.rawgit.com/sindresorhus/awesome/d7305f38d29fed78fa85652e3a63e154dd8e8829/media/badge.svg)](https://github.com/Inria-Chile/awesome)[![License: CeCILLv2.1](https://img.shields.io/badge/license-CeCILL--v2.1-orange)](https://cecill.info/licences.en.html)


## *An Open Ocean Data Collection for AI and ML*

A curated collection of open datasets and datasources related to the ocean, marine biology and climate change.

## Contributing

We welcome contributions to this guide. Please read a [`CONTRIBUTING.md`](https://github.com/Inria-Chile/awesome-ocean-ai-data/blob/main/CONTRIBUTING.md) on how to proceed.

## Genomic sequence datasets

### `oceania-fasta-query`

An online service to extract biologic subsequences of interest from large FASTA files. It currently supports the [Ocean Microbial Reference Gene Catalog v2 (OM-RGC.v2)](https://www.ebi.ac.uk/biostudies/studies/S-BSST297) gene catalog from [Tara Oceans Expedition](https://fondationtaraocean.org). If you would like to try the service on files from other catalogs please the Inria Chile engineering team at <desarrollo@inria.cl>.

`oceania-fasta-query` consists of:

- an online service currently provided by Inria Chile, and
- a Python client that queries on the online services and allows you to work locally on the results through a Python script or a Jupyter notebook.

#### Installing `oceania-fasta-query`

To use `oceania-query-fasta` you just need to install the Python client, for example, by running

```zsh pip install oceania-query-fasta
```

#### Using `oceania-fasta-query`

From your Python code or notebook import the `oceania` module and use method `get_sequences_from_fasta()` to run a query on the server. For example,

```python
TARA_SAMPLE_ID = "TARA_A100000171"

# REQUEST_PARAMS is a list of tuples that identify subsequences to extract
# each tuple must have the values (sequence_id, start_index, stop_index, sequence_type)
# sequence type accepted values are [raw, complement, reverse_complement], optional value if ommited defaults to "raw".
REQUEST_PARAMS = [
            ("TARA_A100000171_G_scaffold48_1", 10, 50, "complement"),
            ("TARA_A100000171_G_scaffold48_1", 10, 50),
            ("TARA_A100000171_G_scaffold48_1", 10, 50, "reverse_complement"),
            ("TARA_A100000171_G_scaffold181_1", 0, 50),
            ("TARA_A100000171_G_scaffold181_1", 100, 200),
            ("TARA_A100000171_G_scaffold181_1", 200, 230),
            ("TARA_A100000171_G_scaffold493_2", 54, 76),
            ("TARA_A100000171_G_scaffold50396_2", 87, 105),
            ("TARA_A100000171_G_C2001995_1", 20, 635),
            ("TARA_A100000171_G_C2026460_1", 0, 100),
        ]
rom oceania import get_sequences_from_fasta

# Run query on server
request_result = get_sequences_from_fasta(
    TARA_SAMPLE_ID,
    REQUEST_PARAMS
)

# get_sequences_from_fasta() returns a pandas dataFrame with the extracted sequences
print(request_result)
```

Additional examples are available as Jupyter notebooks in the GitHub repo [`oceania-query-demo`](https://github.com/Inria-Chile/oceania-query-demo), for instance:
- [A minimal example that extracts a set of sequences from a given file in the catalog.](https://github.com/Inria-Chile/oceania-query-demo/blob/master/notebooks/query_tara_simple.ipynb) [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Inria-Chile/oceania-query-demo/blob/main/notebooks/query_tara_intergenic_region.ipynb)
- [A more complex self-contained example that extracts unidentified sequences (intergenic) from files in the catalogue.](https://github.com/Inria-Chile/oceania-query-demo/blob/main/notebooks/query_tara_intergenic_region.ipynb) [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Inria-Chile/oceania-query-demo/blob/main/notebooks/query_tara_intergenic_region.ipynb)

## Plankton images datasets

### Ecotaxa

[Ecotaxa](https://ecotaxa.obs-vlfr.fr) @ecotaxa that images contains
over 188 million "objects" captured by different microscopes. Part of
the dataset has been manually annotated. They also have an ML-based
image classifier.

### WHOI-Plankton: 3.5 million human annotated plankton imgs

Annotated Plankton Images - Data Set for Developing and Evaluating Classification Methods

The data set available here comprises > 3.5 million images of microscopic marine plankton, organized according to category labels provided by researchers at the Woods Hole Oceanographic Institution (WHOI). The images are currently placed into one of 103 categories. 

The annotated image set can be downloaded at the following citable URI: <http://dx.doi.org/10.1575/1912/7341>.

The images are part of a much larger data set (>700 million images) collected in situ by automated submersible imaging-in-flow cytometry with an instrument called Imaging FlowCytobot (IFCB) [@Olson2007;@Sosik2007] at the Martha's Vineyard Coastal Observatory (MVCO) starting in 2006 and continuing to the present. Near real time image data and the complete archive are accessible for browse and download at the [IFCB Data Dashboard](http://ifcb-data.whoi.edu/mvco).

## Satellite imaging datasets

### google earth, data observatory, sentinel, copernicus, etc.}

## Datasets organized by papers using them

- [@Lima-Mendez2015-cr]:
  - @devargas-2015--w4: Total V9 rDNA information organized at the metabarcode level (Database W4) <https://doi.pangaea.de/10.1594/PANGAEA.843018>
  - @devargas-2015--w5: Total V9 rDNA information organized at the OTU level (Database W5) <https://doi.pangaea.de/10.1594/PANGAEA.843022>