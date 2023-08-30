dPCR primer and probe design for human X chromosome

1. First examine XIST using the ucsc genome browser [link](http://www.genome.ucsc.edu/cgi-bin/hgTracks?db=hg38&lastVirtModeType=default&lastVirtModeExtraState=&virtModeType=default&virtMode=0&nonVirtPosition=&position=chrX%3A73820656%2D73852723&hgsid=1672088950_52BQM4SKEdVAjWVjhr3gdJOJnLo5) Note how XIST has multiple exons and that there are common variants in the dbSNP tracks. SNVs can affect probe binding and should be avoided if possible. There are also repetitive elements in the repeat masker track. It is difficult to design probes that involve repetitive elements because there is a risk they will bind multiple regions in the genome with the same element.

2. We will now extract the nucleotide sequence of XIST using the ucsc table browser [link](http://www.genome.ucsc.edu/cgi-bin/hgTables?hgsid=1672088950_52BQM4SKEdVAjWVjhr3gdJOJnLo5&clade=mammal&org=Human&db=hg38&hgta_group=map&hgta_track=gold&hgta_table=0&hgta_regionType=range&position=chrX%3A73%2C820%2C656-73%2C852%2C723&hgta_outputType=sequence&hgta_outFileName=). We will mask repeats with N. Below is the first chunk of sequence. Note how the sequence captures an area much larger than just XIST and is on the + strand (XIST is on the - strand). The get DNA in window is another tool that can retrieve sequences in target regions if you don't want all of the extra sequences. By convention, we design primers and probes using the + strand rather than the - strand. 

```
>hg38_gold_AL353804.22 range=chrX:73818598-73984265 5'pad=0 3'pad=0 strand=+ repeatMasking=N
AGGAGGCACAAGTTTTTGTGGATGTGGGTTGGGCTGGCACCAAATCCAAC
TACAAGCATACAGTGACCACTTCATACACACCACATAAAAAATACAAAAA
CTGAAAAATACTATCAAATGCTTTGACATTTTCTAAATATTTCTGCTGCC
CCTATAAAATTGCCTTGTCTGACCTTTCCTCACTAACCAGGAGATACGGT
GTTTTTCATTTCCTCTCCCTTCAAATTTTACAAGAGAATCAAGGAATTTG
AGGACCAAAGCACCACAAACACAAGAGTAAGCACAGCAAATATGACAAGG
GGACTGAAGTAAGCCCCTATGGGAATAGGATCTGCTGAAGGAATCAAGAG
GGATGGACAAAGGAACAGAAGACACTCAAGAATAACTTCAGGAAGTCTCC
TTACCGCCTCACCTGCTTTCCCTCTGTCCTACACATCCAGCCTTGCAAAG
AAATAAGAGTAAAGAGAAAAGTCCATGTAGCACCATCCCAGTTCAGAAGC
AACCCCCAAGATATGGGTCAACTTTATCACCTCAAACTCTACTCATTTAT
AATGACAAAATTCAACTGTTAACACATAGGTAAGAGTTCTTCAGGCATCG
GTTTTAAAGGTCCATGTACTG
```

3. We will now check this sequence with BLAT to ensure that it's specific to our target region. Note how it has a very high score for the entire length of the sequence on chrX. The region maps downstream of XIST to the first exon of TSIX on the + strand.  

```
   ACTIONS      QUERY   SCORE START   END QSIZE IDENTITY  CHROM  STRAND  START       END   SPAN
-----------------------------------------------------------------------------------------------
browser details YourSeq   621     1   621   621   100.0%  chrX   +    73818598  73819218    621
browser details YourSeq    28   249   336   621    56.7%  chr10  -    90968001  90968040     40
browser details YourSeq    21   504   524   621   100.0%  chr19  -    44174191  44174211     21
browser details YourSeq    20   208   227   621   100.0%  chr13  +   101624687 101624706     20
```

4. We will now use this sequence to design primers and probes in primer express using a TaqMan MGB quantification design. Below is a primer / probe combination with a melting temperature within 1C of our reference primers. 

```
Forward Primer:TCAAGAGGGATGGACAAAGGA
Reverse Primer:GGTGAGGCGGTAAGGAGACTT
Probe: CAGAAGACACTCAAGAATA
```

5. Check that the amplicon length is between 50-150 and that the melting temperatures are comparable to other primers in the multiplex design. Also check for self-dimers and cross primer dimers with other primers in the multiplex reaction using the Multiple Primer Analyzer: https://www.thermofisher.com/us/en/home/brands/thermo-scientific/molecular-biology/molecular-biology-learning-center/molecular-biology-resource-library/thermo-scientific-web-tools/multiple-primer-analyzer.html
```
Name 	Sequence             	Tm°C	CG%	nt	A	T	C	G	Extinction coefficient(l/(mol·cm)	Molecular weight(g/mol)	nmol	µg/OD260
chr1F	tctcagtgctgccagatcca 	67.8	55.0	20	4.0	5.0	7.0	4.0	184200.0                         	6053.0                 	5.4 	32.9
chr1R	cagcacggaactgtgcctaa 	66.6	55.0	20	6.0	3.0	6.0	5.0	193400.0                         	6111.0                 	5.2 	31.6
chr1P	aggctcgaagcatc       	52.8	57.1	14	4.0	2.0	4.0	4.0	137200.0                         	4272.8                 	7.3 	31.1
chrXF	tcaagagggatggacaaagga	66.1	47.6	21	9.0	2.0	2.0	8.0	227300.0                         	6577.4                 	4.4 	28.9
chrXR	ggtgaggcggtaaggagactt	65.8	57.1	21	5.0	4.0	2.0	10.0	214200.0                         	6591.3                 	4.7 	30.8
chrXP	cagaagacactcaagaata  	50.4	36.8	19	10.0	2.0	4.0	3.0	203700.0                         	5822.9                 	4.9 	28.6
chrYF	tttctgtgcctcctggaagaa	66.3	47.6	21	4.0	7.0	5.0	5.0	194300.0                         	6412.2                 	5.1 	33.0
chrYR	tgggataccagtggaaaatgc	66.0	47.6	21	7.0	4.0	3.0	7.0	213800.0                         	6519.3                 	4.7 	30.5
chrYP	ccatttttcggcttcag    	59.9	47.1	17	2.0	7.0	5.0	3.0	149300.0                         	5127.4                 	6.7 	34.3
```


5. We will now double check this primer set for specificity using primer blast and our target sequence. We will also select "Genomes for selected eukaryotic organisms" and Homo sapiens to check if the primer set will amplify any regions elsewhere in the genome. The only template with a perfect match is our target sequence. 

```
>NC_000023.11 Homo sapiens chromosome X, GRCh38.p14 Primary Assembly

product length = 70
Features flanking this product:
   137937 bp at 5' side: cysteine-rich hydrophobic domain-containing protein 1 iso...
   485256 bp at 3' side: zinc finger cchc domain-containing protein 13

Forward primer  1         TCAAGAGGGATGGACAAAGGA  21
Template        73818941  .....................  73818961

Reverse primer  1         GGTGAGGCGGTAAGGAGACTT  21
Template        73819010  .....................  73818990

```
6. Check that the amplicon length is between 50-150 and that the melting temperatures are comparable to other primers in the multiplex design
```

Sequence (5'->3')	Template strand	Length	Start	Stop	Tm	GC%	Self complementarity	Self 3' complementarity
Forward primer	TCAAGAGGGATGGACAAAGGA	Plus	21	344	364	58.37	47.62	2.00	0.00
Reverse primer	GGTGAGGCGGTAAGGAGACTT	Minus	21	413	393	61.51	57.14	3.00	2.00
Product length	70
```


