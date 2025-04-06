Our target region is rn7 Nd4 gene chrM:10,160-11,537. This gene is in the common deletion region

1. Examine the region using the UCSC Genome Browser. Avoid SNVs as they can affect probe binding. Repetitive elements in the RepeatMasker track should also be avoided to prevent probes from binding to multiple genome regions. 
   
2. We can extract the nucleotide sequence by clicking "View"-->"DNA" in the UCSC Genome Browser. 

```
>rn7_dna range=chrM:10160-11537 5'pad=0 3'pad=0 strand=+ repeatMasking=N
ATGTTAAAAATTATTTTCCCATCTATCATACTCCTCCCACTAACATGACT
CTCAGCCAACAAAAAAATCTGAACCAATGTCACCTCCTACAGCTTTCTAG
TGAGCCTATTAAGCTTATCACTCCTATGACAAAATGACGAAAATTACCTA
AATTTCTCAGTTATATTCTCCTCCGATCCATTATCCACCCCACTAATCAT
TCTAACAACTTGACTCCTCCCACTAATAATGCTCGCTAGCCAAAATCACA
TAAAAAAAGAAAATATAATGCATCAAAAACTTTACATCTCAATACTTATT
AGCCTCCAAATTTTACTCATCATAACATTCTCCGCAACAGAACTAATTTT
ATTTTATATCCTGTTCGAAGCCACTCTAATCCCAACACTAATTATCATTA
CACGATGAGGCAACCAAACAGAACGCTTAAATGCAGGAATTTATTTCCTA
TTTTATACACTAATTGGCTCCATCCCACTCTTAATTGCCCTCATTTCAAT
CCAAAACTCAATAGGAACACTCAACTTCCTAATCCTCTCCCTCACAACAC
ACCCCCTACCCTCAACATGATCCAACACCATTCTATGACTAGCATGTATA
ATAGCATTTATAATCAAAATACCATTATACGGAGTCCATCTATGATTACC
AAAAGCCCACGTAGAAGCTCCAATTGCAGGCTCTATAATTTTAGCAGCAA
TTCTCCTAAAGCTAGGGGGTTATGGGATAATACGAGTTTCCATCATTCTA
GACCCCCTAACAAAATCTTTAGCCTACCCATTCATCATCCTCTCATTATG
AGGCATAATTATAACTAGCTCAATCTGCCTACGCCAAACAGATCTAAAAT
CATTAATTGCTTACTCATCAGTAAGCCATATAGCCCTAGTCATCACAGCC
ATTATAATCCAGACACCATGAAGCTTCATGGGAGCTACAATACTAATAAT
CGCCCACGGCTTAACCTCCTCACTCTTATTCTGCCTAGCAAACACCAACT
ACGAACGAATTCACAGCCGAACTATAATTATAGCTCGAGGATTACAAATA
ATCTTTCCATTGATAGCAACATGATGACTATTAGCAAGCTTAGCCAACCT
AGCACTACCACCCCTAATTAACCTCATAGGCGAGTTATTCATTGTTATAG
CAACATTTTCCTGATCGAACCCCTCTATCATCCTTATAGCAACTAACATT
GTCATCACAGGAATCTACTCAATATATATAATTATCACAACCCAACGAGG
AAAACTAACCAGCCACATAAACAACCTCCAACCTTCCCACACACGAGAAT
TAACACTCATAGCTCTACACATTATTCCCCTCATACTATTAACAATCAAC
CCTAAACTCATCACAGGCCTAACAATAT
```

3. We will now check this sequence with BLAT to ensure that it's specific to our target region. Note how it has a very high score for the entire length of the sequence on the target chromosome. 

