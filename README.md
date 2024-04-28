# Paired metagenomic and metaproteomic analysis
# Introduction
Description below includes the workflow for spectrum correlation with MetaProteomeAnalyzer. Code and data for reproducing the figures in the manuscript can be found in 'R_scripts' and 'data' folder in this repository. 

# Spectrum correlation with MetaProteomeAnalyzer
## Software requirement
  1. MetaProteomeAnalyzer (Schiebenhoefer et al., 2020)
## Input
  1. MS file (raw mass spectroscopy file)
  2. protein fasta file (predicted ORFs from matched metagenome)
## Database search
  1. Import customized protein database (e.g. predicted ORFs from matched metagenome) Note: protein fasta should be formatted as ">contig_id" - when imported into MPA the header will be changed into ">generic|contig_id|Metagenome_unknown"
  2. Create project and experiments in MPA using "Add Project" and "Add Experiment"
  3. Input spectra
  4. Use default search settings unless having special requirement (You may want to unselect Mascot if you don't have Mascot search results)
  5. Select and input MGF files
  6. Select "Single Experiment" if uploading only one MGF file
  7. Start search 
## Protein inference
  1. Select experiment and click "View Results"
  2. Click "Fetch Results"
  3. After loading, click "Process Results"
  4. FDR threshold: 0.01 or 0.05
  5. Choose protein grouping rule
  6. Click "OK"
  7. Go to “Export” in the Menu Bar and select “CSV File...”
  8. Export identified proteins: can export either "Meta-proteins" or "Proteins" (If cluster using Uniref100, the two reports will be similar, i.e. usually only one protein per group)
  9. Export unique peptides
## Output
1. (Meta-)proteins (Useful columns: protein accessions, sequence coverage, peptide count, NSAF, spectral count, protein sequence, peptides)
2. Unique peptides (Useful columns: peptidd no., protein accession(s), peptide sequence, protein count, spectral count)
 
# R packages required for data visualization
library(tidyverse)\
library(ggthemes) \
library(vegan) \
library(reshape2) \
library(ComplexHeatmap) \
library(ggplot2) \
library(stringr) \
library(tidyr) \
library(forcats) \
library(ggsci) \
library(ggthemes)

# Reference
1. Schiebenhoefer, H.; Schallert, K.; Renard, B. Y.; Trappe, K.; Schmid, E.; Benndorf, D.; Riedel, K.; Muth, T.; Fuchs, S. A Complete and Flexible Workflow for Metaproteomics Data Analysis Based on MetaProteomeAnalyzer and Prophane. Nat. Protoc. 2020, 15 (10), 3212–3239. https://doi.org/10.1038/s41596-020-0368-7
