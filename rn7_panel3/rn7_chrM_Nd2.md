Our target region is rn7 Nd2 gene chrM:3,904-4,942. This region is reflective of total mitochondrial copy number because it is not affected by the common deletion.

1. Examine the region using the UCSC Genome Browser. Avoid SNVs as they can affect probe binding. Repetitive elements in the RepeatMasker track should also be avoided to prevent probes from binding to multiple genome regions. 
   
2. We can extract the nucleotide sequence by clicking "View"-->"DNA" in the UCSC Genome Browser. 

```
>rn7_dna range=chrM:3904-4942 5'pad=0 3'pad=0 strand=+ repeatMasking=N
ATAAACCCAATCACCCTAATCATTATTTACTTTACTATCCTCATAGGGCC
TGTAATCACTATATCTAGCTCCAACTTACTCCTAATATGAGTAGGATTGG
AAATAAGCCTTTTAGCTATCATCCCACTTCTAGCCAACAAAAAAAGCCCA
CGATCAACTGAAGCAGCAACAAAATATTTTCTAACCCAAGCTACAGCCTC
AATAATTATCCTACTAGTCATCATCCTCAACTACAAACAATCAGGAATAT
GAACCCTCCAACAACAAACCAATAACATACTACTCAACATAATACTCATT
TCACTAGCCATAAAACTTGGACTAGCCCCCTTCCACTACTGACTACCCGA
AGTCACCCAAGGAATTCCCCTACACATTGGATTAATCTTACTAACATGAC
AAAAAATTGCTCCACTATCAATTCTATACCAATTTTATCAACTCCTAAAC
CCAACTATCACCACCATTCTCGCAATTTCATCAGTCTTTGTTGGCGCCTG
AGGAGGACTTAACCAGACCCAAACACGAAAAATCATAGCATATTCATCAA
TTGCCCACATAGGATGAATAACAGCAATCCTTCCATACAACCCTAACTTA
ACCCTCCTAAACTTAACAATTTACATCCTACTTACTGTTCCAATATTCAT
CACACTCATAACAAACTCAGCAACAACAATCAACACACTCTCACTCGCAT
GAAATAAAACTCCCATAATCCTAACCATAACATCCATCATCCTCCTATCA
CTAGGAGGACTCCCCCCTCTCACAGGATTTTTACCAAAATGAGCAATTAT
CTCCGAGCTTCTAAAAAACAACTGCTCAACCCTATCAACACTAATAGCTA
TCATAGCCCTATTAAGCCTATTCTTCTATACACGACTAATTTACTCTATA
TCCCTCACCATATTCCCAACCAACAACAACTCCAAAATAATCTCCCACCA
CCACCAAAACCCAAAACATAATTTTATCCTCCCAACCCTCACAGTATTAA
GTACCCTTACCCTACCGCTTTCCTCCCAACTAATCACAT
```

3. We will now check this sequence with BLAT to ensure that it's specific to our target region. Note how it has a very high score for the entire length of the sequence on the target chromosome. 

```
   ACTIONS                 QUERY   SCORE START   END QSIZE IDENTITY  CHROM  STRAND  START       END   SPAN
------------------------------------------------------------------------------------------------------------
browser new tab details rn7_dna  1039     1  1039  1039   100.0%  chrM   +        3904      4942   1039
browser new tab details rn7_dna    29   933   962  1039   100.0%  chr10  -    19424321  19424508    188
browser new tab details rn7_dna    27   711   742  1039    93.6%  chr11  +    37933033  37933371    339
browser new tab details rn7_dna    24   655   680  1039    96.2%  chr19  -    49746421  49746446     26
browser new tab details rn7_dna    24   945   968  1039   100.0%  chr9   +   110966933 110966956     24
browser new tab details rn7_dna    24   702   728  1039    96.3%  chr11  +    54664870  54664912     43
browser new tab details rn7_dna    24   945   969  1039   100.0%  chr1   +    66089662  66089687     26
browser new tab details rn7_dna    22   159   180  1039   100.0%  chr10  +    29648102  29648123     22
browser new tab details rn7_dna    21   945   965  1039   100.0%  chr13  -    55022750  55022770     21
browser new tab details rn7_dna    21   159   180  1039   100.0%  chr12  -     7062989   7063011     23
browser new tab details rn7_dna    21   389   409  1039   100.0%  chr11  -    68932931  68932951     21
browser new tab details rn7_dna    21   281   303  1039    95.7%  chr11  -    64472881  64472903     23
browser new tab details rn7_dna    21   159   180  1039   100.0%  chr11  -    62683065  62683087     23
browser new tab details rn7_dna    21   159   181  1039    95.7%  chr11  -    26979255  26979277     23
browser new tab details rn7_dna    21   159   180  1039   100.0%  chr1   -   202582589 202582611     23
browser new tab details rn7_dna    21   946   966  1039   100.0%  chr10  +    86408180  86408200     21
```

4. We will now use this sequence to design primers and probes in primer express using a TaqMan MGB quantification design. Start with the following parameters:

