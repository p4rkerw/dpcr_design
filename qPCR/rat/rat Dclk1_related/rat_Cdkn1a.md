# Introduction
Cdkn1a is widely reported in aging and used as a scenescence marker.

# Primer
- Fwd: 5'-GATGACCTGGGAGGGGACAA-3'
- Rev: 5'-CGGCGCTTGGAGTGATAGAA-3'
- Product length: 215 bp

# Design details
1. Go to GenBank (https://www.ncbi.nlm.nih.gov/gene/114851) to review Cdkn1a isoforms. We can see that hte protein coding regions are shared between all isoforms (clicking into NM_080782.6, from 145-639bp).
2. Go to Primer Blast, input the following. Note that we might need to tweak intro/exon-spanning settings to find the best primer-pairs.
   - Template: NM_080782.6. Range: 145-639bp
    - Product size: 80-250
    - Number of Primer pairs to return: 15
    - Primer Tm: 59 - 61. Optimal: 60. Max Tm difference: 1
    - Primer Pair specificity check search mode: user guided
    - Database: Rattus norvegicus (taxid:10116)
    - Exclude uncultured organisms: Check (we do not check exclude predicted Refseq transcripts here as rats have a lot of predicted transcripts, which exist but just not validated)
    - Allow splice variants: Check
    - Max primer pairs to screen: 1000
    - Primer size: 16-24. Opt: 20
    - Primer GC content %: 40-60.
    - Max Poly-X: 3
    - Max self-complementarity: 4
    - Max pair-complementarity: 4
3. Select all highly-similar Cdkn1a isoforms to include.
4. Choose the primer pair that spans exons, which give the following result:
    ```
                Primer pair 4
            Sequence (5'->3')	Template strand	Length	Start	Stop	Tm	GC%	Self complementarity	Self 3' complementarity
        Forward primer	GATGACCTGGGAGGGGACAA	Plus	20	397	416	60.91	60.00	3.00	0.00
        Reverse primer	CGGCGCTTGGAGTGATAGAA	Minus	20	611	592	60.18	55.00	4.00	0.00
        Product length	215
        Products on intended targets
        >NM_080782.6 Rattus norvegicus cyclin-dependent kinase inhibitor 1A (Cdkn1a), transcript variant 1, mRNA


        product length = 215
        Forward primer  1    GATGACCTGGGAGGGGACAA  20
        Template        397  ....................  416

        Reverse primer  1    CGGCGCTTGGAGTGATAGAA  20
        Template        611  ....................  592

        >NM_001434560.1 Rattus norvegicus cyclin-dependent kinase inhibitor 1A (Cdkn1a), transcript variant 3, mRNA


        product length = 215
        Forward primer  1    GATGACCTGGGAGGGGACAA  20
        Template        351  ....................  370

        Reverse primer  1    CGGCGCTTGGAGTGATAGAA  20
        Template        565  ....................  546

        >NM_001434559.1 Rattus norvegicus cyclin-dependent kinase inhibitor 1A (Cdkn1a), transcript variant 2, mRNA


        product length = 215
        Forward primer  1    GATGACCTGGGAGGGGACAA  20
        Template        555  ....................  574

        Reverse primer  1    CGGCGCTTGGAGTGATAGAA  20
        Template        769  ....................  750

        >NM_001434561.1 Rattus norvegicus cyclin-dependent kinase inhibitor 1A (Cdkn1a), transcript variant 4, mRNA


        product length = 215
        Forward primer  1    GATGACCTGGGAGGGGACAA  20
        Template        473  ....................  492

        Reverse primer  1    CGGCGCTTGGAGTGATAGAA  20
        Template        687  ....................  668
    ```