
dpcr primer and probe design for mouse mm39 Sry promoter on chrY
chrY:2,662,471-2,663,658

We will now extract the nucleotide sequence using the table browser. We will mask repeats with N, pad 1kb upstream and downstream, and take the first chunk (aka upstream promoter region). group: Genes and Gene predictions. track: GENCODE VM23. 
```
>mm10_knownGene_ENSMUST00000091178.1_0 range=chrY:2663659-2664658 5'pad=0 3'pad=0 strand=- repeatMasking=N
**tgtgttttcacagtattaagtttggtatgtttttcaaagatgagtattga
agacttacagatggtttgcatggtgatgctgtaaggaaatgacagccagc
cctgacccgatggcactgtgtttttgcctgctcagaaatgaactactgca
tcccagtcattagaatgctcaacctggatgatttttaccatgaaagaatt
tttgctattatgtaagaaatttgtatacattacttttatgatgcattgat
atgaccaagaaaggaagcaaaagttcttttatggtgtagatatttatact
gggctatagagccagaacagactatttcttagttttttccatgctgcctg
ccgtagtagactatgatactaatgataggttccatgcttatcatttttaa
ccctttccactacttttgcaagctcgttaatttctcacgttagtccatcc
taaacattaggtacgttacagggcaaaagaactcatcagtatgttctttg
tatcttaatacttgttgtgacagaatgatcaaagaaaaagcgatatattt
ttaaggagtgtgaaagtgcagtctctaacattcacaaacttgaggggttt
tgcttgacagtatctaggttcatgagatggcttcaaagtagattagttgg
gctggactagggaggtcctgaaggaggagggataaatattttcttacaca
cgttaaatattaaaatctttgttacaagcacattttggtcagtggctttt
agctcttacactttaagttttgact**nnnnnnnnnnnnnnnnnnnnnnnnn
nnnnnnnnnnnnnnnnnnnnnnnnnnnnnnnnnnnnttctctttgcatca
catctctgtctttttggttgcaatcataattcttccattatgttcagcat
ttcagatcttgatttttagtgttcagccctacagccacatgatatcttaa
actctgaagaagagacaagttttgggactggtgacaattgtctagagagc
```
We will now check the indicated **sequence** with BLAT to ensure that it's specific to our target region. Note how it has a very high score for the entire length of the sequence on the target chromosome. Make sure to avoid regions that have significant overlap with other areas of the genome.
```
   ACTIONS                 QUERY   SCORE START   END QSIZE IDENTITY  CHROM               STRAND  START       END   SPAN
-------------------------------------------------------------------------------------------------------------------------
browser new tab details YourSeq   775     1   775   775   100.0%  chrY                -     2663884   2664658    775
browser new tab details YourSeq   181     1   183   775    99.5%  chrY                +     2661566   2661748    183
browser new tab details YourSeq    49    85   163   775    79.1%  chr8                +    85441528  85441596     69
browser new tab details YourSeq    43    84   159   775    73.7%  chr11_JH584316_alt  -      195636    195699     64   What is chrom_alt?
browser new tab details YourSeq    42   121   176   775    85.2%  chr4                +    19620503  19620557     55
browser new tab details YourSeq    41    89   143   775    87.3%  chr1                +   154041098 154041152     55
browser new tab details YourSeq    26   683   724   775    81.0%  chr5                -    54623731  54623772     42
browser new tab details YourSeq    21   216   237   775   100.0%  chr1                -    78739034  78739056     23
browser new tab details YourSeq    20   340   359   775   100.0%  chr13               -    30786267  30786286     20
browser new tab details YourSeq    20   471   490   775   100.0%  chr12               -    14147536  14147555     20
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
mm10_chrY_Sry_Pr_F: TGCTGCCTGCCGTAGTAGACT
mm10_chrY_Sry_Pr_R: TGAGTTCTTTTGCCCTGTAACG
mm10_chrY_Sry_Pr_P: CTTATCATTTTTAACCCTTTCC
```

Check that the amplicon length is between 50-150 and that the melting temperatures are comparable to other primers in the multiplex design. Also check for self-dimers and cross primer dimers with other primers in the multiplex reaction using the Multiple Primer Analyzer: https://www.thermofisher.com/us/en/home/brands/thermo-scientific/molecular-biology/molecular-biology-learning-center/molecular-biology-resource-library/thermo-scientific-web-tools/multiple-primer-analyzer.html

```
Name                	Sequence              	Tm°C	CG%	nt	A	T	C	G	Extinction coefficient(l/(mol·cm)	Molecular weight(g/mol)	nmol	µg/OD260
mmm10_chrY_Uty_Pr_F:	cgtgggataaaacggttgct  	66.1	50.0	20	5.0	5.0	3.0	7.0	196100.0                         	6197.1                 	5.1 	31.6
mm10_chrY_Uty_Pr_R: 	agtgtgaaccgcacgtaacg  	66.4	55.0	20	6.0	3.0	5.0	6.0	199800.0                         	6151.1                 	5.0 	30.8
mm10_chrY_Uty_Pr_P: 	ccattggaaagcctg       	56.3	53.3	15	4.0	3.0	4.0	4.0	143000.0                         	4577.0                 	7.0 	32.0
mm10_chrY_Sry_Pr_F: 	tgctgcctgccgtagtagact 	66.5	57.1	21	3.0	6.0	6.0	6.0	191400.0                         	6413.2                 	5.2 	33.5
mm10_chrY_Sry_Pr_R: 	tgagttcttttgccctgtaacg	65.4	45.5	22	3.0	9.0	5.0	5.0	199000.0                         	6707.4                 	5.0 	33.7
mm10_chrY_Sry_Pr_P: 	cttatcatttttaaccctttcc	57.8	31.8	22	4.0	11.0	7.0	0.0	192100.0                         	6561.3                 	5.2 	34.2

```

Check NCBI primer blast using target BLAT sequence and selected F and R primers for off-target amplification in mouse genome (with an amplicon size in the same range). The first template below is the intended template. 
```
Products on potentially unintended templates
>NC_000087.8 Mus musculus strain C57BL/6J chromosome Y, GRCm39

product length = 144
Features flanking this product:
   517 bp at 5' side: sex-determining region y protein
   56021 bp at 3' side: histone variant h2al2-like

Forward primer  1        TGCTGCCTGCCGTAGTAGACT  21
Template        2664317  .....................  2664297

Reverse primer  1        TGAGTTCTTTTGCCCTGTAACG  22
Template        2664174  ......................  2664195

>NC_000072.7 Mus musculus strain C57BL/6J chromosome 6, GRCm39

product length = 1538
Features flanking this product:
   649603 bp at 5' side: regenerating islet-derived protein 3-gamma preproprotein
   698549 bp at 3' side: mtrnr2-like

Reverse primer  1         TGAGTTCTTTTGCCCTGTAACG  22
Template        79096684  CA.......C.T.........A  79096663

Reverse primer  1         TGAGTTCTTTTGCCCTGTAACG  22
Template        79095147  .A.T..A.C............T  79095168
```

Check UCSC in-silico PCR using the selected F and R primers for matches with the mm10 genome assembly
```
>chrY:2664174-2664317 144bp TGCTGCCTGCCGTAGTAGACT TGAGTTCTTTTGCCCTGTAACG
TGCTGCCTGCCGTAGTAGACTatgatactaatgataggttccatgcttat
catttttaaccctttccactacttttgcaagctcgttaatttctcacgtt
agtccatcctaaacattaggtaCGTTACAGGGCAAAAGAACTCA

```