```
Min Primer Tm	58
Max Primer Tm	60
Max Difference in Tm of Two Primers	2
Primer GC Content	
Min Primer %GC Content	30
Max Primer %GC Content	80
Max Primer 3' GC's	2
Primer 3' End Length	5
Primer 3' GC Clamp Residues	0
Primer Length	
Min Primer Length	9
Max Primer Length	40
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
Min Amplified Region Length	50
Max Amplified Region Length	150
```

Relax the primer length requirement if no ideal primers are found
   
5. Below is the top primer / probe combination for our target region (5'-3') that does not have an off-target amplicon (maximum size 500bp) in ncbi primer blast using GRCr8. 
   
- rn7_chrM_Nd2_F  TCTCGCAATTTCATCAGTCTTTG
- rn7_chrM_Nd2_R  TTTTCGTGTTTGGGTCTGGTT
- rn7_chrM_Nd2_P  TGGCGCCTGAGGAG

6. Check that the amplicon length is between 50-150 and that the melting temperatures are comparable to other primers in the multiplex design. Also check for self-dimers and cross primer dimers with other primers in the multiplex reaction using the Multiple Primer Analyzer: [link](https://www.thermofisher.com/us/en/home/brands/thermo-scientific/molecular-biology/molecular-biology-learning-center/molecular-biology-resource-library/thermo-scientific-web-tools/multiple-primer-analyzer.html) . Self-dimers are less problematic if not predicted by Primer Express. 
   
```
Name     	Sequence                 	Tm°C	CG%	nt	A	T	C	G	Extinction coefficient(l/(mol·cm)	Molecular weight(g/mol)	nmol	µg/OD260
chr1F    	tcatggacctggctttcttgt    	66.1	47.6	21	2.0	9.0	5.0	5.0	185000.0                         	6394.2                 	5.4 	34.6
chr1R    	tcgtgccaatcgcctactc      	66.7	57.9	19	3.0	5.0	8.0	3.0	167100.0                         	5699.7                 	6.0 	34.1
chr1P    	ccaaagacacagattaa        	49.0	35.3	17	9.0	2.0	4.0	2.0	180400.0                         	5180.5                 	5.5 	28.7
chrM_Nd1F	aacggaaaatcctaggctacataca	64.7	40.0	25	11.0	4.0	6.0	4.0	257800.0                         	7652.1                 	3.9 	29.7
chrM_Nd1R	catatgggcctacgatgttg     	63.1	50.0	20	4.0	6.0	4.0	6.0	191700.0                         	6148.1                 	5.2 	32.1
chrM_Nd1P	ctacgcaaaggcc            	51.4	61.5	13	4.0	1.0	5.0	3.0	123200.0                         	3928.6                 	8.1 	31.9


```

Note that there are no primer options without a cross primer dimer for Nd1
```
                Self-Dimers:


               Cross Primer Dimers:

chrM_Nd1F with chrM_Nd1R
chrM_Nd1F
5-aacggaaaatcctaggctacataca->
       || ||| |||||       
    <-gttgtagcatccgggtatac-5
```

7. Check NCBI primer blast using the selected F and R primers for off-target amplification in rat genome (with an amplicon size in the same range). If there is an off-target make sure that the amplicon length is too long for 15sec dPCR extension.

```
	Sequence (5'->3')	Template strand	Length	Start	Stop	Tm	GC%	Self complementarity	Self 3' complementarity
Forward primer	TCTCGCAATTTCATCAGTCTTTG	Plus	23	468	490	57.71	39.13	4.00	1.00
Reverse primer	TTTTCGTGTTTGGGTCTGGTT	Minus	21	531	511	58.55	42.86	2.00	0.00
Product length	64
Products on potentially unintended templates
>NC_086039.1 Rattus norvegicus strain BN/NHsdMcwi chromosome X, GRCr8

product length = 2444
Features associated with this product:
   ferm and pdz domain-containing protein 4 isoform x3

   ferm and pdz domain-containing protein 4 isoform x6

Reverse primer  1         TTTTCGTGTTTGGGTCTGGTT  21
Template        29854598  ....T.A........T.T...  29854578

Reverse primer  1         TTTTCGTGTTTGGGTCTGGTT  21
Template        29852155  ..G..C.T..........A..  29852175


product length = 1369
Features flanking this product:
   29856 bp at 5' side: calpain-6
   8444 bp at 3' side: neuronal migration protein doublecortin isoform x1

Forward primer  1          TCTCGCAATTTCATCAGTCTTTG  23
Template        112226673  ...GAA..C...........C..  112226651

Reverse primer  1          TTTTCGTGTTTGGGTCTGGTT  21
Template        112225305  .C...A.........T..T..  112225325

>NC_086034.1 Rattus norvegicus strain BN/NHsdMcwi chromosome 16, GRCr8

product length = 1471
Features flanking this product:
   4511689 bp at 5' side: n(4)-(beta-n-acetylglucosaminyl)-l-asparaginase precursor
   498263 bp at 3' side: teneurin-3 isoform x5

Forward primer  1         TCTCGCAATTTCATCAGTCTTTG  23
Template        49761104  .A..C........AA.....A..  49761126

Reverse primer  1         TTTTCGTGTTTGGGTCTGGTT  21
Template        49762574  ...G.T.A....T........  49762554
```
   

