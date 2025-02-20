################################################################################
# Funcotator Data Sources Package README
################################################################################

+---------------------------------------------+ 
| Data Source Version Information             |
+---------------------------------------------+ 

Version:          1.7.20200521g
Use Case:         Germline
Source:           ftp://gsapubftp-anonymous@ftp.broadinstitute.org/bundle/funcotator/funcotator_dataSources.v1.7.20200521g.tar.gz
Alternate Source: gs://broad-public-datasets/funcotator/funcotator_dataSources.v1.7.20200521.tar.gz

################################################################################

+---------------------------------------------+ 
| README                                      | 
+---------------------------------------------+ 

This is a collection of data sources to be used in conjunction with Funcotator
to annotate Somatic data samples.

This folder is a top-level Data Sources Folder for The Broad Institute's 
Funcotator tool.  When running Funcotator, pass the path to this directory in
as a command-line argument:

   ./gatk Funcotator --data-sources-path PATH/TO/THIS/FOLDER ...

For more information on Funcotator, see the GATK development github site:

  https://github.com/broadinstitute/gatk

################################################################################

+---------------------------------------------+ 
| Data Sources                                |
+---------------------------------------------+ 

Using this Data Sources Folder will enable the following data sources:

 acmg_lof
--------------------
 Custom list of genes found with (or without) LoF mechanisms in earlier studies from the Laboratory for Molecular Medicine (LMM).  
 This datasource provides information whether a given gene was found in that list and whether there were any LoF variants found by the LMM.

 acmg_rec
--------------------
 The ACMG59 recommendation list for clinical intervention.  See https://www.ncbi.nlm.nih.gov/clinvar/docs/acmg/ for more information.

 clinvar
--------------------
 ClinVar is a freely accessible, public archive of reports of the relationships among human variations and phenotypes, with supporting evidence.  
 See https://www.ncbi.nlm.nih.gov/clinvar/intro/

 gencode
--------------------
 The GENCODE project produces high quality reference gene annotation and experimental validation for human and mouse genomes.

 gnomAD_exome* 
--------------------
  The Genome Aggregation Database (gnomAD), is a coalition of investigators seeking to aggregate and harmonize exome and genome sequencing data from a variety of large-scale sequencing projects, 
  and to make summary data available for the wider scientific community. In its first release, which contained exclusively exome data, it was known as the Exome Aggregation Consortium (ExAC).
  The data set provided on this website spans 125,748 exomes and 15,708 genomes from unrelated individuals sequenced as part of various disease-specific and population genetic studies, 
  totalling 141,456 individuals. Individuals known to be affected by severe pediatric disease have been removed, as well as their first-degree relatives, so this data set should serve as 
  a useful reference set of allele frequencies for severe disease studies - however, note that some individuals with severe disease may still be included in the data set, albeit likely at 
  a frequency equivalent to or lower than that seen in the general population.

	This subset of gnomAD contains only data generated from exome samples and only the allele frequency related INFO field annotations.

	By default, gnomAD_exome is disabled.  To enable it, you must extract the tar gzipped file `gnomAD_exome.tar.gz` in the data sources directory.

  * - gnomAD_exome requires a connection to the internet.

 gnomAD_genome* 
--------------------
  The Genome Aggregation Database (gnomAD), is a coalition of investigators seeking to aggregate and harmonize exome and genome sequencing data from a variety of large-scale sequencing projects, 
  and to make summary data available for the wider scientific community. In its first release, which contained exclusively exome data, it was known as the Exome Aggregation Consortium (ExAC).
  The data set provided on this website spans 125,748 exomes and 15,708 genomes from unrelated individuals sequenced as part of various disease-specific and population genetic studies, 
  totalling 141,456 individuals. Individuals known to be affected by severe pediatric disease have been removed, as well as their first-degree relatives, so this data set should serve as 
  a useful reference set of allele frequencies for severe disease studies - however, note that some individuals with severe disease may still be included in the data set, albeit likely at 
  a frequency equivalent to or lower than that seen in the general population.

	This subset of gnomAD contains only data generated from genome samples and only the allele frequency related INFO field annotations.

	By default, gnomAD_genome is disabled.  To enable it, you must extract the tar gzipped file `gnomAD_genome.tar.gz` in the data sources directory.

  * - gnomAD_genome requires a connection to the internet.

 lmm_known
--------------------
 Variants flagged as possibly having pathogenic effects found by the Laboratory for Molecular Medicine (LMM).


