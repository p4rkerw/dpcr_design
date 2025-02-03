This design is based on rat_chr1_RPP30.md.

Using CHASM2, we found that the end of the long arm of chr1 may be prone to copy number alterations. Therefore, we targeted regions closer to the other end of chr1 with low CNA susceptibility.

Our target region is chr1:55Mbp-60Mbp (1q12). In detail, it is chr1:54992234-59991527.

1. Examine the region using the UCSC Genome Browser. Note that RAGE24 data is based on **GRCr8**. Avoid SNVs as they can affect probe binding. Repetitive elements in the RepeatMasker track should also be avoided to prevent probes from binding to multiple genome regions. A good region is chr1:50,606,832-50,608,946 [link](https://genome.ucsc.edu/cgi-bin/hgTracks?db=hub_4703362_GCA_036323735.1&lastVirtModeType=default&lastVirtModeExtraState=&virtModeType=default&virtMode=0&nonVirtPosition=&position=chr1%3A50606832%2D50608946&hgsid=2444174923_PiJw9dIP3d4akm2qzaWVQbeBfj3A)
   
2. We can extract the nucleotide sequence of chr1:55,940,413-55,942,181 by clicking "View"-->"DNA" in the UCSC Genome Browser. 
    ```
    >GCA_036323735.1_dna range=CM070391.1:50606832-50608946 5'pad=0 3'pad=0 strand=+ repeatMasking=N
    TCCGCCAGGCGCCCTGAGCTTACAGGCCCTGCTGCAGTTCGGGGCTGTGA
    GTCGGGGGACCTAGGTGAGTGCCTGCTATATCCTTCTACAGCCTTCCCTC
    TCCTGTCCGCACCGTGCCAGGGCTACATGGGGACATGTCCCTGCACGTGA
    GCCTGCTGAGTCAGCTGCGCTGCATGACTGCTCTGCTCTCTGCTCCTTCT
    GCACCCCAAGGCTCTTGCAAGGGAGCATGGAGTACACAGGTCTCACCAGT
    GTCCCAGAGTAGAAATCTCACATGCCCTTTCTCCACACCCCTTTGTGTAG
    GTACTTTATCAATCTGTGCCAAAGAGTATATAAAGGTCCCCTGGACTGCT
    CTGAGAGAGCCAGCATTTGCAAGAAGAGTGCCACTGGTCAAGTCCAGGTT
    TTGGGGCTTGTTCATACTCAAAAACTGGAAGTCATAGGTAAGGCTCTGAG
    GTATTTGTCCTTGGTTCAGTTGCTGCATCAAGATTGAGGCTGTCCCTGGC
    ATGCCAGAGAAAGTGTCTGAACTTCCAGGGCTGCTCCCGTGACTAGTTGA
    AGCATTTCTACCCACTTCCTGAAACATGAAGTACATGCTATTTTGTACAC
    TCTGAGGCACAAGTAGCCTGTTTAAAGCACCTTTGGTGATGGTGTTCTGG
    CTGCACATTGTCTTCTAAATGTATGTCTACACATGTCTAAGAAAGCCACA
    GTTGCGGGGGACGGGGTACAGACTACCATGTATTTCCTCAAGCTCTTGGA
    CAGTAATCGTGACACTGCAGTAGTTTAAATGCGAGGTTGCCAAGAGGAAG
    GTATCTGTTGTTAAAGGACAGGCATACTTTCCCAGCTGAGGGAAAACACA
    GTGGCAAGGCTGTGTTGGATGTTGGACATTTTGCTCTGCCTCTAAGGCTA
    GAGAAGGGTTTGACTGTGCCGATTGAAGTACAAGGTGACATGTGTACTAA
    AATGGAAAGGGAATTCTGAGGGGATGTGGCCTTTAATCACCAACTCAGGT
    TCTAAGACAGTGGCTCCCTTTGAGAATTAAATTCCCAACACATGAACCAG
    ATGGGCAAACTCACATCTTAGGGATCCTCTGTTCCCGAAAGTCCAGGCTA
    CCATGCAGTTGGACGCTAGTCATCTAGGTGTGGCCATGGAGGCTTAGCAT
    TCCTGAGGATCCAGGAAGCTGGTAGGAAGCTCATGGTCTTGCTGTTCCCT
    TGGTAGTGGTGGTATAGGTGTAAGGGCCAGTGCCTGCTATTGAGTATGGA
    GGACACCTTTAGAGAGCTGATACTTGCCTTTGCAGTAGATTTTCAAGCCC
    TGACATTGTTCTGCAGCGCACTAGAAATAACGCCAGCTCGTTGTCTCCTG
    TTGCAGATGAAACAGTCCTTGTCACTTACTCAAAAGGCCATTCTTGTGGT
    GGGAATAAGACTGCATCCTCAGTGATCGAGTTGACCTGTGCAAAGACTGT
    GGGCAGGCCTGCATTCAAGAGGTGAGCCGCTGGCCAGCACACTGTGGCTC
    TTTGCCTCCCCCATTTCCACATGGGAGTTGGGAATGTGCACACACAGACG
    AGAGGGTGTTTGGGACCGCCACTGTCGCAGAAATGCTCACTGAGACTGAG
    GACTTAGAGGACAGATTGTCTTGTCCTATGCAGCATTTTCCCCATAGGAG
    ATGTCCCTACCTCCACTCCAGGGCTAAGGTACATCAAAACAGGGCCACCT
    CAGCTTTTTAACCTGGTTTGCCTTAAGAAGCACACTCCTGAACCAGCCTT
    GGAGCTGTTGATGCTTCACTGAGCAGCACAGAGCTGGCTGCTGTCCCTCA
    GTGTCAAGGTGGAGTTAAGGGGATGCTGCTTGCACCAACAACCACCTCTG
    GGGCCTACAGCAGGTGCTGGGCTTCCTAAGTGATTGCAGTGTCCCAGGCA
    GTTGTTGGGTGGTATTAGGGAGGATCGTGGCCAACAGGGGGAGCATGTGA
    GCTGCTCTTTTGGAAACTGCTTTGAAAAGGTCTTTCTTATTTCTGAGACT
    AAGGTACTACTTGTAAAAGTCTAGGTGCAGAATTCCCAGCTTTGTATGTT
    AAGACATTTTTATTGAGTTTGGTGGTTGAACCAAGGGCTTCATACAAACC
    AGGCAGATGCTCTGC
    ```

3. We will now check this sequence with BLAT to ensure that it's specific to our target region. Note how it has a very high score for the entire length of the sequence on the target chromosome. Also, we will avoid region 1804-2115 due to similarity between chr1 and chr7.
    ```
    ACTIONS                 QUERY   SCORE START   END QSIZE IDENTITY  CHROM       STRAND  START       END   SPAN
    -----------------------------------------------------------------------------------------------------------------
    browser new tab

    details YourSeq  2115     1  2115  2115   100.0%  chr1        +    50606832  50608946   2115
    browser new tab

    details YourSeq    30  1774  1804  2115   100.0%  chr7        -   101896450 101896664    215
    browser new tab

    details YourSeq    25  2079  2111  2115    87.9%  chr7        -    84695906  84695938     33
    browser new tab

    details YourSeq    24   177   201  2115   100.0%  chr1        +   165531565 165531597     33
    browser new tab

    details YourSeq    20   253   272  2115   100.0%  chr1        -     5416388   5416407     20
    ```

4. We will now use this sequence to design primers and probes in primer express using a TaqMan MGB quantification design. Start with the following parameters:

    ```
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
   
5. Below is the top primer / probe combination for our target region (5'-3').
- chr1_1q12_F: GGCCACCTCAGCTTTTTAACC
- chr1_1q12_R: AGTGAAGCATCAACAGCTCCAA
- chr1_1q12_P: CTTAAGAAGCACACTCCTGA

6. 
    Check that the amplicon length is between 50-150 and that the melting temperatures are comparable to other primers in the multiplex design. Also check for self-dimers and cross primer dimers with other primers in the multiplex reaction using the Multiple Primer Analyzer: [link](https://www.thermofisher.com/us/en/home/brands/thermo-scientific/molecular-biology/molecular-biology-learning-center/molecular-biology-resource-library/thermo-scientific-web-tools/multiple-primer-analyzer.html) . Self-dimers are less problematic if not predicted by Primer Express. 
    ```
    Name  	Sequence              	Tm°C	CG%	nt	A	T	C	G	Extinction coefficient(l/(mol·cm)	Molecular weight(g/mol)	nmol	µg/OD260
    chrXF 	ccagcagccaggacagtagaa 	67.0	57.1	21	8.0	1.0	6.0	6.0	215700.0                         	6458.3                 	4.6 	29.9
    chrXR 	ctgaccaaacctggctggat  	66.7	55.0	20	5.0	4.0	6.0	5.0	186600.0                         	6102.0                 	5.4 	32.7
    chrXP 	agtagtgtgaggaccaact   	54.0	47.4	19	6.0	4.0	3.0	6.0	194900.0                         	5876.9                 	5.1 	30.2
    chr10F	gccaaagtggctctgtcgtaa 	66.7	52.4	21	5.0	5.0	5.0	6.0	202400.0                         	6446.3                 	4.9 	31.8
    chr10R	tgtccaagagcactggagttca	67.5	50.0	22	6.0	5.0	5.0	6.0	216000.0                         	6759.5                 	4.6 	31.3
    chr10P	tttgacccaattttctg     	54.8	35.3	17	3.0	8.0	4.0	2.0	152200.0                         	5126.4                 	6.6 	33.7
    chr12F	ggagaccgacagcgatttga  	67.9	55.0	20	6.0	3.0	4.0	7.0	203100.0                         	6191.1                 	4.9 	30.5
    chr12R	tcccaaagaccagtgacacagt	66.2	50.0	22	8.0	3.0	7.0	4.0	217900.0                         	6697.4                 	4.6 	30.7
    chr12P	cactgcttagtgttccca    	57.8	50.0	18	3.0	6.0	6.0	3.0	162500.0                         	5425.6                 	6.2 	33.4
    chr1F 	ggccacctcagctttttaacc 	66.0	52.4	21	4.0	6.0	8.0	3.0	186400.0                         	6317.1                 	5.4 	33.9
    chr1R 	agtgaagcatcaacagctccaa	66.4	45.5	22	9.0	3.0	6.0	4.0	223300.0                         	6721.4                 	4.5 	30.1
    chr1P 	cttaagaagcacactcctga  	57.8	45.0	20	7.0	4.0	6.0	3.0	194500.0                         	6070.0                 	5.1 	31.2
    ```

    ```
                    Self-Dimers:


                Cross Primer Dimers:

    chr10R with chr1R
    chr10R
    5-tgtccaagagcactggagttca->
                ||||| |  
                <-aacctcgacaactacgaagtga-5

    chr10R with chr1P
    chr10R
    5-tgtccaagagcactggagttca->
                | |||||   
            <-agtcctcacacgaagaattc-5
    ```

7. Check NCBI primer blast using the selected F and R primers for off-target amplification in rat genome (with an amplicon size in the same range). There might be an off-target but the length is too long for 15sec dPCR extension.
```
Primer pair 1
	Sequence (5'->3')	Length	Tm	GC%	Self complementarity	Self 3' complementarity
Forward primer	GGCCACCTCAGCTTTTTAACC	21	59.73	52.38	4.00	1.00
Reverse primer	AGTGAAGCATCAACAGCTCCAA	22	60.49	45.45	6.00	0.00
Products on target templates
>NC_086019.1 Rattus norvegicus strain BN/NHsdMcwi chromosome 1, GRCr8


product length = 78
Features associated with this product:
   cation-independent mannose-6-phosphate receptor precursor

Forward primer  1         GGCCACCTCAGCTTTTTAACC  21
Template        50608524  .....................  50608544

Reverse primer  1         AGTGAAGCATCAACAGCTCCAA  22
Template        50608601  ......................  50608580

>NC_086039.1 Rattus norvegicus strain BN/NHsdMcwi chromosome X, GRCr8


product length = 1999
Features flanking this product:
   550779 bp at 5' side: e3 ubiquitin-protein ligase midline-1
   154694 bp at 3' side: holocytochrome c synthase

Forward primer  1         GGCCACCTCAGCTTTTTAACC  21
Template        28349369  T.T.....A..T........T  28349389

Forward primer  1         GGCCACCTCAGCTTTTTAACC  21
Template        28351367  T.T.....A..T........T  28351347
```
   
