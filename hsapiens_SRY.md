This workflow describes how to create custom digital PCR primers targeting the promoter region OR exon 1 of human SRY

1. First examine SRY using the ucsc genome browser [link](https://genome.ucsc.edu/cgi-bin/hgTracks?db=hg38&lastVirtModeType=default&lastVirtModeExtraState=&virtModeType=default&virtMode=0&nonVirtPosition=&position=chrY%3A2786855%2D2787682&hgsid=1662373152_1DFFw2TBAhlHZq7mcWedJA5uZpN8) Note how SRY has a single exon and that there are no common variants in the dbSNP tracks. SNVs can affect probe binding and should be avoided if possible. There are also no repetitive elements in the repeat masker track. It is difficult to design probes that involve repetitive elements because there is a risk they will bind multiple regions in the genome with the same element.


![genome ucsc edu_cgi-bin_hgTracks_db=hg38 lastVirtModeType=default lastVirtModeExtraState= virtModeType=default virtMode=0 nonVirtPosition= position=chrY%3A2786855%2D2787682 hgsid=1662373152_1DFFw2TBAhlHZq7mcWedJA5u](https://github.com/p4rkerw/dpcr_design/assets/53058914/8ca6ace4-736d-406e-a56d-4d11af8a597d)

2. We will now extract the nucleotide sequence of SRY using the ucsc table browser [link](https://genome.ucsc.edu/cgi-bin/hgTables?hgsid=1662123772_FpXeaHHsKgAAMUB54s7ucnMIsOVX&hgta_nextIntersectGroup=varRep&hgta_nextIntersectTrack=dbSnp155Composite&hgta_nextIntersectTable=dbSnp155Common&hgta_nextIntersectOp=none&hgta_nextMoreThreshold=100&hgta_nextLessThreshold=80&boolshad.hgta_nextInvertTable=0&boolshad.hgta_nextInvertTable2=0&hgta_doIntersectSubmit=submit). Here you can see that we have entered the genomic coordinates for SRY.

![genome ucsc edu_cgi-bin_hgTables_hgsid=1662123772_FpXeaHHsKgAAMUB54s7ucnMIsOVX clade=mammal org=Human db=hg38 hgta_group=genes hgta_track=gold hgta_table=0 hgta_regionType=range position=chrY%3A2%2C786%2C855-2%2C78](https://github.com/p4rkerw/dpcr_design/assets/53058914/c5f4634d-36b2-42a0-b11f-2461e70963a0)


3. We have added an optional intersection with dbSNP to exclude regions that have common variants. There are no common variants in the SRY gene body, but this step will be important in the future for handling regions that do contain variants. 

![genome ucsc edu_cgi-bin_hgTables](https://github.com/p4rkerw/dpcr_design/assets/53058914/66f8a3bb-ea6d-4a9e-b902-bdf513a2d1c1)

4. We now select Get Output > Genomic to arrive at the screen below. In this screen, we define the promoter region as 1kb upstream from the TSS. We will retrieve all coding sequences (CDS) from SRY exons. We also ask ucsc to mask any repetitive elements with N. 

![genome ucsc edu_cgi-bin_hgTables_hgsid=1662123772_FpXeaHHsKgAAMUB54s7ucnMIsOVX hgta_geneSeqType=genomic hgta_doGenePredSequence=submit (2)](https://github.com/p4rkerw/dpcr_design/assets/53058914/0a23ba67-9edb-424e-add7-22c60276d3b9)

