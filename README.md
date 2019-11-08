# DBiT-seq

This is a public repository for all code connected to DBiT-Seq (microfluidic Deterministic Barcoding in Tissue for spatial omics sequencing).

**Please cite**: Yang et al. High-Spatial-Resolution Multi-Omics Atlas Sequencing of Mouse Embryos via Deterministic Barcoding in Tissue. bioRxiv 2019: doi: https://doi.org/10.1101/788992.

## Schematic workflow

<p><img src="https://github.com/MingyuYang-Yale/DBiT-seq/blob/master/workflow.png" alt="foo bar" title="train &amp; tracks" /></p>

All raw and processed files are available at GEO **(GSE137986)**

## Pre-processing
This is [code](https://github.com/MingyuYang-Yale/DBiT-seq/tree/master/Pre-processing) for quality control and reformating the read file for compatibility with st-pipeline.

#### RNA-seq:
|SampleID | Raw reads  | Q20 | Q30| With Barcode | Percentage(%)|
| :---: | :---: | :---: | :---: | :---: | :---:   |
| 0628cL (50um-E12)  | 53,619,846 | 93.39;87.52 | 83.07;74.40|22,957,813|42.82|
| 0702cL (50um-E10) | 162,684,631  |94.32;89.67|85.84;77.25|71,560,818|43.99|
| 0713cL (25um-E10) | 108,133,036| 92.94;75.01| 81.72;54.96 | 27,520,710 | 25.45|
| 0719cL (10um-E10) | 90,264,327 | 92.64;76.54 | 80.90;58.41 | 38,181,329| 42.30 |
| 0725e10cL (50um-E10) | 128,523,896 | 93.12;79.41 | 81.57;63.63 | 55,201,084 | 42.95 |

#### CITE-seq:
|SampleID | Raw reads  | Q20 | Q30| With Barcode | Percentage(%)|
| :---: | :---: | :---: | :---: | :---: | :---:   |
|0702aL (50um-E10)|40,575,134|73.98;96.10|58.40;90.31|33,767,548|83.22|
|0713aL (25um-E10)|37,020,491|70.42;86.46|53.31;75.27|30,241,039|81.69|
|0719aL (10um-E10)|20,886,227|71.19;88.49|55.64;78.75|16,145,194|77.30|
|0725e10aL (50um-E10)|23,210,325|77.48;93.09|63.90;86.97|18,963,401|81.7|


<p><img src="https://github.com/MingyuYang-Yale/DBiT-seq/blob/master/Pre-processing/QC.png" alt="foo bar" title="train &amp; tracks" /></p>

## Differential expression
This is [code](https://github.com/MingyuYang-Yale/DBiT-seq/tree/master/Differential%20expression) for differential expression analysis.

Figure 2G: use the “st_qa.py” scripts in st-pipeline to do the quality assemssment

Figure 3B: Spatially variable genes generated by SpatialDE was used to conduct the clustering analysis, Non-negative matrix factorization(NMF) was performed using the NNLM pacakges in R, after the raw values were log-transformed, we chose k of 11 for the mouse embryo DBiT-seq transcriptome data obtained at a 50μm pixel size. For each pixel, the largest factor loading from NMF was used to assign cluster membership. NMF clustering of pixels was plotted by tSNE using the package “Rtsne” in R. 

