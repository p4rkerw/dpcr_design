This design is based on rat_chr1_RPP30.md.

Our target region is rn7 Nd1 gene chrM:2,740-3,694 

1. Examine the region using the UCSC Genome Browser. Note that RAGE24 data is based on **rn7**. Avoid SNVs as they can affect probe binding. Repetitive elements in the RepeatMasker track should also be avoided to prevent probes from binding to multiple genome regions. 
   
2. We can extract the nucleotide sequence of chrM:2,740-3,694 by clicking "View"-->"DNA" in the UCSC Genome Browser. 
    ```
>rn7_dna range=chrM:2740-3694 5'pad=0 3'pad=0 strand=+ repeatMasking=N
GTGTACTTTATTAATATCCTAACACTCCTAATCCCAATCTTAATTGCCAT
GGCCTTCCTCACCCTAGTAGAACGGAAAATCCTAGGCTACATACAACTAC
GCAAAGGCCCCAACATCGTAGGCCCATATGGTATTCTACAACCATTTGCA
GATGCCATAAAACTATTCATAAAAGAACCCATACGCCCCCTAACCACCTC
AATATCACTATTTATTATCGCCCCAACCCTCTCCCTTACACTAGCTCTAA
GCCTATGAATCCCCTTACCAATACCTCACCCCCTTATCAACCTCAACCTA
GGCATACTATTTATTCTAGCCACATCAAGTCTTTCAGTCTACTCCATTCT
ATGATCAGGATGAGCATCAAATTCAAAATACTCCCTATTCGGAGCCCTAC
GAGCCGTTGCCCAAACCATCTCTTACGAAGTCACAATAGCCATTATCCTC
TTATCCGTCCTCCTAATAAGCGGCTCCTTCTCCCTACAAATACTTATCAC
TACACAAGAACATATCTGACTATTAATCCCCGCCTGACCAATAGCCATAA
TATGATACATTTCAACCCTAGCAGAAACAAATCGAGCTCCCTTCGACTTA
ACAGAAGGAGAATCAGAATTAGTCTCAGGCTTTAACGTCGAATACGCCGC
AGGACCATTCGCCCTATTCTTCATAGCCGAGTACACCAATATTATCCTAA
TAAACGCCCTAACATCAATTGTATTCCTAGGCCCCTTATATCACATCAAT
TACCCTGAATTATACTCAACCAGCTTCATAACAGAAACACTACTTCTATC
CACAACTTTCCTATGAATCCGAGCATCCTACCCCCGTTTTCGATATGACC
AACTAATGCACCTCCTATGAAAAAATTTCCTCCCACTAACACTAGCATTC
TGCATATGATACATTTCCCTGCCAATTTTCCTAGCAGGAATTCCACCCTA
CACAT
    ```

3. We will now check this sequence with BLAT to ensure that it's specific to our target region. Note how it has a very high score for the entire length of the sequence on the target chromosome. 
    ```
   ACTIONS                 QUERY   SCORE START   END QSIZE IDENTITY  CHROM  STRAND  START       END   SPAN
------------------------------------------------------------------------------------------------------------
browser new tab details YourSeq   955     1   955   955   100.0%  chrM   +        2740      3694    955
browser new tab details YourSeq    99   611   711   955    99.1%  chr2   +   107518868 107518968    101
browser new tab details YourSeq    62    80   379   955    88.8%  chr5   +    63331786  63332096    311
browser new tab details YourSeq    37   139   181   955    93.1%  chr3   +   163233250 163233292     43
browser new tab details YourSeq    23   332   354   955   100.0%  chr2   +   152322504 152322526     23
browser new tab details YourSeq    22   299   321   955   100.0%  chr16  +    32173165  32173191     27
browser new tab details YourSeq    21   154   176   955    95.7%  chr18  +    67296859  67296881     23
browser new tab details YourSeq    20   150   169   955   100.0%  chr12  -    39739238  39739257     20
browser new tab details YourSeq    20   165   184   955   100.0%  chr11  -    20482848  20482867     20
browser new tab details YourSeq    20   893   912   955   100.0%  chr1   -     8661609   8661628     20
browser new tab details YourSeq    20   474   493   955   100.0%  chr18  +    78389454  78389473     20
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
   
5. Below is the top primer / probe combination for our target region (5'-3').
rn7_chrM_Nd1_F  AACGGAAAATCCTAGGCTACATACA
rn7_chrM_Nd1_R  CCATATGGGCCTACGATGTTG
rn7_chrM_Nd1_P  CTACGCAAAGGCC

6. 
    Check that the amplicon length is between 50-150 and that the melting temperatures are comparable to other primers in the multiplex design. Also check for self-dimers and cross primer dimers with other primers in the multiplex reaction using the Multiple Primer Analyzer: [link](https://www.thermofisher.com/us/en/home/brands/thermo-scientific/molecular-biology/molecular-biology-learning-center/molecular-biology-resource-library/thermo-scientific-web-tools/multiple-primer-analyzer.html) . Self-dimers are less problematic if not predicted by Primer Express. 
   
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
   Primer pair 1
Sequence (5'->3')	Template strand	Length	Start	Stop	Tm	GC%	Self complementarity	Self 3' complementarity
Forward primer	AACGGAAAATCCTAGGCTACATACA	Plus	25	71	95	59.87	40.00	6.00	0.00
Reverse primer	CATATGGGCCTACGATGTTG	Minus	20	130	111	56.07	50.00	6.00	2.00

  
   ```
   

