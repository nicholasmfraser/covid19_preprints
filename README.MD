# COVID-19 Preprints

This repository contains code used to extract details of preprints related to COVID-19 and visualize their distribution over time.

Preprint data is harvested from Crossref and arXiv using the R packages [rcrossref](https://github.com/ropensci/rcrossref) and [aRxiv](https://github.com/ropensci/aRxiv), respectively. 

With respect to Crossref, all records defined as "posted-content" are harvested using the `cr_types` function of the rcrossref package, and filtered for partial matches to keywords relating to COVID-19 ("coronavirus", "covid-19", "sars-cov", "ncov-2019", "2019-ncov") in either their titles or abstracts. The `institution`, `publisher` and `group-title` properties are then used to match preprints to relevant preprint repositories. In some cases, multiple Crossref records are registered for a single preprint (e.g. ChemRxiv registers a new Crossref record for each new version of a preprint). In these cases, only the earliest posted version is included in this dataset. Additionally, some preprints are deposited to multiple preprint repositories - in these cases both preprint records are included.

With respect to arXiv, records are harvested by searching directly (using the `arxiv_search` function of the aRxiv package) for COVID-19 related keywords in titles or abstracts.

![COVID-19 preprints](outputs/figures/covid19_preprints.png)
