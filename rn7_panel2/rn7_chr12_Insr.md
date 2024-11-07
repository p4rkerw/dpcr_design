dpcr primer and probe design for rat rn7 Insr on chr12
chr12:1,197,100-1,330,883

We will now extract the nucleotide sequence using the table browser. We will mask repeats with N and take a chunk of sequence that does not contain Ns. group: Mapping and Sequencing. track: Assembly. Intersection with Genes and Gene Predictions NCBI RefSeq - base-pair-wise intersection (AND) of Assembly and NCBI RefSeq
```
>rn7_gold_chr12.1 range=chr12:1196100-1199350 5'pad=1000 3'pad=1000 strand=+ repeatMasking=N
**GAGCAGCTGTGGTTTGATGCAAAGAGGTTGCGAGTTTGTGTGCCTTCACC
AGTTCTTGGTGGTGGGAAGTGTCCGATGTTCTCTCCTCTAGACTTTAGTC
TCGAGAGACTGAAACATAAGCGCTTGAGAAATAGACTCAGGCGCTCCATC
TGGCCAAGCTGAGGTCTCTGGGCACCGCGAGCAGCTGTGGGGTGGGGTTT
AGTGTGGAGAATAGCCAGATGCCCCAAAGGTGGAGACCGACAGCGATTTG
AAGGTGCACCTCCTCAGACACTGCTTAGTGTTCCCAGAGTCCAACTGTGT
CACTGGTCTTTGGGATCTGAGTTCAGTATCTTTGAGCAAAGTGTAGGCTT
TGAAGAAGTGAGGTACACAAGCAGAGAAAAACCAGACAAACACAGGTGTT
CTGGAAGGCCACCTCGGCCCCAGGTAACCACCAGTGTATCCAAGCAAGGA
ACATCCAGTCAGTGTTACTATCTGAACCAGTCAAAAATCCAGTTACCCAC
AAATCCACAAGAACTCACCGAGTCCTAAAAGGCTAGCAGCTAATGTGGTA
TAATTCC**NNNNNNNNNNNNNNNNNNNNNNNNNNNTGTGTTTCAAAGACCG
AACACAGAGGCCACTCATGTATTGTCCCGTCTCCCCACACAGGCAGATGT
GCCCACCACTTCCCCTGCTCCCAAGGAAATAATAACTTATTAGGCTCATC
TCAAAGATCCCATAAGCTTTAAATATGTTACCAATATATTCTCAAACTTG
TTGCCTTACTTCCTTCTACNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNN
NNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNN
NNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNCGCCCGTGCATGCATGT
CCTTTGTTTGATCTTCCAAAGATCCTCCATGAATCCAGACCAAATAATCA
TCCCTCTGTTTTTGGAAATCATCACCAAAGGGAAGGGGAAGAAGACACCT
GAGCGAGTTCTGACGTGACTGAGGAGAATCTCTCGAGGGCACAAGCTCTC
GGTTCATAAGAAGGAAGAGGACAATATGAGGTCACCCACTCCAAGCAGCG
GGTGCTTCATGAGCCAAGTCACCAAGCATCAGTCCAGAGAAAAATGTAAC
ATACACACAGCCCCCACCCCACCCTGTGATCTCTAACCTGGACACAACAC
ACACGCAAATGCACGCAGGTGTGCAGATGAGCACACACTTAGGAGTACAC
ACCCTTTCCCAAAATAATAAAATATGAAAGCAGCAGCTATTGGTCAATTT
GAGGAACTGATTTTGTGAATGAGGNNNNNNNNNNNNNNNNNNNNNNNNNN
NNNNNGCTCCTTCTCTCAGATTAATGAAACCTTCTCAAAGCCCAACCCCG
CGAAAGCACGCAATTCCAGAACTGGGTTCTGTAGGTCAGGNNNNNNNNNN
NNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNCTGACTTGTGCTCCATA
AATAAAGTCTGTCTTTGACAACTAACTATAACTCAGACACTAGCAGAAAA
AAAAAACTGTAAAAACAGGTTCATCCTTCCAATCTATGAGGAAAACACCA
GCAACAACAATAAAATCTTGGTTTGATACCGTGGGGGCAGGGAAGGGAGT
ATGGAAACCCCAACCCCTCTAGGTTCACAGTTAGCCCTCCACAGGCTCGC
AGGGTTGGCGACCACACCTGTGTGTTTTCAGGTCCAAAGACAAACAGAAA
TGTGTACGAACTATCTGTGAGCTCAGTTTCACATCTGGGTAGAGTCCCGA
TAATCCTGAGTTTCCTGGAGGCAGTCAAACTACAGAAGAGTTTTTANNNN
NNNNNNNNNNNNNNNNNNNNNTCCTTCCCCGAGCGAGCAGGCGCTGTTAG
GAAGGGTTCGACCTCGGCAGGGTGAGGACCCGCCCATTCTTCTTGCCCCC
GTTCATGTGGGTGTAGGGGATGTGTTCATCATAGGTCCGTTTGATGCTCA
GAGAGGACCCTCCCTCCCGGCATCCAGCCTCTTCTCTCTGACAGTGAGAG
GAACGATCCAAGGGGACATTCTCCATGTCCTCGAACTCCATCTCCAGCTC
TTCACTCTCGGGAGCCTTGTTCTCCTCGCTGTAGAAGAAGGAAACTTCCG
GAAAGCTGGGGTGGAGGTCGTCCTTGAGCAGGTTGACGATTTCCAGGAAG
GTCGGCCTCATCTTGGGGTTGAACTGCCAGCACATGCGCATCAGGTCAGT
GCTGTGGAGACAGGAACCAGGGCGGATACGTTTAAGTCAGGGGAGCCTTG
GCCCTGGCTGTGGTTGTACGCAGAGCGGACAGTAAAGGCTGGATCAACAA
TTCTAGCGGGACTGAAAGCCGGTTTTGAAAAGCGAGCCNNNNNNNNNNNN
```
We will now check the indicated **sequence** with BLAT to ensure that it's specific to our target region. Note how it has a very high score for the entire length of the sequence on the target chromosome.
```
   ACTIONS                 QUERY   SCORE START   END QSIZE IDENTITY  CHROM  STRAND  START       END   SPAN
------------------------------------------------------------------------------------------------------------
browser new tab details YourSeq   557     1   557   557   100.0%  chr12  +     1196100   1196656    557
browser new tab details YourSeq    23   322   345   557   100.0%  chr14  +    12529338  12529362     25
browser new tab details YourSeq    22   188   213   557    87.5%  chr14  +    36680624  36680648     25
browser new tab details YourSeq    21   416   437   557   100.0%  chr1   -    44843799  44843821     23
browser new tab details YourSeq    21   368   390   557    95.7%  chr15  +    80784555  80784577     23
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
chr12_Insr_F: GGAGACCGACAGCGATTTGA
chr12_Insr_R: TCCCAAAGACCAGTGACACAGT
chr12_Insr_P: CACTGCTTAGTGTTCCCA
```

