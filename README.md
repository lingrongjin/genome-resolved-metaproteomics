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
  5. Choose protein grouping rule (Cluster rule may be better for sample comparison, Blakeley-Ruiz 2022)
  6. Click "OK"
  7. Go to “Export” in the Menu Bar and select “CSV File...”
  8. Can export either "Meta-proteins" or "Proteins" report (If cluster using Uniref100, the two reports will be similar, i.e. usually only one protein per group)
  9. Select the desired output folder and file name and click the “Save” button.
## Output
1. (Meta-)protein report (Useful columns: protein accessions, sequence coverage, peptide count, NSAF, spectral count, protein sequence, peptides)
 
# Taxonomic and functional annotation with Prophane
## Input
  1. protein report 
  2. protein fasta file 
*Note: If using generic table format, MPA protein report should be arranged as ">sample id|contig id|description"
## Job submission
  1. Start the web service: https://www.prophane.de
  2. Click job submission
  3. Upload protein report and select the correct source format
  4. Upload fasta file (same as the protein database used in MPA search) 
  5. *Can customize the workflow by turning on "expert" mode
  6. Submit
7. Download results in "Job Control"
## Output
  1. job_info
  2. summary_txt.
  3. plots
