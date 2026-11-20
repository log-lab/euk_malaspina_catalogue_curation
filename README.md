# Eukaryotic Gene Catalogue Curation — Malaspina Expedition

Reproducible curation pipeline for the Malaspina eukaryotic gene catalogue, documented in `malaspina_eukaryotic_catalogue_curation.Rmd`.

## Pipeline overview

The pipeline filters a mixed prokaryotic/eukaryotic ORF catalogue down to a curated set of eukaryotic genes through four steps:

1. **Taxonomic assignment** — three parallel MMseqs2 searches against EukProt, MarFERReT v1.1.1, and MMETSP_Uniclust90
2. **Tax ID score filtering** — retention of ORFs with hits in all three databases, ranked by a weighted combination of query coverage and percent identity
3. **MATOU validation** — cross-validation against the Marine Atlas of Tara Oceans Unigenes eukaryotic reference
4. **Consensus taxonomy** — derivation of the lowest common ancestor for each retained gene using NCBI taxonomy

## Dependencies

- [MMseqs2](https://github.com/soedinglab/MMseqs2) (v13-45111)
- R packages: `taxize`, `data.table`, `dplyr`, `stringr`

## Data

Data files accompanying this pipeline are deposited on Zenodo: https://doi.org/10.5281/zenodo.23557900.

## Related publication

The catalogue is described in: Greco M. et al. (2026) *Depth structures metabolic potential and warming responses in marine microbial eukaryotes*. bioRxiv. https://doi.org/10.64898/2026.11.10.765571
