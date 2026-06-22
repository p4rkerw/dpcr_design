# Introduction
Tgfb1 is a CKD/fibrotic marker.

# Design
- Fwd: 5'-GCTGAACCAAGGAGACGGAA-3'
- Rev: 5'-TCGACGTTTGGGACTGATCC-3'
- Product length: 112

# Design details
1. Go to GenBank (https://www.ncbi.nlm.nih.gov/gene/59086) to review isoforms. For transcript NM_021578.2, the coding sequence is from 146-1318 bp.
2. Go to Primer Blast, input the following. Note that we might need to tweak intro/exon-spanning settings to find the best primer-pairs.
   - Template: NM_021578.2. Range: 146-1318 bp
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
3. Select all Tgfb1 isoforms to include.
4. Choose a primer pair that spans exons.
    ```
            Primer pair 2
            Sequence (5'->3')	Template strand	Length	Start	Stop	Tm	GC%	Self complementarity	Self 3' complementarity
        Forward primer	GCTGAACCAAGGAGACGGAA	Plus	20	766	785	59.97	55.00	2.00	0.00
        Reverse primer	TCGACGTTTGGGACTGATCC	Minus	20	877	858	59.75	55.00	4.00	3.00
        Product length	112
        Products on intended targets
        >NM_021578.2 Rattus norvegicus transforming growth factor, beta 1 (Tgfb1), mRNA


        product length = 112
        Forward primer  1    GCTGAACCAAGGAGACGGAA  20
        Template        766  ....................  785

        Reverse primer  1    TCGACGTTTGGGACTGATCC  20
        Template        877  ....................  858
    ```