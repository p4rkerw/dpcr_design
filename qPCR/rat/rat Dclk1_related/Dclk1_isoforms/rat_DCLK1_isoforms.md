# Introduciton
This qPCR primer design is based on the rat Dclk1 gene and its isoforms detected in RAGE24 long read analysis. 

# Design Principles
When I design the primers, I usually use Primer Blast, and follow the below principles (the parameters can be more stringent if needed):
- For genes with multiple isoforms, I try to limit the forward and reverse primers to fall within the protein coding region (CDS).
- PCR product size: 100-200 bp.
- Primer melting temperature (Tm): 58-62 °C. Max Tm difference: 1 °C.
- \# of primers to return: set so that we can select primers that are either spanning exon-exon junctions or separated by introns.
- Search in the Refseq mRNA of the species we are designing primers for. Exclude uncultured/environmental sample sequences.
- Primer size: 16-24. Opt 20
- Primer GC content: 40-60%
- Max self complementarity: 5
- Max self 3' complementarity: 5

# Designs
## DCL (DCX domain)
This design is in dpcr_design/DCLK1/rat_chr2_DCLK1.md. There, I put the primers on exon instead of splice juntions.
-DCL_F: 5'-AGAACGTGAACCCCAATTGG-3'
-DCL_R: 5'-CTTGGCAGTCGCCAGAGAA-3'
-product size: 80bp

## Kinase domain (KD)
This design is in dpcr_design/DCLK1/rat_chr2_DCLK1.md. There, I put the primers on exon instead of splice juntions.
- KD_F: 5'-TGATCCAAAACGAGGTCTCCA-3'
- KD_R: 5'-CGGCACATCCATCTCTTCAA-3'
- Product size: 80bp

## DCL exclusive
XM_039103257.2 is detected in RAGE24 long read analysis, together with the other two DCL isoforms. Here I would design primers that target to the common exons between them, but unique exons in DCL isoforms. 
1. Perform a Blast on those three isoforms (XM_039103257.2, XM_039103258.2 and XM_039103260.2). We can see that starting from 1567bp of XM_039103260.2, the sequences align.
2. Check the exons of XM_039103260.2, and it happens that 1567-3455 is the last exon.
3. Go to Primer Blast, and choose "Primers common for a group of sequences".
    - Set the forward primer to start from 1567bp.
    - Follow the other paramters above.
4. Choose the design that results in fewest off-targets (and also shortest) possible. Also, choose the product size so that it is closer to 80-100bp so that we might take a look at abundancies between primers after qPCR.

Design:
- DCL_Only_F: 5'-TGTGCCTATCTGCATTGGTCT-3'
- DCL_Only_R: 5'-TGACGCAGCTCTGATTTCCA-3'
- Product size: 111bp

