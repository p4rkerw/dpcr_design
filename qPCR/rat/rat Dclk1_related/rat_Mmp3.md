# Introduction
Mmp3 is a classical marker for senescence-associated-secretory-phenotype and act in ECM remodeling.

# Design
- Fwd: 5'-TGGACCCTGAGACCTTACCA-3'
- Rev: 5'-TCGCCAAAAGTGCCTGTCTT-3'
- Product length: 104 bp

# Design details
1. Go to GenBank (https://www.ncbi.nlm.nih.gov/gene/171045) to review isoforms. For transcript NM_133523.4, the coding sequence is from 59-1486 bp.
2. Go to Primer Blast, input the following. Note that we might need to tweak intro/exon-spanning settings to find the best primer-pairs.
   - Template: NM_133523.4. Range: 59-1486 bp
    - Product size: 80-250
    - Number of Primer pairs to return: 15
    - Primer Tm: 59 - 61. Optimal: 60. Max Tm difference: 1
    - Primer Pair specificity check search mode: user guided
    - Database: Rattus norvegicus (taxid:10116)
    - Exclude uncultured organisms: Check (we do not check exclude predicted Refseq transcripts here as rats have a lot of predicted transcripts, which exist but just not validated)
    - Allow splice variants: Check
    - Max primer pairs to screen: 1000
    - Primer size: 16-24. Opt: 20
    - Primer GC content %: 40-60
    - Max Poly-X: 3
    - Max self-complementarity: 4
    - Max pair-complementarity: 4
3. Select all corresponding isoforms to include.
4. Select a primer pair that ideally spans across exons.
    ```
            Primer pair 1
            Sequence (5'->3')	Template strand	Length	Start	Stop	Tm	GC%	Self complementarity	Self 3' complementarity
        Forward primer	TGGACCCTGAGACCTTACCA	Plus	20	897	916	59.51	55.00	3.00	0.00
        Reverse primer	TCGCCAAAAGTGCCTGTCTT	Minus	20	1000	981	60.47	50.00	3.00	1.00
        Product length	104
        Products on intended targets
        >NM_133523.4 Rattus norvegicus matrix metallopeptidase 3 (Mmp3), mRNA


        product length = 104
        Forward primer  1    TGGACCCTGAGACCTTACCA  20
        Template        897  ....................  916

        Reverse primer  1     TCGCCAAAAGTGCCTGTCTT  20
        Template        1000  ....................  981

        Products on allowed transcript variants
        >XM_039080743.2 PREDICTED: Rattus norvegicus matrix metallopeptidase 3 (Mmp3), transcript variant X1, mRNA


        product length = 104
        Forward primer  1    TGGACCCTGAGACCTTACCA  20
        Template        910  ....................  929

        Reverse primer  1     TCGCCAAAAGTGCCTGTCTT  20
        Template        1013  ....................  994
    ```