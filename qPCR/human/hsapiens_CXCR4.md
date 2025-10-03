# Introduction
CXCR4 is a G protein-coupled receptor (GPCR), which is crucial for cell migration and is involved in epithelial-mesenchymal transition (EMT). It is upregulated in DCLK1-overexpressing HEK293T.

# Design Principles
When I design the primers, I usually use Primer Blast, and follow the below principles:
- For genes with multiple isoforms, I try to limit the forward and reverse primers to fall within the protein coding region (CDS) or common region of the isoforms. The range can be found by clicking into "Fastq" record of a transcript in NCBI, and then clicking into "Graphics". For CXCR4, there are 4 RefSeq isoforms with only one common exon, so I will just place the primres in that exon (for isoform NM_003467.3, this is 90-1148 bp).
- PCR product size: 100-200 bp.
- Primer melting temperature (Tm): 58-62 °C. Max Tm difference: 1 °C.
- \# of primers to return: set so that we can select primers that are either spanning exon-exon junctions or separated by introns.
- Search in the Refseq mRNA of the species we are designing primers for. Exclude uncultured/environmental sample sequences.
- Primer size: 16-24. Opt 20
- Primer GC content: 40-60%
- Max self complementarity: 5
- Max self 3' complementarity: 5

# Primer Blast result
The primer we selected is:
- Fwd: 5'-TGGTCTATGTTGGCGTCTGG-3'
- Rev: 5'-GTCATTGGGGTAGAAGCGGT-3'
- Product size: 116 bp

```
Primer pair 9
	Sequence (5'->3')	Template strand	Length	Start	Stop	Tm	GC%	Self complementarity	Self 3' complementarity
Forward primer	TGGTCTATGTTGGCGTCTGG	Plus	20	553	572	59.75	55.00	2.00	0.00
Reverse primer	GTCATTGGGGTAGAAGCGGT	Minus	20	668	649	59.75	55.00	3.00	2.00
Product length	116
Products on intended targets
>XM_054343837.1 PREDICTED: Homo sapiens C-X-C motif chemokine receptor 4 (CXCR4), transcript variant X2, mRNA


product length = 116
Forward primer  1    TGGTCTATGTTGGCGTCTGG  20
Template        783  ....................  802

Reverse primer  1    GTCATTGGGGTAGAAGCGGT  20
Template        898  ....................  879

>XM_047445802.1 PREDICTED: Homo sapiens C-X-C motif chemokine receptor 4 (CXCR4), transcript variant X1, mRNA


product length = 116
Forward primer  1    TGGTCTATGTTGGCGTCTGG  20
Template        947  ....................  966

Reverse primer  1     GTCATTGGGGTAGAAGCGGT  20
Template        1062  ....................  1043

>NM_001008540.2 Homo sapiens C-X-C motif chemokine receptor 4 (CXCR4), transcript variant 1, mRNA


product length = 116
Forward primer  1    TGGTCTATGTTGGCGTCTGG  20
Template        772  ....................  791

Reverse primer  1    GTCATTGGGGTAGAAGCGGT  20
Template        887  ....................  868

>NM_003467.3 Homo sapiens C-X-C motif chemokine receptor 4 (CXCR4), transcript variant 2, mRNA


product length = 116
Forward primer  1    TGGTCTATGTTGGCGTCTGG  20
Template        553  ....................  572

Reverse primer  1    GTCATTGGGGTAGAAGCGGT  20
Template        668  ....................  649

>NM_001348059.2 Homo sapiens C-X-C motif chemokine receptor 4 (CXCR4), transcript variant 4, mRNA


product length = 116
Forward primer  1    TGGTCTATGTTGGCGTCTGG  20
Template        652  ....................  671

Reverse primer  1    GTCATTGGGGTAGAAGCGGT  20
Template        767  ....................  748

>NM_001348060.2 Homo sapiens C-X-C motif chemokine receptor 4 (CXCR4), transcript variant 5, mRNA


product length = 116
Forward primer  1    TGGTCTATGTTGGCGTCTGG  20
Template        790  ....................  809

Reverse primer  1    GTCATTGGGGTAGAAGCGGT  20
Template        905  ....................  886

>NM_001348056.2 Homo sapiens C-X-C motif chemokine receptor 4 (CXCR4), transcript variant 3, mRNA


product length = 116
Forward primer  1    TGGTCTATGTTGGCGTCTGG  20
Template        766  ....................  785

Reverse primer  1    GTCATTGGGGTAGAAGCGGT  20
Template        881  ....................  862
```