Check that the amplicon length is between 50-150 and that the melting temperatures are comparable to other primers in the multiplex design. Also check for self-dimers and cross primer dimers with other primers in the multiplex reaction using the Multiple Primer Analyzer: https://www.thermofisher.com/us/en/home/brands/thermo-scientific/molecular-biology/molecular-biology-learning-center/molecular-biology-resource-library/thermo-scientific-web-tools/multiple-primer-analyzer.html . Self-dimers are less problematic if not predicted by Primer Express. 

```
Name  	Sequence                	Tm°C	CG%	nt	A	T	C	G	Extinction coefficient(l/(mol·cm)	Molecular weight(g/mol)	nmol	µg/OD260
chr1F 	gaagaagccccggtcatca     	67.8	57.9	19	6.0	2.0	6.0	5.0	189000.0                         	5806.8                 	5.3 	30.7
chr1R 	gctttcttgcacgctggaa     	66.9	52.6	19	3.0	6.0	5.0	5.0	171600.0                         	5794.8                 	5.8 	33.8
chr1P 	aagcagaggatgaatct       	52.2	41.2	17	7.0	3.0	2.0	5.0	179700.0                         	5267.5                 	5.6 	29.3
chrXF 	ccagcagccaggacagtagaa   	67.0	57.1	21	8.0	1.0	6.0	6.0	215700.0                         	6458.3                 	4.6 	29.9
chrXR 	ctgaccaaacctggctggat    	66.7	55.0	20	5.0	4.0	6.0	5.0	186600.0                         	6102.0                 	5.4 	32.7
chrXP 	agtagtgtgaggaccaact     	54.0	47.4	19	6.0	4.0	3.0	6.0	194900.0                         	5876.9                 	5.1 	30.2
chrYF 	tgctaccaaagttgcagttatcct	65.0	41.7	24	6.0	8.0	6.0	4.0	225600.0                         	7302.8                 	4.4 	32.4
chrYR 	aggtgataccaaaaaccaaaaggt	64.6	37.5	24	12.0	3.0	4.0	5.0	255500.0                         	7411.9                 	3.9 	29.0
chrYP 	agatttatgtgcctcagggt    	60.5	45.0	20	4.0	7.0	3.0	6.0	194200.0                         	6163.1                 	5.1 	31.7
chr10F	gccaaagtggctctgtcgtaa   	66.7	52.4	21	5.0	5.0	5.0	6.0	202400.0                         	6446.3                 	4.9 	31.8
chr10R	tgtccaagagcactggagttca  	67.5	50.0	22	6.0	5.0	5.0	6.0	216000.0                         	6759.5                 	4.6 	31.3
chr10P	tttgacccaattttctg       	54.8	35.3	17	3.0	8.0	4.0	2.0	152200.0                         	5126.4                 	6.6 	33.7
chr12F	ggagaccgacagcgatttga    	67.9	55.0	20	6.0	3.0	4.0	7.0	203100.0                         	6191.1                 	4.9 	30.5
chr12R	tcccaaagaccagtgacacagt  	66.2	50.0	22	8.0	3.0	7.0	4.0	217900.0                         	6697.4                 	4.6 	30.7
chr12P	cactgcttagtgttccca      	57.8	50.0	18	3.0	6.0	6.0	3.0	162500.0                         	5425.6                 	6.2 	33.4

```

Check NCBI primer blast using target BLAT sequence and selected F and R primers for off-target amplification in rat genome (with an amplicon size in the same range) ie "Genomes for selected eukaryotic organisms"
```
>NC_086030.1 Rattus norvegicus strain BN/NHsdMcwi chromosome 12, GRCr8

product length = 84
Features flanking this product:
   15074 bp at 5' side: rrna-5s ribosomal rna
   1581 bp at 3' side: insulin receptor preproprotein

Forward primer  1        GGAGACCGACAGCGATTTGA  20
Template        5994273  ....................  5994292

Reverse primer  1        TCCCAAAGACCAGTGACACAGT  22
Template        5994356  ......................  5994335
```

