This design is based on rat_chr1_RPP30.md.

Using CHASM2, we found that the end of the long arm of chr1 may be prone to copy number alterations. Therefore, we targeted regions closer to the other end of chr1 with low CNA susceptibility.

Our target region is chr1:55Mbp-60Mbp (1q12). In detail, it is chr1:54992234-59991527.

1. Examine the region using the UCSC Genome Browser. Note that RAGE24 data is based on **GRCr8**. Avoid SNVs as they can affect probe binding. Repetitive elements in the RepeatMasker track should also be avoided to prevent probes from binding to multiple genome regions. A good region is chr1:55,022,086-55,026,842 [link](https://genome.ucsc.edu/cgi-bin/hgTracks?db=hub_5060498_GCF_036323735.1&lastVirtModeType=default&lastVirtModeExtraState=&virtModeType=default&virtMode=0&nonVirtPosition=&position=chr1%3A55022086%2D55026842&hgsid=2446126091_3ytDtsDlhanpnhAayOlaBaBTdkKh)
   
2. We can extract the nucleotide sequence of chr1:55,023,760-55,025,168 by clicking "View"-->"DNA" in the UCSC Genome Browser. This is a region from Ccr6 gene.
    ```
    >GCF_036323735.1_dna range=NC_086019.1:55023760-55025168 5'pad=0 3'pad=0 strand=+ repeatMasking=N
    TGTCATTTTCTACAGTCTCACTGGTCTGCCTGGAGATGTAGCTTTCTGAG
    TAAACCCGGGCACAGAAGAAGGTAGGCACCTTGCTCTTCCTCCTCATACA
    CCACACATCCTTCATGATCTTCATGAAGTAGCTTCTGAATTTCTGTCCAA
    TGAAGGCATACAACACGGGGTTGAGACAGCAGTGCAGGAAAGCCAGGACC
    TCAGCCACATTCCTGGCGTAGGCGAGGGCTTTCTCGGCGCTGCAGCTGCG
    GCCCATTTTGCCCGTGTTGGCTGCAGTCACGAGGAGGACCATGTTGTGAG
    GGATCTGACAAGCCAGGAACACGAGAACCACAGCAATCACGACTCGGATG
    GCTCTGTGCCTCTTGGAATTCTGGGCCTGCACCAAGGTCTTGATGATGAA
    CAGGTAACAGAACACCATAAACAGCAAAGGGATGAAGAAGCCAAAGAGCA
    GCTCGAGTCCCATGCCCAGCAGTTTCCACGTGATGGGCTCCGAGACGAGC
    TTGTACTGAGGCTCGCAGACATCACGGCCCTGCAGCTTGTATTGCTTGTT
    GAAGAAGAATGTGGGGCTTGAGATGATGATGGAAACGAACCACACCGTCA
    GACAGATGACCTTACTGTGCGTCAGTGTTCTGGAGCGTACCCGGAAAGAT
    TTGGTCGCCTGGACGATGGCAATGTACCGGTCCATGCTGATACAGGCCAG
    GAGCAGCATCCCACAGTTAAAGTTGACCGCATACGTGCCTTTCATCAGTT
    TACACATCGTGTTGCCAAAGATCCAAGTGTCAGTGGCATGAGTAACTGCC
    CAGAATGGTAGGGTGAGGACAAAGAGTATGTCTGTGATGGCCATGTTCAA
    TAGGTAGACGTCAGTCATGGACCTGGCTTTCTTGTAGAAGGCAAAGGTTA
    TCACCACCATAATATTGCCAAGGAGGCCAAAGACACAGATTAAGGAGTAG
    GCGATTGGCACGAACACCTTGGTGAAGTCTCTGACCTCTTGCAGAGAGCA
    TGGCTCGGTCTCTGGAAACATAGAGTAATCTGAGCCAGTATAATCTTCCA
    TTCCGTAGTTGGCCTCGGTGAAATTCATCGTTTCCTGGAAGGCAATAGAA
    ATCGTGACGGCACATTTCCAAGCAACCATACATAGCCAAGCTCATGGTCC
    CTGCCAAAATAAAGTAGATGCTCGCTGCAGGTAGGAATGGTTCTCTGAGT
    GGGCGGGAGAGCCAGCTCTGATGTGGAAAGTGAAGCGGGCAGTTCAGCCA
    CAAGCTCGCTAGCACAGATGTTAGGAGAGCAGAGGTGAAGCTAGGGAGGA
    GGAAAGTCAAGGTGTGCAGTCATGCTGTGTTCTGGAACATTCTACCCCAT
    CAGAACACACCGCAATGGACGTTGCTTGATGTGAAAACATCCACTTGACA
    GGCTTTTCC
    ```

3. We will now check this sequence with BLAT to ensure that it's specific to our target region. Note how it has a very high score for the entire length of the sequence on the target chromosome.
    ```
    ACTIONS                 QUERY               SCORE START   END QSIZE IDENTITY  CHROM        STRAND  START       END   SPAN
    ------------------------------------------------------------------------------------------------------------------------------
    browser new tab

    details GCF_036323735.1_dna  1177     1  1177  1177   100.0%  chr1         +    55023850  55025026   1177
    browser new tab

    details GCF_036323735.1_dna    47   567   685  1177    88.4%  chr10        +    84595054  84595172    119
    browser new tab

    details GCF_036323735.1_dna    31    27   123  1177    97.0%  chr2         +    48261321  48261602    282
    browser new tab

    details GCF_036323735.1_dna    26   715   743  1177    85.2%  chr3         -   157990519 157990545     27
    browser new tab

    details GCF_036323735.1_dna    22    98   119  1177   100.0%  chr3         -   110972081 110972102     22
    browser new tab

    details GCF_036323735.1_dna    21    28    48  1177   100.0%  chr2         -    43585805  43585825     21
    browser new tab

    details GCF_036323735.1_dna    20    82   101  1177   100.0%  chr2         +   191736443 191736462     20
    browser new tab

    details GCF_036323735.1_dna    20  1054  1073  1177   100.0%  chr1         +   239313935 239313954     20
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
    Max Primer Length	23
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
- chr1_Ccr6_F: TCATGGACCTGGCTTTCTTGT
- chr1_Ccr6_R: TCGTGCCAATCGCCTACTC
- chr1_Ccr6_P: CCAAAGACACAGATTAA

6. 
    Check that the amplicon length is between 50-150 and that the melting temperatures are comparable to other primers in the multiplex design. Also check for self-dimers and cross primer dimers with other primers in the multiplex reaction using the Multiple Primer Analyzer: [link](https://www.thermofisher.com/us/en/home/brands/thermo-scientific/molecular-biology/molecular-biology-learning-center/molecular-biology-resource-library/thermo-scientific-web-tools/multiple-primer-analyzer.html) . Self-dimers are less problematic if not predicted by Primer Express. 
   ```
  Name  	Sequence                	Tm°C	CG%	nt	A	T	C	G	Extinction coefficient(l/(mol·cm)	Molecular weight(g/mol)	nmol	µg/OD260
chrXF 	ccagcagccaggacagtagaa   	67.0	57.1	21	8.0	1.0	6.0	6.0	215700.0                         	6458.3                 	4.6 	29.9
chrXR 	ctgaccaaacctggctggat    	66.7	55.0	20	5.0	4.0	6.0	5.0	186600.0                         	6102.0                 	5.4 	32.7
chrXP 	agtagtgtgaggaccaact     	54.0	47.4	19	6.0	4.0	3.0	6.0	194900.0                         	5876.9                 	5.1 	30.2
chr10F	gccaaagtggctctgtcgtaa   	66.7	52.4	21	5.0	5.0	5.0	6.0	202400.0                         	6446.3                 	4.9 	31.8
chr10R	tgtccaagagcactggagttca  	67.5	50.0	22	6.0	5.0	5.0	6.0	216000.0                         	6759.5                 	4.6 	31.3
chr10P	tttgacccaattttctg       	54.8	35.3	17	3.0	8.0	4.0	2.0	152200.0                         	5126.4                 	6.6 	33.7
chr12F	ggagaccgacagcgatttga    	67.9	55.0	20	6.0	3.0	4.0	7.0	203100.0                         	6191.1                 	4.9 	30.5
chr12R	tcccaaagaccagtgacacagt  	66.2	50.0	22	8.0	3.0	7.0	4.0	217900.0                         	6697.4                 	4.6 	30.7
chr12P	cactgcttagtgttccca      	57.8	50.0	18	3.0	6.0	6.0	3.0	162500.0                         	5425.6                 	6.2 	33.4
chr1F 	tcatggacctggctttcttgt   	66.1	47.6	21	2.0	9.0	5.0	5.0	185000.0                         	6394.2                 	5.4 	34.6
chr1R 	tcgtgccaatcgcctactc     	66.7	57.9	19	3.0	5.0	8.0	3.0	167100.0                         	5699.7                 	6.0 	34.1
chr1P 	ccaaagacacagattaa       	49.0	35.3	17	9.0	2.0	4.0	2.0	180400.0                         	5180.5                 	5.5 	28.7
chrYF 	tgctaccaaagttgcagttatcct	65.0	41.7	24	6.0	8.0	6.0	4.0	225600.0                         	7302.8                 	4.4 	32.4
chrYR 	aggtgataccaaaaaccaaaaggt	64.6	37.5	24	12.0	3.0	4.0	5.0	255500.0                         	7411.9                 	3.9 	29.0
chrYP 	agatttatgtgcctcagggt    	60.5	45.0	20	4.0	7.0	3.0	6.0	194200.0                         	6163.1                 	5.1 	31.7

   ```

   ```
                Self-Dimers:


               Cross Primer Dimers:

   ```

7. Check NCBI primer blast using the selected F and R primers for off-target amplification in rat genome (with an amplicon size in the same range). There might be an off-target but the length is too long for 15sec dPCR extension.
   ```
   Primer pair 1
      Sequence (5'->3')	Length	Tm	GC%	Self complementarity	Self 3' complementarity
   Forward primer	TCATGGACCTGGCTTTCTTGT	21	59.57	47.62	4.00	0.00
   Reverse primer	TCGTGCCAATCGCCTACTC	19	59.86	57.89	3.00	0.00
   Products on target templates
   >NC_086019.1 Rattus norvegicus strain BN/NHsdMcwi chromosome 1, GRCr8


   product length = 99
   Features associated with this product:
      c-c chemokine receptor type 6 isoform x1

      c-c chemokine receptor type 6 isoform x1

   Forward primer  1         TCATGGACCTGGCTTTCTTGT  21
   Template        55024624  .....................  55024644

   Reverse primer  1         TCGTGCCAATCGCCTACTC  19
   Template        55024722  ...................  55024704

   >NC_086031.1 Rattus norvegicus strain BN/NHsdMcwi chromosome 13, GRCr8


   product length = 3208
   Features associated with this product:
      proton-transporting v-type atpase complex assembly regula...

      proton-transporting v-type atpase complex assembly regula...

   Forward primer  1         TCATGGACCTGGCTTTCTTGT  21
   Template        50026141  C.C...T......C.......  50026161

   Forward primer  1         TCATGGACCTGGCTTTCTTGT  21
   Template        50029348  C..GT.......T.......A  50029328

   >NC_086033.1 Rattus norvegicus strain BN/NHsdMcwi chromosome 15, GRCr8


   product length = 1904
   Features associated with this product:
      disks large-associated protein 5

      disks large-associated protein 5 isoform x1

   Forward primer  1         TCATGGACCTGGCTTTCTTGT  21
   Template        23137295  ..T..TGA.............  23137315

   Forward primer  1         TCATGGACCTGGCTTTCTTGT  21
   Template        23139198  .GCC.C...C...........  23139178

   ```
   
