The primer-probe design of these primer-probes are largely based on qPCR/hsapiens_chr13_DCLK1.md.

## 1. 
We first extract the mRNA sequences.
- For long isoforms represented by NM_004734.5: [link](https://www.ncbi.nlm.nih.gov/nuccore/NM_004734.5?report=fasta)
- For short isoforms represented by NM_001195415.2: [link](https://www.ncbi.nlm.nih.gov/nuccore/NM_004734.5?report=fasta)
- For shortest isoform NM_001195430.2: [link](https://www.ncbi.nlm.nih.gov/nuccore/NM_001195430.2?report=genbank)

## 2.
Fill the sequences above into Multi Primer Analyzer and evaluate cross-dimers.
We choose the primer pairs for long+short isoforms and short only
```
DCLK1LSF CCCTGGAGAAGAAGTGTCGG
DCLK1LSR CATGTGCTCTTTGCCTCGAC
DCLK1LSP AGGAAGGCTTCCAGATTCCAGCT (VIC, since a G at the second position)
DCLK1SF GATTCCGCCGTTGGTATTCAG
DCLK1SR GACGCAAGTGACGTAGAGGA
DCLK1SP TCTCTACTCCGCGCTCAGGCAA (FAM)
```

The properties are shown below:
```
Name    	Sequence               	Tm°C	CG%	nt	A	T	C	G	Extinction coefficient(l/(mol·cm)	Molecular weight(g/mol)	nmol	µg/OD260
DCLK1LSF	ccctggagaagaagtgtcgg   	66.4	60.0	20	5.0	3.0	4.0	8.0	199400.0                         	6207.1                 	5.0 	31.1
DCLK1LSR	catgtgctctttgcctcgac   	66.3	55.0	20	2.0	7.0	7.0	4.0	172100.0                         	6035.0                 	5.8 	35.1
DCLK1LSP	aggaaggcttccagattccagct	69.4	52.2	23	6.0	5.0	6.0	6.0	221800.0                         	7048.6                 	4.5 	31.8
DCLK1SF 	gattccgccgttggtattcag  	67.7	52.4	21	3.0	7.0	5.0	6.0	196500.0                         	6428.2                 	5.1 	32.7
DCLK1SR 	gacgcaagtgacgtagagga   	63.5	55.0	20	7.0	2.0	3.0	8.0	211900.0                         	6240.1                 	4.7 	29.4
DCLK1SP 	tctctactccgcgctcaggcaa 	72.5	59.1	22	4.0	5.0	9.0	4.0	196400.0                         	6631.3                 	5.1 	33.8

```

The primer dimer results are shown here:
```
                Self-Dimers:

1 dimer for: DCLK1LSP
          5-aggaaggcttccagattccagct->
             ||||| ||||| 
<-tcgaccttagaccttcggaagga-5


               Cross Primer Dimers:

DCLK1LSR with DCLK1SR
DCLK1LSR
5-catgtgctctttgcctcgac->
               |||| ||
            <-aggagatgcagtgaacgcag-5
```