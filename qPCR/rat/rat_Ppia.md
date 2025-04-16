# Introduction
Ppia ((peptidyl-proyl-isomerase A) is a common house keeping gene for rats. We can use a pimer set from https://pmc.ncbi.nlm.nih.gov/articles/PMC3224571/#sec6. This probe set has some off-target effects on Ppial4d, LOC100909955 and LOC100911252, which are all very stable across age groups. If the following design does not work, go with this primer set

rn8_Ppia_S1:

Fwd: 5'-GTCAACCCCACCGTGTTCTTC-3'
Rev: 5'-ATCCTTTCTCCCCAGTGCTCAG-3'

# Design
1. Go to Genbank record of [NM_017101.1](https://www.ncbi.nlm.nih.gov/nuccore/NM_017101.1?report=graph). Click "Graphics" to view the graph reprensentation of the sequence. We can see that the protein coding sequence is from 53 to 537. I usually like to use CDS region for primer design.
2. Go to Primer Blast, input the following:
   - Template: NM_017101.1. Range: 53-537
    - Product size: 80-200
    - Number of Primer pairs to return: 15
    - Primer Tm: 59 - 61. Optimal: 60. Max Tm difference: 1
    - Database: Rattus norvegicus (taxid:10116)
    - Exclude uncultured organisms: Check (we do not check exclude predicted Refseq transcripts here as rats have a lot of predicted transcripts, which exist but just not validated)
    - Allow splice variants: Check
    - Primer size: 16-24. Opt: 20
    - Primer GC content %: 40-60.

3. Then we will be asked to include the following transcripts or not due to high similarity. We checked using mRNAseq that those transcripts are stable across ages. We select both of them.
```
Input PCR template
    NM_017101.1 Rattus norvegicus peptidylprolyl isomerase A (Ppia), mRNA 
Range
    53 - 537

Your PCR template is highly similar to the following sequence(s) from the search database. To increase the chance of finding specific primers, please review the list below and select all sequences (within the given sequence ranges) that are intended or allowed targets.
Select:AllNone Selected:2
Accession	Title	Identity	Alignment length	Seq. start	Seq. stop
>XM_006250801.5	PREDICTED: Rattus norvegicus peptidylprolyl isomerase A (cyclophilin A)-like 4D (Ppial4d), mRNA	99.79%	485	60	544
>XM_039108606.2	PREDICTED: Rattus norvegicus peptidyl-prolyl cis-trans isomerase A-like (LOC100911252), mRNA	98.97%	485	56	540
```
4. Then we can select from the results a good primer pair:
```
Primer pair 2
	Sequence (5'->3')	Template strand	Length	Start	Stop	Tm	GC%	Self complementarity	Self 3' complementarity
Forward primer	GTCTGCTTCGAGCTGTTTGC	Plus	20	100	119	60.11	55.00	4.00	2.00
Reverse primer	CACCCTGGCACATGAATCCT	Minus	20	235	216	60.03	55.00	4.00	3.00
Product length	136
Products on intended targets
>XM_039108606.2 PREDICTED: Rattus norvegicus peptidyl-prolyl cis-trans isomerase A-like (LOC100911252), mRNA


product length = 136
Forward primer  1    GTCTGCTTCGAGCTGTTTGC  20
Template        103  ....................  122

Reverse primer  1    CACCCTGGCACATGAATCCT  20
Template        238  .......A............  219

>XM_006250801.5 PREDICTED: Rattus norvegicus peptidylprolyl isomerase A (cyclophilin A)-like 4D (Ppial4d), mRNA


product length = 136
Forward primer  1    GTCTGCTTCGAGCTGTTTGC  20
Template        107  ....................  126

Reverse primer  1    CACCCTGGCACATGAATCCT  20
Template        242  ....................  223

>NM_017101.1 Rattus norvegicus peptidylprolyl isomerase A (Ppia), mRNA


product length = 136
Forward primer  1    GTCTGCTTCGAGCTGTTTGC  20
Template        100  ....................  119

Reverse primer  1    CACCCTGGCACATGAATCCT  20
Template        235  ....................  216

Products on potentially unintended templates
> XM_039080416.1 PREDICTED: Rattus norvegicus peptidyl-prolyl cis-trans isomerase A-like (LOC100909955), mRNA


product length = 136
Forward primer  1    GTCTGCTTCGAGCTGTTTGC  20
Template        127  ....C...............  146

Reverse primer  1    CACCCTGGCACATGAATCCT  20
Template        262  .......A............  243

> XM_341363.7 PREDICTED: Rattus norvegicus peptidylprolyl isomerase A like 4G (Ppial4g), mRNA


product length = 136
Forward primer  1   GTCTGCTTCGAGCTGTTTGC  20
Template        91  ....C...G...T.......  110

Reverse primer  1    CACCCTGGCACATGAATCCT  20
Template        226  ....................  207
```

In summary, our custom designed primer set is:
```
rn8_Ppia_S2:
- Fwd: 5'-GTCTGCTTCGAGCTGTTTGC-3'
- Rev: 5'-CACCCTGGCACATGAATCCT-3'
- Product size: 136
```