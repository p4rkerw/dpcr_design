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

4. We will now use this sequence to design primers and probes in primer express using a TaqMan MGB quantification design. Below is a primer / probe combination with a similar Tm as the other primers in our multiplex design

```
Forward Primer:TTTCTGTGCCTCCTGGAAGAA
Reverse Primer:TGGGATACCAGTGGAAAATGC
Probe: CCATTTTTCGGCTTCAG
```
5. Check that the amplicon length is between 50-150 and that the melting temperatures are comparable to other primers in the multiplex design. Also check for self-dimers and cross primer dimers with other primers in the multiplex reaction using the Multiple Primer Analyzer: https://www.thermofisher.com/us/en/home/brands/thermo-scientific/molecular-biology/molecular-biology-learning-center/molecular-biology-resource-library/thermo-scientific-web-tools/multiple-primer-analyzer.html 
```
Name 	Sequence             	Tm°C	CG%	nt	A	T	C	G	Extinction coefficient(l/(mol·cm)	Molecular weight(g/mol)	nmol	µg/OD260
chr1F	tctcagtgctgccagatcca 	67.8	55.0	20	4.0	5.0	7.0	4.0	184200.0                         	6053.0                 	5.4 	32.9
chr1R	cagcacggaactgtgcctaa 	66.6	55.0	20	6.0	3.0	6.0	5.0	193400.0                         	6111.0                 	5.2 	31.6
chr1P	aggctcgaagcatc       	52.8	57.1	14	4.0	2.0	4.0	4.0	137200.0                         	4272.8                 	7.3 	31.1
chrXF	tcaagagggatggacaaagga	66.1	47.6	21	9.0	2.0	2.0	8.0	227300.0                         	6577.4                 	4.4 	28.9
chrXR	ggtgaggcggtaaggagactt	65.8	57.1	21	5.0	4.0	2.0	10.0	214200.0                         	6591.3                 	4.7 	30.8
chrXP	cagaagacactcaagaata  	50.4	36.8	19	10.0	2.0	4.0	3.0	203700.0                         	5822.9                 	4.9 	28.6
chrYF	tttctgtgcctcctggaagaa	66.3	47.6	21	4.0	7.0	5.0	5.0	194300.0                         	6412.2                 	5.1 	33.0
chrYR	tgggataccagtggaaaatgc	66.0	47.6	21	7.0	4.0	3.0	7.0	213800.0                         	6519.3                 	4.7 	30.5
chrYP	ccatttttcggcttcag    	59.9	47.1	17	2.0	7.0	5.0	3.0	149300.0                         	5127.4                 	6.7 	34.3
```

6. We will now double check this primer set for specificity using primer blast and our target sequence. We will also select "Genomes for selected eukaryotic organisms" and Homo sapiens to check if the primer set will amplify any regions elsewhere in the genome. The only template with a perfect match is our target sequence. 

```
>NC_000024.10 Homo sapiens chromosome Y, GRCh38.p14 Primary Assembly

product length = 65
Features associated with this product:
   sex-determining region y protein

Forward primer  1        TTTCTGTGCCTCCTGGAAGAA  21
Template        2787259  .....................  2787279

Reverse primer  1        TGGGATACCAGTGGAAAATGC  21
Template        2787323  .....................  2787303
```




