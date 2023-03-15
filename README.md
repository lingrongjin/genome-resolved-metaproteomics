# Paired metagenomic and metaproteomic analysis

# Introduction
Input: raw mass spectroscopy file, predicted ORFs from metagenome for each sample \
Output: MPA protein report, Prophane functional and taxonomic annotation summary report \
Software requirement: MetaProteomeAnalyzer, Prophane

# Workflow

# Spectrum correlation and protein grouping with MPA
## Input
  1. MS file
  2. protein fasta file 
## Database search
  1. Import customized protein database (e.g. predicted ORFs from matched metagenome)
  2. Create project and experiments in MPA using "Add Project" and "Add Experiment"
  3. Input spectra
  4. Use default search settings unless having special requirement
  5. Select and input MGF files
  6. Select "Single Experiment" if uploading only one MGF file
  7. Start search 
## Protein grouping
  1. Select and experiment and click "View Results"
  2. Click "Fetch Results"
  3. After loading, click "Process Results"
  4. FDR threshold: 0.01 or 0.05
  5. Choose protein grouping rule (Cluster rule may be better for sample comparison, Blakeley-Ruiz 2022)
  6. Click "OK"
  7. Go to “Export” in the Menu Bar and select “CSV File...”
  8. Click the “Export Metaproteins” button
  9. Select the desired output folder and file name and click the “Save” button.

# Taxonomic and functional annotation with Prophane
## Input
  1. protein report 
  2. protein fasta file (same as the protein database used in MPA search) 
Note: If using generic table format, MPA protein report should be arranged as ">sample id|contig id|description"

