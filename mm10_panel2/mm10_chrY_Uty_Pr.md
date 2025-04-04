
dpcr primer and probe design for mouse mm10 Uty promoter on chrY
chrY:1,096,861-1,245,691

We will now extract the nucleotide sequence using the table browser. We will mask repeats with N, pad 1kb upstream, and take the first chunk of sequence that does not contain Ns. group: Genes and Gene Predictions. track: GENCODE VM23. 
```
>mm10_knownGene_ENSMUST00000143286.7_0 range=chrY:1245692-1246691 5'pad=0 3'pad=0 strand=- repeatMasking=N
tggtttctgagatggggaactaggtttccttgtgaaggtccaggcccagt
aagtaatggtaatacaagtcaattcaaaactcctgagaacagcaaaattg
gaacttgtcnnnnnnnnnnnnnnnnnnnnnnnnnnnnnnnnnnn**gaatgc
tcctcttacaaagtgttggatcatatttacaaattttagctacaacaacc
aaaaggtcaaaagaaatggtattgttctcaaatggttactgcatcttcaa
aatgcaatgagggattcccccgtccttcccccccccccgccccctcacgt
cactccttgcccccgcagggataacctttgtgagggactgttcattcact
atgatctgttgtttaaggacaaagtcatgtgacttttataaagttttttt
ggtttgatgtggttgagtggatgggtaattaatgagtttagctatggtgg
tgacaaaaaaacacgacccagttactcattgaggatgatttcaattttag
ctgaatacattttgttttcccaacgtgtgtgtcattacttcaagatctta
attttaaagtttgctagaattagtattaaggagcaccgattctgggaact
taacagaaggtgttctgtaaggcaagaggaaaatttttttttttaactat
ttggtctctaattggctttcatgtgccctaaaaaccgatgtttgatgtat
tttttcttagtgctctttgttccttgtgagatcagtatagcaattaaatg
aaagggtctggatatctagtgtggaataagaaagagttacaaagcatacc
taaaactaatttcactgtggtcggtaggtagagctcttaggctgacatca
cgagctagcgaagtagcaagtttagctgcactggtgatgacgcaagtcaa
caaaagtcacgtgggataaaacggttgcttccattggaaagcctggcttt
agggagaggttatggacgttacgtgcggttcacactgacggtattataac**
```
We will now check the indicated **sequence** with BLAT to ensure that it's specific to our target region. Note how it has a very high score for the entire length of the sequence on the target chromosome.
```
   ACTIONS                 QUERY   SCORE START   END QSIZE IDENTITY  CHROM  STRAND  START       END   SPAN
------------------------------------------------------------------------------------------------------------
browser new tab details YourSeq   856     1   856   856   100.0%  chrY   -     1245692   1246547    856
browser new tab details YourSeq    30   134   164   856   100.0%  chr1   +   190243821 190244340    520
browser new tab details YourSeq    27   129   174   856    66.7%  chr6   +    28046489  28046521     33
browser new tab details YourSeq    24   259   283   856   100.0%  chr1   +   171357021 171357052     32
browser new tab details YourSeq    22   129   151   856   100.0%  chr13  -     7504723   7504747     25
browser new tab details YourSeq    22   129   152   856    87.0%  chr12  +   105053935 105053957     23
browser new tab details YourSeq    22   129   150   856   100.0%  chr10  +    41420208  41420229     22
browser new tab details YourSeq    21   129   150   856   100.0%  chr6   -    38576124  38576146     23
browser new tab details YourSeq    21   131   152   856   100.0%  chr5   +    99379891  99379913     23
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
mmm10_chrY_Uty_Pr_F: CGTGGGATAAAACGGTTGCT
mm10_chrY_Uty_Pr_R: AGTGTGAACCGCACGTAACG
mm10_chrY_Uty_Pr_P: CCATTGGAAAGCCTG
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

```

Check NCBI primer blast using target BLAT sequence and selected F and R primers for off-target amplification in mouse genome (with an amplicon size in the same range)
```
Primer pair 1
Sequence (5'->3')	Template strand	Length	Start	Stop	Tm	GC%	Self complementarity	Self 3' complementarity
Forward primer	CGTGGGATAAAACGGTTGCT	Plus	20	766	785	58.84	50.00	5.00	2.00
Reverse primer	AGTGTGAACCGCACGTAACG	Minus	20	842	823	61.21	55.00	5.00	5.00
Product length	77
Products on potentially unintended templates
>NC_000087.8 Mus musculus strain C57BL/6J chromosome Y, GRCm39

product length = 77
Features flanking this product:
   155 bp at 5' side: histone demethylase uty isoform x16
   17505 bp at 3' side: atp-dependent rna helicase ddx3y isoform x3

Forward primer  1        CGTGGGATAAAACGGTTGCT  20
Template        1245782  ....................  1245763

Reverse primer  1        AGTGTGAACCGCACGTAACG  20
Template        1245706  ....................  1245725
```

Check UCSC in-silico pcr for mouse genome using F and R primers
```
	
>chrY:1245706-1245782 77bp CGTGGGATAAAACGGTTGCT AGTGTGAACCGCACGTAACG
CGTGGGATAAAACGGTTGCTtccattggaaagcctggctttagggagagg
ttatggaCGTTACGTGCGGTTCACACT

```


