dPCR primer and probe design for human chromosome Y

1. First examine SRY on long arm using the ucsc genome browser [link](http://www.genome.ucsc.edu/cgi-bin/hgTracks?db=hg38&lastVirtModeType=default&lastVirtModeExtraState=&virtModeType=default&virtMode=0&nonVirtPosition=&position=chrY%3A2786855%2D2787682&hgsid=1672248776_rpAp1gzGpHanU8vktIpY5I6kzS0Y) SNVs can affect probe binding and should be avoided if possible. There are also repetitive elements in the repeat masker track. It is difficult to design probes that involve repetitive elements because there is a risk they will bind multiple regions in the genome with the same element.

2. We will now extract the nucleotide sequence using the ucsc get dna in window [link](https://genome-euro.ucsc.edu/cgi-bin/hgc?hgsid=226600623_EcMYrC757dFyLJ6OyJROM4LHm80w&o=72121019&g=getDna&i=mixed&c=chr17&l=72121019&r=72126420&db=hg38&hgsid=226600623_EcMYrC757dFyLJ6OyJROM4LHm80w). We will mask repeats with N. Below is a  chunk of sequence. By convention, we design primers and probes using the + strand rather than the - strand. 

```
>hg38_dna range=chrY:2786855-2787682 5'pad=0 3'pad=0 strand=+ repeatMasking=N
TGAAATGAATAAGGCCTTTATTAGCCAGAGAAAAGAAAACAATATTGAAA
CTAAACATAAGAAAGTGAGGGCTGTAAGTTATCGTAAAAAGGAGCATCTA
GGTAGGTCTTTGTAGCCAATGTTACCCGATTGTCCTACAGCTTTGTCCAG
TGGCTGTAGCGGTCCCGTTGCTGCGGTGAGCTGGCTGCGTTGATGGGCGG
TAAGTGGCCTAGCTGGTGCTCCATTCTTGAGTGTGTGGCTTTCGTACAGT
CATCCCTGTACAACCTGTTGTCCAGTTGCACTTCGCTGCAGAGTACCGAA
GCGGGATCTGCGGGAAGCAAACTGCAATTCTTCGGCAGCATCTTCGCCTT
CCGACGAGGTCGATACTTATAATTCGGGTATTTCTCTCTGTGCATGGCCT
GTAATTTCTGTGCCTCCTGGAAGAATGGCCATTTTTCGGCTTCAGTAAGC
ATTTTCCACTGGTATCCCAGCTGCTTGCTGATCTCTGAGTTTCGCATTCT
GGGATTCTCTAGAGCCATCTTGCGCCTCTGATCGCGAGACCACACGATGA
ATGCGTTCATGGGTCGCTTCACTCTATCCTGGACGTTGCCTTTACTGTTT
TCTCCCGTTTCACACTGATACTTAGAGTTACAGCTTTCAGTGCAAAGGAA
GGAAGAGCTTCTCCGGAGAGCGGGAATATTCTCTTGCACAGCTGGACTGT
AATCATCGCTGTTGAATACGCTTAACATAGCAGAAGCATATGATTGCATT
GTCAAAAACAAGGAGAGTGCGACAAAATTGAAAGGTGCCAGAGTTCGAAA
CTTATTTTACTATCCAAAACTCACTTCT
```



3. We will now check this sequence with BLAT to ensure that it's specific to our target region. Note how it has a very high score for the entire length of the sequence in target region. 

```
   ACTIONS      QUERY   SCORE START   END QSIZE IDENTITY  CHROM  STRAND  START       END   SPAN
-----------------------------------------------------------------------------------------------
browser details YourSeq   828     1   828   828   100.0%  chrY   +     2786855   2787682    828
browser details YourSeq    61   473   563   828    83.6%  chr13  -   112067818 112067908     91
browser details YourSeq    29   540   572   828    94.0%  chr16  -      982226    982258     33
browser details YourSeq    26   482   514   828    75.9%  chr17  -    31801605  31801633     29
browser details YourSeq    26   384   421   828    75.0%  chr1   -     5887897   5887927     31
browser details YourSeq    26    26    55   828    82.2%  chr17  +    57252821  57252848     28
browser details YourSeq    25    24    50   828    88.5%  chr1   +   155419801 155419826     26
browser details YourSeq    22    41    63   828   100.0%  chr16  +    72297875  72297898     24
browser details YourSeq    22   471   493   828   100.0%  chr1   +    59407244  59407268     25
browser details YourSeq    21   397   419   828    95.7%  chr17  -    54606864  54606886     23
browser details YourSeq    20   397   418   828    95.5%  chr2   -    90150600  90150621     22
browser details YourSeq    20    56    75   828   100.0%  chr19  -    22042640  22042659     20
browser details YourSeq    20   400   421   828    95.5%  chr18  -    78522546  78522567     22
browser details YourSeq    20   397   418   828    95.5%  chr2   +    89049946  89049967     22
browser details YourSeq    20   621   640   828   100.0%  chr12  +    90610298  90610317     20
```

4. We will now use this sequence to design primers and probes in primer express using a TaqMan MGB quantification design. Below is the top primer / probe combination for our target region

```
Forward Primer:GCGTTGATGGGCGGTAAGT
Reverse Primer:ACGAAAGCCACACACTCAAGAA
Probe: CCTAGCTGGTGCTCC
```

5. We will now double check this primer set for specificity using primer blast and our target sequence. We will also select "Genomes for selected eukaryotic organisms" and Homo sapiens to check if the primer set will amplify any regions elsewhere in the genome. The only template with a perfect match is our target sequence. 

```
>NC_000024.10 Homo sapiens chromosome Y, GRCh38.p14 Primary Assembly

product length = 59
Features associated with this product:
   sex-determining region y protein

Forward primer  1        GCGTTGATGGGCGGTAAGT  19
Template        2787041  ...................  2787059

Reverse primer  1        ACGAAAGCCACACACTCAAGAA  22
Template        2787099  ......................  2787078
```




