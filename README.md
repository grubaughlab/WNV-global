# WNV-global

## Description

This is the repository used to build the Global Nextstrain build in the putatively named paper "Genomic epidemiology of West Nile Virus in Europe". It contains all whole genome sequences available on Genbank. 

## File Structure

**Snakefile** - contains the augur / WNV custom steps to run the build. Each snakemake command can be run as a bash command on it's own, but snakemake is used to simplify things.

**./data/sequences.fasta** - the sequences used in the builld. Name must match the accession in the metadata.tsv

**./data/metadata.tsv** - contains all metadata for the sequences.fasta

**./config/auspice_config.json** - contains code for formatting the layout of the nextstrain page.

**./config/clades.tsv** - contain nucleotide and amino acid mutations that define clades in build.

**./config/color_generator.csv** - colors that were generated separately to modify the standard color output from nextstrain

**./config/colors.tsv** - colors used in actual build.

**./config/dropped_strains.txt** - strains that you want to manually exclude from the build.

**./config/lat_longs.tsv** - gps coordinates for countries and regions

**./config/reference.gb** - WNV annotated reference genome.

**./results/augur** - will produce a number of (intermediate) files including the alignment, newick trees etc. Not committed to github.

**./auspice/** - will contain the JSONs necessary for visualisation by auspice.

## Run the build
The Snakefile details each step in the build (See that file for the specifics). As such, it should be as simple as running

snakemake clean # remove any files from a previous build

snakemake export --cores all # run the build pipeline. It will take about 30 minutes.

