# Introduction
HILPDA (Hypoxia Inducible Lipid Droplet Associated) is a protein-coding gene that encodes the HILPDA protein, which is involved in lipid metabolism and storage within cells. HILPDA plays a significant role in the formation and regulation of lipid droplets. The expression of HILPDA is known to be upregulated under hypoxic conditions, suggesting its involvement in cellular responses to low oxygen levels. **HILPDA is one of increased DEGs in DCLK1-US overexpression in HEK293T cells.**

Here we will use the primer design from this paper: Targeting MYC induces lipid droplet accumulation by upregulation of HILPDA in clear cell renal cell carcinoma [paper linke](https://www.pnas.org/doi/10.1073/pnas.2310479121):
Fwd: 5'-AGCATGTGTTGAACCTCTACCT-3'
Rev: 5'-GTGGGCTCTGTGTTGGCTAG-3'

# Design
Check the design from the paper:
1. Navigate to the NCBI record of HILPDA [here](https://www.ncbi.nlm.nih.gov/gene/29923). The RefSeq ID for MANE select transript is NM_013332.4
2. Go to Primer Blast, input the following parameters:
   - PCR Template: NM_013332.4
   - Product Size: 80-200 bp
   - Primer Tm: 58-62 °C, Optimal 60 °C, Max Tm difference 1.5 °C
   - Exclusion: 
     - Exclude predicted Refseq transcripts.
     - Exclude uncultured/environmental samples sequences.
   - Organ
3. Input the above primers as "use my own primers".
4. The result is:
    ```
            Primer pair 1
            Sequence (5'->3')	Template strand	Length	Start	Stop	Tm	GC%	Self complementarity	Self 3' complementarity
        Forward primer	AGCATGTGTTGAACCTCTACCT	Plus	22	219	240	59.36	45.45	5.00	0.00
        Reverse primer	GTGGGCTCTGTGTTGGCTAG	Minus	20	369	350	60.67	60.00	4.00	4.00
        Product length	151
        Products on intended targets
        >NM_013332.4 Homo sapiens hypoxia inducible lipid droplet associated (HILPDA), transcript variant 1, mRNA


        product length = 151
        Forward primer  1    AGCATGTGTTGAACCTCTACCT  22
        Template        219  ......................  240

        Reverse primer  1    GTGGGCTCTGTGTTGGCTAG  20
        Template        369  ....................  350

        Products on potentially unintended templates
        >NM_001098786.2 Homo sapiens hypoxia inducible lipid droplet associated (HILPDA), transcript variant 2, mRNA


        product length = 151
        Forward primer  1    AGCATGTGTTGAACCTCTACCT  22
        Template        105  ......................  126

        Reverse primer  1    GTGGGCTCTGTGTTGGCTAG  20
        Template        255  ....................  236

        >XM_047446917.1 PREDICTED: Homo sapiens pistil-specific extensin-like protein (LOC124908089), mRNA


        product length = 98
        Forward primer  1     AGCATGTGTTGAACCTCTACCT  22
        Template        1440  ..GCG.A.........G.....  1419

        Reverse primer  1     GTGGGCTCTGTGTTGGCTAG  20
        Template        1343  ACCT..C.............  1362
    ```

# Summary
- Fwd: 5'-AGCATGTGTTGAACCTCTACCT-3'
- Rev: 5'-GTGGGCTCTGTGTTGGCTAG-3'
- Amplicon size: 151bp