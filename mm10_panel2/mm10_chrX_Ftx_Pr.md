
dpcr primer and probe design for mouse mm10 Ftx promoter on chrX
chrX:103,587,694-103,623,790

We will now extract the nucleotide sequence using the table browser. We will mask repeats with N, pad 1kb upstream, and take the first chunk of sequence that does not contain Ns. group: Genes and Gene Predictions. track: GENCODE VM23. 
```
>mm10_knownGene_ENSMUST00000130063.7_0 range=chrX:103623755-103624754 5'pad=0 3'pad=0 strand=- repeatMasking=N
atcagaggggttttttatgcatgttacctatatgtccattaggtgtcgca
atatatccaatggccctgccttctacttctattctgctcatgatattgtt
tcagatgcaggcatgggactgcttttccttttnnnnnnnnnnnnnnnnnn
nnnnnnnnnnnnnnnnnnnnnnnnnnnnnnnnnnnnnnnnnnnnnnnnnn
nnnnnnnnnnnn**actcttttttacttgtatggttctggtgctttgatgct
ctacatgaaaattcacaattcaatgcaatgatagatagacaggcaggagc
cagtcggatgatctctcaagatccagggctgaataagaagggggagtgga
tcttaaggagacccttaaaactcaagattctccacaggaaacaacatgct
gagagtgaaaatagcctgccccaagagttctggttccaggtattagaaaa
agactttttcttcaggctttgtaacttgggcccacaattaaatctacata
cgtatatttccattcccccaaccccccggatcggtggaggctatt**nnnnn
nnnnnnnnnnnnnnnnnnnnnnnnnnnnnnnnnnnnnnnnnnnnnnnnnn
nnnnnnnnnnnnnnnnnnnnnnnnnnnnnnnnnnnnnnnnnnnnnnnnna
gnnnnnnnnnnnnnnnnnnnnnnnnnnnnnnnnnttcgaaacacttggaa
tattgggtacatcaggaaatatgagggggcctagcagagctccagagaag
cagagaaggtcaagaattgtagggtgagccagaaagggaataataacagt
agtgagatgtgatggtaaattaaaaaggatggggacttattgattagaaa
aggggctgaggaaaggatgggtggtggacgccggtatgagcagaggtagg
aaaagaagtgtgggctagggacctgagtactggactcagtgggctgctgt
aagttgtagaggggcgctctgaggagagggaggagcgcggcgcatgcgtt
```
We will now check the indicated **sequence** with BLAT to ensure that it's specific to our target region. Note how it has a very high score for the entire length of the sequence on the target chromosome.
```
   ACTIONS                 QUERY   SCORE START   END QSIZE IDENTITY  CHROM              STRAND  START       END   SPAN
------------------------------------------------------------------------------------------------------------------------
browser new tab details YourSeq   333     1   333   333   100.0%  chrX               -   103624210 103624542    333
browser new tab details YourSeq   333     1   333   333   100.0%  chrX_GL456031_alt  +      212594    212926    333   What is chrom_alt?
browser new tab details YourSeq    27   109   144   333    96.6%  chr11              +    53445116  53445434    319
browser new tab details YourSeq    26    58    84   333   100.0%  chr5               -     6752436   6752751    316
browser new tab details YourSeq    24   252   276   333   100.0%  chr5               -   135547246 135547271     26
browser new tab details YourSeq    24   111   139   333    76.0%  chr17              -    40201021  40201045     25
browser new tab details YourSeq    20    65    84   333   100.0%  chr10              -   123334635 123334654     20
browser new tab details YourSeq    20   299   318   333   100.0%  chr14              +    60167214  60167233     20
browser new tab details YourSeq    20   234   253   333   100.0%  chr13              +    80800794  80800813     20
```

We will now use this sequence to design primers and probes in primer express using a TaqMan MGB quantification design. 
```
Start with the following parameters:
Min Primer Tm: 58
Max Primer Tm: 60
Max Difference in Tm of Two Primers: 2
Min Primer %GC Content	40
Max Primer %GC Content	60
Max Primer 3' GC's	2
Primer 3' End Length	5
Primer 3' GC Clamp Residues	0
Primer Length	
Min Primer Length	18
Max Primer Length	22
Optimal Primer Length	20
Primer Composition	
Max Primer G Repeats	3
Max Num Ambig Residues in Primer	0
Primer Secondary Structure	
Max Primer Consec Base Pair	4
Max Primer Total Base Pair	8
Primer Site Uniqueness	
Max % Match in Primer	75
Max Consec Match in Primer	9
Max 3' Consec Match in Primer	7
Probe Tm	
Min Probe Tm	68
Max Probe Tm	70
Probe GC Content	
Min Probe %GC Content	30
Max Probe %GC Content	80
Probe Length	
Min Probe Length	13
Max Probe Length	25
Probe Composition	
Max Probe G Repeats	3
Max Num Ambig Residues in Probe	0
No G at 5' End in Probe	true
Select Probe with more C's than G's	false
Probe Secondary Structure	
Max Probe Consec Base Pair	4
Max Probe Total Base Pair	8
Amplicon	
Min Amplified Region Tm	0
Max Amplified Region Tm	85
Min Amplified Region Length	75
Max Amplified Region Length	150
General	
Max Primers / Probes	50
```
Relax the primer length requirement if no ideal primers are found
Below is the top primer / probe combination for our target region

