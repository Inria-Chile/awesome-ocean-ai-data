# Open Ocean Data Collection for AI and ML

> A curated collection of open datasets and datasources related to the
> ocean, marine biology and climate change.

[![Awesome](https://cdn.rawgit.com/sindresorhus/awesome/d7305f38d29fed78fa85652e3a63e154dd8e8829/media/badge.svg)](https://github.com/Inria-Chile/awesome)[![License:
CeCILLv2.1](https://img.shields.io/badge/license-CeCILL--v2.1-orange)](https://cecill.info/licences.en.html)

## About

This is a dataset collection the Challenge [**AI methods for determining
ocean ecosystems from space: Combining genomic information, microscopic
and satellite
imagery**](https://oceania.inria.cl/#ai-ocean-challenge-2022) to be held
in conjunction with the [**31st International Joint Conference on
Artificial Intelligence and the 25th European Conference on Artificial
Intelligence (IJCAI-ECAI-2022)**](https://ijcai-22.org) on July 23-29,
2022, in [Messe Wien](https://www.messecongress.at/), Vienna, Austria.

The collection goes by listing sources for genomic, microscopic imaging
and satelite data. We also list other datasets relevant to particular
papers.

It falls under the activities of [Inria Project
OcéanIA](https://oceania.inria.cl).

## Contributing

We welcome contributions to this guide. Please read a
[`CONTRIBUTING.md`](https://github.com/Inria-Chile/awesome-ocean-ai-data/blob/main/CONTRIBUTING.md)
on how to proceed.

## Genomic sequence datasets

### `oceania-fasta-query`

An online service to extract biologic subsequences of interest from
large FASTA files. It currently supports the [Ocean Microbial Reference
Gene Catalog v2
(OM-RGC.v2)](https://www.ebi.ac.uk/biostudies/studies/S-BSST297) gene
catalog from [Tara Oceans Expedition](https://fondationtaraocean.org).
If you would like to try the service on files from other catalogs please
the Inria Chile engineering team at <desarrollo@inria.cl>.

`oceania-fasta-query` consists of:

  - an online service currently provided by Inria Chile, and
  - a Python client that queries on the online services and allows you
    to work locally on the results through a Python script or a Jupyter
    notebook.

#### Installing `oceania-fasta-query`

To use `oceania-query-fasta` you just need to install the Python client,
for example, by running

``` zsh
pip install oceania-query-fasta
```

#### Using `oceania-fasta-query`

From your Python code or notebook import the `oceania` module and use
method `get_sequences_from_fasta()` to run a query on the server.
Examples are available as Jupyter notebooks in the GitHub repo
[`oceania-query-demo`](https://github.com/Inria-Chile/oceania-query-demo),
for instance:

  - [A minimal example that extracts a set of sequences from a given
    file in the
    catalog.](https://github.com/Inria-Chile/oceania-query-demo/blob/master/notebooks/query_tara_simple.ipynb)
    [![Open In
    Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Inria-Chile/oceania-query-demo/blob/main/notebooks/query_tara_intergenic_region.ipynb)
  - [A more complex self-contained example that extracts unidentified
    sequences (intergenic) from files in the
    catalogue.](https://github.com/Inria-Chile/oceania-query-demo/blob/main/notebooks/query_tara_intergenic_region.ipynb)
    [![Open In
    Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Inria-Chile/oceania-query-demo/blob/main/notebooks/query_tara_intergenic_region.ipynb)

## Plankton images datasets

### Ecotaxa

Credit: part of this information was provided by Fabien.

[Ecotaxa](https://ecotaxa.obs-vlfr.fr) (Picheral et al.,
[2017](#ref-ecotaxa)) that images contains over 188 million “objects”
captured by different microscopes. Part of the dataset has been manually
annotated. They also have an ML-based image classifier.

Ecotaxa data is available via an
[API](https://ecotaxa.obs-vlfr.fr/api/docs) allowing to programatically
interrogate and download parts of the datasets that are both validated
and under CC-BY license (which is the case for the Tara Ocean).

Datasets mentioned [here](https://github.com/ecotaxa/ecotaxa/issues/426)
are all under such license \[Sorbonne Université/CNRS-Institut De La Mer
De Villefranche (IMEV) & Sorbonne Université/CNRS-Laboratoire
D’Océanographie De Villefranche (LOV)
([2020](#ref-10.14284/473));10.14284/479;10.14284/480;10.14284/481;10.14284/477;10.14284/478\].

  - [Python client for the Ecotaxa’s
    API](https://github.com/ecotaxa/pyecotaxa)
  - Another Python API (?)
    <https://github.com/ecotaxa/ecotaxa_py_client>
  - [R client for Ecotaxa’s API](https://github.com/ecotaxa/ecotaxar)
  - Other Ecotaxa-related repositories: https://github.com/ecotaxa

#### Example in R

``` r
library("httr")
# remotes::install_github("jiho/ecotaxar")
library("ecotaxar")

# to log on ecotaxa using API (normally not needed for CCBY projects)
api_login(username="ton_email", password="ton_mot_de_passe")

# launching an export TSV on prohect number185 (to adapt) to the FTP (direct export could also be possible) to loop on project for several
rsp <- ecotaxar:::apiPOST("object_set/export", body=list(
  filters=list(statusfilter="V"),
  request=list(
    project_id = 185,
    exp_type = "TSV",
    use_latin1 = FALSE,
    tsv_entities = "OPAS",
    split_by = "",
    coma_as_separator = FALSE,
    format_dates_times = TRUE,
    with_images = FALSE,
    with_internal_ids = FALSE,
    only_first_image = TRUE,
    sum_subtotal = "S",
    out_to_ftp = TRUE
  )
))

# (optional) rloock the result of the export :
# $progress_pct (progression du job)
# $result$out_file (name of the resulting file)
ecotaxar:::apiGET(paste0("jobs/", rsp$job_id, "/"))
```

Once the job finished files are available on FTP (c.f.
<https://sites.google.com/view/piqv/ecotaxa> for info on how to connect
on this one.)

### WHOI-Plankton: 3.5 million human annotated plankton images

Annotated Plankton Images - Data Set for Developing and Evaluating
Classification Methods

The data set available here comprises \> 3.5 million images of
microscopic marine plankton, organized according to category labels
provided by researchers at the Woods Hole Oceanographic Institution
(WHOI). The images are currently placed into one of 103 categories.

The annotated image set can be downloaded at the following citable URI:
<http://dx.doi.org/10.1575/1912/7341>.

The images are part of a much larger data set (\>700 million images)
collected in situ by automated submersible imaging-in-flow cytometry
with an instrument called Imaging FlowCytobot (IFCB) (Olson & Sosik,
[2007](#ref-Olson2007); Sosik & Olson, [2007](#ref-Sosik2007)) at the
Martha’s Vineyard Coastal Observatory (MVCO) starting in 2006 and
continuing to the present. Near real time image data and the complete
archive are accessible for browse and download at the [IFCB Data
Dashboard](http://ifcb-data.whoi.edu/mvco).

## Satellite imaging datasets

### google earth, data observatory, sentinel, copernicus, etc.}

## Datasets organized by papers using them

  - (Lima-Mendez et al., [2015](#ref-Lima-Mendez2015-cr)):
      - (<span class="citeproc-not-found" data-reference-id="devargas-2015">**???**</span>)–w4:
        Total V9 rDNA information organized at the metabarcode level
        (Database W4) <https://doi.pangaea.de/10.1594/PANGAEA.843018>
      - (<span class="citeproc-not-found" data-reference-id="devargas-2015">**???**</span>)–w5:
        Total V9 rDNA information organized at the OTU level (Database
        W5) <https://doi.pangaea.de/10.1594/PANGAEA.843022>

# References

<div id="refs" class="references">

<div id="ref-Lima-Mendez2015-cr">

Lima-Mendez, G., Faust, K., Henry, N., Decelle, J., Colin, S., Carcillo,
F., Chaffron, S., Ignacio-Espinosa, J. C., Roux, S., Vincent, F.,
Bittner, L., Darzi, Y., Wang, J., Audic, S., Berline, L., Bontempi, G.,
Cabello, A. M., Coppola, L., Cornejo-Castillo, F. M., … Raes, J. (2015).
Ocean plankton: Determinants of community structure in the global
plankton interactome. *Science*, *348*(6237), 1262073.
<https://doi.org/10.1126/science.1262073>

</div>

<div id="ref-Olson2007">

Olson, R. J., & Sosik, H. M. (2007). A submersible imaging-in-flow
instrument to analyze nano-and microplankton: Imaging FlowCytobot.
*Limnology and Oceanography: Methods*, *5*(6), 195–203.
<https://doi.org/10.4319/lom.2007.5.195>

</div>

<div id="ref-ecotaxa">

Picheral, M., Colin, S., & J.-O., I. (2017). *EcoTaxa, a tool for the
taxonomic classification of images*. <http://ecotaxa.obs-vlfr.fr>

</div>

<div id="ref-10.14284/473">

Sorbonne Université/CNRS-Institut De La Mer De Villefranche (IMEV), &
Sorbonne Université/CNRS-Laboratoire D’Océanographie De Villefranche
(LOV). (2020). *Plankton community in wp2 net (200µm), point b,
villefranche-sur-mer, france*. Marine Data Archive.
<https://doi.org/10.14284/473>

</div>

<div id="ref-Sosik2007">

Sosik, H. M., & Olson, R. J. (2007). Automated taxonomic classification
of phytoplankton sampled with imaging-in-flow cytometry. *Limnology and
Oceanography: Methods*, *5*(6), 204–216.
<https://doi.org/10.4319/lom.2007.5.204>

</div>

</div>
