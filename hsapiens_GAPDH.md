This workflow describes how to create custom digital PCR primers targeting human GAPDH

1. First examine GAPDH using the ucsc genome browser [link]([https://genome.ucsc.edu/cgi-bin/hgTracks?db=hg38&lastVirtModeType=default&lastVirtModeExtraState=&virtModeType=default&virtMode=0&nonVirtPosition=&position=chrY%3A2786855%2D2787682&hgsid=1662373152_1DFFw2TBAhlHZq7mcWedJA5uZpN8](https://genome.ucsc.edu/cgi-bin/hgTracks?db=hg38&lastVirtModeType=default&lastVirtModeExtraState=&virtModeType=default&virtMode=0&nonVirtPosition=&position=chr12%3A6534517%2D6538371&hgsid=1656497518_Oi4KCCWcBnE3r8kqOCovV8yU3WR2)
2. Note how GAPDH has a number common variants in the dbSNP tracks. SNVs can affect probe binding and should be avoided if possible. Fortunately, there are no repetitive elements in the repeat masker track. It is difficult to design probes that involve repetitive elements because there is a risk they will bind multiple regions in the genome with the same element.


![genome ucsc edu_cgi-bin_hgTracks_db=hg38 lastVirtModeType=default lastVirtModeExtraState= virtModeType=default virtMode=0 nonVirtPosition= position=chrY%3A2786855%2D2787682 hgsid=1662373152_1DFFw2TBAhlHZq7mcWedJA5u](https://github.com/p4rkerw/dpcr_design/assets/53058914/8ca6ace4-736d-406e-a56d-4d11af8a597d)

2. We will now extract the nucleotide sequence of SRY using the ucsc table browser [link](https://genome.ucsc.edu/cgi-bin/hgTables?hgsid=1662123772_FpXeaHHsKgAAMUB54s7ucnMIsOVX&hgta_nextIntersectGroup=varRep&hgta_nextIntersectTrack=dbSnp155Composite&hgta_nextIntersectTable=dbSnp155Common&hgta_nextIntersectOp=none&hgta_nextMoreThreshold=100&hgta_nextLessThreshold=80&boolshad.hgta_nextInvertTable=0&boolshad.hgta_nextInvertTable2=0&hgta_doIntersectSubmit=submit). Here you can see that we have entered the genomic coordinates for SRY.

![genome ucsc edu_cgi-bin_hgTables_hgsid=1662123772_FpXeaHHsKgAAMUB54s7ucnMIsOVX clade=mammal org=Human db=hg38 hgta_group=genes hgta_track=gold hgta_table=0 hgta_regionType=range position=chrY%3A2%2C786%2C855-2%2C78](https://github.com/p4rkerw/dpcr_design/assets/53058914/c5f4634d-36b2-42a0-b11f-2461e70963a0)


3. We have added an optional intersection with dbSNP to exclude regions that have common variants. There are no common variants in the SRY gene body, but this step will be important in the future for handling regions that do contain variants. 

![genome ucsc edu_cgi-bin_hgTables](https://github.com/p4rkerw/dpcr_design/assets/53058914/66f8a3bb-ea6d-4a9e-b902-bdf513a2d1c1)

4. We now select Get Output > Genomic to arrive at the screen below. We will retrieve all coding sequences (CDS) from SRY exons. We also ask ucsc to mask any repetitive elements with N. 

![genome ucsc edu_cgi-bin_hgTables_hgsid=1662376742_cPo2aKJyODUdf7GS7DVtMeya2tSI hgta_geneSeqType=genomic hgta_doGenePredSequence=submit](https://github.com/p4rkerw/dpcr_design/assets/53058914/01163689-5451-45f5-aa6e-5ad41e98dfb1)


5. Here is the sequence. Note how the fasta file is arranged by ensembl transcripts. The capital letters indicate that this is exon 1 of SRY.
```
>hg38_knownGene_ENST00000383070.2_1 range=chrY:2786989-2787603 5'pad=0 3'pad=0 strand=- repeatMasking=N
ATGCAATCATATGCTTCTGCTATGTTAAGCGTATTCAACAGCGATGATTA
CAGTCCAGCTGTGCAAGAGAATATTCCCGCTCTCCGGAGAAGCTCTTCCT
TCCTTTGCACTGAAAGCTGTAACTCTAAGTATCAGTGTGAAACGGGAGAA
AACAGTAAAGGCAACGTCCAGGATAGAGTGAAGCGACCCATGAACGCATT
CATCGTGTGGTCTCGCGATCAGAGGCGCAAGATGGCTCTAGAGAATCCCA
GAATGCGAAACTCAGAGATCAGCAAGCAGCTGGGATACCAGTGGAAAATG
CTTACTGAAGCCGAAAAATGGCCATTCTTCCAGGAGGCACAGAAATTACA
GGCCATGCACAGAGAGAAATACCCGAATTATAAGTATCGACCTCGTCGGA
AGGCGAAGATGCTGCCGAAGAATTGCAGTTTGCTTCCCGCAGATCCCGCT
TCGGTACTCTGCAGCGAAGTGCAACTGGACAACAGGTTGTACAGGGATGA
CTGTACGAAAGCCACACACTCAAGAATGGAGCACCAGCTAGGCCACTTAC
CGCCCATCAACGCAGCCAGCTCACCGCAGCAACGGGACCGCTACAGCCAC
TGGACAAAGCTGTAG
```

6. Double check that the sequence you have maps to SRY exon 1 by copying the sequence and pasting it unto [BLAT](https://genome.ucsc.edu/cgi-bin/hgBlat) . Make sure the genome is set to Human. BLAT will return the following results. If you click on the browser link next to the match with the top score, it will take you back to the expected region in SRY. You can also try the same thing with the upstream promoter sequence.

![genome ucsc edu_cgi-bin_hgBlat](https://github.com/p4rkerw/dpcr_design/assets/53058914/dc59a939-c0d8-4a6f-bcb2-992cebd99a77)

7. Now that we have our sequence there are multiple options for primer design. The first and simplest option is to enter the sequence into the ThermoFisher primer design tool [link](https://www.thermofisher.com/order/custom-assay-design-tool/). This approach will design a primer and determine if its compatible with the hTERT and/or RNaseP CNV references, however, it will not give you the primer sequences. A better solution is to use Primer Express. In Primer Express, you can upload your sequence by creating a new TaqMan MGB quantification document and pasting it in the box. Click the green arrow to automatically design primers and probes

<img width="1119" alt="Screenshot 2023-07-21 082626" src="https://github.com/p4rkerw/dpcr_design/assets/53058914/73cd970e-3272-49e1-be29-27217cf8b8cf">

8. The top match gives us the following primers and probes:
F - GCGACCCATGAACGCATT
R - GCCATCTTGCGCCTCTGA
P - CGTGTGGTCTCGCG

9. We will now confirm that this primer set will amplify the region of interest using primer blast [link](https://www.ncbi.nlm.nih.gov/tools/primer-blast/index.cgi) . Enter our target sequence and forward and reverse primers as shown below. Change the database to Genomes for selected eukaryotic organisms highlighted in yellow. The RefSeq database only covers transcribed genes and does not include non-coding regions. In this case, we are analyzing exon 1 of SRY so it does not matter. However, if your target region is non-coding, this option may be a valuable crosscheck. Submit the results and check the results below:
![www ncbi nlm nih gov_tools_primer-blast_index cgi (2)](https://github.com/p4rkerw/dpcr_design/assets/53058914/d176bb5b-293f-4211-b0e2-c7d9ccfbbf43)

10. Here are the primer blast results. Note how there are products that are not on the SRY template, but they are not a perfect match. This analysis does not take the probe into consideration, which adds another layer of specificity. All of the primer / probe combinations generated by Primer Express will probably be fine, but cou can also try the next primer/probe option or you can try a different target region. 

![www ncbi nlm nih gov_tools_primer-blast_primertool cgi_ctg_time=1689942989 job_key=radzvp9kksy19gLzD5MmwXWIN_NYmyzuWQ CheckStatus=Check (2)](https://github.com/p4rkerw/dpcr_design/assets/53058914/a2743710-657d-428e-8176-1f8becbb5eed)
