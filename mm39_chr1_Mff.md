
dpcr primer and probe design for mouse mm39 Mff on chr1
chr1:82,702,611-82,730,111

We will now extract the nucleotide sequence using the table browser. We will mask repeats with N and take a chunk of sequence that does not contain Ns. group: Mapping and Sequencing. track: Assembly. Intersection with knownGene - base-pair-wise intersection (AND) of Assembly and GENCODE VM35.
```
>mm39_gold_chr1.6 range=chr1:82713137-82714449 5'pad=0 3'pad=0 strand=+ repeatMasking=N
**CAGAGCCGAGCAGTTGGCAGGCTAAAAAGAGAGCGTTCTATGAGTGAAAA
TGCTGTTCGCCAAAATGGACAGTTGGTCAGAAACGATTCCATGTGAGTAG
AACTGGCATTGTATCATTATAGATCTTCTGTATCTTGTCTGTACGTATCT
CTTCTAAATAATTCTTATAGTTTTTAAAATGTGTTTACAGTGCTGGAAAT
CACTTTGTATTAGTCATAAAATCTGGCAATTCTCTTCATTGTGAGAGTTT
TTAGTCCTGTGTTTCTCTTCTGTGTGTCTGGCACTTTTATTTATGTAAAG
TGAATATTCTTTCTCATCCACTTTTGGTCAGTTTTCATGAATTCATTGGA
AACTCTCTGTGATGTCAAACATCATGTTAGCTTCTCTGGGAATTCAAAAG
CATCAGGAGATGACAACCTCCTTTGAGAGTTTACAAAGTAACAAGAGCGC
AGACAGCATCACTACCATTCTTACAGGTACCATGGTACTGTAGGGTACAG
TGGTGTGGGATGTGCTCTTATGGCAGCAGAGCGTAAATAGTCAGAGATGG
AAGAGGCCTAATGAGCGCATTCCCTGGCGTCTGTAACTGTCATCGAGGTT
CTATCTCAAATGTAAATTTTTGCTTGCTTTGTTGAAACTCCATTCTCTTA
TGTTGGGTGCAAGGGAAAGCTGTGAGGGCTTTGATTGCGCAGAGAGTCTC
TCACAGTGGCTGTAGTTATTCTAAACAATCACATAAGGAGAAATTGGGTT
AAAATAAATAATGTCTCCTACATGAAAGACTGTCTGAAGGCTCAACCATT
ATTAACCTGATTTTTTTTAATGATTGAATGTGTGTTTTCCTAAGGTTTCA
GATATCAACCAACCTATAAAACTCGATTTTCTAAAACTGTTTCCAGGCAT
GCAAACAGTAAAAAAGACTCCACAATGTAGGCTTATGGCTAATGTGGGTT
AAAAAACAGCTCTAATTCAATATTTTCTACTTGTACTATGTAGTTTTTGA
GGCAGCAGAATCTTTTAGTAGGCTTTCCTGCTGTTTAAGTTGTGATTTGC
TGTATAGGGCCATAATTGACTTTTTATATCATTAAAATGAAAGCATGGTT
ACTTCAGAATTGTATCACCTTTTCACAAAGTAGATACTGTTGATGGCTGA
GTCTGGATGTAGGTAATGGAAAAGGCTGTGTGAGTTCCTAACACCAGCGG
TTGATGAACACGTGATTTTCCTTTGTTTTGTTTAAATTGCCTTCATGGTG
GTTTCTAGATGTCTAATAAGAAAGATCTTGATATTAATAAAGGTTTGCCC
ATTCTTCTCCTGC**
```
We will now check the indicated **sequence** with BLAT to ensure that it's specific to our target region. Note how it has a very high score for the entire length of the sequence on the target chromosome.
```
   ACTIONS                 QUERY   SCORE START   END QSIZE IDENTITY  CHROM  STRAND  START       END   SPAN
------------------------------------------------------------------------------------------------------------
browser new tab details YourSeq  1313     1  1313  1313   100.0%  chr1   +    82713137  82714449   1313
browser new tab details YourSeq    30   890  1043  1313    94.0%  chr12  -    28254580  28254733    154
browser new tab details YourSeq    25   378   405  1313    96.3%  chr2   +    69196888  69197378    491
browser new tab details YourSeq    24   178   216  1313    84.7%  chr2   +    19159945  19159981     37
browser new tab details YourSeq    23   268   291  1313   100.0%  chr1   -    32537764  32537789     26
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
chr1_Mff_F: AGTGGTGTGGGATGTGCTCTT
chr1_Mff_R: CAGGGAATGCGCTCATTAGG
chr1_Mff_P: AGCAGAGCGTAAATAG
```

Check that the amplicon length is between 50-150 and that the melting temperatures are comparable to other primers in the multiplex design. Also check for self-dimers and cross primer dimers with other primers in the multiplex reaction using the Multiple Primer Analyzer: https://www.thermofisher.com/us/en/home/brands/thermo-scientific/molecular-biology/molecular-biology-learning-center/molecular-biology-resource-library/thermo-scientific-web-tools/multiple-primer-analyzer.html . Self-dimers are less problematic if not predicted by Primer Express. 

```
Name         	Sequence             	Tm°C	CG%	nt	A	T	C	G	Extinction coefficient(l/(mol·cm)	Molecular weight(g/mol)	nmol	µg/OD260
chrX_Kdm5c_F:	tggctacatcgcgaaaatcag	67.4	47.6	21	7.0	4.0	5.0	5.0	207500.0                         	6439.3                 	4.8 	31.0
chrX_Kdm5c_R:	catcagctcccagccttacc 	66.2	60.0	20	4.0	4.0	10.0	2.0	175600.0                         	5957.9                 	5.7 	33.9
chrX_Kdm5c_P:	cgagaagtccggcatt     	60.5	56.3	16	4.0	3.0	4.0	5.0	155900.0                         	4906.3                 	6.4 	31.5
chrY_Sry_F:  	tgctgaggtgctcctggtatg	67.9	57.1	21	2.0	7.0	4.0	8.0	193100.0                         	6484.3                 	5.2 	33.6
chrY_Sry_R:  	ccacgaccagcagcttaccta	66.6	57.1	21	6.0	3.0	9.0	3.0	196600.0                         	6320.1                 	5.1 	32.1
chrY_Sry_P:  	ctcaccagtgatgtcag    	53.1	52.9	17	4.0	4.0	5.0	4.0	162500.0                         	5170.4                 	6.2 	31.8
chr1_Mff_F:  	agtggtgtgggatgtgctctt	66.2	52.4	21	2.0	8.0	2.0	9.0	199200.0                         	6539.3                 	5.0 	32.8
chr1_Mff_R:  	cagggaatgcgctcattagg 	67.0	55.0	20	5.0	4.0	4.0	7.0	196200.0                         	6182.1                 	5.1 	31.5
chr1_Mff_P:  	agcagagcgtaaatag     	48.7	43.8	16	7.0	2.0	2.0	5.0	173400.0                         	4963.3                 	5.8 	28.6


```




