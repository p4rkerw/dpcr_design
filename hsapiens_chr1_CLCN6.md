dPCR primer and probe design for human chromosome 1p

1. First examine CLCN6 on long arm using the ucsc genome browser [link](http://www.genome.ucsc.edu/cgi-bin/hgTracks?db=hg38&lastVirtModeType=default&lastVirtModeExtraState=&virtModeType=default&virtMode=0&nonVirtPosition=&position=chr1%3A11806191%2D11843130&hgsid=1672192022_W6ut45REA7eVRFc9Jf6UwCpIG9U8) SNVs can affect probe binding and should be avoided if possible. There are also repetitive elements in the repeat masker track. It is difficult to design probes that involve repetitive elements because there is a risk they will bind multiple regions in the genome with the same element.

2. We will now extract the nucleotide sequence using the ucsc table browser [link](http://www.genome.ucsc.edu/cgi-bin/hgTables?hgsid=1672192022_W6ut45REA7eVRFc9Jf6UwCpIG9U8&hgta_nextIntersectGroup=varRep&hgta_nextIntersectTrack=dbSnp155Composite&hgta_nextIntersectTable=dbSnp155Common&hgta_nextIntersectOp=any&hgta_nextMoreThreshold=80&hgta_nextLessThreshold=80&boolshad.hgta_nextInvertTable=0&hgta_nextInvertTable2=1&boolshad.hgta_nextInvertTable2=0&hgta_doIntersectSubmit=submit). We will mask repeats with N. Below is a  chunk of sequence. The get DNA in window is another tool that can retrieve sequences in target regions if you don't want all of the extra sequences. By convention, we design primers and probes using the + strand rather than the - strand. 

```
>hg38_ncbiRefSeq_NM_001256959.2_13 range=chr1:11824554-11826155 5'pad=0 3'pad=0 strand=+ repeatMasking=N
GTAAGATGGGCTGAGAGGGTGTGGGCCTCTGGGCAGGCCTAGTGGGAGGT
CTGGTTACACTGGGCCAAATCCATTGGGACACCCTGACATCACATTGGAA
CCTGGTGCCATTCTGGCTTCACGTGTAAACCATGTGTCTATCTCTCAGGA
AAGGGCATAACTTATACTTGGAAGTTTTAATGATGCCCTACCGAGCCCTA
GGAGCAAAAATGAGACATAGAGAAAAACTGTGACGTGGCGGATGAAAGTC
ACTGGGTGCTTCCATAGCCATCACCAGGCGCCTCTATATAGGGTGGCTGG
GTGGATCATCTCAGTGCTGCCAGATCCAAGAGGCTCGAAGCATCGACTGA
CATGGTTTTAGGCACAGTTCCGTGCTGATTCTAGTTGGCGTGGTACAGTC
ATAATAACTGCTGCTAATTATGGTCTG
```

3. We will now check this sequence with BLAT to ensure that it's specific to our target region. Note how it has a very high score for the entire length of the sequence on chr1. 

```
   ACTIONS      QUERY   SCORE START   END QSIZE IDENTITY  CHROM  STRAND  START       END   SPAN
-----------------------------------------------------------------------------------------------
browser details YourSeq   427     1   427   427   100.0%  chr1   +    11824554  11824980    427
browser details YourSeq    30    19   110   427    94.2%  chr21  +    43974784  43974901    118
browser details YourSeq    23   141   164   427   100.0%  chr16  +    16847547  16847591     45
browser details YourSeq    20   141   160   427   100.0%  chr1   -   203990252 203990271     20
```

4. We will now use this sequence to design primers and probes in primer express using a TaqMan MGB quantification design. Below is the a primer / probe combination for which the F and R primers have the same Tm for our target region. We can modify the default Primer Express parameters as follows:

- Min Primer Tm: 58
- Max Primer Tm: 59
- Max Difference in Tm of Two Primers: 1
- Min Primer %GC Content: 50
- Max Primer %GC Content: 60
- Max Primer 3' GC's: 2
- Primer 3' End Length: 5
- Primer 3' GC Clamp Residues: 0
- Min Primer Length: 19
- Max Primer Length: 21
- Optimal Primer Length: 20
- Max Primer G Repeats: 3
- Max Num Ambig Residues in Primer: 0
- Max Primer Consec Base Pair: 3
- Max Primer Total Base Pair: 8
- Max % Match in Primer: 75
- Max Consec Match in Primer: 9
- Max 3' Consec Match in Primer: 7
- Min Probe Tm: 68
- Max Probe Tm: 70
- Min Probe %GC Content: 30
- Max Probe %GC Content: 80
- Min Probe Length: 13
- Max Probe Length: 25
- Max Probe G Repeats: 3
- Max Num Ambig Residues in Probe: 0
- No G at 5' End in Probe: Check
- Select Probe with more C's than G's: Check
- Max Probe Consec Base Pair: 4
- Max Probe Total Base Pair: 8
- Min Amplified Region Tm: 0
- Max Amplified Region Tm: 85
- Min Amplified Region Length: 75
- Max Amplified Region Length: 150

```
Forward Primer:ACGTGGCGGATGAAAGTCA
Reverse Primer:GATCCACCCAGCCACCCTATA
Probe: TGCTTCCATAGCCATCA
```

Optional: Take the amplicon sequence and put into IDT UNAfold to check for secondary structures that form at a Tm higher than 60C.

5. Check that the amplicon length is between 75-150 and that the melting temperatures are comparable to other primers in the multiplex design. Also check for self-dimers and cross primer dimers with other primers in the multiplex reaction using the Multiple Primer Analyzer: https://www.thermofisher.com/us/en/home/brands/thermo-scientific/molecular-biology/molecular-biology-learning-center/molecular-biology-resource-library/thermo-scientific-web-tools/multiple-primer-analyzer.html 
```
Name 	Sequence             	Tm°C	CG%	nt	A	T	C	G	Extinction coefficient(l/(mol·cm)	Molecular weight(g/mol)	nmol	µg/OD260
chr1F	acgtggcggatgaaagtca  	67.1	52.6	19	6.0	3.0	3.0	7.0	196000.0                         	5901.9                 	5.1 	30.1
chr1R	gatccacccagccaccctata	67.2	57.1	21	6.0	3.0	10.0	2.0	196600.0                         	6280.1                 	5.1 	31.9
chr1P	tgcttccatagccatca    	59.4	47.1	17	4.0	5.0	6.0	2.0	157000.0                         	5105.4                 	6.4 	32.5
```

6. We will now double check this primer set for specificity using primer blast and our target sequence. We will also select "Genomes for selected eukaryotic organisms" and Homo sapiens to check if the primer set will amplify any regions elsewhere in the genome. The only template with a perfect match is our target sequence. 

```
>NC_000001.11 Homo sapiens chromosome 1, GRCh38.p14 Primary Assembly

product length = 75
Features associated with this product:
   h(+)/cl(-) exchange transporter 6 isoform 1

   h(+)/cl(-) exchange transporter 6 isoform 2

Forward primer  1         ACGTGGCGGATGAAAGTCA  19
Template        11824786  ...................  11824804

Reverse primer  1         GATCCACCCAGCCACCCTATA  21
Template        11824860  .....................  11824840
```

7. Check that the amplicon length is between 75-150 and that the melting temperatures are comparable to other primers in the multiplex design
```
Sequence (5'->3')	Template strand	Length	Start	Stop	Tm	GC%	Self complementarity	Self 3' complementarity
Forward primer	ACGTGGCGGATGAAAGTCA	Plus	19	233	251	59.63	52.63	4.00	3.00
Reverse primer	GATCCACCCAGCCACCCTATA	Minus	21	307	287	60.77	57.14	4.00	4.00
Product length	75
```


