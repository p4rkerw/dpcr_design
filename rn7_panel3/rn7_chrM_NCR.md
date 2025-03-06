Our target region is rn7 chrM non-coding region (NCR). Published (PMID:30061621) forward (TCCCGACACAAAATCTTTCCT) and reverse (TCCCGACACAAAATCTTTCCT) primers for NCR1 were used to identify the target which was located at chrM:16239-16281. This region was padded up- and downstream to retrieve the sequence below.

2. We can extract the nucleotide sequence by clicking "View"-->"DNA" in the UCSC Genome Browser. 

```
>rn7_dna range=chrM:16039-16313 5'pad=200 3'pad=54 strand=+ repeatMasking=N
TTTGTAAGACATAAATATTTATAAATACTGAAAAATCTGTCAACAAACCC
CCCCACCCCCTACACCTGAAACTTCAATGCCAAACCCCAAAAACATTAAA
GCAAGAATTAAATAAAACAAAAAGCTACTTAATTCTTAAAAGGCTTCTCC
ATTCTAGTAGACCACAAAATTTTAACTTAAATCTTAGCATTGGTAAAATT
TCCCGACACAAAATCTTTCCTTCTAACTAAACCCTCTTTACTTGCCTACC
CTCAGAAAATTCCACATACACCAAA
```

3. We will now check this sequence with BLAT to ensure that it's specific to our target region. Note how it has a very high score for the entire length of the sequence on the target chromosome. 

