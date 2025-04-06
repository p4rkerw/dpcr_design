# Information
HPRT1 is a gene on human chrX.

# Design
The following design is from Amit:
- Forward: 5'-TGACACTGGCAAAACAATGCA-3'
- Reverse: 5'-GGTCCTTTTCACCAGCAAGCT-3'

# Primer blast validation
- Use RefSeq mRNA as database
- Limit the search to "homo sapiens"
- check "Exclude uncultured/environmental sample sequences"

The result is:
```
Primer pair 1
	Sequence (5'->3')	Length	Tm	GC%	Self complementarity	Self 3' complementarity
Forward primer	TGACACTGGCAAAACAATGCA	21	59.52	42.86	5.00	4.00
Reverse primer	GGTCCTTTTCACCAGCAAGCT	21	61.09	52.38	4.00	4.00
Products on target templates
>NM_000194.3 Homo sapiens hypoxanthine phosphoribosyltransferase 1 (HPRT1), mRNA


product length = 94
Forward primer  1    TGACACTGGCAAAACAATGCA  21
Template        558  .....................  578

Reverse primer  1    GGTCCTTTTCACCAGCAAGCT  21
Template        651  .....................  631

>NM_001145076.3 Homo sapiens EMAP like 4 (EML4), transcript variant 2, mRNA


product length = 3126
Forward primer  1     TGACACTGGCAAAACAATGCA  21
Template        1265  ..GG.......G..G..A...  1285

Forward primer  1     TGACACTGGCAAAACAATGCA  21
Template        4390  A..A.G.AT............  4370

>NM_001410776.1 Homo sapiens EMAP like 4 (EML4), transcript variant 3, mRNA


product length = 3126
Forward primer  1     TGACACTGGCAAAACAATGCA  21
Template        1472  ..GG.......G..G..A...  1492

Forward primer  1     TGACACTGGCAAAACAATGCA  21
Template        4597  A..A.G.AT............  4577

>NM_019063.5 Homo sapiens EMAP like 4 (EML4), transcript variant 1, mRNA


product length = 3126
Forward primer  1     TGACACTGGCAAAACAATGCA  21
Template        1439  ..GG.......G..G..A...  1459

Forward primer  1     TGACACTGGCAAAACAATGCA  21
Template        4564  A..A.G.AT............  4544

```

The predicted amplification of EML4 should not matter as there are mismatches and product length is too long.