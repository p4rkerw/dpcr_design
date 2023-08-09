dpcr primer and probe design for rat ftx on chrX

1. First examine the gene using the ucsc genome browser [link](http://www.genome.ucsc.edu/cgi-bin/hgTracks?db=rn6&lastVirtModeType=default&lastVirtModeExtraState=&virtModeType=default&virtMode=0&nonVirtPosition=&position=chrX%3A74440265%2D74484164&hgsid=1672136792_2YsCHI5ckRqJFZTAa4X5HCOVS7qA). SNVs can affect probe binding and should be avoided if possible. There are also repetitive elements in the repeat masker track. It is difficult to design probes that involve repetitive elements because there is a risk they will bind multiple regions in the genome with the same element.

2. We will now extract the nucleotide sequence using the get dna in window tool [link](https://genome.ucsc.edu/cgi-bin/hgc?hgsid=1660325472_CNTCILrj4QVpKK7xNX1QylmrrE1T&o=24647082&g=getDna&i=mixed&c=chr7&l=24647082&r=24668381&db=rn6&hgsid=1660325472_CNTCILrj4QVpKK7xNX1QylmrrE1T). We will mask repeats with N. 

```
>rn6_dna range=chrX:74440265-74484164 5'pad=0 3'pad=0 strand=+ repeatMasking=N
TTATATAGTAATTGTTTAATGAAATATCCACATTTACTAGTTACAGGCAG
GAATTTGTACAAGTATATTGAGAATAATTCAACAGCAAGTATTCAAAAGG
AAATAATTGGTAGAAATTAATTCTCAAGAAACAAGATATATAACTATTAA
TGTATGGTGTATAATACATTTTATATTAAAAATTTGTTAAGTCCAATTTG
TACAATAATAAATCCAGAAGTACATATTCGATGTAGAACTTATATTAAAC
TTAATGTGAACATAACGGTTTGAGTCTATTAATTTGCATGGTTTTGTGGG
TCTAGAGAGTCATGAACCACGGGTCACCTCTGGCCGCTTACAGGAAGAGT
ATCCATACTTTTACAAGTCATTGCTTCAAGGCTTATATAATTGTGCATGT
TCATAACTTTCAAAATGTTGATCATGTTACTTTCACTGAGGGGGAAATTT
CATTTTTAATAGAATACAGAAAAGCTCAGGCCAATTGAATCGAGTTTTTT
AATGGCTGTCAGTCAGTAGGTCATATTCTTGCCAACTGGGTGTTGGCTTT
CTTGCTCCTTCATTTATCGGACTAACTCACAAGACCATAAAAATTTAAGT
TCAACTTGTCTGGTGAGCTGAAGAGTTACATGAAGAGAAACATCCCTGTG
CCAAACATCTCCCATGAGAAAAATTCCCTGTTGGACAAACAGCAGGAGCT
ACTTCAGGGAATGCTTGTTGTACTTTTTCACTCAGTTAATTAGCACGTCT
GGTGCTATCCCTTGCCCTTGAGCCCTTTATCCATGTAGCAGAATTCAATG
AAAACCCTGATCTGGTTTGTCAATCGGGTAAATAGAAATCTTTAAAAAGG
AGTAATACGTAGAAATCTCCAATCCTTGAGAAGCAGTTTATGTATCCCTC
ACAAAATAAAGACACCTCATTCACTCCATCTTTCTCTCACTTTGCTCCAA
TGGGAAACTCCCAAAACGTCACTCTCCATCTTCTTGGGGCGCCACTCTTG
TTGTTCTATCCAGAGAGCAACACGGGTCCCACTCTGCACTGTGTTTTCAT
TCACGATGCAGCCTTTTCCAGTTCTGGGCAGGGAAACAGAGAGGTAGGAA
TTAAGGAGTCCACATAAGAAAGAGGAGGCAAGATCAAGGATAACACATAA
AACTTGACTCAAATGTATTCTGGGAATTCAAGGAAAATAACTGAAAGTCA
AGACTTCTCACACCTATGTTCTACCCACCCCCCATCCCCAGAGACCTAAC
CAAGACTGCCAATGTCCATGATTGTTGTAGAAAATATAATTGCTACAATA
TTTTCTCACAGAGCTCCTGTTCTTGTATATAGCTTCTCTGGTTGCCAACA
TGGCGTCATTTGATTGTTCTGCACTGTAGGAGTGACCACAAAAGTCTGCA
TCTTCCTTCAAATCCACTGGCCACCCCTTCATTCTAAGCTGGTATTTTGG
TGTTATCTTCGGATACTTGGGCCTGAGGGACTTTTCACTATTGGGGTGTA
ATAGTACCCTAGTACACCACAGAGATTTCTGTGTGTTGTGTGTAAAGACA
TGAATACTGCGGAAAGGAATGGTTCATATAAACAAAAGCGAATGAAAGGG
TTAGCGTGAGCCTGAGAACAGGCCCCAGTGCTCCAGAGAGTATCATGACG
CTGACTTCTTGTTACATGAGGCACTGTGTGACTGTGGTCAACTCAGACAC
CATTTTCCATTTTTTCTGCCTTTTCTAACTTAGCCCCATGAGTGACTATA
AAGCAGCCCAGATTTTAAAAGGACTAGTCCTGAGAACAGTGATTATTAAA
TCACCATTGAAATACTGACACCAGGGATCCTAACCCCAGCAGCCAGGACA
GTAGAAAAGTAGTGTGAGGACCAACTGTGCGATCCAGCCAGGTTTGGTCA
GCTAAGACTTTCTTGTGTTTTACCTTCTAAAATCTCATTTGCATCATCCC
AAACAGCCAACAGAAATTCTACATGAGTCAGTAAATGGGATGTTTCCTGA
TCCTAGACTGGTTCCGATTAGTGCTAATGTAACATGTTGACTTTCATTCC
CCATAGTTCATCCTAAAAGATGATTTACAGAACACTTTTTCTGAACATGT
```

3. We will now check this sequence with BLAT to ensure that it's specific to our target region. Note how it has a very high score for the entire length of the sequence on the target chromosome.

```
   ACTIONS      QUERY   SCORE START   END QSIZE IDENTITY  CHROM  STRAND  START       END   SPAN
-----------------------------------------------------------------------------------------------
browser details rn6_dna  2100     1  2100  2100   100.0%  chrX   +    74440265  74442364   2100
browser details rn6_dna    59   256   349  2100    90.5%  chr19  +    59268013  59268122    110
browser details rn6_dna    59   256   349  2100    90.5%  chr19  +    59918427  59918536    110
browser details rn6_dna    54   282   347  2100    96.7%  chr7   +    42089440  42089520     81
browser details rn6_dna    52   282   349  2100    89.6%  chr17  +    33417611  33417687     77
browser details rn6_dna    32   313   349  2100    94.6%  chr4   -   150449761 150449803     43
browser details rn6_dna    32   322   363  2100    92.2%  chr2   +     2142259   2142302     44
browser details rn6_dna    31   317   349  2100    97.0%  chr4   -    79018296  79018328     33
browser details rn6_dna    28   322   349  2100   100.0%  chr1   -    64466594  64466621     28
browser details rn6_dna    28   322   349  2100   100.0%  chr6   +     8299359   8299386     28
browser details rn6_dna    28   322   349  2100   100.0%  chr3   +   112265596 112265623     28
browser details rn6_dna    28   322   349  2100   100.0%  chr18  +    29556780  29556807     28
browser details rn6_dna    28   322   349  2100   100.0%  chr13  +    96247280  96247307     28
browser details rn6_dna    28   322   349  2100   100.0%  chr10  +    34105660  34105687     28
browser details rn6_dna    28   322   351  2100    96.7%  chr1   +   239848363 239848392     30
browser details rn6_dna    26   322   349  2100    96.5%  chr1   +   238045071 238045098     28
browser details rn6_dna    25   325   349  2100   100.0%  chr1   +   107068489 107068513     25
browser details rn6_dna    24   928   956  2100    84.7%  chr16  -    38338035  38338061     27
browser details rn6_dna    23   318   348  2100    87.1%  chr1   +    84397706  84397736     31
```

4. We will now use this sequence to design primers and probes in primer express using a TaqMan MGB quantification design. Below is the top primer / probe combination for our target region

- Forward Primer:CCAGCAGCCAGGACAGTAGAA 
- Reverse Primer:CTGACCAAACCTGGCTGGAT 
- Probe: AGTAGTGTGAGGACCAACT 

We will now double check this primer set for specificity using primer blast and our target sequence. We will also select "Genomes for selected eukaryotic organisms" and Rattus norvegicus to check if the primer set will amplify any regions elsewhere in the genome. The only template with a perfect match is our target sequence.

```
>NC_051356.1 Rattus norvegicus strain BN/NHsdMcwi chromosome X, mRatBN7.2

product length = 66
Features flanking this product:
   67473 bp at 5' side: similar to gtpase hras precursor (transforming protein p2...
   53411 bp at 3' side: zinc finger cchc-type containing 13

Forward primer  1         CCAGCAGCCAGGACAGTAGAA  21
Template        68590184  .....................  68590204

Reverse primer  1         CTGACCAAACCTGGCTGGAT  20
Template        68590249  ....................  68590230
```
