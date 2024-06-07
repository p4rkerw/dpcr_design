
dpcr primer and probe design for mouse mm39 Sry on chrY
chrY:2,662,471-2,663,658

We will now extract the nucleotide sequence using the table browser. We will mask repeats with N and take the first chunk. group: Mapping and Sequencing. track: Assembly. Intersection with knownGene - base-pair-wise intersection (AND) of Assembly and GENCODE VM35. We will add a 1kb 3' and 5' pad because the sequence in the gene is suboptimal for primer design  
```
>mm39_gold_chrY.1 range=chrY:2661471-2664658 5'pad=1000 3'pad=1000 strand=+ repeatMasking=N
ATGATGTAGTTTTGTGTGCTAGAGAGAAACCCTGATAAACAGAAAGATGC
ATTTGATCAACAAAGGAGTGTTTTGCATACTAAAGAGACACAGCCTGTGT
TTTCACAGTATTAAGTTTGGTATGTTTTTCAAAGATGAGTATTGAAGACT
TACAGATGGTTTGCATGGTGATGCTGTAAGGAAATGACAGCCAGCCCTGA
CCCGATGGCACTGTGTTTTTGCCTGCTCAGAAATGAACTACTGCATCCCA
GTCATTAGAATGCTCAACCTGAATGATTATATACATACCTACNNNNNNNN
NNNNNNNNNNNNNNNNNNNNNNNNNNNNNNN**GTCTCCGGTGGTGGCTAAA
GAAATTTAACATGCAGCCAGGCATCTAGTAAGAGTCCTTGACCTTTGCCT
TGGGATGCCTGGGAGATCCTATTGGCCAAAGAGTAAGATAAGAATAGGCT
AATAGGCTGTGAGGAATTCACAGCTGTCTTTGTTCCTGTAAAACCTGATT
ATCTGTGGAAAAGGGGATGAAATGGTCTTTTATTACTACATAACAGGAAT
GAAAAGAATTTTCTTGCCCAGCTGGATATTTGTCATTACAATGTGTCATT
CTGATGTTTCCTTTAAAACTCCAGCTTACTCACCCCTAGCCCCCACTTTA
GCATGGCATGCTGTATTGACCACAAAGCTGTTTGCTGTCTTTGTGCTAGC
CTAAGAATAAATGCATTTCATCTAAATTGGATCTGAGTGTAAATCTCTGG
TTTCTTCTGTGGATTAAATGCCACAACAATGCAACTAGTACTATGTTAAA
CAAAAACTATGTAGAAGCATTTCTAAGCTTTCTCCTTCCTTACACACTAC
ACATCTTTACACACATTTTAGAACCCAAAAGGAAGGAGCAGGACCTTTTT
CATGACAGGAGAAAAGTCAGTATCTAAACCAACTAGGAATCTCAGACTTA
AAAATCATAGCAAGGGGGAGTGTTGGCATAGGTAGGAGAAAAGGCCAGTG
TCATGAGACTGCCAACCACAGGGCTGTGCTGAGGTGCTCCTGGTATGGTG
TATGCTCACCAGTGATGTCAGCTGTTAGTAAGTAGGTAAGCTGCTGGTCG
TGGAA**NNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNGTGGTG
GTCATGGAANNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNN
NNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNN
NNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNN
NNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNN
NNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNN
NNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNN
NNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNN
NNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNN
NNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNN
NNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNN
NNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNN
NNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNN
NNNNNNNNNNNNNNNNCCAGTGGGGATATCAACAGGCTGCCAATAAAAGC
TTTGCTGGTTTTTGGAGTACAGGTGTGCAGCTCTACTCCAGTCTTGCCTG
TATGTGATGGCATGTGGGTTCCTGTCCCACTGCAGAAGGTTGTACAGTTT
TGTTGAGGCAACTGCAGGCTGTAAAATGCCACTCCTCTGTGACACTTTAG
CCCTCCGATGAGGCTGATATTTATAGTTTGGGTATTTCTCTCTGTGTAGG
ATCTTCAATCTCTGTGCCTCCTGGAAAAAGGGCCTTTTTTCGGCTTCTGT
AAGGCTTTTCCACCTGCATCCCAGCTGCTTGCTGATCTCTGTATTTTGCA
TGCTGGGATTCTGCTGGGCCAACTTGTGCCTCTCACCACGGGACCACACC
ATAAATGCATTCATGGGGCGCTTGACATGGCCCTCCATGCTCTCTAGACA
ATTGTCACCAGTCCCAAAACTTGTCTCTTCTTCAGAGTTTAAGATATCAT
GTGGCTGTAGGGCTGAACACTAAAAATCAAGATCTGAAATGCTGAACATA
ATGGAAGAATTATGATTGCAACCAAAAAGACAGAGATGTGATGCAAAGAG
AANNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNN
NNNNNNNNNNNNNAGTCAAAACTTAAAGTGTAAGAGCTAAAAGCCACTGA
CCAAAATGTGCTTGTAACAAAGATTTTAATATTTAACGTGTGTAAGAAAA
TATTTATCCCTCCTCCTTCAGGACCTCCCTAGTCCAGCCCAACTAATCTA
CTTTGAAGCCATCTCATGAACCTAGATACTGTCAAGCAAAACCCCTCAAG
TTTGTGAATGTTAGAGACTGCACTTTCACACTCCTTAAAAATATATCGCT
TTTTCTTTGATCATTCTGTCACAACAAGTATTAAGATACAAAGAACATAC
TGATGAGTTCTTTTGCCCTGTAACGTACCTAATGTTTAGGATGGACTAAC
GTGAGAAATTAACGAGCTTGCAAAAGTAGTGGAAAGGGTTAAAAATGATA
AGCATGGAACCTATCATTAGTATCATAGTCTACTACGGCAGGCAGCATGG
AAAAAACTAAGAAATAGTCTGTTCTGGCTCTATAGCCCAGTATAAATATC
TACACCATAAAAGAACTTTTGCTTCCTTTCTTGGTCATATCAATGCATCA
TAAAAGTAATGTATACAAATTTCTTACATAATAGCAAAAATTCTTTCATG
GTAAAAATCATCCAGGTTGAGCATTCTAATGACTGGGATGCAGTAGTTCA
TTTCTGAGCAGGCAAAAACACAGTGCCATCGGGTCAGGGCTGGCTGTCAT
TTCCTTACAGCATCACCATGCAAACCATCTGTAAGTCTTCAATACTCATC
TTTGAAAAACATACCAAACTTAATACTGTGAAAACACA
```
We will now check the indicated **sequence** with BLAT to ensure that it's specific to our target region. Note how it has a very high score for the entire length of the sequence on the target chromosome.
```
   ACTIONS                 QUERY   SCORE START   END QSIZE IDENTITY  CHROM  STRAND  START       END   SPAN
------------------------------------------------------------------------------------------------------------
browser new tab details YourSeq   774     1   774   774   100.0%  chrY   +     2661802   2662575    774
browser new tab details YourSeq    96   183   586   774    90.7%  chr1   -    47455476  47712331 256856
browser new tab details YourSeq    72    15   207   774    74.8%  chr6   +   113398627 113398780    154
browser new tab details YourSeq    63   184   397   774    88.1%  chr1   +     7495961   7496194    234
browser new tab details YourSeq    54   105   206   774    88.6%  chr15  +    85040893  85040995    103
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
chrY_Sry_F: TGCTGAGGTGCTCCTGGTATG
chrY_Sry_R: CCACGACCAGCAGCTTACCTA
chrY_Sry_P: CTCACCAGTGATGTCAG
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

Check NCBI primer blast using target BLAT sequence and selected F and R primers for off-target amplification in mouse genome (with an amplicon size in the same range)
```
>NC_000087.8 Mus musculus strain C57BL/6J chromosome Y, GRCm39

product length = 77
Features associated with this product:
   sex-determining region y protein

Forward primer  1        TGCTGAGGTGCTCCTGGTATG  21
Template        2662497  .....................  2662517

Reverse primer  1        CCACGACCAGCAGCTTACCTA  21
Template        2662573  .....................  2662553
```




