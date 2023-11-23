# AAIndex-TSV
## Description
This repository contains the aaindex [[1](https://www.genome.jp/aaindex/)] databases organised in TSV. The aim is to make the use of aaindex more accessible.

We did not generate these data ourself. For any additional information, please refer to the original website [[1](https://www.genome.jp/aaindex/)].

## Version
This was based on the aaindex updated on February 13, 2017 [[1](https://www.genome.jp/aaindex/)].

## Load the TSVs in Python3.x
You can load the files by using the following python code. Please note that pandas [[2](https://pandas.pydata.org)] is necessary.

```
import pandas as pd

df_aaindex1 = pd.read_csv('aaindex1.tsv',sep='\t',header=[0,1],index_col=0)
df_aaindex2 = pd.read_csv('aaindex2.tsv',sep='\t',header=[0,1],index_col=0)
df_aaindex3 = pd.read_csv('aaindex3.tsv',sep='\t',header=[0,1],index_col=0)
```

## DataFrame Description
The TSV files are organised on two column levels:

`df_aaindexX.index` --> Accession number

`df_aaindexX.Info` contains all information on each encoding
`df_aaindexX.Info.D` --> Data description
`df_aaindexX.Info.R` --> PMID
`df_aaindexX.Info.A` --> Author(s)
`df_aaindexX.Info.T` --> Title of the article
`df_aaindexX.Info.J` --> Journal reference
`df_aaindexX.Info.Comments` --> Comments

`df_aaindexX.pearson` contains the complete pearson [[3](https://en.wikipedia.org/wiki/Pearson_correlation_coefficient)] correlation matrix between each descriptor. NaN values were ignored in the calculations.

`df_aaindexX.spearman` contains the complete spearman [[4](https://en.wikipedia.org/wiki/Spearman%27s_rank_correlation_coefficient)] correlation matrix between each descriptor. NaN values were ignored in the calculations.

`df_aaindexX.I` contains the amino acids descriptors (aaindex1), the amino acid mutation pairs descriptors (aaindex2) or the pairwise contact potentials descriptors (aaindex3).


## Citation
If you use these files in your work, please cite accordingly with the guidelines of the original aaindex database [[1](https://www.genome.jp/aaindex/)]
