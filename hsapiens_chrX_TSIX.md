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
Reverse Primer:AAAGCAGGTGAGGCGGTAAG
Probe: CAGAAGACACTCAAGAAT
```

5. Check that the amplicon length is between 50-150 and that the melting temperatures are comparable to other primers in the multiplex design. Also check for self-dimers and cross primer dimers with other primers in the multiplex reaction using the Multiple Primer Analyzer: https://www.thermofisher.com/us/en/home/brands/thermo-scientific/molecular-biology/molecular-biology-learning-center/molecular-biology-resource-library/thermo-scientific-web-tools/multiple-primer-analyzer.html
```
Name 	Sequence             	Tm°C	CG%	nt	A	T	C	G	Extinction coefficient(l/(mol·cm)	Molecular weight(g/mol)	nmol	µg/OD260
chr1F	acgtggcggatgaaagtca  	67.1	52.6	19	6.0	3.0	3.0	7.0	196000.0                         	5901.9                 	5.1 	30.1
chr1R	gatccacccagccaccctata	67.2	57.1	21	6.0	3.0	10.0	2.0	196600.0                         	6280.1                 	5.1 	31.9
chr1P	tgcttccatagccatca    	59.4	47.1	17	4.0	5.0	6.0	2.0	157000.0                         	5105.4                 	6.4 	32.5
chrXF	tcaagagggatggacaaagga	66.1	47.6	21	9.0	2.0	2.0	8.0	227300.0                         	6577.4                 	4.4 	28.9
chrXR	aaagcaggtgaggcggtaag 	65.7	55.0	20	7.0	2.0	2.0	9.0	212400.0                         	6280.2                 	4.7 	29.6
chrXP	cagaagacactcaagaat   	49.9	38.9	18	9.0	2.0	4.0	3.0	189000.0                         	5509.7                 	5.3 	29.2
chrYF	tgtgcctcctggaagaatgg 	67.8	55.0	20	4.0	5.0	4.0	7.0	190600.0                         	6173.1                 	5.2 	32.4
chrYR	gatcagcaagcagctgggata	66.8	52.4	21	7.0	3.0	4.0	7.0	214700.0                         	6504.3                 	4.7 	30.3
chrYP	catttttcggcttcagtaag 	59.5	40.0	20	4.0	8.0	4.0	4.0	186900.0                         	6098.0                 	5.4 	32.6
```


5. We will now double check this primer set for specificity using primer blast and our target sequence. We will also select "Genomes for selected eukaryotic organisms" and Homo sapiens to check if the primer set will amplify any regions elsewhere in the genome. The only template with a perfect match is our target sequence. 

```
>NC_000023.11 Homo sapiens chromosome X, GRCh38.p14 Primary Assembly

product length = 76
Features flanking this product:
   137937 bp at 5' side: cysteine-rich hydrophobic domain-containing protein 1 iso...
   485250 bp at 3' side: zinc finger cchc domain-containing protein 13

Forward primer  1         TCAAGAGGGATGGACAAAGGA  21
Template        73818941  .....................  73818961

Reverse primer  1         AAAGCAGGTGAGGCGGTAAG  20
Template        73819016  ....................  73818997

```
6. Check that the amplicon length is between 75-150 and that the melting temperatures are comparable to other primers in the multiplex design
```
Sequence (5'->3')	Template strand	Length	Start	Stop	Tm	GC%	Self complementarity	Self 3' complementarity
Forward primer	TCAAGAGGGATGGACAAAGGA	Plus	21	344	364	58.37	47.62	2.00	0.00
Reverse primer	AAAGCAGGTGAGGCGGTAAG	Minus	20	419	400	60.32	55.00	2.00	0.00
Product length	76
```