```
   ACTIONS                 QUERY   SCORE START   END QSIZE IDENTITY  CHROM  STRAND  START       END   SPAN
------------------------------------------------------------------------------------------------------------
browser new tab details YourSeq   275     1   275   275   100.0%  chrM   +       16039     16313    275
browser new tab details YourSeq    25    46    75   275    82.2%  chr6   +    10231454  10231481     28
browser new tab details YourSeq    24    78   108   275    77.0%  chr10  -    19129190  19129216     27
browser new tab details YourSeq    22    23    45   275   100.0%  chr3   -    26205746  26205770     25
browser new tab details YourSeq    22    34    55   275   100.0%  chr2   +   201306753 201306774     22
browser new tab details YourSeq    20    73    92   275   100.0%  chr4   -   177701347 177701366     20
browser new tab details YourSeq    20     7    26   275   100.0%  chr17  -    56669741  56669760     20
browser new tab details YourSeq    20     9    28   275   100.0%  chr2   +   132332381 132332400     20
browser new tab details YourSeq    20    46    65   275   100.0%  chr18  +    26382165  26382184     20
browser new tab details YourSeq    20    91   110   275   100.0%  chr16  +    81144612  81144631     20
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
   
- rn7_chrM_NCR_F  CACCTGAAACTTCAATGCCAAA
- rn7_chrM_NCR_R  GGTCTACTAGAATGGAGAAGCCTTTTAA
- rn7_chrM_NCR_P  CCCAAAAACATTAAAGCAAGAA

6. Check that the amplicon length is between 50-150 and that the melting temperatures are comparable to other primers in the multiplex design. Also check for self-dimers and cross primer dimers with other primers in the multiplex reaction using the Multiple Primer Analyzer: [link](https://www.thermofisher.com/us/en/home/brands/thermo-scientific/molecular-biology/molecular-biology-learning-center/molecular-biology-resource-library/thermo-scientific-web-tools/multiple-primer-analyzer.html) . Self-dimers are less problematic if not predicted by Primer Express. 
   
```
Name            	Sequence                    	Tm°C	CG%	nt	A	T	C	G	Extinction coefficient(l/(mol·cm)	Molecular weight(g/mol)	nmol	µg/OD260
rn7-chr1-Rpp30-F	tcatggacctggctttcttgt       	66.1	47.6	21	2.0	9.0	5.0	5.0	185000.0                         	6394.2                 	5.4 	34.6
rn7-chr1-Rpp30-R	tcgtgccaatcgcctactc         	66.7	57.9	19	3.0	5.0	8.0	3.0	167100.0                         	5699.7                 	6.0 	34.1
rn7-chr1-Rpp30-P	ccaaagacacagattaa           	49.0	35.3	17	9.0	2.0	4.0	2.0	180400.0                         	5180.5                 	5.5 	28.7
rn7-chrM-Nd1-F  	aacggaaaatcctaggctacataca   	64.7	40.0	25	11.0	4.0	6.0	4.0	257800.0                         	7652.1                 	3.9 	29.7
rn7-chrM-Nd1-R  	catatgggcctacgatgttg        	63.1	50.0	20	4.0	6.0	4.0	6.0	191700.0                         	6148.1                 	5.2 	32.1
rn7-chrM-Nd1-P  	ctacgcaaaggcc               	51.4	61.5	13	4.0	1.0	5.0	3.0	123200.0                         	3928.6                 	8.1 	31.9
rn7-chrM-Nd2-F  	ccaccattctcgcaatttca        	66.2	45.0	20	5.0	6.0	8.0	1.0	180900.0                         	5971.9                 	5.5 	33.0
rn7-chrM-Nd2-R  	tcgtgtttgggtctggttaagtc     	66.3	47.8	23	2.0	10.0	3.0	8.0	213900.0                         	7107.7                 	4.7 	33.2
rn7-chrM-Nd2-P  	cagtctttgttggcgcct          	64.5	55.6	18	1.0	7.0	5.0	5.0	155900.0                         	5472.6                 	6.4 	35.1
rn7-chrM-Nd4-F  	tcgcccacggcttaacc           	67.6	64.7	17	3.0	3.0	8.0	3.0	149300.0                         	5091.3                 	6.7 	34.1
rn7-chrM-Nd4-R  	tcgttcgtagttggtgtttgct      	65.9	45.5	22	1.0	11.0	3.0	7.0	199000.0                         	6769.5                 	5.0 	34.0
rn7-chrM-Nd4-P  	cctcactcttattctgc           	50.6	47.1	17	2.0	7.0	7.0	1.0	142600.0                         	5047.3                 	7.0 	35.4
rn7-chrM-NCR-F  	cacctgaaacttcaatgccaaa      	66.2	40.9	22	9.0	4.0	7.0	2.0	213800.0                         	6656.4                 	4.7 	31.1
rn7-chrM-NCR-R  	ggtctactagaatggagaagccttttaa	64.8	39.3	28	9.0	8.0	4.0	7.0	282200.0                         	8651.7                 	3.5 	30.7
rn7-chrM-NCR-P  	cccaaaaacattaaagcaagaa      	62.1	31.8	22	13.0	2.0	5.0	2.0	234200.0                         	6722.5                 	4.3 	28.7



```

Note that these primers result in predicted primer dimers. 
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

rn7-chr1-Rpp30-F with rn7-chrM-NCR-R
rn7-chr1-Rpp30-F
5-ggtctactagaatggagaagccttttaa->
       || |||| |      || |  
     <-tgttctttcggtccaggtact-5

rn7-chr1-Rpp30-F with rn7-chrM-NCR-P
rn7-chr1-Rpp30-F
5-cccaaaaacattaaagcaagaa->
                  ||||||
               <-tgttctttcggtccaggtact-5

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

rn7-chrM-Nd1-P with rn7-chrM-NCR-R
rn7-chrM-Nd1-P
5-ggtctactagaatggagaagccttttaa->
                     ||||||   
                  <-ccggaaacgcatc-5

rn7-chrM-Nd2-F with rn7-chrM-NCR-F
rn7-chrM-Nd2-F
5-cacctgaaacttcaatgccaaa->
      ||||| | | |       
    <-actttaacgctcttaccacc-5

rn7-chrM-Nd2-F with rn7-chrM-NCR-R
rn7-chrM-Nd2-F
  5-ggtctactagaatggagaagccttttaa->
        | | ||||||| | 
<-actttaacgctcttaccacc-5

rn7-chrM-Nd2-R with rn7-chrM-Nd4-F
rn7-chrM-Nd2-R
5-tcgtgtttgggtctggttaagtc->
                ||||||| |
              <-ccaattcggcacccgct-5



```

7. Check NCBI primer blast using the selected F and R primers for off-target amplification in rat genome (with an amplicon size in the same range). If there is an off-target make sure that the amplicon length is too long for 15sec dPCR extension.

```

Sequence (5'->3')	Template strand	Length	Start	Stop	Tm	GC%	Self complementarity	Self 3' complementarity
Forward primer	CACCTGAAACTTCAATGCCAAA	Plus	22	63	84	57.94	40.91	6.00	0.00
Reverse primer	GGTCTACTAGAATGGAGAAGCCTTTTAA	Minus	28	163	136	60.59	39.29	7.00	4.00
Product length	101
Products on potentially unintended templates
>NC_086020.1 Rattus norvegicus strain BN/NHsdMcwi chromosome 2, GRCr8

product length = 2046
Features flanking this product:
   338704 bp at 5' side: large ribosomal subunit protein el6-like
   244345 bp at 3' side: cadherin-10 precursor

Forward primer  1         CACCTGAAACTTCAATGCCAAA  22
Template        70197855  .C............T.T..T..  70197876

Forward primer  1         CACCTGAAACTTCAATGCCAAA  22
Template        70199900  T..T...T.......A...C..  70199879
```
   