```
mm10_chrX_Ftx_Pr_F: GAAAATAGCCTGCCCCAAGAG
mm10_chrX_Ftx_Pr_R: GCCCAAGTTACAAAGCCTGAAG
mm10_chrX_Ftx_Pr_P: TCTGGTTCCAGGTATTAGA
```

Check that the amplicon length is between 50-150 and that the melting temperatures are comparable to other primers in the multiplex design. Also check for self-dimers and cross primer dimers with other primers in the multiplex reaction using the Multiple Primer Analyzer: https://www.thermofisher.com/us/en/home/brands/thermo-scientific/molecular-biology/molecular-biology-learning-center/molecular-biology-resource-library/thermo-scientific-web-tools/multiple-primer-analyzer.html . Self-dimers are less problematic if not predicted by Primer Express. 

```
Name                	Sequence              	Tm°C	CG%	nt	A	T	C	G	Extinction coefficient(l/(mol·cm)	Molecular weight(g/mol)	nmol	µg/OD260
mmm10_chrY_Uty_Pr_F:	cgtgggataaaacggttgct  	66.1	50.0	20	5.0	5.0	3.0	7.0	196100.0                         	6197.1                 	5.1 	31.6
mm10_chrY_Uty_Pr_R: 	agtgtgaaccgcacgtaacg  	66.4	55.0	20	6.0	3.0	5.0	6.0	199800.0                         	6151.1                 	5.0 	30.8
mm10_chrY_Uty_Pr_P: 	ccattggaaagcctg       	56.3	53.3	15	4.0	3.0	4.0	4.0	143000.0                         	4577.0                 	7.0 	32.0
mm10_chrY_Sry_Pr_F: 	tgctgcctgccgtagtagact 	66.5	57.1	21	3.0	6.0	6.0	6.0	191400.0                         	6413.2                 	5.2 	33.5
mm10_chrY_Sry_Pr_R: 	tgagttcttttgccctgtaacg	65.4	45.5	22	3.0	9.0	5.0	5.0	199000.0                         	6707.4                 	5.0 	33.7
mm10_chrY_Sry_Pr_P: 	cttatcatttttaaccctttcc	57.8	31.8	22	4.0	11.0	7.0	0.0	192100.0                         	6561.3                 	5.2 	34.2
mm10_chr1_Eya1_Pr_F:	tcccccacagctgtttattca 	66.7	47.6	21	4.0	7.0	8.0	2.0	188400.0                         	6292.1                 	5.3 	33.4
mm10_chr1_Eya1_Pr_R:	ctgactcaacctcgctgcttta	65.9	50.0	22	4.0	7.0	8.0	3.0	194000.0                         	6621.4                 	5.2 	34.1
mm10_chr1_Eya1_Pr_P:	cgcgtcatttacataat     	52.3	35.3	17	5.0	6.0	4.0	2.0	163900.0                         	5144.4                 	6.1 	31.4
mm10_chrX_Ftx_Pr_F: 	gaaaatagcctgccccaagag 	66.1	52.4	21	8.0	2.0	6.0	5.0	210700.0                         	6433.3                 	4.7 	30.5
mm10_chrX_Ftx_Pr_R: 	gcccaagttacaaagcctgaag	66.0	50.0	22	8.0	3.0	6.0	5.0	218600.0                         	6737.4                 	4.6 	30.8
mm10_chrX_Ftx_Pr_P: 	tctggttccaggtattaga   	55.2	42.1	19	4.0	7.0	3.0	5.0	185900.0                         	5833.9                 	5.4 	31.4

```

Check NCBI primer blast using target BLAT sequence and selected F and R primers for off-target amplification in mouse genome (with an amplicon size in the same range)
```

Sequence (5'->3')	Template strand	Length	Start	Stop	Tm	GC%	Self complementarity	Self 3' complementarity
Forward primer	GAAAATAGCCTGCCCCAAGAG	Plus	21	195	215	58.97	52.38	3.00	0.00
Reverse primer	GCCCAAGTTACAAAGCCTGAAG	Minus	22	269	248	60.03	50.00	3.00	2.00
Product length	75
Products on potentially unintended templates
>NC_000086.8 Mus musculus strain C57BL/6J chromosome X, GRCm39

product length = 75
Features flanking this product:
   199986 bp at 5' side: testis-specific protein tsx
   6324 bp at 3' side: zinc finger cchc domain-containing protein 13

Forward primer  1          GAAAATAGCCTGCCCCAAGAG  21
Template        102667954  .....................  102667934

Reverse primer  1          GCCCAAGTTACAAAGCCTGAAG  22
Template        102667880  ......................  102667901
```

Check UCSC in-silico pcr for mouse genome using F and R primers
```
	
	
>chrX_GL456031_alt:212788+212862 75bp GAAAATAGCCTGCCCCAAGAG GCCCAAGTTACAAAGCCTGAAG
GAAAATAGCCTGCCCCAAGAGttctggttccaggtattagaaaaagactt
tttCTTCAGGCTTTGTAACTTGGGC
>chrX:103624274-103624348 75bp GAAAATAGCCTGCCCCAAGAG GCCCAAGTTACAAAGCCTGAAG
GAAAATAGCCTGCCCCAAGAGttctggttccaggtattagaaaaagactt
tttCTTCAGGCTTTGTAACTTGGGC

```
Its ok that there's a predicted sequence on the alt contig for chrX. 

