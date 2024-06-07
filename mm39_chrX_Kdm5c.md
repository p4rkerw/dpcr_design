dpcr primer and probe design for mouse mm39 Kdm5c on chrX
chrX:151,016,225-151,057,531

We will now extract the nucleotide sequence using the table browser. We will mask repeats with N and take the first chunk
```
>mm39_knownGene_ENSMUST00000112584.8 range=chrX:151016016-151056764 5'pad=0 3'pad=0 strand=+ repeatMasking=N
TTGTTCTTCCGCCAATGAAATGAACTATTTTCTCTTAGCCTGAGAAATGT
TTTTAACTAACCACCTCCAAATAAGGGACATATACAACCCGATTTCTTTC
GGTCATCACATGATGAAGGCTTCCTAGGTTTTTTTCTGACTCAAAGTAAA
CGGAACTCGGAGAGACACCTTGCGGAGGGATCTGGTTTGTTGTGGTGAGG
TACAGAGGTGGGGGGGAGGAGACGCTGACAAACCAAGATGGCGGTGGCAG
CGGTGAAACCTGCCGCGACTGGGACTTAACTGTAGTAGTGAAGGCTTCAG
TAGTTGGGAGGCAGCGGTAAGGTGTGGAAGAAACGGAACAGGACTAAGAA
CCTGTAAAAGGAACCTCAGCCTGAGACTTTTAGAGCACGGCACCCGCCCC
CCTAAGCCCTTGACGGGCGGTGGCCGTCCTGCTTAGGGCCTAGACTCCGA
GAAGTACCTCGGTTTCAGACAGCGGCGGCGCCATGCGTCCTTAAGGGCGA
CCTGAGCCCTCCCGATCTCTGGCCCAGCCCTCGGGCCCACCATGGAGCTG
GGGTCCGACGATTTCCTACCGCCGCCGGAGTGTCCGGTGTTCGAGCCTAG
CTGGGCCGAGTTCCGAGACCCTCTTGGCTACATCGCGAAAATCAGACCCA
TCGCCGAGAAGTCCGGCATTTGCAAGATCCGCCCACCCGCGGTAAGGCTG
GGAGCTGATGGTCGCCAGCGGCGAGTTTGTGGGTGGATCCGGGTAGCCAG
TGGTGAAGTCCCGGGCGGAGGGCAGCAGGTGTGGGAAGAATATGGGATGG
CTGGTATTTTGTGGATGCCTCACGAAGCGGAAAAAGGGTGCTGGGGTCAG
GGCTCCTCGTTTTGTGGCATACAAGTGACCTGGGGTCTGAGACCCACTCC
CACTCTGCTCTTGAGAATTTCCCTTGATTCAATACACAGATGCTTAATGG
GCTGGGGAGAGTTCGCAGGGAGGCACAGAGACTCCCATCTTTTACTTTGT
ATCACCCTGGTCGAGGCAGTTACAAAGTAACGACTACTGTCATTATTCCC
TTTAAGGCAA
```
We will now check this sequence with BLAT to ensure that it's specific to our target region. Note how it has a very high score for the entire length of the sequence on the target chromosome.
```
   ACTIONS                 QUERY   SCORE START   END QSIZE IDENTITY  CHROM  STRAND  START       END   SPAN
------------------------------------------------------------------------------------------------------------
browser new tab details YourSeq  1060     1  1060  1060   100.0%  chrX   +   151016016 151017075   1060
browser new tab details YourSeq    27   938  1001  1060    96.6%  chr1   +     8893706   8893836    131
browser new tab details YourSeq    22   773   799  1060    95.9%  chr11  -    65981146  65981176     31
browser new tab details YourSeq    21   891   911  1060   100.0%  chr5   +    52699161  52699181     21
browser new tab details YourSeq    21   832   852  1060   100.0%  chr19  +    44097596  44097616     21
```
We will now use this sequence to design primers and probes in primer express using a TaqMan MGB quantification design. Below is the top primer / probe combination for our target region
```
chrX_Kdm5c_F:TGGCTACATCGCGAAAATCAG
chrX_Kdm5c_R:CATCAGCTCCCAGCCTTACC
chrX_Kdm5c_P: CGAGAAGTCCGGCATT
```

