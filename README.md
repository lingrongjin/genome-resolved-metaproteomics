#Paired metagenomic and metaproteomic analysis

# Introduction
Input: raw mass spectroscopy file, predicted ORFs from metagenome for each sample \
Output: MPA protein report, Prophane functional and taxonomic annotation summary report \
Software requirement: MetaProteomeAnalyzer, Prophane

# Workflow

# Spectrum correlation and protein grouping with MPA
Input
  1. MS file
  2. protein fasta file
Database search
  1. Import customized protein database (e.g. predicted ORFs from matched metagenome)
  2. Create project and experiments in MPA using "Add Project" and "Add Experiment"
  3. Input spectra
  4. Use default search settings unless having special requirement
  5. Select and input MGF files
  6. Select "Single Experiment" if uploading only one MGF file
  7. Start search
Protein grouping
1. 

# Taxonomic and functional annotation with Prophane
Input
  1. protein report 
  2. protein fasta file (same as the protein database used in MPA search)
Note: If using generic table format, MPA protein report should be arranged as ">sample id|contig id|description"
