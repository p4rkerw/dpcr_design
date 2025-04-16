# Introduction
Ipo8 (importin 8) is a common house keeping gene for rats. 

# Design
1. Go to Genbank record of [NM_001400882.1](https://www.ncbi.nlm.nih.gov/nuccore/NM_001400882.1?report=genbank). Click "Graphics" to view the graph reprensentation of the sequence. We can see that the protein coding sequence is from 217 to 3246. I usually like to use CDS region for primer design. 
2. Go to Primer Blast, input the following. Note that we might need to tweak intro/exon-spanning settings to find the best primer-pairs.
   - Template: NM_017101.1. Range: 217-3246
    - Product size: 80-200
    - Number of Primer pairs to return: 15
    - Primer Tm: 59 - 61. Optimal: 60. Max Tm difference: 1
    - Intron inclusion: Check
    - Intro length range: 500-10000
    - Database: Rattus norvegicus (taxid:10116)
    - Exclude uncultured organisms: Check (we do not check exclude predicted Refseq transcripts here as rats have a lot of predicted transcripts, which exist but just not validated)
    - Allow splice variants: Check
    - Primer size: 16-24. Opt: 20
    - Primer GC content %: 40-60.

3. Then we will be asked to include the following transcripts or not due to high similarity.
```
Input PCR template
    NM_001400882.1 Rattus norvegicus importin 8 (Ipo8), mRNA 
Range
    217 - 3246

Your PCR template is highly similar to the following sequence(s) from the search database. To increase the chance of finding specific primers, please review the list below and select all sequences (within the given sequence ranges) that are intended or allowed targets.
Select:AllNone Selected:2
Accession	Title	Identity	Alignment length	Seq. start	Seq. stop
>XM_039108919.2	PREDICTED: Rattus norvegicus importin 8 (Ipo8), transcript variant X2, mRNA	99.9%	3033	4950	7982
>XM_063286698.1	PREDICTED: Rattus norvegicus importin 8 (Ipo8), transcript variant X1, mRNA	99.97%	3018	4957	7974
```

4. Select the best primer pair from the results:
```
Primer pair 5
	Sequence (5'->3')	Template strand	Length	Start	Stop	Tm	GC%	Self complementarity	Self 3' complementarity
Forward primer	AACCAGTGGATGAGCGACAC	Plus	20	2671	2690	60.32	55.00	5.00	1.00
Reverse primer	CCAAGAGCACGCTTAGTCCT	Minus	20	2752	2733	59.75	55.00	4.00	2.00
Product length	82
Total intron size	1765 (between pos. 183474118 and 183472352 on NC_086022.1)
Products on intended targets
>NM_001400882.1 Rattus norvegicus importin 8 (Ipo8), mRNA


product length = 82
Forward primer  1     AACCAGTGGATGAGCGACAC  20
Template        2671  ....................  2690

Reverse primer  1     CCAAGAGCACGCTTAGTCCT  20
Template        2752  ....................  2733

>XM_039108919.2 PREDICTED: Rattus norvegicus importin 8 (Ipo8), transcript variant X2, mRNA


product length = 82
Forward primer  1     AACCAGTGGATGAGCGACAC  20
Template        7404  ....................  7423

Reverse primer  1     CCAAGAGCACGCTTAGTCCT  20
Template        7485  ....................  7466

>XM_063286698.1 PREDICTED: Rattus norvegicus importin 8 (Ipo8), transcript variant X1, mRNA


product length = 82
Forward primer  1     AACCAGTGGATGAGCGACAC  20
Template        7411  ....................  7430

Reverse primer  1     CCAAGAGCACGCTTAGTCCT  20
Template        7492  ....................  7473
```

In summary, our final primer pair is:
```
rn8_Ipo8:
- Fwd: 5'-AACCAGTGGATGAGCGACAC-3'
- Rev: 5'-CCAAGAGCACGCTTAGTCCT-3'
- Product size: 82 bp
```