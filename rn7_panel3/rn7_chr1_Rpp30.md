dpcr primer and probe design for rat rpp30 on chr1. This is a single copy reference gene.

1. First examine the gene using the ucsc genome browser [link](http://www.genome.ucsc.edu/cgi-bin/hgTracks?db=rn7&lastVirtModeType=default&lastVirtModeExtraState=&virtModeType=default&virtMode=0&nonVirtPosition=&position=chr1%3A233786112%2D233808954&hgsid=1672249230_IGwmcTsrcqJa5aejTsTa8dxaRAad). SNVs can affect probe binding and should be avoided if possible. There are also repetitive elements in the repeat masker track. It is difficult to design probes that involve repetitive elements because there is a risk they will bind multiple regions in the genome with the same element.

2. We will now extract the nucleotide sequence using View -> DNA and mask repeats with N. 

```
>rn7_gold_chr1.13 range=chr1:233808220-233808954 5'pad=0 3'pad=0 strand=+ repeatMasking=N
AAACTAGGAAAACTGCTTTTGGAATTATTTCTACAGTGAAGAAGCCCCGG
TCATCAGAAGCAGAGGATGAATCTCTTCCAGCGTGCAAGAAAGCTAAACA
TGAGGGCTGAGGAGACAGCCTGAGTCTCCATCACGCTGCTCCTCCCCTCA
CAGCTCATCAGTCACTGCAAATACACTCCGCTCGGCTGACGTTTTCACTA
AACTAGAAACCAAGTCTATAAAAACAGCTTCATATTCAGACATTAAAACA
GCAAATAAAACCCAGTGAAGCATTTTTAAAGACTAACGATTAATTTAGAT
ATACTTTTAAAAGAAAAACTATTACCCTTCATGTGAGTAATGAATAGCAG
TAGGTGCACTGAAACAAGATGTCTCGATATTGTAAAATATTGAAAAATAA
TAAATTAATGTTTTTTGTTCTTGGTACATATGGATTTGTAACTTTTACTA
TCCCAAAAAGTGGTTATTTTGAAGACTTAAGCTCTGTTGTGCAGGTGACT
TTAACCAACTGATTATGTTTTAAGCTCTTTGATGTCCTGCTCGGGTTAAA
GCCTTTCTGAAGGCCTCCTGGACCTGTGAAAGGAGAAGGGCACTCACAAG
AGTTGCTTATCCCCTCTATGTGCTCCCTCCTGCCTTCAAGTTGTCCTGAA
GACATATTCCTCCCTTTAGTTAGACATCATTCAGTAGCTAATACTGATTT
TCCTAGTTGCTATAGGTTTAAAGCATTTGGCTCAA
```

3. We will now check this sequence with BLAT to ensure that it's specific to our target region. Note how it has a very high score for the entire length of the sequence on the target chromosome.

```
   ACTIONS      QUERY   SCORE START   END QSIZE IDENTITY  CHROM  STRAND  START       END   SPAN
-----------------------------------------------------------------------------------------------
browser details YourSeq   735     1   735   735   100.0%  chr1   +   233808220 233808954    735
browser details YourSeq    32   477   540   735    97.2%  chr17  +    22232610  22233098    489
browser details YourSeq    24   243   278   735    69.3%  chr13  -    81265946  81265972     27
browser details YourSeq    24   419   447   735    92.9%  chr13  -    47313345  47313374     30
browser details YourSeq    23   581   607   735    92.6%  chr1   +    84823925  84823951     27
browser details YourSeq    21   112   132   735   100.0%  chr14  -    57160957  57160977     21
browser details YourSeq    20   512   531   735   100.0%  chr10  +    50546103  50546122     20
```

4. We will now use this sequence to design primers and probes in primer express using a TaqMan MGB quantification design. Below is the top primer / probe combination for our target region. Primer express predicts a forward primer self dimer and F+R and F+P cross dimers.  

- Forward Primer:GAAGAAGCCCCGGTCATCA 
- Reverse Primer:GCTTTCTTGCACGCTGGAA 
- Probe: AAGCAGAGGATGAATCT 

identify the amplicon using the ucsc in silico pcr tool for rn7 rat genome
```
GAAGAAGCCCCGGTCATCAgaagcagaggatgaatctcTTCCAGCGTGCAAGAAAGC
```

check neb NEBCutter tool to find restriction enzyme sites in this amplicon sequence
https://nc2.neb.com/NEBcutter2/?noredir

document enzymes with sites in the amplicon and exclude as potential digestion enzymes.


We will now double check this primer set for specificity using primer blast and our target sequence. We will also select "Genomes for selected eukaryotic organisms" and Rattus norvegicus to check if the primer set will amplify any regions elsewhere in the genome. The only template with a perfect match is our target sequence.

```
>NC_051336.1 Rattus norvegicus strain BN/NHsdMcwi chromosome 1, mRatBN7.2

product length = 57
Features associated with this product:
   ribonuclease p protein subunit p30

   ribonuclease p protein subunit p30 isoform x2

Forward primer  1          GAAGAAGCCCCGGTCATCA  19
Template        233808257  ...................  233808275

Reverse primer  1          GCTTTCTTGCACGCTGGAA  19
Template        233808313  ...................  233808295
```
