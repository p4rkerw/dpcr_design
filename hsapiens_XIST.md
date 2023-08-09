dPCR primer and probe design for human X chromosome

1. First examine XIST using the ucsc genome browser [link](http://www.genome.ucsc.edu/cgi-bin/hgTracks?db=hg38&lastVirtModeType=default&lastVirtModeExtraState=&virtModeType=default&virtMode=0&nonVirtPosition=&position=chrX%3A73820656%2D73852723&hgsid=1672088950_52BQM4SKEdVAjWVjhr3gdJOJnLo5) Note how XIST has multiple exons and that there are common variants in the dbSNP tracks. SNVs can affect probe binding and should be avoided if possible. There are also repetitive elements in the repeat masker track. It is difficult to design probes that involve repetitive elements because there is a risk they will bind multiple regions in the genome with the same element.

2. We will now extract the nucleotide sequence of XIST using the ucsc table browser [link](http://www.genome.ucsc.edu/cgi-bin/hgTables?hgsid=1672088950_52BQM4SKEdVAjWVjhr3gdJOJnLo5&clade=mammal&org=Human&db=hg38&hgta_group=map&hgta_track=gold&hgta_table=0&hgta_regionType=range&position=chrX%3A73%2C820%2C656-73%2C852%2C723&hgta_outputType=sequence&hgta_outFileName=). We will mask repeats with N. Below is the first chunk of sequence

```
>hg38_gold_AL353804.22 range=chrX:73818598-73984265 5'pad=0 3'pad=0 strand=+ repeatMasking=N
AGGAGGCACAAGTTTTTGTGGATGTGGGTTGGGCTGGCACCAAATCCAAC
TACAAGCATACAGTGACCACTTCATACACACCACATAAAAAATACAAAAA
CTGAAAAATACTATCAAATGCTTTGACATTTTCTAAATATTTCTGCTGCC
CCTATAAAATTGCCTTGTCTGACCTTTCCTCACTAACCAGGAGATACGGT
GTTTTTCATTTCCTCTCCCTTCAAATTTTACAAGAGAATCAAGGAATTTG
AGGACCAAAGCACCACAAACACAAGAGTAAGCACAGCAAATATGACAAGG
GGACTGAAGTAAGCCCCTATGGGAATAGGATCTGCTGAAGGAATCAAGAG
GGATGGACAAAGGAACAGAAGACACTCAAGAATAACTTCAGGAAGTCTCC
TTACCGCCTCACCTGCTTTCCCTCTGTCCTACACATCCAGCCTTGCAAAG
AAATAAGAGTAAAGAGAAAAGTCCATGTAGCACCATCCCAGTTCAGAAGC
AACCCCCAAGATATGGGTCAACTTTATCACCTCAAACTCTACTCATTTAT
AATGACAAAATTCAACTGTTAACACATAGGTAAGAGTTCTTCAGGCATCG
GTTTTAAAGGTCCATGTACTG
```
