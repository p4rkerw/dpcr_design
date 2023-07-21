This workflow describes how to create custom digital PCR primers targeting human GAPDH

1. First examine GAPDH using the ucsc genome browser [link](https://genome.ucsc.edu/cgi-bin/hgTracks?db=hg38&lastVirtModeType=default&lastVirtModeExtraState=&virtModeType=default&virtMode=0&nonVirtPosition=&position=chr12%3A6534517%2D6538371&hgsid=1656497518_Oi4KCCWcBnE3r8kqOCovV8yU3WR2) Note how GAPDH has a number common variants in the dbSNP tracks. SNVs can affect probe binding and should be avoided if possible. Fortunately, there are no repetitive elements in the repeat masker track. It is difficult to design probes that involve repetitive elements because there is a risk they will bind multiple regions in the genome with the same element.

![genome ucsc edu_cgi-bin_hgTracks_db=hg38 lastVirtModeType=default lastVirtModeExtraState= virtModeType=default virtMode=0 nonVirtPosition= position=chr12%3A6534517%2D6538371 hgsid=1656497518_Oi4KCCWcBnE3r8kqOCovV8y](https://github.com/p4rkerw/dpcr_design/assets/53058914/aae86718-6fbe-43ec-9bd1-ce75c79b792f)

2. We will now extract the nucleotide sequence of GAPDH using the ucsc table browser [link](https://genome.ucsc.edu/cgi-bin/hgTables?hgsid=1662123772_FpXeaHHsKgAAMUB54s7ucnMIsOVX&hgta_nextIntersectGroup=varRep&hgta_nextIntersectTrack=dbSnp155Composite&hgta_nextIntersectTable=dbSnp155Common&hgta_nextIntersectOp=none&hgta_nextMoreThreshold=100&hgta_nextLessThreshold=80&boolshad.hgta_nextInvertTable=0&boolshad.hgta_nextInvertTable2=0&hgta_doIntersectSubmit=submit). Here you can see that we have entered the genomic coordinates for GAPDH.

![genome ucsc edu_cgi-bin_hgTables_hgsid=1656497518_Oi4KCCWcBnE3r8kqOCovV8yU3WR2 clade=mammal org=Human db=hg38 hgta_group=map hgta_track=gold hgta_table=0 hgta_regionType=range position=chr12%3A6%2C534%2C517-6%2C538](https://github.com/p4rkerw/dpcr_design/assets/53058914/95a03760-5f49-4d72-8182-267b3eb4dbb3)


3. We have added an optional intersection with dbSNP to exclude regions that have common variants. 

![genome ucsc edu_cgi-bin_hgTables](https://github.com/p4rkerw/dpcr_design/assets/53058914/6b2c1f50-0d4b-4a48-ae66-2f611b3bd14b)


4. We now select Get Output to arrive at the screen below. We ask ucsc to mask any repetitive elements with N. 

![genome ucsc edu_cgi-bin_hgTables (1)](https://github.com/p4rkerw/dpcr_design/assets/53058914/dba1d260-3eeb-4150-ac18-fd31fe07ad86)


5. Here is the sequence.
```
>hg38_gold_chr12.1 range=chr12:6534517-6534536 5'pad=0 3'pad=0 strand=+ repeatMasking=N
GCTCTCTGCTCCTCCTGTTC
>hg38_gold_chr12.2 range=chr12:6534538-6534713 5'pad=0 3'pad=0 strand=+ repeatMasking=N
ACAGTCAGCCGCATCTTCTTTTGCGTCGCCAGGTGAAGACGGGCGGAGAG
AAACCCGGGAGGCTAGGGACGGCCTGAAGGCGGCAGGGGCGGGCGCAGGC
CGGATGTGTTCGCGCCGCTGCGGGGTGGGCCCGGGCGGCCTCCGCATTGC
AGGGGCGGGCGGAGGACGTGATGCGG
>hg38_gold_chr12.3 range=chr12:6534715-6534760 5'pad=0 3'pad=0 strand=+ repeatMasking=N
GCGGGCTGGGCATGGAGGCCTGGTGGGGGAGGGGAGGGGAGGCGTG
>hg38_gold_chr12.4 range=chr12:6534762-6534824 5'pad=0 3'pad=0 strand=+ repeatMasking=N
GTGTCGGCCGGGGCCACTAGGCGCTCACTGTTCTCTCCCTCCGCGCAGCC
GAGCCACATCGCT
>hg38_gold_chr12.5 range=chr12:6534826-6534918 5'pad=0 3'pad=0 strand=+ repeatMasking=N
AGACACCATGGGGAAGGTGAAGGTCGGAGTCAACGGGTGAGTTCGCGGGT
GGCTGGGGGGCCCTGGGCTGCGACCGCCCCCGAACCGCGTCTA
>hg38_gold_chr12.6 range=chr12:6534920-6534944 5'pad=0 3'pad=0 strand=+ repeatMasking=N
GAGCCTTGCGGGCTCCGGGTCTTTG
>hg38_gold_chr12.7 range=chr12:6534946-6534972 5'pad=0 3'pad=0 strand=+ repeatMasking=N
AGTCGTATGGGGGCAGGGTAGCTGTTC
>hg38_gold_chr12.8 range=chr12:6534974-6535060 5'pad=0 3'pad=0 strand=+ repeatMasking=N
CCGCAAGGAGAGCTCAAGGTCAGCGCTCGGACCTGGCGGAGCCCCGCACC
CAGGCTGTGGCGCCCTGTGCAGCTCCGCCCTTGCGGC
>hg38_gold_chr12.9 range=chr12:6535062-6535089 5'pad=0 3'pad=0 strand=+ repeatMasking=N
CCATCTGCCCGGAGCCTCCTTCCCCTAG
>hg38_gold_chr12.10 range=chr12:6535091-6535404 5'pad=0 3'pad=0 strand=+ repeatMasking=N
CCCCAGAAACAGGAGGTCCCTACTCCCGCCCGAGATCCCGACCCGGACCC
CTAGGTGGGGGACGCTTTCTTTCCTTTCGCGCTCTGCGGGGTCACGTGTC
GCAGAGGAGCCCCTCCCCCACGGCCTCCGGCACCGCAGGCCCCGGGATGC
TAGTGCGCAGCGGGTGCATCCCTGTCCGGATGCTGCGCCTGCGGTAGAGC
GGCCGCCATGTTGCAACCGGGAAGGAAATGAATGGGCAGCCGTTAGGAAA
GCCTGCCGGTGACTAACCCTGCGCTCCTGCCTCGATGGGTGGAGTCGCGT
GTGGCGGGGAAGTC
>hg38_gold_chr12.11 range=chr12:6535406-6535500 5'pad=0 3'pad=0 strand=+ repeatMasking=N
GGTGGAGCGAGGCTAGCTGGCCCGATTTCTCCTCCGGGTGATGCTTTTCC
TAGATTATTCTCTGGTAAATCAAAGAAGTGGGTTTATGGAGGTCC
>hg38_gold_chr12.12 range=chr12:6535502-6535529 5'pad=0 3'pad=0 strand=+ repeatMasking=N
CTTGTGTCCCCTCCCCGCAGAGGTGTGG
>hg38_gold_chr12.13 range=chr12:6535531-6535555 5'pad=0 3'pad=0 strand=+ repeatMasking=N
GGCTGTGGCATGGTGCCAAGCCGGG
>hg38_gold_chr12.14 range=chr12:6535557-6535614 5'pad=0 3'pad=0 strand=+ repeatMasking=N
GAAGCTGAGTCATGGGTAGTTGGAAAAGGACATTTCCACCGCAAAATGGC
CCCTCTGG
>hg38_gold_chr12.15 range=chr12:6535616-6535648 5'pad=0 3'pad=0 strand=+ repeatMasking=N
GGTGGCCCCTTCCTGCAGCGCCGGCTCACCTCA
>hg38_gold_chr12.16 range=chr12:6535650-6535791 5'pad=0 3'pad=0 strand=+ repeatMasking=N
GGCCCCGCCCTTCCCCTGCCAGCCTAGCGTTGACCCGACCCCAAAGGCCA
GGCTGTAAATGTCACCGGGAGGATTGGGTGTCTGGGCGCCTCGGGGAACC
TGCCCTTCTCCCCATTCCGTCTTCCGGAAACCAGATCTCCCA
>hg38_gold_chr12.17 range=chr12:6535793-6535907 5'pad=0 3'pad=0 strand=+ repeatMasking=N
CGCACCCTGGTCTGAGGTTAAATATAGCTGCTGACCTTTCTGTAGCTGGG
GGCCTGGGCTGGGGCTCTCTCCCATCCCTTCTCCCCACACACATGCACTT
ACCTGTGCTCCCACT
>hg38_gold_chr12.18 range=chr12:6535910-6536031 5'pad=0 3'pad=0 strand=+ repeatMasking=N
TGATTTCTGGAAAAGAGCTAGGAAGGACAGGCAACTTGGCAAATCAAAGC
CCTGGGACTAGGGGGTTAAAATACAGCTTCCCCTCTTCCCACCCGCCCCA
GTCTCTGTCCCTTTTGTAGGAG
>hg38_gold_chr12.19 range=chr12:6536033-6536398 5'pad=0 3'pad=0 strand=+ repeatMasking=N
GACTTAGAGAAGGGGTGGGCTTGCCCTGTCCAGTTAATTTCTGACCTTTA
CTCCTGCCCTTTGAGTTTGATGATGCTGAGTGTACAAGCGTTTTCTCCCT
AAAGGGTGCAGCTGAGCTAGGCAGCAGCAAGCATTCCTGGGGTGGCATAG
TGGGGTGGTGAATACCATGTACAAAGCTTGTGCCCAGACTGTGGGTGGCA
GTGCCCCACATGGCCGCTTCTCCTGGAAGGGCTTCGTATGACTGGGGGTG
TTGGGCAGCCCTGGAGCCTTCAGTTGCAGCCATGCCTTAAGCCAGGCCAG
CCTGGCAGGGAAGCTCAAGGGAGATAAAATTCAACCTCTTGGGCCCTCCT
GGGGGTAAGGAGATGC
>hg38_gold_chr12.20 range=chr12:6536400-6537066 5'pad=0 3'pad=0 strand=+ repeatMasking=N
GCATTCGCCCTCTTAATGGGGAGGTGGCCTAGGGCTGCTCACATATTCTG
GAGGAGCCTCCCCTCCTCATGCCTTCTTGCCTCTTGTCTCTTAGATTTGG
TCGTATTGGGCGCCTGGTCACCAGGGCTGCTTTTAACTCTGGTAAAGTGG
ATATTGTTGCCATCAATGACCCCTTCATTGACCTCAACTACATGGTGAGT
GCTACATGGTGAGCCCCAAAGCTGGTGTGGGAGGAGCCACCTGGCTGATG
GGCAGCCCCTTCATACCCTCACGTATTCCCCCAGGTTTACATGTTCCAAT
ATGATTCCACCCATGGCAAATTCCATGGCACCGTCAAGGCTGAGAACGGG
AAGCTTGTCATCAATGGAAATCCCATCACCATCTTCCAGGAGTGAGTGGA
AGACAGAATGGAAGAAATGTGCTTTGGGGAGGCAACTAGGATGGTGTGGC
TCCCTTGGGTATATGGTAACCTTGTGTCCCTCAATATGGTCCTGTCCCCA
TCTCCCCCCCACCCCCATAGGCGAGATCCCTCCAAAATCAAGTGGGGCGA
TGCTGGCGCTGAGTACGTCGTGGAGTCCACTGGCGTCTTCACCACCATGG
AGAAGGCTGGGGTGAGTGCAGGAGGGCCCGCGGGAGGGGAAGCTGACTCA
GCCCTGCAAAGGCAGGA
>hg38_gold_chr12.21 range=chr12:6537068-6537153 5'pad=0 3'pad=0 strand=+ repeatMasking=N
CCGGGTTCATAACTGTCTGCTTCTCTGCTGTAGGCTCATTTGCAGGGGGG
AGCCAAAAGGGTCATCATCTCTGCCCCCTCTGCTGA
>hg38_gold_chr12.22 range=chr12:6537155-6537942 5'pad=0 3'pad=0 strand=+ repeatMasking=N
GCCCCCATGTTCGTCATGGGTGTGAACCATGAGAAGTATGACAACAGCCT
CAAGATCATCAGGTGAGGAAGGCAGGGCCCGTGGAGAAGCGGCCAGCCTG
GCACCCTATGGACACGCTCCCCTGACTTGCGCCCCGCTCCCTCTTTCTTT
GCAGCAATGCCTCCTGCACCACCAACTGCTTAGCACCCCTGGCCAAGGTC
ATCCATGACAACTTTGGTATCGTGGAAGGACTCATGGTATGAGAGCTGGG
```

We will take the largest block from the above sequence:
```
GCATTCGCCCTCTTAATGGGGAGGTGGCCTAGGGCTGCTCACATATTCTG
GAGGAGCCTCCCCTCCTCATGCCTTCTTGCCTCTTGTCTCTTAGATTTGG
TCGTATTGGGCGCCTGGTCACCAGGGCTGCTTTTAACTCTGGTAAAGTGG
ATATTGTTGCCATCAATGACCCCTTCATTGACCTCAACTACATGGTGAGT
GCTACATGGTGAGCCCCAAAGCTGGTGTGGGAGGAGCCACCTGGCTGATG
GGCAGCCCCTTCATACCCTCACGTATTCCCCCAGGTTTACATGTTCCAAT
ATGATTCCACCCATGGCAAATTCCATGGCACCGTCAAGGCTGAGAACGGG
AAGCTTGTCATCAATGGAAATCCCATCACCATCTTCCAGGAGTGAGTGGA
AGACAGAATGGAAGAAATGTGCTTTGGGGAGGCAACTAGGATGGTGTGGC
TCCCTTGGGTATATGGTAACCTTGTGTCCCTCAATATGGTCCTGTCCCCA
TCTCCCCCCCACCCCCATAGGCGAGATCCCTCCAAAATCAAGTGGGGCGA
TGCTGGCGCTGAGTACGTCGTGGAGTCCACTGGCGTCTTCACCACCATGG
AGAAGGCTGGGGTGAGTGCAGGAGGGCCCGCGGGAGGGGAAGCTGACTCA
GCCCTGCAAAGGCAGGA
```

6. Double check that the sequence you have maps to GAPDH by copying the sequence and pasting it unto [BLAT](https://genome.ucsc.edu/cgi-bin/hgBlat) . Make sure the genome is set to Human. BLAT will return the following results. If you click on the browser link next to the match with the top score, it will take you to a multi-exon spanning region in GAPDH with no common variants or repetitive elements. Note how there are regions on other chromosomes that match a significant portion of our region. This is usually a bad sign that our selected region is not specific enough for primer design, but we will proceed to see what happens. 

![genome ucsc edu_cgi-bin_hgBlat](https://github.com/p4rkerw/dpcr_design/assets/53058914/e1eddad0-2571-4edf-9da7-a41c0c4b24f4)


7. Now that we have our sequence there are multiple options for primer design. The first and simplest option is to enter the sequence into the ThermoFisher primer design tool [link](https://www.thermofisher.com/order/custom-assay-design-tool/). This approach will design a primer and determine if its compatible with the hTERT and/or RNaseP CNV references, however, it will not give you the primer sequences. A better solution is to use Primer Express. In Primer Express, you can upload your sequence by creating a new TaqMan MGB quantification document and pasting it in the box. Click the green arrow to automatically design primers and probes


8. The top match gives us the following primers and probes:
F - ATGCTGGCGCTGAGTACGT
R - GCCTTCTCCATGGTGGTGAA
P - TGGAGTCCACTGGCG

9. We will now confirm that this primer set will amplify the region of interest using primer blast [link](https://www.ncbi.nlm.nih.gov/tools/primer-blast/index.cgi) . Enter our target sequence and forward and reverse primers as shown below. Change the database to Genomes for selected eukaryotic organisms highlighted in yellow. The RefSeq database only covers transcribed genes and does not include non-coding regions. Submit the results and check the results below:
Here are the primer blast results. Note how there are products that are not on the GAPDH template. This analysis does not take the probe into consideration, which adds another layer of specificity, but there are products that are a perfect match which is a concern. We can always try the next primer/probe option or a different target region. 

![www ncbi nlm nih gov_tools_primer-blast_primertool cgi_ctg_time=1689947109 job_key=RU-bVqIgr4iItqqzp9OOgd3In7Pw24Su8Q (1)](https://github.com/p4rkerw/dpcr_design/assets/53058914/b32250a8-37d0-40ae-bd74-0d3529843d8e)
