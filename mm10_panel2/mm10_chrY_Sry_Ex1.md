
dpcr primer and probe design for mouse mm39 Sry coding region on chrY
chrY:2,662,471-2,663,658

We will now extract the nucleotide sequence using the table browser. group: Genes and Gene predictions. track: GENCODE VM23. 
```
>mm10_knownGene_ENSMUST00000091178.1 range=chrY:2662471-2663658 5'pad=0 3'pad=0 strand=- repeatMasking=N
**ATGGAGGGCCATGTCAAGCGCCCCATGAATGCATTTATGGTGTGGTCCCG
TGGTGAGAGGCACAAGTTGGCCCAGCAGAATCCCAGCATGCAAAATACAG
AGATCAGCAAGCAGCTGGGATGCAGGTGGAAAAGCCTTACAGAAGCCGAA
AAAAGGCCCTTTTTCCAGGAGGCACAGAGATTGAAGATCCTACACAGAGA
GAAATACCCAAACTATAAATATCAGCCTCATCGGAGGGCTAAAGTGTCAC
AGAGGAGTGGCATTTTACAGCCTGCAGTTGCCTCAACAAAACTGTACAAC
CTTCTGCAGTGGGACAGGAACCCACATGCCATCACATACAGGCAAGACTG
GAGTAGAGCTGCACACCTGTACTCCAAAAACCAGCAAAGCTTTTATTGGC
AGCCTGTTGATATCCCCACTGGGCACCT**NNNNNNNNNNNNNNNNNNNNNN
NNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNN
NNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNTTNNNNN
NNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNN
NNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNN
NNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNN
NNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNN
NNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNN
NNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNTTCCATGACC
ACCCCCAGCAGAAGCAGCAGTTCCATGACCACCCCCAGCAGCAACAGCAG
TTCCATGACCACCACCACNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNN
NNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNN
NNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNN
NNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNTTCCACGACCAGCAGCT
TACCTACTTACTAACAGCTGACATCACTGGTGAGCATACACCATACCAGG
AGCACCTCAGCACAGCCCTGTGGTTGGCAGTCTCATGA

```
We will now check the indicated **sequence** with BLAT to ensure that it's specific to our target region. Note how it has a very high score for the entire length of the sequence on the target chromosome. Make sure to avoid regions that have significant overlap with other areas of the genome.
```
   ACTIONS                 QUERY   SCORE START   END QSIZE IDENTITY  CHROM  STRAND  START       END   SPAN
------------------------------------------------------------------------------------------------------------
browser new tab details YourSeq   428     1   428   428   100.0%  chrY   -     2663231   2663658    428
browser new tab details YourSeq    38   353   392   428   100.0%  chr10  -    26682976  27001682 318707
browser new tab details YourSeq    28    10    41   428    93.8%  chr11  +    45983357  45983388     32
browser new tab details YourSeq    28    79   130   428    63.7%  chr10  +    52890716  52890748     33
browser new tab details YourSeq    26    82   111   428    96.6%  chr11  -    75736035  75736076     42
browser new tab details YourSeq    25   115   142   428    96.5%  chr5   -    18290546  18290576     31
browser new tab details YourSeq    20   378   397   428   100.0%  chr10  -    62227459  62227478     20
browser new tab details YourSeq    20   378   397   428   100.0%  chr10  +    60140320  60140339     20
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
mm10_chrY_Sry_Pr_Ex1: GCCTGCAGTTGCCTCAACA
mm10_chrY_Sry_Pr_Ex1: TGCCTGTATGTGATGGCATGT
mm10_chrY_Sry_Pr_Ex1: AACTGTACAACCTTCTGC
```

Check that the amplicon length is between 50-150 and that the melting temperatures are comparable to other primers in the multiplex design. Also check for self-dimers and cross primer dimers with other primers in the multiplex reaction using the Multiple Primer Analyzer: https://www.thermofisher.com/us/en/home/brands/thermo-scientific/molecular-biology/molecular-biology-learning-center/molecular-biology-resource-library/thermo-scientific-web-tools/multiple-primer-analyzer.html

```
Name                 	Sequence              	Tm°C	CG%	nt	A	T	C	G	Extinction coefficient(l/(mol·cm)	Molecular weight(g/mol)	nmol	µg/OD260
mmm10_chrY_Uty_Pr_F: 	cgtgggataaaacggttgct  	66.1	50.0	20	5.0	5.0	3.0	7.0	196100.0                         	6197.1                 	5.1 	31.6
mm10_chrY_Uty_Pr_R:  	agtgtgaaccgcacgtaacg  	66.4	55.0	20	6.0	3.0	5.0	6.0	199800.0                         	6151.1                 	5.0 	30.8
mm10_chrY_Uty_Pr_P:  	ccattggaaagcctg       	56.3	53.3	15	4.0	3.0	4.0	4.0	143000.0                         	4577.0                 	7.0 	32.0
mm10_chrY_Sry_Pr_Ex1:	gcctgcagttgcctcaaca   	68.1	57.9	19	4.0	4.0	7.0	4.0	173300.0                         	5748.8                 	5.8 	33.2
mm10_chrY_Sry_Pr_Ex1:	tgcctgtatgtgatggcatgt 	66.7	47.6	21	3.0	8.0	3.0	7.0	197700.0                         	6483.3                 	5.1 	32.8
mm10_chrY_Sry_Pr_Ex1:	aactgtacaaccttctgc    	53.0	44.4	18	5.0	5.0	6.0	2.0	166700.0                         	5418.6                 	6.0 	32.5
mm10_chrY_Eya1_Pr_F: 	tcccccacagctgtttattca 	66.7	47.6	21	4.0	7.0	8.0	2.0	188400.0                         	6292.1                 	5.3 	33.4
mm10_chrY_Eya1_Pr_R: 	ctgactcaacctcgctgcttta	65.9	50.0	22	4.0	7.0	8.0	3.0	194000.0                         	6621.4                 	5.2 	34.1
mm10_chrY_Eya1_Pr_P: 	cgcgtcatttacataat     	52.3	35.3	17	5.0	6.0	4.0	2.0	163900.0                         	5144.4                 	6.1 	31.4
mm10_chrX_Ftx_Pr_F:  	gaaaatagcctgccccaagag 	66.1	52.4	21	8.0	2.0	6.0	5.0	210700.0                         	6433.3                 	4.7 	30.5
mm10_chrX_Ftx_Pr_R:  	gcccaagttacaaagcctgaag	66.0	50.0	22	8.0	3.0	6.0	5.0	218600.0                         	6737.4                 	4.6 	30.8
mm10_chrX_Ftx_Pr_P:  	tctggttccaggtattaga   	55.2	42.1	19	4.0	7.0	3.0	5.0	185900.0                         	5833.9                 	5.4 	31.4

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






