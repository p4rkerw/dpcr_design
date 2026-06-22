# Introduction
Cdkn2a is widely reported in aging and used as a scenescence marker.

# Design
- Fwd: 5'-GCGGTATTTGCGGTATCTACTC-3'
- Rev: 5'-CCAGAAGTGAAGCCAAGGAGA-3'
- Product length: 167bp

# Degisn details
1. Go to GenBank (https://www.ncbi.nlm.nih.gov/gene/25163) to review isoforms. We can see that the isoforms share part of the coding sequence. For transcript NM_031550.2, the shared sequence is roughly around the start of second exon to the end of CDS (172-525 bp).
2. Go to Primer Blast, input the following. Note that we might need to tweak intro/exon-spanning settings to find the best primer-pairs.
   - Template: NM_031550.2. Range: 172-525 bp
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
3. Select all Cdkn2a isoforms to include.
4. Choose a primer pair that spans exons.
    ```
            Primer pair 10
            Sequence (5'->3')	Template strand	Length	Start	Stop	Tm	GC%	Self complementarity	Self 3' complementarity
        Forward primer	GCGGTATTTGCGGTATCTACTC	Plus	22	402	423	59.01	50.00	4.00	2.00
        Reverse primer	CCAGAAGTGAAGCCAAGGAGA	Minus	21	568	548	59.65	52.38	2.00	0.00
        Product length	167
        Products on intended targets
        >NM_031550.2 Rattus norvegicus cyclin-dependent kinase inhibitor 2A (Cdkn2a), mRNA


        product length = 167
        Forward primer  1    GCGGTATTTGCGGTATCTACTC  22
        Template        402  ......................  423

        Reverse primer  1    CCAGAAGTGAAGCCAAGGAGA  21
        Template        568  .....................  548

        >XM_063287166.1 PREDICTED: Rattus norvegicus cyclin-dependent kinase inhibitor 2A (Cdkn2a), transcript variant X1, mRNA


        product length = 167
        Forward primer  1    GCGGTATTTGCGGTATCTACTC  22
        Template        358  ......................  379

        Reverse primer  1    CCAGAAGTGAAGCCAAGGAGA  21
        Template        524  .....................  504
    ```