# BIOC3301
"Linkage between soil microbial community composition and nitrogen level in Gordon Square"


For complete metadata mapping file, consult 2018_02_smb/map.complete.tsv

Basic pipeline conducted using QIIME performed on Cirrus server:
Brief Outline:
  1. Forward and reverse paired end Illumina reads were merged using SeqPrep method. Script used: join_paired_ends.py
    -- script file: join
  2. Demultiplexing Fastq sequence data where barcode and sequences were combined together. Script used: split_libraries_fastq.py
    -- script file: demultiplex
  3. OTUs picked using closed reference, and an OTU table was generated. Script used: pick_closed_reference_otus.py
    -- script file: pickingotus
  4. Basic workflow for running diversity analysis performed using the script: core_diversity_analyses.py. Output gives a combination of alpha rarefaction, beta diversity, taxonomy summary at different taxonomic level.
    -- script file: cdanalysis
  5. Heatmap of identified phyla generated. Script used: make_otu_heatmap.py
    -- script file: heatmap_all
  6. 3D beta-diversity PCoA converted into 2D. Script used: make_2d_plots.py
    -- script file: 2D_PCoA
  7. Statistical test (ANOSIM) performed to determine significance level. Script used: compare_categories.py
    -- script file: compare_category
  8. Taxonomy of all phyla except Proteobacteria and Thaumarchaeota were filtered out. Script used: filter_taxa_from_otu_table.py
    -- script file: taxafilter
  9. Core diversity analyses ran again with a filtered OTU table from previous step. Script used: core_diversity_analyses.py
    -- script file: cda_taxafiltered
  10. Heatmap of identifed classes below Proteobacteria and Thaumarchaeota phyla were generated. Script used: make_otu_heatmap.py
    -- script file: heatmap
  11. New 3D PCoA generated from (9.) converted into 2D. Script used: make_2d_plots.py
    -- script file: 2D_PCoA_filtered
  12. ANOSIM performed again to determine significance level. Script used: compare_categories.py
    -- script file: compare_category_taxafiltered
  13. Kruskal-Wallis Test (another statistical test) was performed at the end to conclude the significance level of data. Script used: group_significance.py
    -- script file: group_significance

Reference:

QIIME allows analysis of high-throughput community sequencing data

J Gregory Caporaso, Justin Kuczynski, Jesse Stombaugh, Kyle Bittinger, Frederic D Bushman, Elizabeth K Costello, Noah Fierer, Antonio Gonzalez Pena, Julia K Goodrich, Jeffrey I Gordon, Gavin A Huttley, Scott T Kelley, Dan Knights, Jeremy E Koenig, Ruth E Ley, Catherine A Lozupone, Daniel McDonald, Brian D Muegge, Meg Pirrung, Jens Reeder, Joel R Sevinsky, Peter J Turnbaugh, William A Walters, Jeremy Widmann, Tanya Yatsunenko, Jesse Zaneveld and Rob Knight; Nature Methods, 2010; doi:10.1038/nmeth.f.303
