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

4. We will now use this sequence to design primers and probes in primer express using a TaqMan MGB quantification design. Below is the top primer / probe combination for our target region

```
Forward Primer:CTGGGCCAAATCCATTGG
Reverse Primer:GCCAGAATGGCACCAGGTT
Probe: ACACCCTGACATCACAT
```

5. We will now double check this primer set for specificity using primer blast and our target sequence. We will also select "Genomes for selected eukaryotic organisms" and Homo sapiens to check if the primer set will amplify any regions elsewhere in the genome. The only template with a perfect match is our target sequence. 

```
>NC_000001.11 Homo sapiens chromosome 1, GRCh38.p14 Primary Assembly

product length = 58
Features associated with this product:
   h(+)/cl(-) exchange transporter 6 isoform 1

   h(+)/cl(-) exchange transporter 6 isoform 2

Forward primer  1         CTGGGCCAAATCCATTGG  18
Template        11824613  ..................  11824630

Reverse primer  1         GCCAGAATGGCACCAGGTT  19
Template        11824670  ...................  11824652
```

7. Check that the amplicon length is between 50-150 and comparable to other amplicons in the multiplex design
```

Sequence (5'->3')	Template strand	Length	Start	Stop	Tm	GC%	Self complementarity	Self 3' complementarity
Forward primer	CTGGGCCAAATCCATTGG	Plus	18	60	77	55.98	55.56	5.00	5.00
Reverse primer	GCCAGAATGGCACCAGGTT	Minus	19	117	99	60.61	57.89	5.00	3.00
Product length	58

```

6. Check that the primer melting temperatures for the F and R primers are similar and ensure there are no self-dimers or cross primer dimers using the Multiple Primer Analyzer. Note that the estimated primer melting temperatures may differ from Primer Express or Primer Blast due to a different algorithm
```
Name 	Sequence           	Tm°C	CG%	nt	A	T	C	G	Extinction coefficient(l/(mol·cm)	Molecular weight(g/mol)	nmol	µg/OD260
chr1F	ctgggccaaatccattgg 	66.6	55.6	18	4.0	4.0	5.0	5.0	168600.0                         	5499.6                 	5.9 	32.6
chr1R	gccagaatggcaccaggtt	67.7	57.9	19	5.0	3.0	5.0	6.0	184700.0                         	5837.8                 	5.4 	31.6
chr1P	acaccctgacatcacat  	54.5	47.1	17	6.0	3.0	7.0	1.0	162300.0                         	5083.4                 	6.2 	31.3
```


