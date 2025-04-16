# Introduction
beta-actin (Actb) is a common house keeping gene for rats. This [publication](https://pmc.ncbi.nlm.nih.gov/articles/PMC3224571/#sec14) has sequences for Actb primers. However, there are potential off-target products on Acta1, Actb, Actg2, Acta2, etc. Their design is:
```
rn8_Actb_S1:
- Fwd: 5'-CAGGGTGTGATGGTGGGTATGG-3'
- Rev: 5'-AGTTGGTGACAATGCCGTGTTC-3'
- Product size: 115 bp
```
use this design if the following does not work.

# Design
1. Go to Genbank record of [NM_031144.3](https://www.ncbi.nlm.nih.gov/nuccore/NM_031144.3?report=genbank). Click "Graphics" to view the graph reprensentation of the sequence. We can see that the protein coding sequence is from 79 to 1206. I usually like to use CDS region for primer design. 
2. Go to Primer Blast, input the following. Note that we might need to tweak intro/exon-spanning settings to find the best primer-pairs.
   - Template: NM_031144.3. Range: 79-1206
    - Product size: 80-200
    - Number of Primer pairs to return: 15
    - Primer Tm: 59 - 61. Optimal: 60. Max Tm difference: 1
    - Database: Rattus norvegicus (taxid:10116)
    - Exclude uncultured organisms: Check (we do not check exclude predicted Refseq transcripts here as rats have a lot of predicted transcripts, which exist but just not validated)
    - Allow splice variants: Check
    - Max primer pairs to screen: 1000
    - Primer size: 16-24. Opt: 20
    - Primer GC content %: 40-60.
    - Max Poly-X: 3
    - Max self-complementarity: 6
    - Max pair-complementarity: 6
3. We can then select the best primer pair from the results:
```
Primer pair 1
	Sequence (5'->3')	Template strand	Length	Start	Stop	Tm	GC%	Self complementarity	Self 3' complementarity
Forward primer	ACCCTAAGGCCAACCGTGA	Plus	19	410	428	60.84	57.89	5.00	1.00
Reverse primer	ATGCCAGTGGTACGACCAGA	Minus	20	530	511	60.90	55.00	6.00	2.00
Product length	121
Products on intended targets
>NM_031144.3 Rattus norvegicus actin, beta (Actb), mRNA


product length = 121
Forward primer  1    ACCCTAAGGCCAACCGTGA  19
Template        410  ...................  428

Reverse primer  1    ATGCCAGTGGTACGACCAGA  20
Template        530  ....................  511

```

In summary, we have the following design:
```
rn8_Actb_S2:
- Fwd: 5'-ACCCTAAGGCCAACCGTGA-3'
- Rev: 5'-ATGCCAGTGGTACGACCAGA-3'
- Product size: 121 bp
```