```
   ACTIONS                 QUERY   SCORE START   END QSIZE IDENTITY  CHROM  STRAND  START       END   SPAN
------------------------------------------------------------------------------------------------------------
browser new tab details rn7_dna  1378     1  1378  1378   100.0%  chrM   +       10160     11537   1378
browser new tab details rn7_dna    70   967  1044  1378    94.9%  chr2   -   135777314 135777391     78
browser new tab details rn7_dna    30  1272  1333  1378    68.8%  chr20  +    33857441  33857483     43
browser new tab details rn7_dna    24   287   310  1378   100.0%  chr2   -    24721861  24721884     24
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
   
- rn7_chrM_Nd4_F  TCGCCCACGGCTTAACC
- rn7_chrM_Nd4_R  TCGTTCGTAGTTGGTGTTTGCT
- rn7_chrM_Nd4_P  CCTCACTCTTATTCTGC

6. Check that the amplicon length is between 50-150 and that the melting temperatures are comparable to other primers in the multiplex design. Also check for self-dimers and cross primer dimers with other primers in the multiplex reaction using the Multiple Primer Analyzer: [link](https://www.thermofisher.com/us/en/home/brands/thermo-scientific/molecular-biology/molecular-biology-learning-center/molecular-biology-resource-library/thermo-scientific-web-tools/multiple-primer-analyzer.html) . Self-dimers are less problematic if not predicted by Primer Express. 
   
```
Name            	Sequence                 	Tm°C	CG%	nt	A	T	C	G	Extinction coefficient(l/(mol·cm)	Molecular weight(g/mol)	nmol	µg/OD260
rn7-chr1-Rpp30-F	tcatggacctggctttcttgt    	66.1	47.6	21	2.0	9.0	5.0	5.0	185000.0                         	6394.2                 	5.4 	34.6
rn7-chr1-Rpp30-R	tcgtgccaatcgcctactc      	66.7	57.9	19	3.0	5.0	8.0	3.0	167100.0                         	5699.7                 	6.0 	34.1
rn7-chr1-Rpp30-P	ccaaagacacagattaa        	49.0	35.3	17	9.0	2.0	4.0	2.0	180400.0                         	5180.5                 	5.5 	28.7
rn7-chrM-Nd1-F  	aacggaaaatcctaggctacataca	64.7	40.0	25	11.0	4.0	6.0	4.0	257800.0                         	7652.1                 	3.9 	29.7
rn7-chrM-Nd1-R  	catatgggcctacgatgttg     	63.1	50.0	20	4.0	6.0	4.0	6.0	191700.0                         	6148.1                 	5.2 	32.1
rn7-chrM-Nd1-P  	ctacgcaaaggcc            	51.4	61.5	13	4.0	1.0	5.0	3.0	123200.0                         	3928.6                 	8.1 	31.9
rn7-chrM-Nd2-F  	ccaccattctcgcaatttca     	66.2	45.0	20	5.0	6.0	8.0	1.0	180900.0                         	5971.9                 	5.5 	33.0
rn7-chrM-Nd2-R  	tcgtgtttgggtctggttaagtc  	66.3	47.8	23	2.0	10.0	3.0	8.0	213900.0                         	7107.7                 	4.7 	33.2
rn7-chrM-Nd2-P  	cagtctttgttggcgcct       	64.5	55.6	18	1.0	7.0	5.0	5.0	155900.0                         	5472.6                 	6.4 	35.1
rn7-chrM-Nd4-F  	tcgcccacggcttaacc        	67.6	64.7	17	3.0	3.0	8.0	3.0	149300.0                         	5091.3                 	6.7 	34.1
rn7-chrM-Nd4-R  	tcgttcgtagttggtgtttgct   	65.9	45.5	22	1.0	11.0	3.0	7.0	199000.0                         	6769.5                 	5.0 	34.0
rn7-chrM-Nd4-P  	cctcactcttattctgc        	50.6	47.1	17	2.0	7.0	7.0	1.0	142600.0                         	5047.3                 	7.0 	35.4



```

Note that these primers result in predicted cross primer dimers. 
```
                Self-Dimers:

1 dimer for: rn7-chrM-Nd2-F
5-ccaccattctcgcaatttca->
             | |||| | 
          <-actttaacgctcttaccacc-5

1 dimer for: rn7-chrM-Nd2-P
5-cagtctttgttggcgcct->
             |||||| 
          <-tccgcggttgtttctgac-5

1 dimer for: rn7-chrM-Nd4-F
5-tcgcccacggcttaacc->
           | |||| |
         <-ccaattcggcacccgct-5


               Cross Primer Dimers:

rn7-chr1-Rpp30-P with rn7-chrM-Nd4-P
rn7-chr1-Rpp30-P
5-ccaaagacacagattaa->
           |||| |||
        <-cgtcttattctcactcc-5

rn7-chrM-Nd1-F with rn7-chrM-Nd1-R
rn7-chrM-Nd1-F
5-aacggaaaatcctaggctacataca->
       || ||| |||||       
    <-gttgtagcatccgggtatac-5

rn7-chrM-Nd1-F with rn7-chrM-Nd2-F
rn7-chrM-Nd1-F
5-aacggaaaatcctaggctacataca->
      |||| | | ||  |     
   <-actttaacgctcttaccacc-5

rn7-chrM-Nd1-P with rn7-chrM-Nd2-P
rn7-chrM-Nd1-P
5-cagtctttgttggcgcct->
    | |||||     
 <-ccggaaacgcatc-5

rn7-chrM-Nd2-R with rn7-chrM-Nd4-F
rn7-chrM-Nd2-R
5-tcgtgtttgggtctggttaagtc->
                ||||||| |
              <-ccaattcggcacccgct-5

```

7. Check NCBI primer blast using the selected F and R primers for off-target amplification in rat genome (with an amplicon size in the same range). If there is an off-target make sure that the amplicon length is too long for 15sec dPCR extension.

```
	Sequence (5'->3')	Template strand	Length	Start	Stop	Tm	GC%	Self complementarity	Self 3' complementarity
Forward primer	TCGCCCACGGCTTAACC	Plus	17	950	966	59.68	64.71	4.00	4.00
Reverse primer	TCGTTCGTAGTTGGTGTTTGCT	Minus	22	1008	987	60.74	45.45	2.00	0.00
Product length	59
Products on potentially unintended templates
>NC_086019.1 Rattus norvegicus strain BN/NHsdMcwi chromosome 1, GRCr8

product length = 2257
Features flanking this product:
   12249 bp at 5' side: zinc finger protein 790
   6691 bp at 3' side: zinc finger protein ozf-like

Reverse primer  1         TCGTTCGTAGTTGGTGTTTGCT  22
Template        94193425  .G.....C.T............  94193404

Reverse primer  1         TCGTTCGTAGTTGGTGTTTGCT  22
Template        94191169  .GA...AG.T............  94191190

>NC_086026.1 Rattus norvegicus strain BN/NHsdMcwi chromosome 8, GRCr8

product length = 1354
Features associated with this product:
   transcriptional coactivator yap1 1

   transcriptional coactivator yap1 isoform x1

Reverse primer  1         TCGTTCGTAGTTGGTGTTTGCT  22
Template        13402704  .TC...CC...G..........  13402683

Reverse primer  1         TCGTTCGTAGTTGGTGTTTGCT  22
Template        13401351  .TC...CC...G..........  13401372
```
   

