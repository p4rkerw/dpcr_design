qPCR primer and probe design for DCLK1.
All the alignments below (positions) is based on GRCh38.p14.
# Introduction

DCLK1 has several kinds of isoforms.
![alt text](image.png)
The longest isofrom can be represended by **NM_004734.5**. One shorter isoform can be represented by **NM_001195415.2**. There is another isoform (**NM_001195430.2**) which is different from the other two.
# Literature
- Sarkar S, O'Connell MR, Okugawa Y, Lee BS, Toiyama Y, Kusunoki M, Daboval RD, Goel A, Singh P. FOXD3 Regulates CSC Marker, DCLK1-S, and Invasive Potential: Prognostic Implications in Colon Cancer. Mol Cancer Res. 2017 Dec;15(12):1678-1691. doi: 10.1158/1541-7786.MCR-17-0287. Epub 2017 Aug 29. PMID: 28851816; PMCID: PMC5748292.
| Isoform Description      | Forward Primer            | Reverse Primer            | Comments              |
|--------------------------|----------------------------|----------------------------|------------------------|
| NM_004734.5 (long)    | GGAGTGGTGAAACGCCTGTAC   |  GGTTCCATTAACTGAGCTGG |     |
| NM_001195415.2 (short) | ACACTAAGACTGTGTCCATGTTAGAACTC    | AAGCCTTCCTCCGACACTTCT   |      |
- For internal controls, we can use GAPDH reported in this publication: Gao T, Wang M, Xu L, Wen T, Liu J, An G. DCLK1 is up-regulated and associated with metastasis and prognosis in colorectal cancer. J Cancer Res Clin Oncol. 2016 Oct;142(10):2131-40. doi: 10.1007/s00432-016-2218-0. Epub 2016 Aug 12. PMID: 27520310. 
GAPDH forward, 5′-AATCCCATCACCATCTTCCA-3′, GAPDH reverse 5′-TGGACTCCACGACGTACTCA-3′.

