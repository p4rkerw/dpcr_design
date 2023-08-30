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
Forward Primer:TGTGCCTCCTGGAAGAATGG
Reverse Primer:GATCAGCAAGCAGCTGGGATA
Probe: CATTTTTCGGCTTCAGTAAG
```
5. Check that the amplicon length is between 50-150 and that the melting temperatures are comparable to other primers in the multiplex design. Also check for self-dimers and cross primer dimers with other primers in the multiplex reaction using the Multiple Primer Analyzer: https://www.thermofisher.com/us/en/home/brands/thermo-scientific/molecular-biology/molecular-biology-learning-center/molecular-biology-resource-library/thermo-scientific-web-tools/multiple-primer-analyzer.html 
```
Name 	Sequence               	Tm°C	CG%	nt	A	T	C	G	Extinction coefficient(l/(mol·cm)	Molecular weight(g/mol)	nmol	µg/OD260
chr1F	acgtggcggatgaaagtca    	67.1	52.6	19	6.0	3.0	3.0	7.0	196000.0                         	5901.9                 	5.1 	30.1
chr1R	gatccacccagccaccctata  	67.2	57.1	21	6.0	3.0	10.0	2.0	196600.0                         	6280.1                 	5.1 	31.9
chr1P	tgcttccatagccatca      	59.4	47.1	17	4.0	5.0	6.0	2.0	157000.0                         	5105.4                 	6.4 	32.5
chrXF	cctacacatccagccttgca   	66.5	55.0	20	5.0	4.0	9.0	2.0	181200.0                         	5981.9                 	5.5 	33.0
chrXR	ttgcttctgaactgggatggt  	66.1	47.6	21	3.0	8.0	3.0	7.0	194500.0                         	6483.3                 	5.1 	33.3
chrXP	ataagagtaaagagaaaagtcca	55.3	30.4	23	13.0	3.0	2.0	5.0	258800.0                         	7146.8                 	3.9 	27.6
chrYF	tgtgcctcctggaagaatgg   	67.8	55.0	20	4.0	5.0	4.0	7.0	190600.0                         	6173.1                 	5.2 	32.4
chrYR	gatcagcaagcagctgggata  	66.8	52.4	21	7.0	3.0	4.0	7.0	214700.0                         	6504.3                 	4.7 	30.3
chrYP	catttttcggcttcagtaag   	59.5	40.0	20	4.0	8.0	4.0	4.0	186900.0                         	6098.0                 	5.4 	32.6
```

6. We will now double check this primer set for specificity using primer blast and our target sequence. We will also select "Genomes for selected eukaryotic organisms" and Homo sapiens to check if the primer set will amplify any regions elsewhere in the genome. The only template with a perfect match is our target sequence. 

```
>NC_000024.10 Homo sapiens chromosome Y, GRCh38.p14 Primary Assembly

product length = 75
Features associated with this product:
   sex-determining region y protein

Forward primer  1        TGTGCCTCCTGGAAGAATGG  20
Template        2787263  ....................  2787282

Reverse primer  1        GATCAGCAAGCAGCTGGGATA  21
Template        2787337  .....................  2787317
```

7. Check that the amplicon length is between 75-150 and that the melting temperatures are comparable to other primers in the multiplex design
```
Sequence (5'->3')	Template strand	Length	Start	Stop	Tm	GC%	Self complementarity	Self 3' complementarity
Forward primer	TGTGCCTCCTGGAAGAATGG	Plus	20	409	428	59.67	55.00	5.00	1.00
Reverse primer	GATCAGCAAGCAGCTGGGATA	Minus	21	483	463	60.20	52.38	6.00	2.00
Product length	75
```


