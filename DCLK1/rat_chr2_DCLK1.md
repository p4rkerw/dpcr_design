The primer probe design are based on GRCr8. 

Date: Nov/21/2024

Notes:
- validation in qPCR suggested that we should only use Dclk1 long+short spliced and unspliced primers (Dclk1 L+S all) and Dclk1 long spliced 
  and unspliced primers (Dclk1 L all).
## Information
- The Refseq record of this gene is at [link](https://www.ncbi.nlm.nih.gov/gene/83825). Current Refseq only has two curated isoforms for rats, corresponding to human short isoform (NM_001195416.2) and human shortest isoform (less documented NM_001195430.2), respectively.
  - The homology can be confirmed by Blastp on corresponding protein sequences (blasting mRNA is also fine, but the sequences are less similar). 
- Long isoform is chosen to be XM_039103253.2. Querying human long isoform protein NP_004725.1 (NM_004734.2) against the corresponding rat protein XP_038959181.1 yields following result: (only a few mismatches)
    ```
    Score	Expect	Method	Identities	Positives	Gaps
    1481 bits(3834) 	0.0 	Compositional matrix adjust. 	717/729(98%) 	724/729(99%) 	1/729(0%)

    Query  1    MSFGRDMELEHFDERDKAQRYSRGSRVNGLPSPTHSAHCSFYRTRTLQTLSSEKKAKKVR  60
    Sbjct  1    ............................................................  60

    Query  61   FYRNGDRYFKGIVYAISPDRFRSFEALLADLTRTLSDNVNLPQGVRTIYTIDGLKKISSL  120
    Sbjct  61   ............................................................  120

    Query  121  DQLVEGESYVCGSIEPFKKLEYTKNVNPNWSVNVKTTSASRAVSSLATAKGSPSEVRENK  180
    Sbjct  121  ...................................................G........  180

    Query  181  DFIRPKLVTIIRSGVKPRKAVRILLNKKTAHSFEQVLTDITDAIKLDSGVVKRLYTLDGK  240
    Sbjct  181  ............................................................  240

    Query  241  QVMCLQDFFGDDDIFIACGPEKFRYQDDFLLDESECRVVKSTSYTKIASSSRRSTTKSPG  300
    Sbjct  241  .................................................A...G......  300

    Query  301  PSRRSKSPASTSSVNGTPGSQLSTPRSGKSPSPSPTSPGSLRKQRSSQHGGSSTSLASTK  360
    Sbjct  301  .............................................I..........S...  360

    Query  361  VCSSMDENDGPGEEVSEEGFQIPATITERYKVGRTIGDGNFAVVKECVERSTAREYALKI  420
    Sbjct  361  ..............-.D..............................I............  419

    Query  421  IKKSKCRGKEHMIQNEVSILRRVKHPNIVLLIEEMDVPTELYLVMELVKGGDLFDAITST  480
    Sbjct  420  ............................................................  479

    Query  481  NKYTERDASGMLYNLASAIKYLHSLNIVHRDIKPENLLVYEHQDGSKSLKLGDFGLATIV  540
    Sbjct  480  S...........................................................  539

    Query  541  DGPLYTVCGTPTYVAPEIIAETGYGLKVDIWAAGVITYILLCGFPPFRGSGDDQEVLFDQ  600
    Sbjct  540  ............................................................  599

    Query  601  ILMGQVDFPSPYWDNVSDSAKELITMMLLVDVDQRFSAVQVLEHPWVNDDGLPENEHQLS  660
    Sbjct  600  ........................N.....N.............................  659

    Query  661  VAGKIKKHFNTGPKPNSTAAGVSVIALDHGFTIKRSGSLDYYQQPGMYWIRPPLLIRRGR  720
    Sbjct  660  ...............S............................................  719

    Query  721  FSDEDATRM  729
    Sbjct  720  .........  728
    ```
- Short isoform NM_053343.3 information [here](https://www.ncbi.nlm.nih.gov/nuccore/NM_053343.3?report=graph). This is homologous to human short isoform NM_001195416.2. If we blast the corresponding proteins, we can get:
    ```
    Score	Expect	Method	Identities	Positives	Gaps
    877 bits(2267) 	0.0 	Compositional matrix adjust. 	423/433(98%) 	429/433(99%) 	0/433(0%)

    Query  1    MLELIEVNGTPGSQLSTPRSGKSPSPSPTSPGSLRKQRISQHGGSSTSLSSTKVCSSMDE  60
    Sbjct  1    ......................................S..........A..........  60

    Query  61   NDGPGEEESDEGFQIPATITERYKVGRTIGDGNFAVVKECIERSTAREYALKIIKKSKCR  120
    Sbjct  61   .......V.E..............................V...................  120

    Query  121  GKEHMIQNEVSILRRVKHPNIVLLIEEMDVPTELYLVMELVKGGDLFDAITSTSKYTERD  180
    Sbjct  121  .....................................................N......  180

    Query  181  ASGMLYNLASAIKYLHSLNIVHRDIKPENLLVYEHQDGSKSLKLGDFGLATIVDGPLYTV  240
    Sbjct  181  ............................................................  240

    Query  241  CGTPTYVAPEIIAETGYGLKVDIWAAGVITYILLCGFPPFRGSGDDQEVLFDQILMGQVD  300
    Sbjct  241  ............................................................  300

    Query  301  FPSPYWDNVSDSAKELINMMLLVNVDQRFSAVQVLEHPWVNDDGLPENEHQLSVAGKIKK  360
    Sbjct  301  .................T.....D....................................  360

    Query  361  HFNTGPKPSSTAAGVSVIATTALDKERQVFRRRRNQDVRGRYKAQPAPPELNSESEDYSP  420
    Sbjct  361  ........N..............................S....................  420

    Query  421  SSSETVRSPNSPF  433
    Sbjct  421  .............  433
    ```
- Shortest isoform NM_021584.2 information [here](https://www.ncbi.nlm.nih.gov/nuccore/NM_021584.2?report=graph). This is homologous to human NM_001195430.2. Blasting corresponding protein (only 56 amino acid long!), we can get:
    ```
    Score	Expect	Method	Identities	Positives	Gaps
    107 bits(268) 	1e-38 	Compositional matrix adjust. 	56/56(100%) 	56/56(100%) 	0/56(0%)

    Query  1   MLELIEVNGTPGSQLSTPRSGKSPSPSPTSPGSLRKQRDLYRPLSSDDLDSVGDSV  56
    Sbjct  1   ........................................................  56
    ```

## Design guidelines
1. We will only consider certain exons of DCLK1 mRNA into Primer Express to achieve high specificity. 

2. The starting **Primer Express** parameters are the same for all primer-probe sets. We can tweak the settings a little bit if no ideal primer-probe sets are found. Note that Tm for the primers may not be the same as calculated on other platforms such as IDT OligoAnalyzer or Primer Blast. Here I loosened Max Primer 3' GC's.
    ```
    Min Primer Tm: 58
    Max Primer Tm: 60
    Max Difference in Tm of Two Primers: 1
    Min Primer %GC Content	40
    Max Primer %GC Content	60
    Max Primer 3' GC's	3
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
3. Setup for Primer Blast:
    ```
    - PCR product size 80-85
    - Melting temperatures: 58-62 Opt 60 Max Tm difference = 1
    - Search mode: User guided
    - Database: Refseq mRNA
    - Organism: Rattus norvegicus (taxid:10116)
    - Primer Size: 18 opt 20 max 24
    - Primer GC content: 40-60
    - Max C in primer 3' end: 3
    ```
4. Keep the Primer Blast results and Primer Express files. At the final step we will tweak the probe/primers based on multiplexing results.
## 1. For long+short spliced and unspliced
We use short isoform NM_053343.3 as the template. From the graph, we can see that exon 2- exon 10 are shared by long and short transcripts. After several trial and errors, we can use exon 5 as template to design primer probe sets. 

We can copy paste the sequence into Primer Express:
```
GAACACATGATCCAAAACGAGGTCTCCATCTTAAGGAGAGTGAAGCATCCGAACATTGTTCTCCTGATTGAAGAGATGGATGTGCCGACTGAACTATATCTTGTAATGGAGTTAGTAAAG
```
Use the above setting to derive primer probe sets. Pick one without self-dimer or significant cross-dimers. Blast it against NM_053343.3.

For a primer probe set with good specificity we have:
```
Fwd: TGATCCAAAACGAGGTCTCCA
Rev: CGGCACATCCATCTCTTCAA
Probe: AAGCATCCGAACATTGT
```
The Blast result for these primers is as shown below. One potential unintended template has amplicon size ~ 667 bp. But there are four mismatches and 
```
Primer pair 1
	Sequence (5'->3')	Template strand	Length	Start	Stop	Tm	GC%	Self complementarity	Self 3' complementarity
Forward primer	TGATCCAAAACGAGGTCTCCA	Plus	21	520	540	59.03	47.62	4.00	0.00
Reverse primer	CGGCACATCCATCTCTTCAA	Minus	20	599	580	57.97	50.00	3.00	3.00
Product length	80
Products on intended targets
>NM_053343.3 Rattus norvegicus doublecortin-like kinase 1 (Dclk1), transcript variant 1, mRNA


product length = 80
Forward primer  1    TGATCCAAAACGAGGTCTCCA  21
Template        520  .....................  540

Reverse primer  1    CGGCACATCCATCTCTTCAA  20
Template        599  ....................  580

Products on allowed transcript variants
>XM_039103256.2 PREDICTED: Rattus norvegicus doublecortin-like kinase 1 (Dclk1), transcript variant X12, mRNA


product length = 80
Forward primer  1    TGATCCAAAACGAGGTCTCCA  21
Template        710  .....................  730

Reverse primer  1    CGGCACATCCATCTCTTCAA  20
Template        789  ....................  770

>XM_008761005.4 PREDICTED: Rattus norvegicus doublecortin-like kinase 1 (Dclk1), transcript variant X11, mRNA


product length = 80
Forward primer  1    TGATCCAAAACGAGGTCTCCA  21
Template        713  .....................  733

Reverse primer  1    CGGCACATCCATCTCTTCAA  20
Template        792  ....................  773

>XM_039103255.2 PREDICTED: Rattus norvegicus doublecortin-like kinase 1 (Dclk1), transcript variant X10, mRNA


product length = 80
Forward primer  1    TGATCCAAAACGAGGTCTCCA  21
Template        710  .....................  730

Reverse primer  1    CGGCACATCCATCTCTTCAA  20
Template        789  ....................  770

>XM_063282639.1 PREDICTED: Rattus norvegicus doublecortin-like kinase 1 (Dclk1), transcript variant X9, mRNA


product length = 80
Forward primer  1    TGATCCAAAACGAGGTCTCCA  21
Template        761  .....................  781

Reverse primer  1    CGGCACATCCATCTCTTCAA  20
Template        840  ....................  821

>XM_017591138.3 PREDICTED: Rattus norvegicus doublecortin-like kinase 1 (Dclk1), transcript variant X8, mRNA


product length = 80
Forward primer  1    TGATCCAAAACGAGGTCTCCA  21
Template        761  .....................  781

Reverse primer  1    CGGCACATCCATCTCTTCAA  20
Template        840  ....................  821

>XM_039103254.2 PREDICTED: Rattus norvegicus doublecortin-like kinase 1 (Dclk1), transcript variant X7, mRNA


product length = 80
Forward primer  1     TGATCCAAAACGAGGTCTCCA  21
Template        1796  .....................  1816

Reverse primer  1     CGGCACATCCATCTCTTCAA  20
Template        1875  ....................  1856

>XM_039103253.2 PREDICTED: Rattus norvegicus doublecortin-like kinase 1 (Dclk1), transcript variant X6, mRNA


product length = 80
Forward primer  1     TGATCCAAAACGAGGTCTCCA  21
Template        1745  .....................  1765

Reverse primer  1     CGGCACATCCATCTCTTCAA  20
Template        1824  ....................  1805

>XM_017591139.3 PREDICTED: Rattus norvegicus doublecortin-like kinase 1 (Dclk1), transcript variant X5, mRNA


product length = 80
Forward primer  1     TGATCCAAAACGAGGTCTCCA  21
Template        1748  .....................  1768

Reverse primer  1     CGGCACATCCATCTCTTCAA  20
Template        1827  ....................  1808

>XM_039103252.2 PREDICTED: Rattus norvegicus doublecortin-like kinase 1 (Dclk1), transcript variant X4, mRNA


product length = 80
Forward primer  1     TGATCCAAAACGAGGTCTCCA  21
Template        1745  .....................  1765

Reverse primer  1     CGGCACATCCATCTCTTCAA  20
Template        1824  ....................  1805

>XM_039103250.2 PREDICTED: Rattus norvegicus doublecortin-like kinase 1 (Dclk1), transcript variant X3, mRNA


product length = 80
Forward primer  1     TGATCCAAAACGAGGTCTCCA  21
Template        1748  .....................  1768

Reverse primer  1     CGGCACATCCATCTCTTCAA  20
Template        1827  ....................  1808

>XM_039103249.2 PREDICTED: Rattus norvegicus doublecortin-like kinase 1 (Dclk1), transcript variant X2, mRNA


product length = 80
Forward primer  1     TGATCCAAAACGAGGTCTCCA  21
Template        1796  .....................  1816

Reverse primer  1     CGGCACATCCATCTCTTCAA  20
Template        1875  ....................  1856

>XM_039103247.2 PREDICTED: Rattus norvegicus doublecortin-like kinase 1 (Dclk1), transcript variant X1, mRNA


product length = 80
Forward primer  1     TGATCCAAAACGAGGTCTCCA  21
Template        1796  .....................  1816

Reverse primer  1     CGGCACATCCATCTCTTCAA  20
Template        1875  ....................  1856

Products on potentially unintended templates
>XM_006249360.5 PREDICTED: Rattus norvegicus ring finger protein 34 (Rnf34), transcript variant X3, mRNA


product length = 1688
Reverse primer  1     CGGCACATCCATCTCTTCAA  20
Template        2609  .AT.C.T....C........  2590

Reverse primer  1    CGGCACATCCATCTCTTCAA  20
Template        922  .T..T..............G  941

>XM_063281337.1 PREDICTED: Rattus norvegicus putative homeodomain transcription factor 1 (Phtf1), transcript variant X2, mRNA


product length = 667
Forward primer  1      TGATCCAAAACGAGGTCTCCA  21
Template        25475  ...........C.TTG....C  25495

Reverse primer  1      CGGCACATC-CATCTCTTCAA  20
Template        26142  .AC..G...T...........  26122

>XM_039081565.2 PREDICTED: Rattus norvegicus NIMA-related kinase 11 (Nek11), transcript variant X10, mRNA


product length = 2430
Forward primer  1     TGATCCAAAACGAGGTCTCCA  21
Template        7345  .T..T....GG..T.......  7325

Reverse primer  1     CGGCACATCCATCTCTTCAA  20
Template        4916  GTA..........C...A..  4935
```
## 2. For long + short spliced only
For spliced transcripts, it is better to use Primer Blast. We focus on exon 2 and 3 of the short isoform NM_053343.3. In Primer Blast:
- Use NM_053343.3 as PCR template. Reverse primer to 260 bp.
- PCR product size from 80-85. Return 20 primers
- Melting temperatures 58 to 62. Tm max = 1.
- Exon junction span: Primer must span an exon-exon junction
- Specificity check: enabled
- Search mode: user guided.
- Database: Refseq mRNA
- Exclusion: DO NOT exclude predicted
- Oragnism: Rattus norvegicus (taxid:10116)
- Allow splice variants: Allow primer to amplify mRNA splice variants.
- Primer size: 18-24. Opt 20
- Primer GC content: 40 - 60
- Max GC in primer 3' end: 3

We can get several set of primers. Then we paste the corresponding sequences into Primer Express. Annotate the primers and find probe. If no probe can be found, manually select probe sequence and test it in **Primer Probe Test Tool**. If the probe has good Tm, GC content and length, annotate the probe and run find primer/probe sets again. The run may fail but you can check the **interim result** to make sure that the probe passes all the tests.

One set we can get is:
```
Fwd: TCAAGAAGCATTTCAACACGGG
Rev: ATCAAGAGCGGTGGTTGCTA
Probe: ACGGCAGCTGGAGTT
```
The Primer Blast result is
```
Primer pair 1
	Sequence (5'->3')	Template strand	Length	Start	Stop	Tm	GC%	Self complementarity	Self 3' complementarity
Forward primer	TCAAGAAGCATTTCAACACGGG	Plus	22	1219	1240	59.71	45.45	3.00	2.00
Reverse primer	ATCAAGAGCGGTGGTTGCTA	Minus	20	1298	1279	59.39	50.00	3.00	2.00
Product length	80
Exon junction	1283/1284 (reverse primer) on template NM_053343.3
Products on intended targets
>XM_039103255.2 PREDICTED: Rattus norvegicus doublecortin-like kinase 1 (Dclk1), transcript variant X10, mRNA


product length = 80
Forward primer  1     TCAAGAAGCATTTCAACACGGG  22
Template        1409  ......................  1430

Reverse primer  1     ATCAAGAGCGGTGGTTGCTA  20
Template        1488  ....................  1469

>XM_017591138.3 PREDICTED: Rattus norvegicus doublecortin-like kinase 1 (Dclk1), transcript variant X8, mRNA


product length = 80
Forward primer  1     TCAAGAAGCATTTCAACACGGG  22
Template        1460  ......................  1481

Reverse primer  1     ATCAAGAGCGGTGGTTGCTA  20
Template        1539  ....................  1520

>XM_039103252.2 PREDICTED: Rattus norvegicus doublecortin-like kinase 1 (Dclk1), transcript variant X4, mRNA


product length = 80
Forward primer  1     TCAAGAAGCATTTCAACACGGG  22
Template        2444  ......................  2465

Reverse primer  1     ATCAAGAGCGGTGGTTGCTA  20
Template        2523  ....................  2504

>XM_039103250.2 PREDICTED: Rattus norvegicus doublecortin-like kinase 1 (Dclk1), transcript variant X3, mRNA


product length = 80
Forward primer  1     TCAAGAAGCATTTCAACACGGG  22
Template        2447  ......................  2468

Reverse primer  1     ATCAAGAGCGGTGGTTGCTA  20
Template        2526  ....................  2507

>XM_039103247.2 PREDICTED: Rattus norvegicus doublecortin-like kinase 1 (Dclk1), transcript variant X1, mRNA


product length = 80
Forward primer  1     TCAAGAAGCATTTCAACACGGG  22
Template        2495  ......................  2516

Reverse primer  1     ATCAAGAGCGGTGGTTGCTA  20
Template        2574  ....................  2555

>NM_053343.3 Rattus norvegicus doublecortin-like kinase 1 (Dclk1), transcript variant 1, mRNA


product length = 80
Forward primer  1     TCAAGAAGCATTTCAACACGGG  22
Template        1219  ......................  1240

Reverse primer  1     ATCAAGAGCGGTGGTTGCTA  20
Template        1298  ....................  1279
```

## 3. For Long spliced and unspliced
With XM_039103253.2, we can select the first 5 exons that are unique to long transcripts. After several trials, we can find that it is easier to select the 3rd exon (XM_039103253.2: 830-1176). In Primer Express, we can get the following pairs:
```
Fwd: AGAACGTGAACCCCAATTGG
Rev: CTTGGCAGTCGCCAGAGAA
Probe: ACGTCAAGACCACCTCA
```
Bast the primer pairs to check specificity. The Primer Blast results is shown below:
```
Primer pair 1
	Sequence (5'->3')	Length	Tm	GC%	Self complementarity	Self 3' complementarity
Forward primer	AGAACGTGAACCCCAATTGG	20	58.38	50.00	8.00	8.00
Reverse primer	CTTGGCAGTCGCCAGAGAA	19	60.00	57.89	5.00	2.00
Products on target templates
>XM_039103260.2 PREDICTED: Rattus norvegicus doublecortin-like kinase 1 (Dclk1), transcript variant X15, mRNA


product length = 80
Forward primer  1    AGAACGTGAACCCCAATTGG  20
Template        884  ....................  903

Reverse primer  1    CTTGGCAGTCGCCAGAGAA  19
Template        963  ...................  945

>XM_039103258.2 PREDICTED: Rattus norvegicus doublecortin-like kinase 1 (Dclk1), transcript variant X14, mRNA


product length = 80
Forward primer  1    AGAACGTGAACCCCAATTGG  20
Template        884  ....................  903

Reverse primer  1    CTTGGCAGTCGCCAGAGAA  19
Template        963  ...................  945

>XM_039103257.2 PREDICTED: Rattus norvegicus doublecortin-like kinase 1 (Dclk1), transcript variant X13, mRNA


product length = 80
Forward primer  1    AGAACGTGAACCCCAATTGG  20
Template        884  ....................  903

Reverse primer  1    CTTGGCAGTCGCCAGAGAA  19
Template        963  ...................  945

>XM_039103254.2 PREDICTED: Rattus norvegicus doublecortin-like kinase 1 (Dclk1), transcript variant X7, mRNA


product length = 80
Forward primer  1    AGAACGTGAACCCCAATTGG  20
Template        884  ....................  903

Reverse primer  1    CTTGGCAGTCGCCAGAGAA  19
Template        963  ...................  945

>XM_039103253.2 PREDICTED: Rattus norvegicus doublecortin-like kinase 1 (Dclk1), transcript variant X6, mRNA


product length = 80
Forward primer  1    AGAACGTGAACCCCAATTGG  20
Template        884  ....................  903

Reverse primer  1    CTTGGCAGTCGCCAGAGAA  19
Template        963  ...................  945

>XM_017591139.3 PREDICTED: Rattus norvegicus doublecortin-like kinase 1 (Dclk1), transcript variant X5, mRNA


product length = 80
Forward primer  1    AGAACGTGAACCCCAATTGG  20
Template        884  ....................  903

Reverse primer  1    CTTGGCAGTCGCCAGAGAA  19
Template        963  ...................  945

>XM_039103252.2 PREDICTED: Rattus norvegicus doublecortin-like kinase 1 (Dclk1), transcript variant X4, mRNA


product length = 80
Forward primer  1    AGAACGTGAACCCCAATTGG  20
Template        884  ....................  903

Reverse primer  1    CTTGGCAGTCGCCAGAGAA  19
Template        963  ...................  945

>XM_039103250.2 PREDICTED: Rattus norvegicus doublecortin-like kinase 1 (Dclk1), transcript variant X3, mRNA


product length = 80
Forward primer  1    AGAACGTGAACCCCAATTGG  20
Template        884  ....................  903

Reverse primer  1    CTTGGCAGTCGCCAGAGAA  19
Template        963  ...................  945

>XM_039103249.2 PREDICTED: Rattus norvegicus doublecortin-like kinase 1 (Dclk1), transcript variant X2, mRNA


product length = 80
Forward primer  1    AGAACGTGAACCCCAATTGG  20
Template        884  ....................  903

Reverse primer  1    CTTGGCAGTCGCCAGAGAA  19
Template        963  ...................  945

>XM_039103247.2 PREDICTED: Rattus norvegicus doublecortin-like kinase 1 (Dclk1), transcript variant X1, mRNA


product length = 80
Forward primer  1    AGAACGTGAACCCCAATTGG  20
Template        884  ....................  903

Reverse primer  1    CTTGGCAGTCGCCAGAGAA  19
Template        963  ...................  945
```
## 4. For Long spliced only
Using the XM_039103253.2, we will focus on exon 1-5. Copy XM_039103253.2:1-1393 into Primer Express and annotate the junctions. 

One primer set is 
```
Fwd: TCCGTTACCAGGATGATTTCTTG
Rev: CCGATGCTATTTTGGTGTAGGAA
Probe: TAGATGAAAGTGAATGTCG
```
We can use [Primer3Plus](https://www.primer3plus.com/) to check Tm for any secondary structures.
In Primer Blast we can see that the pair will amplify only the Dclk1 transcripts
```
Primer pair 1
	Sequence (5'->3')	Length	Tm	GC%	Self complementarity	Self 3' complementarity
Forward primer	TCCGTTACCAGGATGATTTCTTG	23	58.49	43.48	4.00	2.00
Reverse primer	CCGATGCTATTTTGGTGTAGGAA	23	58.80	43.48	3.00	0.00
Products on target templates
>XM_039103260.2 PREDICTED: Rattus norvegicus doublecortin-like kinase 1 (Dclk1), transcript variant X15, mRNA


product length = 81
Forward primer  1     TCCGTTACCAGGATGATTTCTTG  23
Template        1241  .......................  1263

Reverse primer  1     CCGATGCTATTTTGGTGTAGGAA  23
Template        1321  .......................  1299

>XM_039103258.2 PREDICTED: Rattus norvegicus doublecortin-like kinase 1 (Dclk1), transcript variant X14, mRNA


product length = 81
Forward primer  1     TCCGTTACCAGGATGATTTCTTG  23
Template        1241  .......................  1263

Reverse primer  1     CCGATGCTATTTTGGTGTAGGAA  23
Template        1321  .......................  1299

>XM_039103257.2 PREDICTED: Rattus norvegicus doublecortin-like kinase 1 (Dclk1), transcript variant X13, mRNA


product length = 81
Forward primer  1     TCCGTTACCAGGATGATTTCTTG  23
Template        1241  .......................  1263

Reverse primer  1     CCGATGCTATTTTGGTGTAGGAA  23
Template        1321  .......................  1299

>XM_039103254.2 PREDICTED: Rattus norvegicus doublecortin-like kinase 1 (Dclk1), transcript variant X7, mRNA


product length = 81
Forward primer  1     TCCGTTACCAGGATGATTTCTTG  23
Template        1241  .......................  1263

Reverse primer  1     CCGATGCTATTTTGGTGTAGGAA  23
Template        1321  .......................  1299

>XM_039103253.2 PREDICTED: Rattus norvegicus doublecortin-like kinase 1 (Dclk1), transcript variant X6, mRNA


product length = 81
Forward primer  1     TCCGTTACCAGGATGATTTCTTG  23
Template        1241  .......................  1263

Reverse primer  1     CCGATGCTATTTTGGTGTAGGAA  23
Template        1321  .......................  1299

>XM_017591139.3 PREDICTED: Rattus norvegicus doublecortin-like kinase 1 (Dclk1), transcript variant X5, mRNA


product length = 81
Forward primer  1     TCCGTTACCAGGATGATTTCTTG  23
Template        1241  .......................  1263

Reverse primer  1     CCGATGCTATTTTGGTGTAGGAA  23
Template        1321  .......................  1299

>XM_039103252.2 PREDICTED: Rattus norvegicus doublecortin-like kinase 1 (Dclk1), transcript variant X4, mRNA


product length = 81
Forward primer  1     TCCGTTACCAGGATGATTTCTTG  23
Template        1241  .......................  1263

Reverse primer  1     CCGATGCTATTTTGGTGTAGGAA  23
Template        1321  .......................  1299

>XM_039103250.2 PREDICTED: Rattus norvegicus doublecortin-like kinase 1 (Dclk1), transcript variant X3, mRNA


product length = 81
Forward primer  1     TCCGTTACCAGGATGATTTCTTG  23
Template        1241  .......................  1263

Reverse primer  1     CCGATGCTATTTTGGTGTAGGAA  23
Template        1321  .......................  1299

>XM_039103249.2 PREDICTED: Rattus norvegicus doublecortin-like kinase 1 (Dclk1), transcript variant X2, mRNA


product length = 81
Forward primer  1     TCCGTTACCAGGATGATTTCTTG  23
Template        1241  .......................  1263

Reverse primer  1     CCGATGCTATTTTGGTGTAGGAA  23
Template        1321  .......................  1299

>XM_039103247.2 PREDICTED: Rattus norvegicus doublecortin-like kinase 1 (Dclk1), transcript variant X1, mRNA


product length = 81
Forward primer  1     TCCGTTACCAGGATGATTTCTTG  23
Template        1241  .......................  1263

Reverse primer  1     CCGATGCTATTTTGGTGTAGGAA  23
Template        1321  .......................  1299
```
#### As an aside:
If you directly use human's primers, there will be some mismatches.

## Final: Multiplexing
At this point, we have collected 4 sets of primer-probes. As we can see, this process contains a lot of trial-and-errors. Nevertheless, after checking primer positions, it is very hard to find primers that do not form cross-dimers since rat Dclk1 only has 

Now, we will test multiplexing primers in Multiple primer analyzer.

### Multiple primer analyzer 
Use thermofisher's [Multiple Primer Analyzer](https://www.thermofisher.com/us/en/home/brands/thermo-scientific/molecular-biology/molecular-biology-learning-center/molecular-biology-resource-library/thermo-scientific-web-tools/multiple-primer-analyzer.html).


We will then have to go back to Primer Express documents to adjust probe sequences so that the probes do not form cross primer dimers. When switching the probes, make sure to check "Interim results" if no primer-probe set can be returned. The probe should pass the tests in ideal case.

If there is no much room in probe selection, go back to Primer Blast results to switch primers, and then iterate the whole process again. (Long process warning!!)

After that, the final result is here:
```
LS_all_fwd TGATCCAAAACGAGGTCTCCA
LS_all_rev CGGCACATCCATCTCTTCAA
LS_all_probe AAGCATCCGAACATTGT
LS_spliced_fwd TCAAGAAGCATTTCAACACGGG
LS_spliced_rev ATCAAGAGCGGTGGTTGCTA
LS_spliced_probe ACGGCAGCTGGAGTT
L_all_fwd AGAACGTGAACCCCAATTGG
L_all_rev CTTGGCAGTCGCCAGAGAA
L_all_probe ACGTCAAGACCACCTCA
L_spliced_fwd TCCGTTACCAGGATGATTTCTTG
L_spliced_rev CCGATGCTATTTTGGTGTAGGAA
L_spliced_probe TAGATGAAAGTGAATGTCG
```

Some sort of cross-dimer exist, but should be ok due to mismatches
```
                Self-Dimers:

1 dimer for: L_all_fwd
5-agaacgtgaaccccaattgg->
              ||||||||
            <-ggttaaccccaagtgcaaga-5


               Cross Primer Dimers:

LS_all_rev with L_spliced_probe
LS_all_rev
    5-cggcacatccatctcttcaa->
         ||| | ||||| 
<-gctgtaagtgaaagtagat-5

LS_spliced_rev with L_all_probe
LS_spliced_rev
5-atcaagagcggtggttgcta->
         | ||||||    |
      <-actccaccagaactgca-5


```
