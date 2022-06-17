# Open Ocean Data Collection for AI and ML

> A curated collection of open datasets and datasources related to the
> ocean, marine biology and climate change.

[![Awesome](https://cdn.rawgit.com/sindresorhus/awesome/d7305f38d29fed78fa85652e3a63e154dd8e8829/media/badge.svg)](https://github.com/Inria-Chile/awesome-ocean-ai-data)[![License:
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
and satellite data. We also list other datasets relevant to particular
papers.

This compilation falls under the activities of [Inria Project
OcéanIA](https://oceania.inria.cl).

**Note:** This document will be frequently updated. Stay tuned\!

## Contributing

We welcome contributions to this guide. Please read a
[`CONTRIBUTING.md`](https://github.com/Inria-Chile/awesome-ocean-ai-data/blob/main/CONTRIBUTING.md)
on how to proceed.

## Genomic sequence datasets

### `Ocean Microbial Reference Gene Catalog v2 (OM-RGC v2)`

  - It is highly recommended to view the
    [metadata](https://zenodo.org/record/3539258) (excel format) that is
    associated with the Ocean Microbial Reference Gene Catalog v2 as
    this will give you an overview of the data available.
  - You can directly access to [OM-RGC v2
    dabase](https://www.ebi.ac.uk/biostudies/studies/S-BSST297) or via
    `oceania-fasta-query`.

### `oceania-fasta-query`

An online service to extract biologic subsequences of interest from
large FASTA files. It currently supports the [Ocean Microbial Reference
Gene Catalog v2
(OM-RGC.v2)](https://www.ebi.ac.uk/biostudies/studies/S-BSST297) gene
catalog from [Tara Oceans Expedition](https://fondationtaraocean.org).
If you would like to try the service on files from other catalogs please
the Inria Chile engineering team at <desarrollo@inria.cl>.

`oceania-fasta-query` consists of:

  - An online service currently provided by Inria Chile, and
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

Furthermore, omics data (including metagenome-assembled genomes,
metatranscriptomes, genes, proteins and functional annotations) from
plankton communities and some single-cell assays can be download
directly from [here](https://www.genoscope.cns.fr/tara/)

## Plankton images datasets

### Ecotaxa

Credit: part of this information was provided by
[Fabien Lombard](https://lov.imev-mer.fr/web/member/fabien-lombard/).

[Ecotaxa](https://ecotaxa.obs-vlfr.fr) (Picheral et al.,
[2017](#ref-ecotaxa)) contains over 188 million “objects” captured by
different microscopes. Part of the dataset has been manually annotated.
They also have an ML-based image classifier.

Ecotaxa data is available via an
[API](https://ecotaxa.obs-vlfr.fr/api/docs) allowing to programmatically
query and download parts of the datasets that are both validated and
under CC-BY license (which is the case for the Tara Ocean).

Datasets mentioned [here](https://github.com/ecotaxa/ecotaxa/issues/426)
are all under that license.

  - [Python client for the Ecotaxa’s
    API](https://github.com/ecotaxa/ecotaxa_py_client).
  - Other Ecotaxa-related repositories: <https://github.com/ecotaxa>.

#### References for datasets

  - (Sorbonne Université/CNRS-Institut De La Mer De Villefranche (IMEV)
    & Sorbonne Université/CNRS-Laboratoire D’Océanographie De
    Villefranche (LOV), [2020](#ref-10-14284-473))
  - (Sorbonne Université/CNRS, Institut De La Mer De
    Villefranche-Sorbonne Université, France & Sorbonne Université/CNRS,
    Laboratoire D’Océanographie De Villefranche-Sorbonne Université,
    France, [2020](#ref-10-14284-479)[d](#ref-10-14284-479))
  - (Sorbonne Université/CNRS, Institut De La Mer De
    Villefranche-Sorbonne Université, France & Sorbonne Université/CNRS,
    Laboratoire D’Océanographie De Villefranche-Sorbonne Université,
    France, [2020](#ref-10-14284-480)[a](#ref-10-14284-480))
  - (Sorbonne Université/CNRS, Institut De La Mer De
    Villefranche-Sorbonne Université, France et al.,
    [2020](#ref-10-14284-481))
  - (Sorbonne Université/CNRS, Institut De La Mer De
    Villefranche-Sorbonne Université, France & Sorbonne Université/CNRS,
    Laboratoire D’Océanographie De Villefranche-Sorbonne Université,
    France, [2020](#ref-10-14284-477)[c](#ref-10-14284-477))
  - (Sorbonne Université/CNRS, Institut De La Mer De
    Villefranche-Sorbonne Université, France & Sorbonne Université/CNRS,
    Laboratoire D’Océanographie De Villefranche-Sorbonne Université,
    France, [2020](#ref-10-14284-478)[b](#ref-10-14284-478))

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

## Occurrence datasets

### [Ocean Biodiversity Information System (OBIS)](https://obis.org)

OBIS is a global open-access data and information clearing-house on
marine biodiversity for science, conservation and sustainable
development. OBIS harvests occurrence records from thousands of datasets
and makes them available as a single integrated dataset. There are
several ways to access OBIS data:

  - The [mapper](https://mapper.obis.org/) allows users to visualize and
    inspect subsets of OBIS data. A variety of filters (taxonomic,
    geographic, time, data quality) is available and multiple layers can
    be combined in a single view. Layers can be downloaded as CSV files.
  - [OBIS R package](https://obis.org/manual/accessr) provides direct
    access to the OBIS database from R.
  - Both the mapper and the R package are based on the [OBIS
    API](https://api.obis.org/) which can be used by third party
    developers as well.
  - Full exports of the quality controlled presence records as `csv` or
    `parquet` [here](https://obis.org/data/access/).

## Satellite imaging datasets

### Google Earth Engine

[Google Earth Engine](https://earthengine.google.com) combines a
multi-petabyte catalog of satellite imagery and geospatial datasets with
planetary-scale analysis capabilities. Scientists, researchers, and
developers use Earth Engine to detect changes, map trends, and quantify
differences on the Earth’s surface. Earth Engine is now available for
commercial use, and remains free for academic and research use.

  - Available datasets:
    <https://developers.google.com/earth-engine/datasets/>.
  - Case studies: <https://earthengine.google.com/case_studies/>.

### Open Data on AWS

The Registry of Open Data on AWS makes it easy to find datasets made
publicly available through AWS services. Browse available data and learn
how to register your own datasets.

  - Datasets available are listed here: <https://registry.opendata.aws>.
  - A (probably incomplete) list of datasets of interest:   -
    [Sentinel-2](https://registry.opendata.aws/sentinel-2/)   - [NOAA
    Geostationary Operational Environmental Satellites (GOES) 16
    & 17](https://registry.opendata.aws/noaa-goes/)   -
    [SpaceNet](https://registry.opendata.aws/spacenet/)

## Datasets organized by papers that them

  - (Lima-Mendez et al., [2015](#ref-Lima-Mendez2015-cr)):   - De Vargas
    et al. ([2015](#ref-devargas-2015-w4)[a](#ref-devargas-2015-w4)):
    Total V9 rDNA information organized at the metabarcode level
    (Database W4) <https://doi.pangaea.de/10.1594/PANGAEA.843018>   - De
    Vargas et al.
    ([2015](#ref-devargas-2015-w5)[b](#ref-devargas-2015-w5)): Total V9
    rDNA information organized at the OTU level (Database W5)
    <https://doi.pangaea.de/10.1594/PANGAEA.843022>

# References

<div id="refs" class="references">

<div id="ref-devargas-2015-w4">

De Vargas, C., Tara Oceans Consortium, C., & Tara Oceans Expedition, P.
(2015a). *Total V9 rDNA information organized at the metabarcode level
(Database W4), supplement to: De Vargas, Colomban; Audic, Stephane;
Henry, Nicolas; Decelle, Johan; Mahe, Jean-Claude; Logares, Ramiro;
Lara, Enrique; Berney, Cédric; Le Bescot, Noan; Probert, Ian;
Carmichael, Margaux; Poulain, Julie; Romac, Sarah; Colin, Sébastien;
Aury, Jean-Marc; Bittner, Lucie; Chaffron, Samuel; Dunthorn, Micah;
Engelen, Stefan; Flegontova, Olga; Horák, Aleš; Jaillon, Olivier;
Lima-Mendez, Gipsi; Lukes, Julius; Malviya, Shruti; Morard, Raphael;
Mulot, Matthieu; Scalco, Eleonora; Siano, Raffaele; Zingone, Adriana;
Picheral, Marc; Searson, Sarah; Kandels-Lewis, Stefanie; Acinas, Silvia
G; Gorsky, Gabriel; Grimsley, Nigel; Hingamp, Pascal; Iudicone, Daniele;
Not, Fabrice; Ogata, Hiroyuki; Sieracki, Michael; Speich, Sabrina;
Stemmann, Lars; Sunagawa, Shinichi; Wincker, Patrick; Karsenti, Eric
(2015): First Tara Oceans V9 rDNA metabarcoding dataset*. PANGAEA - Data
Publisher for Earth & Environmental Science.
<https://doi.org/10.1594/PANGAEA.843018>

</div>

<div id="ref-devargas-2015-w5">

De Vargas, C., Tara Oceans Consortium, C., & Tara Oceans Expedition, P.
(2015b). *Total V9 rDNA information organized at the OTU level (Database
W5), supplement to: De Vargas, Colomban; Audic, Stephane; Henry,
Nicolas; Decelle, Johan; Mahe, Jean-Claude; Logares, Ramiro; Lara,
Enrique; Berney, Cédric; Le Bescot, Noan; Probert, Ian; Carmichael,
Margaux; Poulain, Julie; Romac, Sarah; Colin, Sébastien; Aury,
Jean-Marc; Bittner, Lucie; Chaffron, Samuel; Dunthorn, Micah; Engelen,
Stefan; Flegontova, Olga; Horák, Aleš; Jaillon, Olivier; Lima-Mendez,
Gipsi; Lukes, Julius; Malviya, Shruti; Morard, Raphael; Mulot, Matthieu;
Scalco, Eleonora; Siano, Raffaele; Zingone, Adriana; Picheral, Marc;
Searson, Sarah; Kandels-Lewis, Stefanie; Acinas, Silvia G; Gorsky,
Gabriel; Grimsley, Nigel; Hingamp, Pascal; Iudicone, Daniele; Not,
Fabrice; Ogata, Hiroyuki; Sieracki, Michael; Speich, Sabrina; Stemmann,
Lars; Sunagawa, Shinichi; Wincker, Patrick; Karsenti, Eric (2015): First
Tara Oceans V9 rDNA metabarcoding dataset*. PANGAEA - Data Publisher for
Earth & Environmental Science. <https://doi.org/10.1594/PANGAEA.843022>

</div>

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

<div id="ref-10-14284-480">

Sorbonne Université/CNRS, Institut De La Mer De Villefranche-Sorbonne
Université, France, & Sorbonne Université/CNRS, Laboratoire
D’Océanographie De Villefranche-Sorbonne Université, France. (2020a).
*Plankton community in bongo net, moose-ge cruises, north-western
mediterranean sea*. Marine Data Archive. <https://doi.org/10-14284-480>

</div>

<div id="ref-10-14284-478">

Sorbonne Université/CNRS, Institut De La Mer De Villefranche-Sorbonne
Université, France, & Sorbonne Université/CNRS, Laboratoire
D’Océanographie De Villefranche-Sorbonne Université, France. (2020b).
*Plankton community in juday-bogorov (330µm) net, point b,
villefranche-sur-mer, france*. Marine Data Archive.
<https://doi.org/10-14284-478>

</div>

<div id="ref-10-14284-477">

Sorbonne Université/CNRS, Institut De La Mer De Villefranche-Sorbonne
Université, France, & Sorbonne Université/CNRS, Laboratoire
D’Océanographie De Villefranche-Sorbonne Université, France. (2020c).
*Plankton community in régent (680µm) net, point b,
villefranche-sur-mer, france*. Marine Data Archive.
<https://doi.org/10-14284-477>

</div>

<div id="ref-10-14284-479">

Sorbonne Université/CNRS, Institut De La Mer De Villefranche-Sorbonne
Université, France, & Sorbonne Université/CNRS, Laboratoire
D’Océanographie De Villefranche-Sorbonne Université, France. (2020d).
*Plankton community in wp2 net (200µm), dyfamed point, ligurian sea,
france*. Marine Data Archive. <https://doi.org/10.14284/479>

</div>

<div id="ref-10-14284-481">

Sorbonne Université/CNRS, Institut De La Mer De Villefranche-Sorbonne
Université, France, Sorbonne Université/CNRS, Laboratoire
D’Océanographie De Villefranche-Sorbonne Université, France, & Office
Français De La Biodiversité (OFB). (2020). *Plankton community in wp2
net (200µm), pnmir cruises, parc naturel marin d’Iroise, france*. Marine
Data Archive. <https://doi.org/10-14284-481>

</div>

<div id="ref-10-14284-473">

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
