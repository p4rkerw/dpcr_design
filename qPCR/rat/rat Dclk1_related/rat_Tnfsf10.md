# Intro
Tnfsf10 (TRAIL) is related to Dclk1 as well.

# Design
1. Go to Genbank record of [NM_145681.2](https://www.ncbi.nlm.nih.gov/nuccore/NM_145681.2?report=genbank). Click "Graphics" to view the graph reprensentation of the sequence. We can see that the protein coding sequence is from 1 to 876. I usually like to use CDS region for primer design. 
2. Go to Primer Blast, input the following. Note that we might need to tweak intro/exon-spanning settings to find the best primer-pairs.
   - Template: NM_031144.3. Range: 1-876
    - Product size: 80-200
    - Number of Primer pairs to return: 15
    - Primer Tm: 59 - 61. Optimal: 60. Max Tm difference: 1
    - Database: Rattus norvegicus (taxid:10116)
    - Exclude uncultured organisms: Check (we do not check exclude predicted Refseq transcripts here as rats have a lot of predicted transcripts, which exist but just not validated)
    - Allow splice variants: Check
    - Max primer pairs to screen: 1000
    - Primer size: 16-24. Opt: 20
    - Primer GC content %: 40-60.
    - Max Poly-X: 3
    - Max self-complementarity: 6
    - Max pair-complementarity: 6

3. It will ask you to include the following transcripts or not due to high similarity. We will select this as well.
```
Input PCR template
    NM_145681.2 Rattus norvegicus TNF superfamily member 10 (Tnfsf10), mRNA 
Range
    1 - 876

Your PCR template is highly similar to the following sequence(s) from the search database. To increase the chance of finding specific primers, please review the list below and select all sequences (within the given sequence ranges) that are intended or allowed targets.
Select:AllNone Selected:1
Accession	Title	Identity	Alignment length	Seq. start	Seq. stop
>XM_017590632.3	PREDICTED: Rattus norvegicus TNF superfamily member 10 (Tnfsf10), transcript variant X1, mRNA	100%	876	195	1070
```

4. Select one good primer pair from the results:
```
Primer pair 9
	Sequence (5'->3')	Template strand	Length	Start	Stop	Tm	GC%	Self complementarity	Self 3' complementarity
Forward primer	TTGAACAGACCTTGCTTGCAG	Plus	21	229	249	59.32	47.62	4.00	2.00
Reverse primer	CCGAGTGATCCCGGTAATGT	Minus	20	405	386	59.25	55.00	4.00	0.00
Product length	177
Products on intended targets
>NM_145681.2 Rattus norvegicus TNF superfamily member 10 (Tnfsf10), mRNA


product length = 177
Forward primer  1    TTGAACAGACCTTGCTTGCAG  21
Template        229  .....................  249

Reverse primer  1    CCGAGTGATCCCGGTAATGT  20
Template        405  ....................  386

>XM_017590632.3 PREDICTED: Rattus norvegicus TNF superfamily member 10 (Tnfsf10), transcript variant X1, mRNA


product length = 177
Forward primer  1    TTGAACAGACCTTGCTTGCAG  21
Template        423  .....................  443

Reverse primer  1    CCGAGTGATCCCGGTAATGT  20
Template        599  ....................  580
```

In summary we have our design:
```
rn8_Tnfsf10:
- Fwd: 5'-TTGAACAGACCTTGCTTGCAG  -3'
- Rev: 5'-CCGAGTGATCCCGGTAATGT -3'
- Product size: 177 bp
```