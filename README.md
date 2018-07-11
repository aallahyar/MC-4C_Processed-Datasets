# MC-4C_Processed-Datasets
This repository encloses all processed datasets used in MC-4C manuscript: https://doi.org/10.1038/s41588-018-0161-5

## Dataset format
Datasets are prepared in gzipped tab-delimitted files. Each row in the .gz files represents a single fragment. 
Each fragment is then described by the following columns (as header):
- ReadID: A numeric identifier (starting from 1) representing each sequenced read.
- Chr: A number between 1 to #chr in the genome representing the chromosome where the corresponding fragment is mapped to.
- MappedBegin and MappedEnd: Begin and end coordinates of closest restriction site in the genome where the fragment is mapped to.
- Strand: A numberic value representing strand of mapped fragment in the reference genome (i.e. 1 --> Forward, -1 --> Reverse).
- MQ: Mapping quality, representing mapping confidence of aligner for mapping that fragment (i.e. BWA-SW).
- SeqRunIndex: A numeric identifier to represent sequencing runs of the same view point 
(can be potentially ignored as after PCR filter, data from same the viewpoint but different sequencing runs can be combined together).

*Note* Reads in these datasets are already filtered for PCR duplicates and therefore, each read uniquely represents a single allele.