dPCR primer and probe design for human X chromosome

1. First examine XIST using the ucsc genome browser [link](http://www.genome.ucsc.edu/cgi-bin/hgTracks?db=hg38&lastVirtModeType=default&lastVirtModeExtraState=&virtModeType=default&virtMode=0&nonVirtPosition=&position=chrX%3A73820656%2D73852723&hgsid=1672088950_52BQM4SKEdVAjWVjhr3gdJOJnLo5) Note how XIST has multiple exons and that there are common variants in the dbSNP tracks. SNVs can affect probe binding and should be avoided if possible. There are also repetitive elements in the repeat masker track. It is difficult to design probes that involve repetitive elements because there is a risk they will bind multiple regions in the genome with the same element.

2. We will now extract the nucleotide sequence of XIST using the ucsc table browser [link](http://www.genome.ucsc.edu/cgi-bin/hgTables?hgsid=1672088950_52BQM4SKEdVAjWVjhr3gdJOJnLo5&clade=mammal&org=Human&db=hg38&hgta_group=map&hgta_track=gold&hgta_table=0&hgta_regionType=range&position=chrX%3A73%2C820%2C656-73%2C852%2C723&hgta_outputType=sequence&hgta_outFileName=). We will mask repeats with N. Below is the first chunk of sequence. Note how the sequence captures an area much larger than just XIST and is on the + strand (XIST is on the - strand). The get DNA in window is another tool that can retrieve sequences in target regions if you don't want all of the extra sequences. By convention, we design primers and probes using the + strand rather than the - strand. 

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

3. We will now check this sequence with BLAT to ensure that it's specific to our target region. Note how it has a very high score for the entire length of the sequence on chrX. The region maps downstream of XIST to the first exon of TSIX on the + strand.  

```
   ACTIONS      QUERY   SCORE START   END QSIZE IDENTITY  CHROM  STRAND  START       END   SPAN
-----------------------------------------------------------------------------------------------
browser details YourSeq   621     1   621   621   100.0%  chrX   +    73818598  73819218    621
browser details YourSeq    28   249   336   621    56.7%  chr10  -    90968001  90968040     40
browser details YourSeq    21   504   524   621   100.0%  chr19  -    44174191  44174211     21
browser details YourSeq    20   208   227   621   100.0%  chr13  +   101624687 101624706     20
```

4. We will now use this sequence to design primers and probes in primer express using a TaqMan MGB quantification design. Below is the top primer / probe combination for our target region

```
Forward Primer:AGGGATGGACAAAGGAACAGAA
Reverse Primer:GGTGAGGCGGTAAGGAGACTT
Probe: ACACTCAAGAATAACTTC
```

5. We will now double check this primer set for specificity using primer blast and our target sequence. We will also select "Genomes for selected eukaryotic organisms" and Homo sapiens to check if the primer set will amplify any regions elsewhere in the genome. The only template with a perfect match is our target sequence. 

```
>NC_000023.11 Homo sapiens chromosome X, GRCh38.p14 Primary Assembly

product length = 65
Features flanking this product:
   137942 bp at 5' side: cysteine-rich hydrophobic domain-containing protein 1 iso...
   485256 bp at 3' side: zinc finger cchc domain-containing protein 13

Forward primer  1         AGGGATGGACAAAGGAACAGAA  22
Template        73818946  ......................  73818967

Reverse primer  1         GGTGAGGCGGTAAGGAGACTT  21
Template        73819010  .....................  73818990

```



