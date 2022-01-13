# Reproducibility

## General info

All genome coordinates are stored as 0-based half-open intervals (i.e. positions are counted starting with 0, and the second coordinate points at the position right after the last position of an interval).

### Folder organisation

- The data are located in folder `<experiment>/data/`
- The data for the individual experiments (reference, query, chromosome lengths) are described in file `<experiment>/experiments.tsv`
- The results are located in folder `<experiment>/results/`
  - p-values computed by MCDP are located in folder `<experiment>/results/sf/direct_eigen/`
  - p-values computed by sampling from gold null hypothesis are located in folder `<experiment>/results/sf/perm_nc/10000/`
  - p-values computed by SBDP [^1] are located in folder `<experiment>/results/sf/dp/<scaling>/`
  - running times and peak memory usages are located in folders `<experiment>/results/metrics/<algorithm>/...`

## 01 - 4 real datasets from Sarmashghi and Bafna (2019) (`01-4-real-datasets/`)

The data are prepared and provided by Sarmashghi and Bafna (2019)[^1] (published with their consent).

### Labels of experiments:

- `orig1` - EC
- `orig2` - CNV
- `orig3` - H3K4me3
- `orig4` - CS


## 02 - Genes vs CNV maps (`02-genes-vs-cnv-maps/`)

### CNV maps

The CNV maps were obtained from Supplementary Table S9 and S10 of the publication by Zarrei et al. (2015)[^7].

### Genes

The classification of gene names into categories was obtained from Supplementary Table S4 of the publication by Zarrei et al. (2015)[^7].

We used gene names (first column) as gene identificators. 
The gene coordinates were obtained from UCSC Gene Browser RefSeq on human genome hg19, track `ncbiRefSeq` and merged using `ncbiRefSeqLink` [table](https://hgdownload.soe.ucsc.edu/goldenPath/hg19/database/ncbiRefSeqLink.txt.gz).

We had two strategies to merge multiple annotations with the same gene name:

1. (used in the paper) `all`: all annotations
2. `lex-smallest`: the one with the lexicographically smallest item ID


## 03 - Synthetic data for accuracy (`03-synthetic-data-accuracy`)


## 04 - Synthetic data for time and memory requirements (`04-synthetic-data-time-mem`)



## References

[^1]: Sarmashghi S, Bafna V. Computing the Statistical Significance of Overlap between Genome Annotations with ISTAT. Cell Syst. 2019;8(6):523-529.e4. doi:10.1016/j.cels.2019.05.006
[^2]: Ernst J, Kellis M. Discovery and characterization of chromatin states for systematic annotation of the human genome. Nat Biotechnol. 2010;28(8):817-825. doi:10.1038/nbt.1662
[^3]: Ernst J, Kheradpour P, Mikkelsen TS, et al. Mapping and analysis of chromatin state dynamics in nine human cell types. Nature. 2011;473(7345):43-49. doi:10.1038/nature09906
[^4]: Bernstein BE, Kamal M, Lindblad-Toh K, Bekiranov S, Bailey DK, Huebert DJ, McMahon S, Karlsson EK, Kulbokas EJ 3rd, Gingeras TR et al. Genomic maps and comparative analysis of histone modifications in human and mouse. Cell. 2005 Jan 28;120(2):169-81.
[^5]: Bernstein BE, Mikkelsen TS, Xie X, Kamal M, Huebert DJ, Cuff J, Fry B, Meissner A, Wernig M, Plath K et al. A bivalent chromatin structure marks key developmental genes in embryonic stem cells. Cell. 2006 Apr 21;125(2):315-26.
[^6]: Ram O, Goren A, Amit I, Shoresh N, Yosef N, Ernst J, Kellis M, Gymrek M, Issner R, Coyne M et al. Combinatorial patterning of chromatin regulators uncovered by genome-wide location analysis in human cells. Cell. 2011 Dec 23;147(7):1628-39.
[^7]: Zarrei M, MacDonald JR, Merico D, Scherer SW. A copy number variation map of the human genome. Nat Rev Genet. 2015;16(3):172-183. doi:10.1038/nrg3871


