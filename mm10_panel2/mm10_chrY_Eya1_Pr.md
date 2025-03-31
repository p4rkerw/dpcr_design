
dpcr primer and probe design for mouse mm10 Uty promoter on chrY
chr1:14,168,954-14,310,200

We will now extract the nucleotide sequence using the table browser. We will mask repeats with N, pad 1kb upstream, and take the first chunk of sequence that does not contain Ns. group: Genes and Gene Predictions. track: GENCODE VM23. 
```
>mm10_knownGene_ENSMUST00000027066.12_0 range=chr1:14310201-14311200 5'pad=0 3'pad=0 strand=- repeatMasking=N
**tttgtttgcatcatctgaaggtgctttcgtttcctaattggcagagttaa
ggtaggacccatctatctcctctattagttgatgtgaagttactgtgatg
taaaaacatgttcataccaaggtgagaaattaaaataaggagactttttt
tttaataaaaagagcacatagaatagaaatattggtgatgataaaaatac
cttcttaaaatgcatatccagacttaatttcagagtgagtgttagtttgc
atttgcatttaaactgtgatataggaccgacaaaatattaacccatataa
ggagacgccttctttcaagattacaaattatcataatggctaaacccttg
acttggataaaacatagtttgttaactgaagctcagctcctaggtgtcac
cgaacgaacgcctaactcatagattctgaattaaggttgtgagtttttaa
aaggataagttgcaaagcaagttccagactaaacgaatctcttctcaaga
cccatttaaaaatgttaatggtgaaatattatctgggtcctagccaaaga
actgaagcctttggcctcctagcaacccttgcagaatcctccgccaggct
ttcattgttaagctgctaatagctaacacgtttgcccattctccctctac
ttcatagaaacagctttttttttttaaatcttctccagacctgtaagtag
gtaggtactttaggaaaaagtgttaaaagtatccgttctcctaagtttca
ggtcctcaaaaaaaattttaaaaaaagtattgaaaaagtgtaaaagataa
catgcaactactccccaaagatcttaattgggagctactggcgcgggagg
atgtgtgtgtgttgacagaggttcccacaagttcttcccccacagctgtt
tattcagatatcatggggcgcgtcatttacataataaatttttttttaaa
gcagcgaggttgagtcagaccaagctctgctcctctcaattgttgcattt**
```
We will now check the indicated **sequence** with BLAT to ensure that it's specific to our target region. Note how it has a very high score for the entire length of the sequence on the target chromosome.
```
   ACTIONS                 QUERY                                  SCORE START   END QSIZE IDENTITY  CHROM  STRAND  START       END   SPAN
-------------------------------------------------------------------------------------------------------------------------------------------
browser new tab details mm10_knownGene_ENSMUST00000027066.12_0  1000     1  1000  1000   100.0%  chr1   -    14310201  14311200   1000
browser new tab details mm10_knownGene_ENSMUST00000027066.12_0    23   282   305  1000   100.0%  chr1   +    77825559  77825584     26
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
mm10_chr1_Eya1_Pr_F: TCCCCCACAGCTGTTTATTCA
mm10_chr1_Eya1_Pr_R: CTGACTCAACCTCGCTGCTTTA
mm10_chr1_Eya1_Pr_P: CGCGTCATTTACATAAT
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

```

Check NCBI primer blast using target BLAT sequence and selected F and R primers for off-target amplification in mouse genome (with an amplicon size in the same range)
```
Products on potentially unintended templates
>NC_000067.7 Mus musculus strain C57BL/6J chromosome 1, GRCm39

product length = 83
Features flanking this product:
   7341 bp at 5' side: eyes absent homolog 1 isoform x10
   443923 bp at 3' side: musculin isoform 1

Forward primer  1         TCCCCCACAGCTGTTTATTCA  21
Template        14380539  .....................  14380519

Reverse primer  1         CTGACTCAACCTCGCTGCTTTA  22
Template        14380457  ......................  14380478

>NC_000076.7 Mus musculus strain C57BL/6J chromosome 10, GRCm39

product length = 2136
Features associated with this product:
   camp-specific 3',5'-cyclic phosphodiesterase 7b isoform 2

Reverse primer  1         CTGACTCAACCTCGCTGCTTTA  22
Template        20535752  ........T.....A.T.....  20535731

Reverse primer  1         CTGACTCAACCTCGCTGCTTTA  22
Template        20533617  TG..G.......G........T  20533638

```

Check UCSC in-silico pcr for mouse genome using F and R primers
```
	
>chr1:14310233-14310315 83bp TCCCCCACAGCTGTTTATTCA CTGACTCAACCTCGCTGCTTTA
TCCCCCACAGCTGTTTATTCAgatatcatggggcgcgtcatttacataat
aaattttttttTAAAGCAGCGAGGTTGAGTCAG

```


