qPCR primer and probe design for MSMB.
This is based on GRCh38.p14.

# Introduction
MSMB is located on chr10, and is differentially expressed in rat data. 

# Primer probe design
## 1.
First search for MSMB in NCBI gene database. The result can be found [here](https://www.ncbi.nlm.nih.gov/gene/4477). 
## 2.
From the graphical result, we can see that there are only 2 variants. Place the cursor on the graphical representation of NM_002443.4 (longer variant), and click "GenBank record" of this transcript. Then, on the right hand side, choose "Pick Primers". This automatically redirects us to Primer Blast with this sequence as PCR Template. 
## 3.
In Primer Blast, edit in the following parameters:
- PCR product size: 70-200
- Number of primers to return: 20
- Primer melting tempeatures: 57-62. Max Tm difference = 1
- Choose "Primers must span an exon-exon junction" within Exon junction span. 
- Under "Search mode", choose "User guided"
- Use Refseq mRNA as database.
- Check both "Exclude predicted Refseq transcripts" and "Exclude uncultured/environmental sample sequences"
- Organism should be homo sapiens (taxid: 9606)
- **Check "Allow primer to amiplify mRNA splice variants"**
- Within "Advanced parameters", choose primer GC content% to be 40-60%

Then click "Get Primers".

Select primers to use for **Step 5** according to README.md.

## 4.
Download exon sequences. In the graphic view, put the cursor on the transcript NM_002443.4, and click under "Donwload FASTA:"
- NM_002443.4:
```
>ref|NM_002443.4|:1-486 Homo sapiens microseminoprotein beta (MSMB), transcript variant PSP94, mRNA
GTACCTGTCTATAAGGAGTCCTGCTTATCACAATGAATGTTCTCCTGGGCAGCGTTGTGATCTTTGCCAC
CTTCGTGACTTTATGCAATGCATCATGCTATTTCATACCTAATGAGGGAGTTCCAGGAGATTCAACCAGG
AAATGCATGGATCTCAAAGGAAACAAACACCCAATAAACTCGGAGTGGCAGACTGACAACTGTGAGACAT
GCACTTGCTACGAAACAGAAATTTCATGTTGCACCCTTGTTTCTACACCTGTGGGTTATGACAAAGACAA
CTGCCAAAGAATCTTCAAGAAGGAGGACTGCAAGTATATCGTGGTGGAGAAGAAGGACCCAAAAAAGACC
TGTTCTGTCAGTGAATGGATAATCTAATGTGCTTCTAGTAGGCACAGGGCTCCCAGGCCAGGCCTCATTC
TCCTCTGGCCTCTAATAGTCAATGATTGTGTAGCCATGCCTATCAGTAAAAAGATTTTTGAGCAAA
```

## 5. 
Open IDT primer quest, fill in the mRNA sequence. Under Custom Design Parameters, set design parameters for qPCR (2 Primers + Probe). Then change the parameters:
- Probe GC %: 30-80. Opt = 50
- Partial Design Input: fill in primer pairs selected from **Step 3**.

## 6. 
Verify using Oligo Analyzer that the primers are good.
Now we have:
- Forward Primer: 5'-CCAGGAGATTCAACCAGGAAATG-3'
- Reverse Primer: 5'-TCGTAGCAAGTGCATGTCTCA-3'
- Probe: 5'-ACACCCAATAAACTCGGAGTGGCA-3'