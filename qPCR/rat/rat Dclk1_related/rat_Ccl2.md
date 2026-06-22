# Introduction
Ccl2 is a chemokine. It can act as a monocyte recruitment marker.

# Design
- Fwd: 5'-GCCTGTTGTTCACAGTTGCT-3'
- Rev: 5'-CCTTATTGGGGTCAGCACAGA-3'
- Product size: 216 bp

# Design details
1. Go to GenBank (https://www.ncbi.nlm.nih.gov/gene/24770) to review isoforms. For transcript NM_031530.1, the coding sequence is from 76-522 bp.
2. Go to Primer Blast, input the following. Note that we might need to tweak intro/exon-spanning settings to find the best primer-pairs.
   - Template: NM_031530.1. Range: 76-522 bp
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
4. Choose a primer pair that spans exons.
    ```
            Primer pair 1
            Sequence (5'->3')	Template strand	Length	Start	Stop	Tm	GC%	Self complementarity	Self 3' complementarity
        Forward primer	GCCTGTTGTTCACAGTTGCT	Plus	20	101	120	59.26	50.00	4.00	1.00
        Reverse primer	CCTTATTGGGGTCAGCACAGA	Minus	21	316	296	59.72	52.38	3.00	2.00
        Product length	216
        Products on intended targets
        >NM_031530.1 Rattus norvegicus C-C motif chemokine ligand 2 (Ccl2), mRNA


        product length = 216
        Forward primer  1    GCCTGTTGTTCACAGTTGCT  20
        Template        101  ....................  120

        Reverse primer  1    CCTTATTGGGGTCAGCACAGA  21
        Template        316  .....................  296
    ```