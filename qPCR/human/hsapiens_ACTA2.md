# Introduction
ACTA2 (actin alpha 2, smooth muscle) provides instructions for making smooth muscle alpha-2 actin. This gene is upregulated in DCLK1-US overexpression in HEK293T cells.

We will use primer design from this paper: Actin alpha 2, smooth muscle, a transforming growth factor-β1-induced factor, regulates collagen production in human periodontal ligament cells via Smad2/3 pathway -[paper link](https://pmc.ncbi.nlm.nih.gov/articles/PMC10068375/):

Fwd: 5'-CAATGAGCTTCGTGTTGCCC-3'
Rev: 5'-GGCATAGAGAGACAGCACCG-3'
Amplicon size: 160bp.

# Design
Note ACTA2 has several transcript variants. The MANE select transcript is NM_001613.4. The shared exons are from 2 to 9. Run Primer Blast to check the primers.
1. Navigate to the NCBI record of ACTA2 [here](https://www.ncbi.nlm.nih.gov/gene/59). The RefSeq ID for MANE select transript is NM_001613.4.
2. Go to Primer Blast, input the following parameters:
   - PCR Template: NM_001613.4
   - Product Size: 80-200 bp
   - Primer Tm: 58-62 °C, Optimal 60 °C, Max Tm difference 1.5 °C
   - Exclusion: 
     - Exclude predicted Refseq transcripts.
     - Exclude uncultured/environmental samples sequences.
   - Organism: Homo sapiens
3. Input the above primers as "use my own primers".
4. The result shows that the above primer set amplifies exon 4-5 and covers most of ACTA2 transcript variants. Also the CG%, self-complementarity are pretty good.
    ```
            Primer pair 1
        Sequence (5'->3')	Template strand	Length	Start	Stop	Tm	GC%	Self complementarity	Self 3' complementarity
    Forward primer	CAATGAGCTTCGTGTTGCCC	Plus	20	345	364	60.11	55.00	4.00	0.00
    Reverse primer	GGCATAGAGAGACAGCACCG	Minus	20	504	485	60.25	60.00	2.00	2.00
    Product length	160
    Products on intended targets
    >NM_001613.4 Homo sapiens actin alpha 2, smooth muscle (ACTA2), transcript variant 2, mRNA


    product length = 160
    Forward primer  1    CAATGAGCTTCGTGTTGCCC  20
    Template        345  ....................  364

    Reverse primer  1    GGCATAGAGAGACAGCACCG  20
    Template        504  ....................  485

    Products on potentially unintended templates
    >NM_001406468.1 Homo sapiens actin alpha 2, smooth muscle (ACTA2), transcript variant 9, mRNA


    product length = 160
    Forward primer  1    CAATGAGCTTCGTGTTGCCC  20
    Template        572  ....................  591

    Reverse primer  1    GGCATAGAGAGACAGCACCG  20
    Template        731  ....................  712

    >NM_001406462.1 Homo sapiens actin alpha 2, smooth muscle (ACTA2), transcript variant 4, mRNA


    product length = 160
    Forward primer  1    CAATGAGCTTCGTGTTGCCC  20
    Template        776  ....................  795

    Reverse primer  1    GGCATAGAGAGACAGCACCG  20
    Template        935  ....................  916

    >NM_001406469.1 Homo sapiens actin alpha 2, smooth muscle (ACTA2), transcript variant 10, mRNA


    product length = 160
    Forward primer  1    CAATGAGCTTCGTGTTGCCC  20
    Template        216  ....................  235

    Reverse primer  1    GGCATAGAGAGACAGCACCG  20
    Template        375  ....................  356

    >NM_001406463.1 Homo sapiens actin alpha 2, smooth muscle (ACTA2), transcript variant 5, mRNA


    product length = 160
    Forward primer  1    CAATGAGCTTCGTGTTGCCC  20
    Template        859  ....................  878

    Reverse primer  1     GGCATAGAGAGACAGCACCG  20
    Template        1018  ....................  999

    >NM_001141945.3 Homo sapiens actin alpha 2, smooth muscle (ACTA2), transcript variant 1, mRNA


    product length = 160
    Forward primer  1    CAATGAGCTTCGTGTTGCCC  20
    Template        701  ....................  720

    Reverse primer  1    GGCATAGAGAGACAGCACCG  20
    Template        860  ....................  841

    >NM_001406467.1 Homo sapiens actin alpha 2, smooth muscle (ACTA2), transcript variant 8, mRNA


    product length = 160
    Forward primer  1    CAATGAGCTTCGTGTTGCCC  20
    Template        489  ....................  508

    Reverse primer  1    GGCATAGAGAGACAGCACCG  20
    Template        648  ....................  629

    >NM_001406464.1 Homo sapiens actin alpha 2, smooth muscle (ACTA2), transcript variant 6, mRNA


    product length = 160
    Forward primer  1    CAATGAGCTTCGTGTTGCCC  20
    Template        490  ....................  509

    Reverse primer  1    GGCATAGAGAGACAGCACCG  20
    Template        649  ....................  630

    >NM_001320855.2 Homo sapiens actin alpha 2, smooth muscle (ACTA2), transcript variant 3, mRNA


    product length = 160
    Forward primer  1    CAATGAGCTTCGTGTTGCCC  20
    Template        618  ....................  637

    Reverse primer  1    GGCATAGAGAGACAGCACCG  20
    Template        777  ....................  758

    >NM_001406471.1 Homo sapiens actin alpha 2, smooth muscle (ACTA2), transcript variant 11, mRNA


    product length = 160
    Forward primer  1    CAATGAGCTTCGTGTTGCCC  20
    Template        701  ....................  720

    Reverse primer  1    GGCATAGAGAGACAGCACCG  20
    Template        860  ....................  841

    ```

# Summary
- Fwd: 5'-CAATGAGCTTCGTGTTGCCC-3'
- Rev: 5'-GGCATAGAGAGACAGCACCG-3'
- Amplicon size: 160bp.