# DCLK1 primer design
## Step 1. Locate gene info
Go to NIH gene search [link](https://www.ncbi.nlm.nih.gov/gene) and search **Homo sapiens DCLK1**. The result is [here](https://www.ncbi.nlm.nih.gov/gene/9201). In the graphical view, we can see different isoforms of the transcripts. 
## Step 2. Design primer pairs
Put the cursor on the transcripts, we can see options for "GenBank Record". We can go directly to the GenBank record for the isoforms. On the right hand side under "Analyze this sequence" tab, we click on "Pick Primers". Since we would like to distinguish isoforms with high specificity, we will carry out primer pair design in Primer Blast first, and then use IDT Primer Quest to design corresponding probe.
### Step 2.1 For long isoform NM_004734.5
- Pick primers using NM_004734.5 as PCR template. 
- Limit PCR product size to 70-200. Change max Tm difference to 1. 
- In Exon/intron selection, set "Primer must span an exon-exon junction". 
- Under primer pair specificity checking parameters, make sure the search mode is "user guided". 
- Check "Exclude predicted Refseq transcripts" and "Exclude uncultured/environmentalsample sequences". 
- Pick Homo sapiens (taxid: 9606). Uncheck "Allow primers to amplify mRNA splice variants".
- In advanced settings, set Primer GC content to be 40%-60%.
From this result, pick primers that looks good. 
### Step 2.2 For short isoform NM_001195415.2
- Pick primers using NM_001195415.2 as PCR template.
- For Reverse Primer, set the range from 254 so that the reverse primer lands on the third exon, which can be used to differentiate from NM_001195430.2
- Use "No preference" for Exon junction span, as we have specified reverse primer range.
- Keep other parameters same as Step 2.1

The acceptable potentially unintended template should be only NM_001195416.2.
### Step 2.3 For shortest isoform NM_001195430.2
- Pick primers using NM_001195430.2 as template. 
- For Reverse Primer, set the range from 240 (just a little bit upstream of the third unique exon) so that the reverse primer lands on the third exon, which can be used to differentiate from other isoforms. 
- Set # of primers to return = 20
- Primer melting temperatures should have a maximum at 62.0.
- Use "No preference" for Exon junction span, as we have specified reverse primer range. If we require to span exon junctions, there will not be any primer pairs returned.
- Keep other parameters same as Step 2.1
### Step 2.4 For long/short isoform NM_004734.5+NM_001195415.2
In this case, we would like to make a primer pair for both long and short isoforms to prove that the isoform-specific expression is true.
- Pick primers using the short isoform **NM_001195415.2**. 
- Note that it shares the same as long isoforms starting from exon 2 to 12. So the forward primer should be from 159, and reverse primer should be ending before 1276.
- Set # of primers to return = 20
- Primer melting temperature should be a maximum at 62.0. Tm difference should be within 1.
- Use "No preference" for Exon junction span.
- Keep other parameters the same as Step 2.1. It will ask you if you also want the other isoforms. Check the boxes.
- Select primer pairs that is seperated by at least 1 introns or span across exons.
## Step 3. Get probe using primer pairs from Step 2
This step will needs primer sets from Step 2.
### Step 3.1 For long isofrorm NM_004734.5
From step 1 graphical view, put cursor on the transcript and we can download the fasta. Copy that sequence into IDT PrimerQuest Custom design. In "Set Design Parameters for..." options, use qPCR (2Primers + Probe). Fill in the forward and reverse primers from **Step 2.1**.
- For the probe, enter desired GC content to be 30%-80%. Length from 18-25 bp.

Hit "Get Assays". Try several times to select a primer-probe set that meets the requirements.

Take some time to review the oligos in OligoAnalyzer to check. Good primers should have low self-dimer and low hair-pin Tm.

Now for NM_004734.5, we have:
- Forward primer: 5'-GGCTGATTTGACCCGAACTC-3'
- Reverse primer: 5'-GCCACATACATAACTCTCTCCTTC-3'
- Probe: 5'-TGGGCTCAAGAAGATTTCCAGCCT-3'

Results from Primer blast is below. We can see that this primer pair covers all three RefSeq curated "long" form of DCLK1 transcripts.
```
Primer pair 1
	Sequence (5'->3')	Length	Tm	GC%	Self complementarity	Self 3' complementarity
Forward primer	GGCTGATTTGACCCGAACTC	20	58.91	55.00	3.00	2.00
Reverse primer	GCCACATACATAACTCTCTCCTTC	24	58.71	45.83	2.00	0.00
Products on target templates
>NM_001330071.2 Homo sapiens doublecortin like kinase 1 (DCLK1), transcript variant 5, mRNA


product length = 133
Forward primer  1    GGCTGATTTGACCCGAACTC  20
Template        552  ....................  571

Reverse primer  1    GCCACATACATAACTCTCTCCTTC  24
Template        684  ........................  661

>NM_001330072.2 Homo sapiens doublecortin like kinase 1 (DCLK1), transcript variant 6, mRNA


product length = 133
Forward primer  1    GGCTGATTTGACCCGAACTC  20
Template        453  ....................  472

Reverse primer  1    GCCACATACATAACTCTCTCCTTC  24
Template        585  ........................  562

>NM_004734.5 Homo sapiens doublecortin like kinase 1 (DCLK1), transcript variant 1, mRNA


product length = 133
Forward primer  1    GGCTGATTTGACCCGAACTC  20
Template        552  ....................  571

Reverse primer  1    GCCACATACATAACTCTCTCCTTC  24
Template        684  ........................  661
```
### Step 3.2 For short NM_001195415.2
From step 1 graphical view, put cursor on the transcript and we can download the fasta for the transcript. Follow the same procedure as in Step 3.1 to select the best primer-probe sets.

Now for NM_001195415.2, we have:
- Forward primer: 5'-GATTCCGCCGTTGGTATTCAG-3'
- Reverse primer: 5'-GACGCAAGTGACGTAGAGGA-3'
- Probe: 5'-TCTCTACTCCGCGCTCAGGCAA-3'

Results from Primer Blast shows that this primer pair binds to both "short" isoforms in RefSeq curated database.
```
Primer pair 1
	Sequence (5'->3')	Length	Tm	GC%	Self complementarity	Self 3' complementarity
Forward primer	GATTCCGCCGTTGGTATTCAG	21	59.40	52.38	4.00	1.00
Reverse primer	GACGCAAGTGACGTAGAGGA	20	59.48	55.00	4.00	0.00
Products on target templates
>NM_001195415.2 Homo sapiens doublecortin like kinase 1 (DCLK1), transcript variant 2, mRNA


product length = 195
Forward primer  1   GATTCCGCCGTTGGTATTCAG  21
Template        97  .....................  117

Reverse primer  1    GACGCAAGTGACGTAGAGGA  20
Template        291  ....................  272

>NM_001195416.2 Homo sapiens doublecortin like kinase 1 (DCLK1), transcript variant 3, mRNA


product length = 195
Forward primer  1   GATTCCGCCGTTGGTATTCAG  21
Template        97  .....................  117

Reverse primer  1    GACGCAAGTGACGTAGAGGA  20
Template        291  ....................  272

```

### Step 3.3 For shortest isoform NM_001195430.2
From step 1 graphical view, put cursor on the transcript and we can download the fasta for the transcript. Follow the same procedure as in Step 3.1 to select the best primer-probe sets.

Now for NM_001195430.2, we have:
- Forward primer: 5'-CGTTGGTATTCAGGTCCAACAC-3'
- Reverse primer: 5'-TCCTACTGAATCCAAGTCATCCG-3'
- probe: 5'-TAGTCAGCTCTCTACTCCGCGCTC-3'

Primer Blast results show that this pair only binds to transcript variant 4 of DCLK1
```
Primer pair 1
	Sequence (5'->3')	Length	Tm	GC%	Self complementarity	Self 3' complementarity
Forward primer	CGTTGGTATTCAGGTCCAACAC	22	59.52	50.00	5.00	1.00
Reverse primer	TCCTACTGAATCCAAGTCATCCG	23	59.62	47.83	4.00	2.00
Products on target templates
>NM_001195430.2 Homo sapiens doublecortin like kinase 1 (DCLK1), transcript variant 4, mRNA


product length = 194
Forward primer  1    CGTTGGTATTCAGGTCCAACAC  22
Template        105  ......................  126

Reverse primer  1    TCCTACTGAATCCAAGTCATCCG  23
Template        298  .......................  276


```

### Step 3.4 For long/short isoform NM_004734.5+NM_001195415.2
From step 1 graphical view, pur cursor on transcript and download fasta for the transcript(exons). Follow the same steps as Step 3.1 to select best primer-probe sets.

Now for long/short isoforms, we have:
- Forward primer: 5'-CCCTGGAGAAGAAGTGTCGG-3'
- Reverse primer: 5'-CATGTGCTCTTTGCCTCGAC-3'
- Probe: 5'-AGGAAGGCTTCCAGATTCCAGCT-3' (Cannot be FAM due to a G in the second position of the 5' end)

From Primer-Blast, we can see that this isoform amplifies both long and short isoforms (not the shortest one). Some off-target effect can be found on MTHFR, but the amplicon length is 3962 and there are mismatches, which should not be an issue for us.
```
Primer pair 1
	Sequence (5'->3')	Length	Tm	GC%	Self complementarity	Self 3' complementarity
Forward primer	CCCTGGAGAAGAAGTGTCGG	20	59.75	60.00	3.00	1.00
Reverse primer	CATGTGCTCTTTGCCTCGAC	20	59.55	55.00	4.00	2.00
Products on target templates
>NM_001195415.2 Homo sapiens doublecortin like kinase 1 (DCLK1), transcript variant 2, mRNA


product length = 187
Forward primer  1    CCCTGGAGAAGAAGTGTCGG  20
Template        328  ....................  347

Reverse primer  1    CATGTGCTCTTTGCCTCGAC  20
Template        514  ....................  495

>NM_001330071.2 Homo sapiens doublecortin like kinase 1 (DCLK1), transcript variant 5, mRNA


product length = 187
Forward primer  1     CCCTGGAGAAGAAGTGTCGG  20
Template        1398  ....................  1417

Reverse primer  1     CATGTGCTCTTTGCCTCGAC  20
Template        1584  ....................  1565

>NM_001330072.2 Homo sapiens doublecortin like kinase 1 (DCLK1), transcript variant 6, mRNA


product length = 187
Forward primer  1     CCCTGGAGAAGAAGTGTCGG  20
Template        1299  ....................  1318

Reverse primer  1     CATGTGCTCTTTGCCTCGAC  20
Template        1485  ....................  1466

>NM_001195416.2 Homo sapiens doublecortin like kinase 1 (DCLK1), transcript variant 3, mRNA


product length = 187
Forward primer  1    CCCTGGAGAAGAAGTGTCGG  20
Template        328  ....................  347

Reverse primer  1    CATGTGCTCTTTGCCTCGAC  20
Template        514  ....................  495

>NM_004734.5 Homo sapiens doublecortin like kinase 1 (DCLK1), transcript variant 1, mRNA


product length = 187
Forward primer  1     CCCTGGAGAAGAAGTGTCGG  20
Template        1398  ....................  1417

Reverse primer  1     CATGTGCTCTTTGCCTCGAC  20
Template        1584  ....................  1565

>NM_001410750.1 Homo sapiens methylenetetrahydrofolate reductase (MTHFR), transcript variant 3, mRNA


product length = 3962
Forward primer  1    CCCTGGAGAAGAAGTGTCGG  20
Template        277  T..G........T.A.G...  296

Forward primer  1     CCCTGGAGAAGAAGTGTCGG  20
Template        4238  .T....T.C..C........  4219

>NM_005957.5 Homo sapiens methylenetetrahydrofolate reductase (MTHFR), transcript variant 2, mRNA


product length = 3962
Forward primer  1    CCCTGGAGAAGAAGTGTCGG  20
Template        224  T..G........T.A.G...  243

Forward primer  1     CCCTGGAGAAGAAGTGTCGG  20
Template        4185  .T....T.C..C........  4166

>NM_001330358.2 Homo sapiens methylenetetrahydrofolate reductase (MTHFR), transcript variant 1, mRNA


product length = 3962
Forward primer  1    CCCTGGAGAAGAAGTGTCGG  20
Template        280  T..G........T.A.G...  299

Forward primer  1     CCCTGGAGAAGAAGTGTCGG  20
Template        4241  .T....T.C..C........  4222

```

