dpcr primer and probe design for rat Eif2s3y on chrY

1. First examine the gene using the ucsc genome browser [link](https://genome.ucsc.edu/cgi-bin/hgTracks?db=rn7&lastVirtModeType=default&lastVirtModeExtraState=&virtModeType=default&virtMode=0&nonVirtPosition=&position=chrY%3A869689%2D889341&hgsid=1672094940_rcEIzCJRP025xOYa1v0XOMi7Ls8R). SNVs can affect probe binding and should be avoided if possible. There are also repetitive elements in the repeat masker track. It is difficult to design probes that involve repetitive elements because there is a risk they will bind multiple regions in the genome with the same element.

2. We will now extract the nucleotide sequence using the ucsc table browser [link](https://genome.ucsc.edu/cgi-bin/hgTables?hgsid=1672094940_rcEIzCJRP025xOYa1v0XOMi7Ls8R&clade=mammal&org=Rat&db=rn7&hgta_group=genes&hgta_track=gold&hgta_table=0&hgta_regionType=range&position=chrY%3A869%2C689-889%2C341&hgta_outputType=sequence&hgta_outFileName=). We will mask repeats with N. Below is the first chunk of sequence. Note how the sequence captures an area much larger than just the gene and is on the + strand. The get DNA in window is another tool that can retrieve sequences in target regions if you don't want all of the extra sequences. By convention, we design primers and probes using the + strand rather than the - strand.

```
>rn7_ncbiRefSeq_XM_039100656.1_9 range=chrY:872224-872980 5'pad=0 3'pad=0 strand=+ repeatMasking=N
GTAAAGTCAGAATTGATTTGGTTAAGTCAGTGTAAAGTCTAAGAACTTTT
AAAGCTCTTAAAGACTATAGGATGATATAAATGGAAAATTTCCAACGACT
TAACCAAAAATACTGATACTAATCATGAATACTCATCCATTTTTCCAGAA
GCATGGAACTTGGTTATTCGAATAGCCAAATTAATATCATAGCTTAGGGA
GTATGATCCTAATTGTGTAAAACAAATACTTCTTTATAGTACATTGTTAC
ATTTTTGCTTTTTTTTTTAAATCTTTGAATGTGATATTTTTTTGTTTTGT
TAATAGTTAATTTTTTTGTCTGTTGCTATGTTTAAGAAAGTACTTCAAAT
CAAAATTTATTAATTGAGACTATAAATATAAAGTTTCTTTTGTTCAGGAA
TTTGGCATCTTTGCCTTGTCTTTTTCAGGCTAAAGAACAGTATGAACACA
AACTTAAATTTTTGTACAGGCTAAGAACCCTTAATACTTAAGAATGTTTG
AATCACTTTGATAGACAGTAGATATAATTTAAATATGCTACCAAAGTTGC
AGTTATCCTAAGATTTATGTGCCTCAGGGTAAGTTTTTAAGACCTTTTGG
TTTTTGGTATCACCTCTGCTTCTAGTAAATTTAGTGTCTAGTGCTTCTGT
CTTGAGGCATTATATCCAACATCATGAGTAAAACAANNNNNNNNNNNNNN
NNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNNATC
ATTTTAG
```

Extract non-repetitive sequence
```
GTAAAGTCAGAATTGATTTGGTTAAGTCAGTGTAAAGTCTAAGAACTTTT
AAAGCTCTTAAAGACTATAGGATGATATAAATGGAAAATTTCCAACGACT
TAACCAAAAATACTGATACTAATCATGAATACTCATCCATTTTTCCAGAA
GCATGGAACTTGGTTATTCGAATAGCCAAATTAATATCATAGCTTAGGGA
GTATGATCCTAATTGTGTAAAACAAATACTTCTTTATAGTACATTGTTAC
ATTTTTGCTTTTTTTTTTAAATCTTTGAATGTGATATTTTTTTGTTTTGT
TAATAGTTAATTTTTTTGTCTGTTGCTATGTTTAAGAAAGTACTTCAAAT
CAAAATTTATTAATTGAGACTATAAATATAAAGTTTCTTTTGTTCAGGAA
TTTGGCATCTTTGCCTTGTCTTTTTCAGGCTAAAGAACAGTATGAACACA
AACTTAAATTTTTGTACAGGCTAAGAACCCTTAATACTTAAGAATGTTTG
AATCACTTTGATAGACAGTAGATATAATTTAAATATGCTACCAAAGTTGC
AGTTATCCTAAGATTTATGTGCCTCAGGGTAAGTTTTTAAGACCTTTTGG
TTTTTGGTATCACCTCTGCTTCTAGTAAATTTAGTGTCTAGTGCTTCTGT
CTTGAGGCATTATATCCAACATCATGAGTAAAACAA
```

3. We will now check this sequence with BLAT to ensure that it's specific to our target region. Note how it has a very high score for the entire length of the sequence on the target chromosome.

```
   ACTIONS      QUERY   SCORE START   END QSIZE IDENTITY  CHROM  STRAND  START       END   SPAN
-----------------------------------------------------------------------------------------------
browser details YourSeq   686     1   686   686   100.0%  chrY   +      872224    872909    686
browser details YourSeq    56   425   501   686    90.4%  chrY   +      873096    873170     75
browser details YourSeq    31   253   298   686    74.3%  chr5   -   130617267 130617302     36
browser details YourSeq    27   298   325   686   100.0%  chr1   +   151475811 151475891     81
browser details YourSeq    25   252   279   686    84.7%  chr10  -    42215480  42215505     26
browser details YourSeq    25   243   273   686    96.3%  chr1   -    27309302  27309333     32
browser details YourSeq    25   308   336   686    96.3%  chr1   +   223415891 223415930     40
browser details YourSeq    24   254   277   686   100.0%  chr9   +    17376651  17376674     24
browser details YourSeq    22   253   274   686   100.0%  chr2   -   105906331 105906352     22
browser details YourSeq    22    57    80   686    95.9%  chr10  +    50084585  50084608     24
browser details YourSeq    21   251   271   686   100.0%  chr10  -    54106311  54106331     21
browser details YourSeq    21   249   269   686   100.0%  chr1   -   148717082 148717102     21
browser details YourSeq    21   244   264   686   100.0%  chr1   +   131095589 131095609     21
browser details YourSeq    20   311   330   686   100.0%  chr12  -    11335492  11335511     20
browser details YourSeq    20   103   122   686   100.0%  chr10  -    25776961  25776980     20
```

4. We will now use this sequence to design primers and probes in primer express using a TaqMan MGB quantification design. Below is the top primer / probe combination for our target region

- Forward Primer:TGCTACCAAAGTTGCAGTTATCCT 
- Reverse Primer:AGGTGATACCAAAAACCAAAAGGT 
- Probe: AGATTTATGTGCCTCAGGGT 

We will now double check this primer set for specificity using primer blast and our target sequence. We will also select "Genomes for selected eukaryotic organisms" and Rattus norvegicus to check if the primer set will amplify any regions elsewhere in the genome. The only template with a perfect match is our target sequence.

```
>NC_051357.1 Rattus norvegicus strain BN/NHsdMcwi chromosome Y, mRatBN7.2

product length = 80
Features associated with this product:
   eukaryotic translation initiation factor 2 subunit 3, y-l...

   eukaryotic translation initiation factor 2 subunit 3, y-l...

Forward primer  1       TGCTACCAAAGTTGCAGTTATCCT  24
Template        872759  ........................  872782

Reverse primer  1       AGGTGATACCAAAAACCAAAAGGT  24
Template        872838  ........................  872815
```

Check for interactions with other primers using the the Multiple Primer Design tool: https://www.thermofisher.com/us/en/home/brands/thermo-scientific/molecular-biology/molecular-biology-learning-center/molecular-biology-resource-library/thermo-scientific-web-tools/multiple-primer-analyzer.html

```
Name 	Sequence                	Tm°C	CG%	nt	A	T	C	G	Extinction coefficient(l/(mol·cm)	Molecular weight(g/mol)	nmol	µg/OD260
chr1F	gaagaagccccggtcatca     	67.8	57.9	19	6.0	2.0	6.0	5.0	189000.0                         	5806.8                 	5.3 	30.7
chr1R	gctttcttgcacgctggaa     	66.9	52.6	19	3.0	6.0	5.0	5.0	171600.0                         	5794.8                 	5.8 	33.8
chr1P	aagcagaggatgaatct       	52.2	41.2	17	7.0	3.0	2.0	5.0	179700.0                         	5267.5                 	5.6 	29.3
chrXF	ccagcagccaggacagtagaa   	67.0	57.1	21	8.0	1.0	6.0	6.0	215700.0                         	6458.3                 	4.6 	29.9
chrXR	ctgaccaaacctggctggat    	66.7	55.0	20	5.0	4.0	6.0	5.0	186600.0                         	6102.0                 	5.4 	32.7
chrXP	agtagtgtgaggaccaact     	54.0	47.4	19	6.0	4.0	3.0	6.0	194900.0                         	5876.9                 	5.1 	30.2
chrYF	tgctaccaaagttgcagttatcct	65.0	41.7	24	6.0	8.0	6.0	4.0	225600.0                         	7302.8                 	4.4 	32.4
chrYR	aggtgataccaaaaaccaaaaggt	64.6	37.5	24	12.0	3.0	4.0	5.0	255500.0                         	7411.9                 	3.9 	29.0
chrYP	agatttatgtgcctcagggt    	60.5	45.0	20	4.0	7.0	3.0	6.0	194200.0                         	6163.1                 	5.1 	31.7
```
