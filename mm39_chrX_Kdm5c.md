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
Forward Primer:CGAGTTCCGAGACCCTCTTG
Reverse Primer:CATCAGCTCCCAGCCTTACC
Probe: CATCGCGAAAATCAGA
```

Check that the amplicon length is between 50-150 and that the melting temperatures are comparable to other primers in the multiplex design. Also check for self-dimers and cross primer dimers with other primers in the multiplex reaction using the Multiple Primer Analyzer: https://www.thermofisher.com/us/en/home/brands/thermo-scientific/molecular-biology/molecular-biology-learning-center/molecular-biology-resource-library/thermo-scientific-web-tools/multiple-primer-analyzer.html

```
Name        	Sequence            	Tm°C	CG%	nt	A	T	C	G	Extinction coefficient(l/(mol·cm)	Molecular weight(g/mol)	nmol	µg/OD260
chrX_Kdm5c_F	cgagttccgagaccctcttg	66.5	60.0	20	3.0	5.0	7.0	5.0	181900.0                         	6069.0                 	5.5 	33.4
chrX_Kdm5c_R	catcagctcccagccttacc	66.2	60.0	20	4.0	4.0	10.0	2.0	175600.0                         	5957.9                 	5.7 	33.9
chrX_Kdm5c_P	catcgcgaaaatcaga    	57.2	43.8	16	7.0	2.0	4.0	3.0	165100.0                         	4883.3                 	6.1 	29.6

```