Check that the amplicon length is between 50-150 and that the melting temperatures are comparable to other primers in the multiplex design. Also check for self-dimers and cross primer dimers with other primers in the multiplex reaction using the Multiple Primer Analyzer: https://www.thermofisher.com/us/en/home/brands/thermo-scientific/molecular-biology/molecular-biology-learning-center/molecular-biology-resource-library/thermo-scientific-web-tools/multiple-primer-analyzer.html

```
Name         	Sequence              	Tm°C	CG%	nt	A	T	C	G	Extinction coefficient(l/(mol·cm)	Molecular weight(g/mol)	nmol	µg/OD260
chrX_Kdm5c_F:	tggctacatcgcgaaaatcag 	67.4	47.6	21	7.0	4.0	5.0	5.0	207500.0                         	6439.3                 	4.8 	31.0
chrX_Kdm5c_R:	catcagctcccagccttacc  	66.2	60.0	20	4.0	4.0	10.0	2.0	175600.0                         	5957.9                 	5.7 	33.9
chrX_Kdm5c_P:	cgagaagtccggcatt      	60.5	56.3	16	4.0	3.0	4.0	5.0	155900.0                         	4906.3                 	6.4 	31.5
chrY_Sry_F:  	tgctgaggtgctcctggtatg 	67.9	57.1	21	2.0	7.0	4.0	8.0	193100.0                         	6484.3                 	5.2 	33.6
chrY_Sry_R:  	ccacgaccagcagcttaccta 	66.6	57.1	21	6.0	3.0	9.0	3.0	196600.0                         	6320.1                 	5.1 	32.1
chrY_Sry_P:  	ctcaccagtgatgtcag     	53.1	52.9	17	4.0	4.0	5.0	4.0	162500.0                         	5170.4                 	6.2 	31.8
chr1_Mff_F:  	agtggtgtgggatgtgctctt 	66.2	52.4	21	2.0	8.0	2.0	9.0	199200.0                         	6539.3                 	5.0 	32.8
chr1_Mff_R:  	cagggaatgcgctcattagg  	67.0	55.0	20	5.0	4.0	4.0	7.0	196200.0                         	6182.1                 	5.1 	31.5
chr1_Mff_P:  	agcagagcgtaaatag      	48.7	43.8	16	7.0	2.0	2.0	5.0	173400.0                         	4963.3                 	5.8 	28.6
chr1_Gsta3_F:	gcccttcctgaccaaatacaca	67.3	50.0	22	7.0	4.0	9.0	2.0	206500.0                         	6608.3                 	4.8 	32.0
chr1_Gsta3_R:	gccccagggaaatcaattg   	66.7	52.6	19	6.0	3.0	5.0	5.0	187000.0                         	5821.9                 	5.3 	31.1
chr1_Gsta3_P:	tgtgcacactcaaac       	49.1	46.7	15	5.0	3.0	5.0	2.0	142000.0                         	4521.0                 	7.0 	31.8
chrX_Clcn5_F:	gccctctgcctaccttatgct 	65.8	57.1	21	2.0	7.0	9.0	3.0	176400.0                         	6284.1                 	5.7 	35.6
chrX_Clcn5_R:	tgggtggtgcctgatggtat  	67.8	55.0	20	2.0	7.0	2.0	9.0	190400.0                         	6235.1                 	5.3 	32.7
chrX_Clcn5_P:	caggatggctttctt       	51.7	46.7	15	2.0	6.0	3.0	4.0	135900.0                         	4574.0                 	7.4 	33.7
chrY_Uty_F:  	ggacaatccaaaatccacgaa 	66.0	42.9	21	10.0	2.0	6.0	3.0	216800.0                         	6401.3                 	4.6 	29.5
chrY_Uty_R:  	ggtccgcagcaagtttctgt  	66.9	55.0	20	3.0	6.0	5.0	6.0	185200.0                         	6124.0                 	5.4 	33.1
chrY_Uty_P:  	attttttctgccttgtccaaa 	62.7	33.3	21	4.0	10.0	5.0	2.0	189400.0                         	6337.2                 	5.3 	33.5
```

Check NCBI primer blast for off-target amplification in mouse genome (with an amplicon size in the same range).
```
>NC_000086.8 Mus musculus strain C57BL/6J chromosome X, GRCm39
product length = 86
Features associated with this product:
   lysine-specific demethylase 5c isoform 2

   lysine-specific demethylase 5c isoform 9

Forward primer  1          TGGCTACATCGCGAAAATCAG  21
Template        151016640  .....................  151016660

Reverse primer  1          CATCAGCTCCCAGCCTTACC  20
Template        151016725  ....................  151016706
```




