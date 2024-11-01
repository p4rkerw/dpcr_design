qPCR primer and probe design for DCLK1.
This is based on GRCh38.p14.
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
- Set $ of primers to return = 20
- Primer melting temperatures should have a maximum at 62.0.
- Use "No preference" for Exon junction span, as we have specified reverse primer range. If we require to span exon junctions, there will not be any primer pairs returned.
- Keep other parameters same as Step 2.1

## Step 3. Get probe using primer pairs from Step 2
This step will needs primer sets from Step 2.
### Step 3.1 For long isofrorm NM_004734.5
From step 1 graphical view, put cursor on the transcript and we can download the fasta. Copy that sequence into IDT PrimerQuest Custom design. In "Set Design Parameters for..." options, use qPCR (2Primers + Probe). Fill in the forward and reverse primers from **Step 2.1**. Hit "Get Assays". Try several times to select a primer-probe set that meets the requirements.

Now for NM_004734.5, we have:
- Forward primer: 5'-GGCTGATTTGACCCGAACTC-3'
- Reverse primer: 5'-GCCACATACATAACTCTCTCCTTC-3'
- Probe: 5'-TGGGCTCAAGAAGATTTCCAGCCT-3'
  
### Step 3.2 For short NM_001195415.2
From step 1 graphical view, put cursor on the transcript and we can download the fasta for the transcript. Follow the same procedure as in Step 3.1 to select the best primer-probe sets.

Now for NM_001195415.2, we have:
- Forward primer: 5'-GATTCCGCCGTTGGTATTCAG-3'
- Reverse primer: 5'-GACGCAAGTGACGTAGAGGA-3'
- Probe: 5'-TCTCTACTCCGCGCTCAGGCAA-3'

### Step 3.3 For shortest isoform NM_001195430.2
From step 1 graphical view, put cursor on the transcript and we can download the fasta for the transcript. Follow the same procedure as in Step 3.1 to select the best primer-probe sets.

Now for NM_001195430.2, we have:
- Forward primer: 5'-CGTTGGTATTCAGGTCCAACAC-3'
- Reverse primer: 5'-TCCTACTGAATCCAAGTCATCCG-3'
- probe: 5'-TAGTCAGCTCTCTACTCCGCGCTC-3'