dpcr primer and probe design for rat ftx on chrX

1. First examine the gene using the ucsc genome browser [link](https://genome.ucsc.edu/cgi-bin/hgTracks?db=rn7&lastVirtModeType=default&lastVirtModeExtraState=&virtModeType=default&virtMode=0&nonVirtPosition=&position=chrX%3A68588349%2D68630338&hgsid=1672295268_BAZ92FEJKSykAa5hYPLWUSPmJo2C). SNVs can affect probe binding and should be avoided if possible. There are also repetitive elements in the repeat masker track. It is difficult to design probes that involve repetitive elements because there is a risk they will bind multiple regions in the genome with the same element.

2. We will now extract the nucleotide sequence using the get dna in window tool [link](https://genome.ucsc.edu/cgi-bin/hgc?hgsid=1672295268_BAZ92FEJKSykAa5hYPLWUSPmJo2C&o=68588348&g=getDna&i=mixed&c=chrX&l=68588348&r=68630338&db=rn7&hgsid=1672295268_BAZ92FEJKSykAa5hYPLWUSPmJo2C). We will mask repeats with N. 

```
>rn7_dna range=chrX:68588349-68630338 5'pad=0 3'pad=0 strand=+ repeatMasking=N
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
browser details rn7_dna  2100     1  2100  2100   100.0%  chrX   +    68588349  68590448   2100
browser details rn7_dna    54   282   349  2100    91.1%  chr3   -    87568434  87568518     85
browser details rn7_dna    54   282   347  2100    96.7%  chr7   +    34711848  34711928     81
browser details rn7_dna    51   282   348  2100    89.4%  chr11  +    35468440  35468522     83
browser details rn7_dna    45   282   349  2100    97.9%  chr3   +   108671128 108671211     84
browser details rn7_dna    37   322   465  2100    61.0%  chr2   -   241128603 241128653     51
browser details rn7_dna    33   313   348  2100    97.3%  chr10  +    45362769  45362810     42
browser details rn7_dna    32   322   363  2100    92.2%  chr2   +     4875399   4875442     44
browser details rn7_dna    31   317   349  2100    97.0%  chr4   -    78333752  78333784     33
browser details rn7_dna    28   322   349  2100   100.0%  chr8   -    53987670  53987697     28
browser details rn7_dna    28   322   349  2100   100.0%  chr6   -     9627432   9627459     28
browser details rn7_dna    28   322   349  2100   100.0%  chr1   -    65892249  65892276     28
browser details rn7_dna    28   322   349  2100   100.0%  chr8   +    66766139  66766166     28
browser details rn7_dna    28   322   349  2100   100.0%  chr3   +   107445046 107445073     28
browser details rn7_dna    28   322   349  2100   100.0%  chr19  +    54980287  54980314     28
browser details rn7_dna    28   322   349  2100   100.0%  chr18  +    28331956  28331983     28
browser details rn7_dna    28   322   349  2100   100.0%  chr13  +    90095338  90095365     28
browser details rn7_dna    28   322   349  2100   100.0%  chr10  +    33125379  33125406     28
browser details rn7_dna    27   323   349  2100   100.0%  chr1   -   246380255 246380281     27
browser details rn7_dna    25   325   349  2100   100.0%  chr1   +   101282204 101282228     25
browser details rn7_dna    24   928   956  2100    84.7%  chr16  -    34971581  34971607     27
browser details rn7_dna    24   158   181  2100   100.0%  chr15  +    55247198  55247221     24
browser details rn7_dna    23   326   348  2100   100.0%  chr3   -   144180569 144180591     23
browser details rn7_dna    22   444   465  2100   100.0%  chr9   +    24871911  24871932     22
browser details rn7_dna    21  1143  1163  2100   100.0%  chr6   +    15625651  15625671     21
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
