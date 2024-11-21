The primer-probe design of these primer-probes are largely based on qPCR/hsapiens_chr13_DCLK1.md.

## Information
The gene structure in RefSeq can be found here [link](https://www.ncbi.nlm.nih.gov/gene?Db=gene&Cmd=DetailsSearch&Term=9201)
- For long isoforms represented by NM_004734.5: [link](https://www.ncbi.nlm.nih.gov/nuccore/NM_004734.5?report=fasta)
- For short isoforms represented by NM_001195415.2: [link](https://www.ncbi.nlm.nih.gov/nuccore/NM_004734.5?report=fasta)
- For shortest isoform NM_001195430.2: [link](https://www.ncbi.nlm.nih.gov/nuccore/NM_001195430.2?report=genbank)
- 

## Design
Based on previous (qPCR) design experiences, we will only paste certain exons of DCLK1 mRNA into Primer Express to achieve high specificity.
The starting **Primer Express** parameters are the same for all primer-probe sets. We can tweak the settings a little bit if no ideal primer-probe sets are found:

Note that Tm for the primers may not be the same as calculated on other platforms such as IDT OligoAnalyzer or Primer Blast.
```
Min Primer Tm: 55
Max Primer Tm: 65
Max Difference in Tm of Two Primers: 1
Min Primer %GC Content	40
Max Primer %GC Content	60
Max Primer 3' GC's	2
Primer 3' End Length	5
Primer 3' GC Clamp Residues	0
Primer Length	
Min Primer Length	18
Max Primer Length	24
Optimal Primer Length	20
Primer Composition	
Max Primer G Repeats	3
Max Num Ambig Residues in Primer	0
Primer Secondary Structure	
Max Primer Consec Base Pair	4
Max Primer Total Base Pair	8
Primer Site Uniqueness	
Max % Match in Primer	75
Max Consec Match in Primer	9
Max 3' Consec Match in Primer	7
Probe Tm	
Min Probe Tm	68
Max Probe Tm	72
Probe GC Content	
Min Probe %GC Content	30
Max Probe %GC Content	80
Probe Length	
Min Probe Length	13
Max Probe Length	25
Probe Composition	
Max Probe G Repeats	3
Max Num Ambig Residues in Probe	0
No G at 5' End in Probe	true
Select Probe with more C's than G's	false
Probe Secondary Structure	
Max Probe Consec Base Pair	4
Max Probe Total Base Pair	8
Amplicon	
Min Amplified Region Tm	0
Max Amplified Region Tm	85
Min Amplified Region Length	80
Max Amplified Region Length	150
General	
Max Primers / Probes	50
```
### 1. For Long + short isoform both spliced and unspliced
We will design a probe to detect all spliced/unspliced isoforms of DCLK1 (except NM_001195430.2). We will use the 11th exon of NM_004734.5 (>NM_004734.5:1696-1842):
```
GGGGGAGACCTTTTTGATGCCATTACTTCCACTAACAAATACACCGAGAGAGACGCCAGTGGGATGCTGT
ACAACCTAGCCAGCGCCATCAAATACCTGCATAGCCTGAACATCGTCCACCGTGATATCAAGCCAGAGAA
CCTGCTG
```
Load the above Primer Express settings and chose a primer-probe set. 
One primer-probe set (5' to 3') is:
```
Fwd: ACGCCAGTGGGATGCTGTA
Rev: CTTGATATCACGGTGGACGATGT
Probe: AACCTAGCCAGCGCCAT
```

***Make sure you save the Primer Express file! Also do not close Primer Blast page*** We will examine and change probe sequences later at the multiplexing step.

Use the fwd and rev primers to run a **Primer Blast** with the following settings:
- PCR template: NM_004734.5
- Primer Pair Specificity Check Search mode: User guided
- Database: Refseq mRNA
  - Exclusion: check both "Exclude predicted Refseq transcripts" and "Exclude uncultured/environmental sample sequences"
- Organism: Homo sapiens


The result is expected, as all transcripts will be amplified:
```
Primer pair 1
	Sequence (5'->3')	Template strand	Length	Start	Stop	Tm	GC%	Self complementarity	Self 3' complementarity
Forward primer	ACGCCAGTGGGATGCTGTA	Plus	19	1748	1766	61.29	57.89	5.00	2.00
Reverse primer	CTTGATATCACGGTGGACGATGT	Minus	23	1827	1805	60.49	47.83	8.00	2.00
Product length	80
Products on intended targets
>NM_004734.5 Homo sapiens doublecortin like kinase 1 (DCLK1), transcript variant 1, mRNA


product length = 80
Forward primer  1     ACGCCAGTGGGATGCTGTA  19
Template        1748  ...................  1766

Reverse primer  1     CTTGATATCACGGTGGACGATGT  23
Template        1827  .......................  1805

Products on allowed transcript variants
>NM_001195415.2 Homo sapiens doublecortin like kinase 1 (DCLK1), transcript variant 2, mRNA


product length = 80
Forward primer  1    ACGCCAGTGGGATGCTGTA  19
Template        678  ...................  696

Reverse primer  1    CTTGATATCACGGTGGACGATGT  23
Template        757  .......................  735

>NM_001330071.2 Homo sapiens doublecortin like kinase 1 (DCLK1), transcript variant 5, mRNA


product length = 80
Forward primer  1     ACGCCAGTGGGATGCTGTA  19
Template        1748  ...................  1766

Reverse primer  1     CTTGATATCACGGTGGACGATGT  23
Template        1827  .......................  1805

>NM_001330072.2 Homo sapiens doublecortin like kinase 1 (DCLK1), transcript variant 6, mRNA


product length = 80
Forward primer  1     ACGCCAGTGGGATGCTGTA  19
Template        1649  ...................  1667

Reverse primer  1     CTTGATATCACGGTGGACGATGT  23
Template        1728  .......................  1706

>NM_001195416.2 Homo sapiens doublecortin like kinase 1 (DCLK1), transcript variant 3, mRNA


product length = 80
Forward primer  1    ACGCCAGTGGGATGCTGTA  19
Template        678  ...................  696

Reverse primer  1    CTTGATATCACGGTGGACGATGT  23
Template        757  .......................  735

```


### 2. For Long + short isoforms spliced only
We will design a probe to detect spliced isoforms of DCLK1 (except NM_001195430.2). We will use the 6-16 th exon of NM_004734.5 (>NM_004734.5:1229-2054). 
We can use "Change region shown" to get the sequence:
```
TTAATGGAACCCCTGGTAGTCAGCTCTCTACTCCGCGCTCAGGCAAGTCGCCAAGCCCATCACCCACCAG
CCCAGGAAGCCTGCGGAAGCAGAGGAGCTCTCAGCATGGCGGCTCCTCTACGTCACTTGCGTCCACCAAA
GTCTGCAGCTCGATGGATGAGAACGATGGCCCTGGAGAAGAAGTGTCGGAGGAAGGCTTCCAGATTCCAG
CTACAATAACAGAACGATATAAAGTCGGAAGAACAATAGGAGATGGAAATTTTGCTGTTGTCAAGGAATG
TGTAGAAAGATCGACTGCTAGAGAGTATGCTCTGAAAATTATCAAGAAAAGCAAATGTCGAGGCAAAGAG
CACATGATCCAGAATGAAGTGTCTATTTTAAGAAGAGTGAAGCATCCCAATATCGTTCTTCTGATTGAGG
AGATGGATGTGCCAACTGAACTGTATCTTGTCATGGAATTAGTAAAGGGGGGAGACCTTTTTGATGCCAT
TACTTCCACTAACAAATACACCGAGAGAGACGCCAGTGGGATGCTGTACAACCTAGCCAGCGCCATCAAA
TACCTGCATAGCCTGAACATCGTCCACCGTGATATCAAGCCAGAGAACCTGCTGGTGTATGAGCACCAAG
ATGGCAGCAAATCACTGAAGCTGGGTGACTTTGGACTGGCCACCATTGTAGACGGCCCCCTGTACACAGT
CTGTGGCACCCCAACATACGTGGCTCCAGAAATCATTGCAGAGACTGGATACGGCCTCAAGGTGGACATC
TGGGCAGCAGGTGTAATCACTTATATCCTGCTGTGTGGTTTCCCTCCATTCCGTGG
```
A issue in this design is that Primer Express do not generate primer-pairs with enough specificity. A workaround is design primer pairs with Primer Blast, and then select probes in Primer Express.
#### 2.1 Primer Blast
Use the fwd and rev primers to run a **Primer Blast** with the following settings:
- PCR template: NM_004734.5
- Range: From 1229 (Forward primer) to 2054 (Reverse primer)
- PCR product size: 80-85 (to be consistent with previous dPCR primers)
- Primer melting temperature: 59-61, opt 60, max Tm diff = 1
- Intro Inclusion: True
  - Length range: 800 - 100000
- Primer Pair Specificity Check Search mode: User guided (will be asked to select allowed transcripts)
- Database: Refseq mRNA
  - Exclusion: check both "Exclude predicted Refseq transcripts" and "Exclude uncultured/environmental sample sequences"
- Organism: Homo sapiens
- Primer Parameters:
  - GC content: 40 - 60

One primer pair is (5' to 3'):
```
Fwd: ACCAAAGTCTGCAGCTCGATG
Rev: TTGTAGCTGGAATCTGGAAGCC
```
All transcripts will be amplified with this primer pair. Now annotate these primers in Primer Express using the mRNA exon sequence above. The reverse primer will need reverse complement to find. Then select probes between the primer following the MGB Probe Design guideline in Primer Express. Test the primer-probe set with **Primer Probe Set Test Tool** to get a good Tm, %GC and length. Might need to iterate many times for different primer pairs.

Now we have one primer probe set: (5'-3')
```
Fwd: ACCAAAGTCTGCAGCTCGATG
Rev: TTGTAGCTGGAATCTGGAAGCC
Probe: AGAAGAAGTGTCGGAGGAA
```
***Make sure you save the Primer Express file! Also do not close Primer Blast page*** We will examine and change probe sequences later at the multiplexing step.
The Primer Blast result is:
```
Primer pair 1
	Sequence (5'->3')	Template strand	Length	Start	Stop	Tm	GC%	Self complementarity	Self 3' complementarity
Forward primer	ACCAAAGTCTGCAGCTCGATG	Plus	21	1363	1383	60.94	52.38	6.00	2.00
Reverse primer	TTGTAGCTGGAATCTGGAAGCC	Minus	22	1444	1423	60.36	50.00	4.00	2.00
Product length	82
Total intron size	2950 (between pos. 35839092 and 35836141 on NC_000013.11)
Products on intended targets
>NM_001195415.2 Homo sapiens doublecortin like kinase 1 (DCLK1), transcript variant 2, mRNA


product length = 82
Forward primer  1    ACCAAAGTCTGCAGCTCGATG  21
Template        293  .....................  313

Reverse primer  1    TTGTAGCTGGAATCTGGAAGCC  22
Template        374  ......................  353

>NM_001330071.2 Homo sapiens doublecortin like kinase 1 (DCLK1), transcript variant 5, mRNA


product length = 82
Forward primer  1     ACCAAAGTCTGCAGCTCGATG  21
Template        1363  .....................  1383

Reverse primer  1     TTGTAGCTGGAATCTGGAAGCC  22
Template        1444  ......................  1423

>NM_001330072.2 Homo sapiens doublecortin like kinase 1 (DCLK1), transcript variant 6, mRNA


product length = 82
Forward primer  1     ACCAAAGTCTGCAGCTCGATG  21
Template        1264  .....................  1284

Reverse primer  1     TTGTAGCTGGAATCTGGAAGCC  22
Template        1345  ......................  1324

>NM_001195416.2 Homo sapiens doublecortin like kinase 1 (DCLK1), transcript variant 3, mRNA


product length = 82
Forward primer  1    ACCAAAGTCTGCAGCTCGATG  21
Template        293  .....................  313

Reverse primer  1    TTGTAGCTGGAATCTGGAAGCC  22
Template        374  ......................  353

>NM_004734.5 Homo sapiens doublecortin like kinase 1 (DCLK1), transcript variant 1, mRNA


product length = 82
Forward primer  1     ACCAAAGTCTGCAGCTCGATG  21
Template        1363  .....................  1383

Reverse primer  1     TTGTAGCTGGAATCTGGAAGCC  22
Template        1444  ......................  1423


```

### 3. For long isoforms spliced or unspliced
We use NM_004734.5 as a template. We will focus on exon 1-5, which are unique to long isoforms. We can get the sequence from RefSeq GenBank record (NM_004734.5:1-1228):
```
GCCGCCGCCCTCCTCTGGAGAGAGAGGCTGGAGTGAGGCTGTGCGAAGCGCCGCATTTCAATGAGGACGG
GCCGAGGCACATCCCTGCACTAGTGGCCGCAACCGAGGCGCCGCGCTCCAGCAGCTGCTGCCGCCCAGCC
CGGCCCCGCCGCCGCCCCCCAGCCCTGCAGCCCCGCAGCCCCGGCCGCGCCCAGCCCGGCGAGGACAGCA
CCAGGAGGCGGCCCCCAGCGCGGCCACAAAGACCCCCGGCGGCGTCTCTCCGCGGACCGGTCCTACTTGA
AGTCCATCATGTCCTTCGGCAGAGACATGGAGCTGGAGCACTTCGACGAGCGGGATAAGGCGCAGAGATA
CAGCCGAGGGTCGCGGGTGAACGGCCTGCCGAGCCCGACGCACAGCGCCCACTGCAGCTTCTACCGCACC
CGCACGCTGCAGACGCTCAGCTCCGAGAAGAAGGCCAAGAAAGTTCGTTTCTATCGAAACGGAGATCGAT
ACTTCAAAGGGATTGTGTATGCCATCTCCCCAGACCGGTTCCGATCTTTTGAGGCCCTGCTGGCTGATTT
GACCCGAACTCTGTCGGATAACGTGAATTTGCCCCAGGGAGTGAGAACAATCTACACCATTGATGGGCTC
AAGAAGATTTCCAGCCTGGACCAACTGGTGGAAGGAGAGAGTTATGTATGTGGCTCCATAGAGCCCTTCA
AGAAACTGGAGTACACCAAGAATGTGAACCCCAACTGGTCGGTGAACGTCAAGACCACCTCGGCTTCTCG
GGCAGTGTCTTCACTGGCCACTGCCAAAGGAAGCCCTTCAGAGGTGCGAGAGAATAAGGATTTCATTCGG
CCCAAGCTGGTCACCATCATCAGAAGTGGCGTGAAGCCACGGAAAGCTGTCAGGATTCTGCTGAACAAGA
AAACGGCTCATTCCTTTGAGCAGGTCCTCACCGATATCACCGATGCCATCAAGCTGGACTCGGGAGTGGT
GAAACGCCTGTACACGTTGGATGGGAAACAGGTGATGTGCCTTCAGGACTTTTTTGGTGATGATGACATT
TTTATTGCATGTGGACCGGAGAAGTTCCGTTACCAGGATGATTTCTTGCTAGATGAAAGTGAATGTCGAG
TGGTAAAGTCCACTTCTTACACCAAAATAGCTTCATCATCCCGCAGGAGCACCACCAAGAGCCCAGGACC
GTCCAGGCGTAGCAAGTCCCCTGCCTCCACCAGCTCAG
```

Paste this sequence into Primer Express. Generate primer-probe sets with below parameters.
```
Primer Tm	
Min Primer Tm	58
Max Primer Tm	60
Max Difference in Tm of Two Primers	1
Primer GC Content	
Min Primer %GC Content	40
Max Primer %GC Content	60
Max Primer 3' GC's	2
Primer 3' End Length	5
Primer 3' GC Clamp Residues	0
Primer Length	
Min Primer Length	18
Max Primer Length	24
Optimal Primer Length	20
Primer Composition	
Max Primer G Repeats	3
Max Num Ambig Residues in Primer	0
Primer Secondary Structure	
Max Primer Consec Base Pair	4
Max Primer Total Base Pair	8
Primer Site Uniqueness	
Max % Match in Primer	75
Max Consec Match in Primer	9
Max 3' Consec Match in Primer	7
Probe Tm	
Min Probe Tm	68
Max Probe Tm	71
Probe GC Content	
Min Probe %GC Content	30
Max Probe %GC Content	80
Probe Length	
Min Probe Length	16
Max Probe Length	25
Probe Composition	
Max Probe G Repeats	3
Max Num Ambig Residues in Probe	0
No G at 5' End in Probe	true
Select Probe with more C's than G's	false
Probe Secondary Structure	
Max Probe Consec Base Pair	4
Max Probe Total Base Pair	8
Amplicon	
Min Amplified Region Tm	0
Max Amplified Region Tm	85
Min Amplified Region Length	80
Max Amplified Region Length	90
General	
Max Primers / Probes	100
```

One primer-probe set is
```
Fwd: TTCTCGGGCAGTGTCTTCACT
Rev: TGGGCCGAATGAAATCCTTA
Probe: CTTCAGAGGTGCGAGAGA
```
***Make sure you save the Primer Express file! Also do not close Primer Blast page*** We will examine and change probe sequences later at the multiplexing step.

Blast the primer pairs (if specificity is not good, then you have to pick another primer pair). Exclude predicted or environmental RNA, and limit your search on homo sapiens. The result is here, which shows that all long isoforms are amplified:
```
Primer pair 1
	Sequence (5'->3')	Length	Tm	GC%	Self complementarity	Self 3' complementarity
Forward primer	TTCTCGGGCAGTGTCTTCACT	21	61.37	52.38	4.00	4.00
Reverse primer	TGGGCCGAATGAAATCCTTA	20	56.89	45.00	4.00	2.00
Products on target templates
>NM_001330071.2 Homo sapiens doublecortin like kinase 1 (DCLK1), transcript variant 5, mRNA


product length = 80
Forward primer  1    TTCTCGGGCAGTGTCTTCACT  21
Template        765  .....................  785

Reverse primer  1    TGGGCCGAATGAAATCCTTA  20
Template        844  ....................  825

>NM_001330072.2 Homo sapiens doublecortin like kinase 1 (DCLK1), transcript variant 6, mRNA


product length = 80
Forward primer  1    TTCTCGGGCAGTGTCTTCACT  21
Template        666  .....................  686

Reverse primer  1    TGGGCCGAATGAAATCCTTA  20
Template        745  ....................  726

>NM_004734.5 Homo sapiens doublecortin like kinase 1 (DCLK1), transcript variant 1, mRNA


product length = 80
Forward primer  1    TTCTCGGGCAGTGTCTTCACT  21
Template        765  .....................  785

Reverse primer  1    TGGGCCGAATGAAATCCTTA  20
Template        844  ....................  825


```

### 4. For long isoforms spliced only
For long isoforms spliced, we use Primer Blast first on exon 2-5, which are unique to long isoforms and can yield unique primers.
We can get the sequence from GenBank record (NM_004734.5: 270-1228)
```
GTCCTACTTGAAGTCCATCATGTCCTTCGGCAGAGACATGGAGCTGGAGCACTTCGACGAGCGGGATAAG
GCGCAGAGATACAGCCGAGGGTCGCGGGTGAACGGCCTGCCGAGCCCGACGCACAGCGCCCACTGCAGCT
TCTACCGCACCCGCACGCTGCAGACGCTCAGCTCCGAGAAGAAGGCCAAGAAAGTTCGTTTCTATCGAAA
CGGAGATCGATACTTCAAAGGGATTGTGTATGCCATCTCCCCAGACCGGTTCCGATCTTTTGAGGCCCTG
CTGGCTGATTTGACCCGAACTCTGTCGGATAACGTGAATTTGCCCCAGGGAGTGAGAACAATCTACACCA
TTGATGGGCTCAAGAAGATTTCCAGCCTGGACCAACTGGTGGAAGGAGAGAGTTATGTATGTGGCTCCAT
AGAGCCCTTCAAGAAACTGGAGTACACCAAGAATGTGAACCCCAACTGGTCGGTGAACGTCAAGACCACC
TCGGCTTCTCGGGCAGTGTCTTCACTGGCCACTGCCAAAGGAAGCCCTTCAGAGGTGCGAGAGAATAAGG
ATTTCATTCGGCCCAAGCTGGTCACCATCATCAGAAGTGGCGTGAAGCCACGGAAAGCTGTCAGGATTCT
GCTGAACAAGAAAACGGCTCATTCCTTTGAGCAGGTCCTCACCGATATCACCGATGCCATCAAGCTGGAC
TCGGGAGTGGTGAAACGCCTGTACACGTTGGATGGGAAACAGGTGATGTGCCTTCAGGACTTTTTTGGTG
ATGATGACATTTTTATTGCATGTGGACCGGAGAAGTTCCGTTACCAGGATGATTTCTTGCTAGATGAAAG
TGAATGTCGAGTGGTAAAGTCCACTTCTTACACCAAAATAGCTTCATCATCCCGCAGGAGCACCACCAAG
AGCCCAGGACCGTCCAGGCGTAGCAAGTCCCCTGCCTCCACCAGCTCAG
```
We start by Primer Blast to find primers that are separated by introns with following settings:
- PCR template: NM_004734.5 from 270 to 1228
- PCR product size: 80-85
- Melting temperature: 58-60 opt 60 max Tm diff 1
- Intron inclusion: checked
- Specificity check: checked
- Search mode: User guided
- Exclusion: exclude both predicted and uncultured/environmental
- Organism: Homo sapiens
- Primer Size: 18-24, opt 20
- Primer GC content(%): 40-60

Then we can get some primer pairs. Annotate the one primer pair (pick your favorite) in Primer Express. Then test and pick probes with **Primer Probe Test Tool", following the MGB probe guidelines. Then, we can get the following primer-probe set (5'-3'):
```
Fwd: TATTGCATGTGGACCGGAGA
Rev: AGTGGACTTTACCACTCGACA
Probe: TTCCGTTACCAGGATGAT
```
***Make sure you save the Primer Express file! Also do not close Primer Blast page*** We will examine and change probe sequences later at the multiplexing step.

The Primer Blast result for this transcript shows that it will only amplify long transcripts:
```
Primer pair 2
	Sequence (5'->3')	Template strand	Length	Start	Stop	Tm	GC%	Self complementarity	Self 3' complementarity
Forward primer	TATTGCATGTGGACCGGAGA	Plus	20	1053	1072	58.80	50.00	4.00	0.00
Reverse primer	AGTGGACTTTACCACTCGACA	Minus	21	1134	1114	58.69	47.62	5.00	0.00
Product length	82
Total intron size	76017 (between pos. 35947358 and 35871340 on NC_000013.11)
Products on intended targets
>NM_001330071.2 Homo sapiens doublecortin like kinase 1 (DCLK1), transcript variant 5, mRNA


product length = 82
Forward primer  1     TATTGCATGTGGACCGGAGA  20
Template        1053  ....................  1072

Reverse primer  1     AGTGGACTTTACCACTCGACA  21
Template        1134  .....................  1114

>NM_001330072.2 Homo sapiens doublecortin like kinase 1 (DCLK1), transcript variant 6, mRNA


product length = 82
Forward primer  1    TATTGCATGTGGACCGGAGA  20
Template        954  ....................  973

Reverse primer  1     AGTGGACTTTACCACTCGACA  21
Template        1035  .....................  1015

>NM_004734.5 Homo sapiens doublecortin like kinase 1 (DCLK1), transcript variant 1, mRNA


product length = 82
Forward primer  1     TATTGCATGTGGACCGGAGA  20
Template        1053  ....................  1072

Reverse primer  1     AGTGGACTTTACCACTCGACA  21
Template        1134  .....................  1114



```
## Multiplexing
At this point, we have collected 4 sets of primer-probes. As we can see, this process contains a lot of trial-and-errors. The design for primer pairs on a single exon is much easier than that on exon-exon junctions.

Now, we will test multiplexing primers in Multiple primer analyzer.

### Multiple primer analyzer 
Use thermofisher's [Multiple Primer Analyzer](https://www.thermofisher.com/us/en/home/brands/thermo-scientific/molecular-biology/molecular-biology-learning-center/molecular-biology-resource-library/thermo-scientific-web-tools/multiple-primer-analyzer.html).


We will then have to go back to Primer Express documents to adjust probe sequences so that the probes do not form cross primer dimers. When switching the probes, make sure to check "Interim results" if no primer-probe set can be returned. The probe should pass the tests in ideal case.

If there is no much room in probe selection, go back to Primer Blast results to switch primers, and then iterate the whole process again. (Long process warning!!)

After that, the final result is here:


- L+S spliced and unspliced
  - Fwd: ACGCCAGTGGGATGCTGTA
  - Rev: CTTGATATCACGGTGGACGATGT
  - Probe: AACCTAGCCAGCGCCAT
- L+S spliced 
  - Fwd: ACCAAAGTCTGCAGCTCGATG
  - Rev: TTGTAGCTGGAATCTGGAAGCC
  - Probe: AGAAGAAGTGTCGGAGGAA
- L spliced and unspliced
  - Fwd: TTCTCGGGCAGTGTCTTCACT
  - Rev: TGGGCCGAATGAAATCCTTA
  - Probe: CTTCAGAGGTGCGAGAGA
- L spliced
  - Fwd: TATTGCATGTGGACCGGAGA
  - Rev: AGTGGACTTTACCACTCGACA
  - Probe: TTCCGTTACCAGGATGAT


```
L+S_all_fwd ACGCCAGTGGGATGCTGTA
L+S_all_rev CTTGATATCACGGTGGACGATGT
L+S_all_probe AACCTAGCCAGCGCCAT
L+S_spliced_fwd ACCAAAGTCTGCAGCTCGATG
L+S_spliced_rev TTGTAGCTGGAATCTGGAAGCC
L+S_spliced_probe AGAAGAAGTGTCGGAGGAA
L_all_fwd TTCTCGGGCAGTGTCTTCACT
L_all_rev TGGGCCGAATGAAATCCTTA
L_all_probe CTTCAGAGGTGCGAGAGA
L_spliced_fwd TATTGCATGTGGACCGGAGA
L_spliced_rev AGTGGACTTTACCACTCGACA
L_spliced_probe TTCCGTTACCAGGATGAT
```
The result is
```
                Self-Dimers:

1 dimer for: L+S_all_rev
           5-cttgatatcacggtggacgatgt->
             | |||||||| |
<-tgtagcaggtggcactatagttc-5


               Cross Primer Dimers:


```

The self-dimer should be ok, as the Tm of the dimer sequence is ~30 degree C. At our extension temperature (60 degree C), the dimers should be denatured.