# MC-4C_Processed-Datasets
This repository encloses all processed datasets used in MC-4C manuscript: https://doi.org/10.1038/s41588-018-0161-5

## Dataset format
Reads in these datasets are already filtered for PCR duplicates and therefore, each read uniquely represents a single allele. Datasets are prepared in gzipped tab-delimitted files. Each row in the .gz files represents a single fragment. 
Each fragment is then described by the following columns (as header):
- **ReadID:** A numeric identifier (starting from 1) representing each sequenced read.
- **Chr:** A number between 1 to `#chr` in the genome representing the chromosome where the corresponding fragment is mapped to.
- **MappedBegin** and **MappedEnd:** Begin and end coordinates of closest restriction site in the genome where the fragment is mapped to.
- **Strand:** A numberic value representing strand of mapped fragment in the reference genome (i.e. `1` --> Forward, `-1` --> Reverse).
- **MQ:** Mapping quality, representing mapping confidence of aligner (i.e. BWA-SW) for mapping that fragment.
- **SeqRunIndex:** A numeric identifier to represent sequencing runs of the same view point 
(*this column can be potentially ignored most of the time as after PCR filter, data from same the viewpoint but different sequencing run can be combined together*).

## Dataset information (meta-data)
A meta-data file is provided for each dataset to provide additional information about that might be useful in analysing MC-4C. 
These files are named as `<Dataset name>_run-info.txt`. Each file contain the following rows:
- **SequencingRuns:** List of sequencing runs used for this dataset (delimitted by `;`)
**ViewpointRegion:** Viewpoint coordinate for this dataset (format:	`<chromosome>:<primerBegin>-<primerEnd>`)
RestrictionEnzymes	MboI;HindIII
ReferenceGenome	hg19
LocusofInterest	chr8:120800000-122075000
