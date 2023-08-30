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

4. We will now use this sequence to design primers and probes in primer express using a TaqMan MGB quantification design. Below is the a primer / probe combination for which the F and R primers have the same Tm for our target region

```
Forward Primer:CAGTGCTGCCAGATCCAAGA
Reverse Primer:CAGCACGGAACTGTGCCTAA
Probe: CGAAGCATCGACTGAC
```

5. Check that the amplicon length is between 50-150 and that the melting temperatures are comparable to other primers in the multiplex design. Also check for self-dimers and cross primer dimers with other primers in the multiplex reaction using the Multiple Primer Analyzer: https://www.thermofisher.com/us/en/home/brands/thermo-scientific/molecular-biology/molecular-biology-learning-center/molecular-biology-resource-library/thermo-scientific-web-tools/multiple-primer-analyzer.html 
```
Name 	Sequence            	Tm°C	CG%	nt	A	T	C	G	Extinction coefficient(l/(mol·cm)	Molecular weight(g/mol)	nmol	µg/OD260
chr1F	cagtgctgccagatccaaga	67.0	55.0	20	6.0	3.0	6.0	5.0	195400.0                         	6111.0                 	5.1 	31.3
chr1R	cagcacggaactgtgcctaa	66.6	55.0	20	6.0	3.0	6.0	5.0	193400.0                         	6111.0                 	5.2 	31.6
chr1P	cgaagcatcgactgac    	56.6	56.3	16	5.0	2.0	5.0	4.0	155800.0                         	4875.2                 	6.4 	31.3
```

6. We will now double check this primer set for specificity using primer blast and our target sequence. We will also select "Genomes for selected eukaryotic organisms" and Homo sapiens to check if the primer set will amplify any regions elsewhere in the genome. The only template with a perfect match is our target sequence. 

```
>NC_000001.11 Homo sapiens chromosome 1, GRCh38.p14 Primary Assembly

product length = 66
Features associated with this product:
   h(+)/cl(-) exchange transporter 6 isoform 1

   h(+)/cl(-) exchange transporter 6 isoform 2

Forward primer  1         CAGTGCTGCCAGATCCAAGA  20
Template        11824865  ....................  11824884

Reverse primer  1         CAGCACGGAACTGTGCCTAA  20
Template        11824930  ....................  11824911
```

7. Check that the amplicon length is between 50-150 and that the melting temperatures are comparable to other primers in the multiplex design
```
Sequence (5'->3')	Template strand	Length	Start	Stop	Tm	GC%	Self complementarity	Self 3' complementarity
Forward primer	CAGTGCTGCCAGATCCAAGA	Plus	20	312	331	60.04	55.00	5.00	1.00
Reverse primer	CAGCACGGAACTGTGCCTAA	Minus	20	377	358	60.60	55.00	6.00	1.00
Product length	66
```