## DCL novel transcript
The sequence is predicted below:
```
>transcript61069.NC_086020.1.nic::NC_086020.1:141567376-141582594(+)
GCGGAGGgcggagcaggagaaggagggagaagggagggcatGTGAGCGAGTGAGACACAAGAAAAGCTTGCGCGCCACCGCCCTCCTCGGGAGAGAGGCTGGAGTGAAGCTGAGCGGAGAACCGCATTTCAATGAGGACCAGCTCCAGCGCATCAGTGCACTAGCGGCCGCAGATTCCAGACGCTCCTGCTCCGCCGCCCCAGCCGCGCCCAGCCCGGCGAGGACAGCTCCAGCAGCCGGCCACAGACGACCCAGCCTCCACTCGCAACCGGTTCCATACACAAGCCAGTCATGTCGTTCGGCAGAGATATGGAGTTGGAGCATTTTGATGAGCGGGACAAGGCTCAGAGGTACAGCAGGGGGTCCCGTGTGAATGGCCTGCCCAGCCCCACACACAGCGCCCACTGCAGCTTCTACCGCACCCGCACACTGCAGACGCTCAGCTCCGAGAAGAAAGCCAAAAAGGTTCGATTCTACAGAAACGGCGACCGCTACTTCAAAGGAATTGTGTATGCCATCTCCCCAGACCGCTTCAGATCCTTCGAGGCCCTGCTGGCTGATTTGACCCGAACTCTCTCGGATAATGTGAATTTGCCCCAGGGGGTGAGAACCATCTACACCATCGATGGACTCAAGAAGATCTCCAGCCTGGATCAGCTGGTGGAAGgtGAGAGCTATGTCTGTGGCTCCATTGAGCCCTTTAAGAAGCTGGAGTACACCAAGAACGTGAACCCCAATTGGTCAGTGAACGTCAAGACCACCTCAGCCTCCCGGGCAGTGTCTTCTCTGGCGACTGCCAAGGGGGGACCTTCGGAGGTTCGGGAGAATAAGGATTTCATTCGACCCAAGCTGGTCACCATCATCAGAAGTGGGGTGAAGCCACGAAAGGCTGTCAGAATCCTGTTGAACAAGAAGACGGCTCATTCCTTCGAGCAGGTTCTCACTGACATTACCGATGCTATCAAGCTGGACTCGGGTGTGGTGAAGCGTCTGTACACCCTGGATGGGAAGCAGGTAAGAACGGAGCATCAGGACTCTGGCTTTATGGGCGAGAGTCAGGAAACTGGGGTGGGAGGTTATACCTGGCACACAGTGTGGACCTGAAGCACACGTTTTGTTGGTTGTAGAAGGGACTGGGTTATTTAGTCATCAACAAACACTTTGTAATCTGATGTTAGTTGAATATTAGTACCAAACAGGATTAATCatcataataaagaaaaaacagagaGGGGATATCTTTGAAGAGTAAaccattatttttattgtttcagtaTTTATTTGCTTAGGATAACAATGCTGTTTTGTCTTCTGTTTTCAAATTTGTCCTATGTCCTTTAAGGCCTGCAAGAGCCTTAAAGCTAAGATTCTGAGAGAAACCGAGGCTGATGGGGCAAGATAGAAGTCATCTCAGAAGCGTTCATTAGTCAGCTTCAATTGAATtgtagagatttttttaaaactctagcTAAGGAATGGCATGCCCCCCTGGGCTACTTTGTCAGACATGGATGGGGAGCTGCAGGAAAACGCCACACTGTTCACATGCACAGTGTGTTTGCTACTCATTTGGAGTTTAGTGGGGCCTTTTTGCTTACGGTGATCATTTTCAGCATTATTACCTTTGCTCGAAATGTATGTTTTTGCAATGTATTTTATTGGTAtttaagaatttcatgcagtatattttgatcatgtccaTCCCCTACTACTTCCCCTAACGTCTCCCagatccacccccacctcctcacaCCCTTCCAACTTcatgtgctttatttatttatttttttaataacccACTGGATCCAATTTGTACTGCTTATATATTTAAGGGTGTGGGATCACCCCCTGAAGCACGGTCAACTTACCAGAAGCCTCTTACCCATAAAGCACTCACTTCCCCAGAAACCATTCCAAAATGTAGTTTTAATGTGGTTCTTTTGAATagcttttttttataatttgaagGCAATTTGAAGGATTTGCATGATTTAGCTCATCTTAAATTCTAAACTAGATTCATAACGAAGAGACTGTGTTAAGTGGAACTCTCATGAAAGTTCCTGAAGGCTAACACAACCAAACTTTATGAATGAGAATAGATGGTAACACTATAAAACGTGTCAGTCGTGAAGAATCCCTTCTCCCAGGGATGCCTTTAAATGTCCTAAGTTATTAAAATTCATTAGCAGCAAAGGAGTGTGCTGTTGTCTGTGACGATTGACCAGCTTCTGCTTGTCTCATCAAACCTGCATGTAGATAAGGATTTGTGGGGCCATATTCTCCATCTTATAGATCTAAGTGGCCTCAATGTTCTCTATGTATCAGGACCCAGCAAGTCCACCATGGGATGGTGAATTACGGTGGCAGCAAAGAGAGGAACAACACATTTAGACATTTCAGCCCATCTCCGGTTGTACAAAACATCTTGTAGTTGTGCGTTTCTCTGAGACGATTGTTTTCAACACGAGTGTTTatctgttttcaaaaaaaaa
```
1. Go to ORF finder, we can see that the coding sequence is from 292-1104 bp.
2. Select forward primer starts from 292 and reverse primer to ends before 1104 (if possible, design primers on/overlapping with CDS)

Design:
- DCL_Nov_F: 5'-AGCAGGTAAGAACGGAGCATC-3'
- DCL_Nov_R: 5'-ACCAACAAAACGTGTGCTTCA-3'
- Product size: 113 bp

## Kinase Domain only
Exon 1 is unique to kinase domain isoforms (DCLK-S isoforms). We restrict the forward primer to exon 1 in NM_053343.3 (1-165bp). 
1. Choose NM_053343.3 as the template in Primer Blast, and forward primer to end before 165 bp.
2. In the first result, select the other kinase domain isoforms to be acceptable templates.

Design:
- KD_only_F: 5'-GCTCTGGCTCTTGGCTATTGTC-3'
- KD_only_R: 5'-GATGGACTTGGTGACTTGCCG-3'
- Product size: 126 bp

## Ultrashort only isoform
The ultrashort protein isoform (56aa) is transcribed from both XM_063282640.1 and NM_021584.2. However, these CDS are not unique to them. In this case, I will put the primer pairs on CDS of XM_063282640.1 (can be found in the graphical view of XM063262640.1, from 975-1145bp). Also, since exon 1 is not in the DCL isoforms, we restrict the forward primer to be on exon 1 (1-993bp).
1. In Primer Blast, use XM_063282640.1 as the template, and set forward to be from 975bp to 1010bp and reverse primer to be before 1145bp.
    - Restricting forward to be 975-1010 bp forces it to be overlapping with exon 1.
2. In the design, allow it to also amplify NM_021584.2.

Design:
- US_only_F: 5'-CTCATAGAAGTTAATGGAACCCCTG-3'
- US_only_R: 5'-GAGAGAGGGCGGTACAGGT-3'
- Product size: 125bp