# Introduction
NR3C1 encodes glucocorticoid receptor (GR) in humans.

# Design
There are several isoforms according to RefSeq. THe common regions are exon 2 to exon 7 on transcript NM_000176.3. Go to [graphical view](https://www.ncbi.nlm.nih.gov/nuccore/NM_000176.3?report=graph) to confirm the positions (477-2512bp). In [Primer Blast](https://www.ncbi.nlm.nih.gov/tools/primer-blast/), modify the following:
- PCR template: NM_000176.3
- Forward primer from: 477 bp
- Reverse primer to: 2512 bp
- PCR product size: 80-250 bp
- Primer Tm: 58-62 °C, Optimal 60 °C, Max Tm difference 1 °C
- Search mode: User guided 
- Organism: Homo sapiens
- Advanced parameters:
    - Primer GC content: 40%-60%
    - Max Self Complementarity: Any 5
    - Max Pair Complementarity: Any 5

Then the program will ask for confirmation of which transcripts to check specificity. Select all the NR3C1 transcripts.

# Result
Select a primer pair tocheck on thermo's [Multiple Primer Analyzer](https://www.thermofisher.com/us/en/home/brands/thermo-scientific/molecular-biology/molecular-biology-learning-center/molecular-biology-resource-library/thermo-scientific-web-tools/multiple-primer-analyzer.html) to see if there are primer dimers/cross dimers.

The selected pair is:
```
Primer pair 2
	Sequence (5'->3')	Template strand	Length	Start	Stop	Tm	GC%	Self complementarity	Self 3' complementarity
Forward primer	ACCAATTCCCGTTGGTTCCG	Plus	20	1554	1573	60.89	55.00	5.00	2.00
Reverse primer	CATCTGGTCTCATGCTGGGG	Minus	20	1693	1674	60.18	60.00	4.00	0.00
Product length	140
Total intron size	85487 (between pos. 143399656 and 143314168 on NC_000005.10)
```

# Summary:
- hsapiens_NR3C1_Fwd: 5'-ACCAATTCCCGTTGGTTCCG-3'
- hsapiens_NR3C1_Rev: 5'-CATCTGGTCTCATGCTGGGG-3'
- Amplicon size: 140 bp