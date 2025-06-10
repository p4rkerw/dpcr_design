dpcr primer and probe design for non-unique region in Gapdh on chr4. This primer / probe set is designated "chrB" for chromosome basket - because it is not a single copy reference region. The 17 stands for the 17 predicted genomic regions that it amplifies and detects across
chromosomes. 

1. First navigate to Gapdh https://genome.ucsc.edu/cgi-bin/hgTracks?db=rn7&lastVirtModeType=default&lastVirtModeExtraState=&virtModeType=default&virtMode=0&nonVirtPosition=&position=chr4%3A157962358%2D157966230&hgsid=2661133848_7b3Ya9s0aHPcvM214jAMEBJaqxHU

2. We will now extract the nucleotide sequence using View -> DNA with 200bp up- and downstream padding and mask repeats to lower case. 

```
>rn7_dna range=chr4:157962158-157966430 5'pad=200 3'pad=200 strand=+ repeatMasking=none
AGTGTCAAGCCCCACCCTCCACACTGCCAGACACATCAGGTGTCTGGACA
GGCGGCCTGGGCTGGCACTCGGTTAGAATGTAGCCCTGGACCTCTAGCAC
CCAGCTGGATGGCAGAGCCAATAAAGATATGTGCACAAAACCGAATGGAG
CCTCCTTCACCTGCCCATAACCCCCACAACACTGCATTCACACACAAGAA
GAGGGTGCAGCGAACTTTATTGATGGTATTCGAGAGAAGGGAGGGCTCCC
CAGGCCCCTCCTGTTGTTATGGGGTCTGGGATGGAATTGTGAGGGAGATG
CTCAGTGTTGGGGGCTGAGTTGGGATGGGGACTCCTCAGCAACTGAGGGC
CTCTCTCTTGCTCTCAGTATCCTTGCTGGGCTGGGTGGTCCAGGGTTTCT
TACTCCTTGGAGGCCATGTAGGCCATGAGGTCCACCACCCTGTTGCTGTA
GCCATATTCATTGTCATACCTAGAACAGATTGGGACAACGGTTAGTTTGG
GCTTCTTTTCTAAGCTGGCCACCAGAGGGCACCAAACCTTCAGTTACTCT
CAAGAGCCAGGCTTGCGGTCCCCACATACCAGGAAATGAGCTTCACAAAG
TTGTCATTGAGAGCAATGCCAGCCCCAGCATCAAAGGTGGAAGAATGGGA
GTTGCTGTTGAAGTCACAGGAGACAACCTGGTCCTCAGTGTAGCCCAGGA
TGCCCTTTAGTGGGCCCTCGGCCGCCTGCTTCACCACCTTCTTGATGTCA
TCATACTTGGCCTTGTAAGGGCAAAACCAAAGATGACTGCTCTTGCCCCA
AGTCACCACCATACCATAGACAAAACAAACCCAGCTCTCCCCCTACGTAC
AGGTTTCTCCAGGCGGCATGTCAGATCCACAACGGATACATTGGGGGTAG
GAACACGGAAGGCCATGCCAGTGAGCTTCCCGTTCAGCTCTGGGATGACC
TTGCCCACAGCCTTGGCAGCACCAGTGGATGCAGGGATGATGTTCTGGGC
TGCCCCACGGCCATCACGCCACAGCTTTCCAGAGGGGCCATCCACAGTCT
TCTGAGTGGCAGTGATGGCATGGACTGTGGTCTAGAAAGCATAGAGGCAA
TGGGTGAGGTCTTGCAGGGCAGCCCTCCTACCCAAAGGGACATCTTCAAA
GAAAGGTCCACTCATGCATGAGCTGTCTCCATTGCCTACATACCATGAGC
CCTTCCACGATGCCAAAGTTGTCATGGATGACCTTGGCCAGGGGGGCTAA
GCAGTTGGTGGTGCAGGATGCATTGCTGACAATCTTGAGGGAGTTGTCAT
ATTTCTCGTGGTTCACACCCATCACAAACATGGGGGCATCAGCGGAAGGG
GCGGAGATGATGACCCTTTTGGCCCCACCCTTCAGGTGAGCCTGTGCAGG
AGAAGTTGATTTCAGACTCAGCTCTTCAGTTTGGAGGTTGCACCCATATC
AAGGGTTCCCCTTACCTCCAGCTTCCTGGCCACTTACCCCAGCCTTCTCC
ATGGTGGTGAAGACGCCAGTAGACTCCACGACATACTCAGCACCAGCATC
ACCCCATTTGATGTTAGCGGGATCTCGCCTACAGGCGGGGAACAGGACAG
AGTTAATGCCGCCCCTTACCATCTCCTCGAAGTACCCTGTGCATGTTTCC
ATACGTACTCCTGGAAGATGGTGATGGGTTTCCCGTTGATGACCAGCTTC
CCATTCTCAGCCTTGACTGTGCCGTTGAACTTGCCGTGGGTAGAGTCATA
CTGGAACATGTAGACCATGTAGTTGAGGTCAATGAAGGGGTCGTTGATGG
CAACAATGTCCACTTTGTCACAAGAGAAGGCAGCCCTGGTAACCAGGCGT
CCGATACGGCCAAATCTGAGGCAAGAAATAGGCGAGTTAGTTGGGATCAG
TGAACCCCTCCTGGGTTTGTAGTCAGCCCTGGGCCAACGCATGTTCTTCA
GAAAGTAAAGCATCGCTGCACCATGGGCGTGGAGATCCTACAGCAGCCCG
CTACACACGCATCACAAAAAGGTGCAAGTTCTTACGCTGATTCAGTACAG
CATCAGAAACGTAAGCAGCAGGAAGTTCATGTTTTGTCCAGAATTTCCTT
TAATAAAGCCGGTTGAATGCTTGGATGTACAACCCAAATATAGAATGTTC
CCTCCCTAGAAAGTCCAAAGAGATCTAATTTTATATTCCTTGAGCCACCC
AGGGCTGGCAGGACTTTTATAGCAGCTATAAAGTGGAGGTTCCTTTCCTG
TCCAAGAGGTGATTAGGCCCACAGCCTTGCCCGGCACCCCAAAGTCATTT
TAAGTCTCTTAAGAAGTGGCGGTTTGCCCCGGTCTGGGTACAAGCTTGGC
ACATGGTATTCATCACCCCCACCACACAGGCCTGGGAAGCCGGTTCCAGC
ATGGCTGGACTTCAGGCTACACTCCCGGACAGGAGAGAACTCATTCATCA
GCAGCTCAAAGGGCAAGGCTAAAGGTCAGAGTGAGCAGGACAGGGCCAGC
CCACCTGCTTCCTCCAAGTCCCTTTCTGGGGGAAAGATCAAGAAAACCAG
TGATTTTCCAGCCCTAATCCCAGGACTCATTTGCAAAACACCTGTCTTTC
CCGGCCAAAAAAAAAAAAAAAAAAAAATCGGAGCAGGAGCAACAGATGTG
TGGAGGGATGAACAGGGCAGAGAGCCCAGCTCAGACCCCAGATACAGAAA
GGTCAGACAGCTAAATTTAACCCCAGATCAGGGCGGAATGGGGAGATCTG
GTTTCTGGAGGATGGGTTGGGGAAAAGGGTAGGATCCTGAGGCTCAGAGA
CACCCAATCCTCTTAGTGACCTTTACATCCTGGCCTATAGGGTTTGGGTC
AGTGCTGAGCTGGGATGGAAGTGGAGGCCCTGGAGGGAGGGGGCTGCTAC
CACCGGAGCCATTTTGTGGCAGAAAATTTCTTTTCAGGACCATCATGACT
CAGCTCCCCACCCCACCCCCGGGCTCGGCACTACGCCATTGCTACCGCAC
CTCCGGGGCTGGGAGGCCAAGTAGACCTCTGTAAATGCACTTCGACTTCC
AGAGAACAATCTAGAATATAAGTTATGCCCGAGGGAAATAAGGCTGGAGG
CCTATAAAGGCTGACGAGAGACGGATTGTATAGTAGAGCTCTAATGAGAG
CACGGAAACCCTGCCATCCATCACCTGGCCTACAGAATAAAGGACACTCC
ACCCAGCTGAGAGGAATGAGAAAGTTAGTCACAAGCTAAGAATGAGGAAG
GCCGAAGGAAGATTTCTTAACGGTGGTTCATTCATTTCCTTCCCGTTTGC
AACATGGCGGCGGCCAGTTACCATAAGTGAAGCCCTTAGAAGATGCGCAA
AGGTATGCACCTCACACCCCCGTGCCACCGACCCTGAGGAAGGGGACGAT
GGGGGAGGGGCTCCCCTTCTGGCACGTGACTCCTCTGGGCGCGAAAGTAA
AGAAAGAAGCCCCAGCCTGGGGATTACGGGTCGGATCCTGAGCGGGTGCG
CGCCAGTGTCGGGGGTGCTCCTGCTACTTTAGACTCCGGGCCGCTCCCCA
GCAAAGGCGGAGTTACAAGGGGAGCAACAGCTGGGGTCCCGTTAAGTGCG
AGCCTTCCCCAGGTCCGAGCGCTGACCTTGAGGTCTCCTTGGGTACTTCG
GCCACCCTATCCACCTCCCCGCACGCTACAGCACAGCCCCGAATTTAGCC
AGACCGGCATGCGCAACGGAGCGGGGCCCCGCCCTGGAACTCACCCGTTC
ACACCGACCTTCACCATCTTGTCTATGAGACGAGGCTGCGGGAGAAGAAA
GTCAGATTAGCGTGGCCAGTCCCCTCCCCCCACCCGCCTCCATTCCCGCC
GCATGCCCCATCACGTCCTCTACCATCCTCTGCAATGCGGAGCCTGGGCT
CGGCTTCCGGACCTCGCACCAGCGCCCCTAAACCCGTACAGCGTCCTTCC
CCCCATTCCTAATTTCCATTCGTCTCCGGCCTCCTGCGGCCCAGTCCTTT
TTTTTCTTTTCTTTTTCACCTGGCACTGCACAAGAAGATGCGGCTGTCTC
TAGAACAGGGAGGAGCAGAGAGCACCAGGGAGGGCTGCAGTCCGTATTTA
TAGGAACTGGATGGTGGGGGGAGCTGATGACGCGCGCCCCGCCTCCCGCT
CGGCTCATCCAGTCCCAGCTCAAGGGCGCAGAGGCCTGAGCTACGTGCAC
CCGTAAAGCCGCGAGTAGCTGGGCCTCTCTCATTCCCCCCCTCCCTCTTT
TTGGACCCGCCTCGTTTTTGAAA
```

3. We will now check this sequence with BLAT to see if there is a region that is non-unique

```
  ACTIONS                 QUERY   SCORE START   END QSIZE IDENTITY  CHROM  STRAND  START       END   SPAN
------------------------------------------------------------------------------------------------------------
browser new tab details rn7_dna  4273     1  4273  4273   100.0%  chr4   +   157962158 157966430   4273
browser new tab details rn7_dna  1174   199  1866  4273    97.9%  chr5   -   111671971 111673151   1181
browser new tab details rn7_dna  1166   201  1866  4273    97.7%  chr16  -    24030074  24031252   1179
browser new tab details rn7_dna  1155   201  1866  4273    97.3%  chr5   +    69853778  69854957   1180
browser new tab details rn7_dna  1146   201  1866  4273    96.9%  chr8   -    41716411  41717592   1182
browser new tab details rn7_dna  1129   201  1866  4273    96.1%  chr11  +    68857742  68858922   1181
browser new tab details rn7_dna  1120   201  1866  4273    96.2%  chr7   +   114359073 114360248   1176
browser new tab details rn7_dna  1115   201  1866  4273    95.8%  chr8   +   101205904 101207080   1177
browser new tab details rn7_dna  1101   201  1866  4273    95.0%  chr12  -     3782274   3783450   1177
browser new tab details rn7_dna  1101   201  1866  4273    95.0%  chr18  +    61626955  61628135   1181
browser new tab details rn7_dna  1095   201  1866  4273    94.8%  chr16  -    46413792  46414972   1181
browser new tab details rn7_dna  1094   201  1868  4273    94.8%  chr18  +    49339291  49340468   1178
browser new tab details rn7_dna  1091   201  1866  4273    94.6%  chr13  +    83870716  83871895   1180
browser new tab details rn7_dna  1081   201  1866  4273    94.5%  chr20  +    30914977  30916159   1183
browser new tab details rn7_dna  1078   203  1864  4273    94.2%  chr4   +   130314650 130315822   1173
browser new tab details rn7_dna  1074   201  1866  4273    94.4%  chr14  -      198244    199411   1168
browser new tab details rn7_dna  1073   203  1866  4273    94.7%  chr16  -    18232516  18233680   1165
browser new tab details rn7_dna  1066   203  1868  4273    94.0%  chr2   +     6192343   6193524   1182
browser new tab details rn7_dna  1065   203  1865  4273    94.0%  chr4   +    86251931  86253109   1179
browser new tab details rn7_dna  1040   204  1866  4273    93.4%  chr5   -   148831735 148832889   1155
browser new tab details rn7_dna  1010   203  1836  4273    92.8%  chr6   +    61865750  61866903   1154
browser new tab details rn7_dna   943   351  1866  4273    94.2%  chr14  +    40809115  40810153   1039
browser new tab details rn7_dna   940   351  1866  4273    95.9%  chr3   -   126310208 126350787  40580
browser new tab details rn7_dna   932   352  1866  4273    93.8%  chr2   -    15484791  15485822   1032
browser new tab details rn7_dna   917   353  1868  4273    93.1%  chr2   -    60847972  60848992   1021
browser new tab details rn7_dna   916   351  1868  4273    92.5%  chr13  +    34334496  34335524   1029
browser new tab details rn7_dna   915   353  1866  4273    92.9%  chr10  +    25193395  25194426   1032
browser new tab details rn7_dna   906   357  1868  4273    92.7%  chr12  +    13267430  13268460   1031
browser new tab details rn7_dna   902   353  1866  4273    93.0%  chr4   -   161924879 161925887   1009
browser new tab details rn7_dna   900   200  1578  4273    96.9%  chr5   -    54794483  54803796   9314
browser new tab details rn7_dna   897   201  1576  4273    95.0%  chr3   +    98345628  98346590    963
browser new tab details rn7_dna   891   203  1578  4273    94.1%  chr14  -    40634023  40634990    968
browser new tab details rn7_dna   888   203  1578  4273    93.8%  chr9   -    58083620  58084588    969
browser new tab details rn7_dna   866   203  1578  4273    93.6%  chrX   -   105466697 105467665    969
browser new tab details rn7_dna   858   213  1572  4273    93.0%  chr7   -    11065555  11066508    954
browser new tab details rn7_dna   852   216  1575  4273    94.2%  chr14  -     3055286   3056227    942
browser new tab details rn7_dna   851   218  1577  4273    92.8%  chr15  +    77442302  77443258    957
browser new tab details rn7_dna   849   203  1575  4273    93.1%  chr8   -   112339932 112340886    955
browser new tab details rn7_dna   848   202  1576  4273    92.1%  chr13  -     1965731   1966699    969
browser new tab details rn7_dna   843   205  1578  4273    92.1%  chr17  +    83129232  83130207    976
browser new tab details rn7_dna   841   206  1543  4273    93.3%  chr5   -    11793765  11794695    931
browser new tab details rn7_dna   831   204  1578  4273    92.0%  chr4   +   124333111 124334085    975
browser new tab details rn7_dna   800   213  1567  4273    92.3%  chr4   +    35977951  35978883    933
browser new tab details rn7_dna   779   352  1817  4273    90.7%  chr5   -   121312135 121313205   1071
browser new tab details rn7_dna   757   353  1575  4273    94.2%  chr16  -    15370532  15371352    821
browser new tab details rn7_dna   748   353  1578  4273    93.3%  chr13  +    59484314  59485137    824
browser new tab details rn7_dna   747   351  1575  4273    93.5%  chr10  -    66803930  66804746    817
browser new tab details rn7_dna   742   351  1566  4273    93.9%  chrX   -    70801844  70802652    809
browser new tab details rn7_dna   741   354  1578  4273    93.7%  chr20  -    31384347  31385165    819
browser new tab details rn7_dna   738   354  1578  4273    93.1%  chr8   -    71665146  71665967    822
browser new tab details rn7_dna   736   354  1578  4273    93.2%  chrX   -   126965707 126966511    805
browser new tab details rn7_dna   735   352  1578  4273    92.8%  chr4   -    28454036  28454862    827
browser new tab details rn7_dna   734   350  1571  4273    92.7%  chr5   +    36225980  36226797    818
browser new tab details rn7_dna   734   201  1329  4273    92.8%  chr11  +    84649971  84650789    819
browser new tab details rn7_dna   733   354  1578  4273    92.6%  chrX   -    31634262  31635081    820
browser new tab details rn7_dna   731   351  1566  4273    94.0%  chr7   +   117379330 117380130    801
browser new tab details rn7_dna   731   350  1578  4273    92.4%  chr1   +    23808110  23808929    820
browser new tab details rn7_dna   728   360  1578  4273    93.1%  chr3   -    13501303  13502126    824
browser new tab details rn7_dna   727   354  1574  4273    93.3%  chr1   -   221248547 221249347    801
browser new tab details rn7_dna   726   351  1576  4273    92.7%  chr6   -   103938146 103938964    819
browser new tab details rn7_dna   724   352  1575  4273    92.3%  chr10  +    75962555  75963376    822
browser new tab details rn7_dna   722   354  1576  4273    92.7%  chr14  -    11248137  11248951    815
browser new tab details rn7_dna   721   350  1577  4273    92.4%  chr7   +    31389973  31390784    812
browser new tab details rn7_dna   721   351  1566  4273    92.6%  chr11  +    71700270  71701082    813
browser new tab details rn7_dna   720   353  1573  4273    92.5%  chr1   -   185016624 185017423    800
browser new tab details rn7_dna   719   353  1569  4273    92.9%  chr14  +     1401643   1402443    801
browser new tab details rn7_dna   718   350  1575  4273    92.2%  chr6   -    36958714  36959537    824
browser new tab details rn7_dna   718   353  1574  4273    92.9%  chr2   -   183913468 183914271    804
browser new tab details rn7_dna   717   351  1578  4273    92.3%  chr14  -   103937766 103938570    805
browser new tab details rn7_dna   716   351  1561  4273    93.1%  chr9   -    49272690  49273497    808
browser new tab details rn7_dna   716   353  1566  4273    92.0%  chr7   +     8895765   8896575    811
browser new tab details rn7_dna   714   698  1866  4273    92.6%  chr10  +    98813982  98814773    792
browser new tab details rn7_dna   712   350  1578  4273    91.8%  chr2   -   175359511 175360337    827
browser new tab details rn7_dna   710   350  1560  4273    92.7%  chr1   +   175984866 175985672    807
browser new tab details rn7_dna   709   367  1578  4273    93.3%  chr19  -    17899211  17900012    802
browser new tab details rn7_dna   708   368  1569  4273    92.9%  chr20  +    32795525  32796338    814
browser new tab details rn7_dna   705   351  1578  4273    92.0%  chr8   +    31614721  31615533    813
browser new tab details rn7_dna   700   351  1578  4273    91.0%  chr15  +    97128847  97129671    825
browser new tab details rn7_dna   698   369  1576  4273    91.8%  chr9   +    83365243  83366048    806
browser new tab details rn7_dna   697   698  1866  4273    92.4%  chr7   -    95450615  95451405    791
browser new tab details rn7_dna   697   697  1866  4273    92.4%  chr3   -   131934128 131934915    788
browser new tab details rn7_dna   697   351  1578  4273    92.1%  chr9   +      603553    604356    804
browser new tab details rn7_dna   695   353  1578  4273    92.1%  chr10  -    67912233  67913036    804
browser new tab details rn7_dna   694   353  1578  4273    93.1%  chr2   +   175578936 175579858    923
browser new tab details rn7_dna   683   351  1557  4273    91.3%  chrX   +   143320335 143321138    804
browser new tab details rn7_dna   681   354  1576  4273    90.9%  chr3   -    69198725  69199530    806
browser new tab details rn7_dna   680   362  1577  4273    90.3%  chr4   -   110616668 110617471    804
browser new tab details rn7_dna   678   370  1578  4273    91.7%  chr2   -   210784881 210785687    807
browser new tab details rn7_dna   674   696  1868  4273    92.0%  chr5   -    19038148  19038924    777
browser new tab details rn7_dna   669   372  1576  4273    91.6%  chr14  -    88009542  88010429    888
browser new tab details rn7_dna   666   353  1554  4273    91.7%  chr3   -   127431433 127432217    785
browser new tab details rn7_dna   666   205  1291  4273    93.1%  chr2   -   207573815 207574588    774
browser new tab details rn7_dna   665   375  1566  4273    91.2%  chr1   +   100145825 100146600    776
browser new tab details rn7_dna   662   351  1576  4273    90.3%  chr18  +    39661693  39662509    817
browser new tab details rn7_dna   660   388  1578  4273    90.6%  chr16  +    69286633  69287406    774
browser new tab details rn7_dna   659   694  1865  4273    91.2%  chr6   +   109432055 109432819    765
browser new tab details rn7_dna   658   366  1559  4273    91.5%  chr13  +    96691375  96692130    756
browser new tab details rn7_dna   656   201  1260  4273    92.8%  chr4   -   121902092 121902816    725
browser new tab details rn7_dna   655   710  1814  4273    93.1%  chr18  +    47844510  47845239    730
browser new tab details rn7_dna   645   353  1568  4273    91.5%  chr2   -   190502468 190503264    797
browser new tab details rn7_dna   645   353  1566  4273    91.1%  chr7   +    71072513  71073298    786
browser new tab details rn7_dna   640   384  1577  4273    90.0%  chr2   -    48957364  48958148    785
browser new tab details rn7_dna   629   600  1578  4273    93.5%  chr3   -   126310416 126311097    682
browser new tab details rn7_dna   620   353  1384  4273    90.7%  chr1   +   129758419 129759144    726
browser new tab details rn7_dna   576   205  1235  4273    88.7%  chrX   -    76298735  76299564    830
browser new tab details rn7_dna   513   203   968  4273    92.3%  chrX   -   113979755 113980320    566
browser new tab details rn7_dna   508   203   968  4273    91.9%  chr3   +   129269799 129270366    568
browser new tab details rn7_dna   507   204   967  4273    95.9%  chr1   -    66366672  66367598    927
browser new tab details rn7_dna   504   208   968  4273    92.5%  chr2   -    94165844  94166508    665
browser new tab details rn7_dna   489   203   970  4273    91.9%  chr5   +    95958296  95958848    553
browser new tab details rn7_dna   488   212   957  4273    92.4%  chr6   +    72328649  72329186    538
browser new tab details rn7_dna   487   215   967  4273    91.2%  chr11  -    67455465  67456021    557
browser new tab details rn7_dna   486   710  1578  4273    91.4%  chr3   +    41993963  41994557    595
browser new tab details rn7_dna   485   203   957  4273    92.2%  chr5   +     8497749   8498294    546
browser new tab details rn7_dna   482   728  1576  4273    90.4%  chr7   +   102774191 102774741    551
browser new tab details rn7_dna   466   205   970  4273    91.3%  chr1   -   177335221 177335774    554
browser new tab details rn7_dna   464   206   953  4273    90.7%  chr4   -    17169734  17170272    539
browser new tab details rn7_dna   456   204   963  4273    89.5%  chr9   +    94698833  94699397    565
browser new tab details rn7_dna   448   203   883  4273    93.2%  chr2   -    62737920  62738408    489
browser new tab details rn7_dna   435   204   883  4273    92.1%  chr16  -    75941492  75941976    485
browser new tab details rn7_dna   431   203   882  4273    91.7%  chr14  +    45034623  45035114    492
browser new tab details rn7_dna   416   201   761  4273    93.1%  chr9   -    21944726  21945176    451
browser new tab details rn7_dna   278   208   639  4273    91.7%  chr2   +    56520343  56520655    313
browser new tab details rn7_dna   255   851  1232  4273    92.2%  chr11  +    84740115  84740383    269
browser new tab details rn7_dna   143   602   761  4273    95.0%  chr11  +    84739925  84740114    190
```

4. We will now subset for the first non-unique region and retrieve the dna sequence
browser new tab details rn7_dna  1174   199  1866  4273    97.9%  chr5   -   111671971 111673151   1181

```
>rn7_dna range=chr5:111671971-111673151 5'pad=0 3'pad=0 strand=+ repeatMasking=none
GATTTGGCCGTATCGGACGCCTGGTTACCAGGGCTGCCTTCTCTTGTGAC
AAAGTGGACATTGTTGCCATCAACGACCCCTTCATTGACCTCAACTACAT
GGTCTACATGTTCCAGTATGACTCTACCCACGGCAAGTTCAACGGCACAG
TCAAGGCTGAGAATGGGAAGCTGGTCATCAACGGGAAACCCATCACCATC
TTCCAGGAGCGAGATCCCGCTAACATCAAATGGGGTGATGCTGGTGCTGA
GTATGTCGTGGAGTCTACTGGCGTCTTCACCACCATGGAGAAGGCTGGGG
CTCACCTGAAGGGTGGGGCCAAAAGGGTCATCATCTCCGCCCCTTCCGCT
GATGCCCCCATGTTTGTGATGGGTGTGAACCACGAGAAATATGACAACTC
CCTCAAGATTGTCAGCAATGCATCCTGCACCACCAACTGCTTAGCCCCCC
TGGCCAAGGTCATCCATGACAACTTTGGCATCGTGGAAGGGCTCATGACC
ACAGTCCATGCCATCACTGCCACTCAGAAGACTGTGGATGGCCCCTCTGG
AAAGCTGTGGCGTGATGGCCGTGGGGCAGCCCAGAACATCATCCCTGCAT
CCACTGGTGCTGCCAAGGCTGTGGGCAAGGTCATCCCAGAGCTGAACGGG
AAGCTCACTGGCATGGCCTTCCGTGTTCCTACCCCCAATGTATCCGTTGT
GGATCTGACATGCCGCCTGGAGAAACCTGCCAAGTATGATGACATCAAGA
AGGTGGTGAAGCAGGCGGCCGAGGGCCCACTAAAGGGCATCCTGGGCTAC
ACTGAGGACCAGGTTGTCTCCTGTGACTTCAACAGCAACTCCCATTCTTC
CACCTTTGATGCTGGGGCTGGCATTGCTCTCAATGACAACTTTGTGAAGC
TCATTTCCTGGTATGACAATGAATATGGCTACAGCAACAGGGTGGTGGAC
CTCATGGCCTACATGGCCTCCAAGGAGTAAGAAACCCTGGACCACCCAGC
CCAGCAAGGATACTGAGAGCAAGAGAGAGGCCCTCAGTTGCTGAGGAGTC
CCCATCCCAACTCAGCCCCCAACACTGAGCATCTCCCTCACAATTCCATC
CCAGACCCCATAACAACAGGAGAGGCCTGGGGAGCCCTCCCTTCTCTCGA
ATACCATCAATAAAGTTCGCTGCACCCTCTT

```

6. We will perform blat again using the dna sequence. Note how it has a high identity match with regions on other chromosomes

```
   ACTIONS                 QUERY   SCORE START   END QSIZE IDENTITY  CHROM  STRAND  START       END   SPAN
------------------------------------------------------------------------------------------------------------
browser new tab details rn7_dna  1181     1  1181  1181   100.0%  chr5   +   111671971 111673151   1181
browser new tab details rn7_dna  1169     1  1179  1181    99.6%  chr16  +    24030074  24031252   1179
browser new tab details rn7_dna  1158     1  1179  1181    99.2%  chr5   -    69853778  69854957   1180
browser new tab details rn7_dna  1149     1  1179  1181    98.9%  chr8   +    41716411  41717592   1182
browser new tab details rn7_dna  1132     1  1179  1181    98.1%  chr11  -    68857742  68858922   1181
browser new tab details rn7_dna  1123     1  1179  1181    97.8%  chr7   -   114359073 114360248   1176
browser new tab details rn7_dna  1118     1  1179  1181    97.4%  chr8   -   101205904 101207080   1177
browser new tab details rn7_dna  1104     1  1179  1181    96.9%  chr18  -    61626955  61628135   1181
browser new tab details rn7_dna  1104     1  1179  1181    96.7%  chr12  +     3782274   3783450   1177
browser new tab details rn7_dna  1098     1  1179  1181    96.7%  chr16  +    46413792  46414972   1181
browser new tab details rn7_dna  1095     1  1179  1181    96.4%  chr18  -    49339291  49340466   1176
browser new tab details rn7_dna  1094     1  1179  1181    96.5%  chr13  -    83870716  83871895   1180
browser new tab details rn7_dna  1087     1  1179  1181    96.2%  chr20  -    30914977  30916159   1183
browser new tab details rn7_dna  1083     1  1179  1181    96.1%  chr3   +   126310208 126311393   1186
browser new tab details rn7_dna  1083     1  1179  1181    96.1%  chr3   +   126349754 126350939   1186
browser new tab details rn7_dna  1081     3  1177  1181    95.9%  chr4   -   130314650 130315822   1173
browser new tab details rn7_dna  1078     1  1181  1181    95.7%  chr16  +    18232516  18233684   1169
browser new tab details rn7_dna  1076     1  1179  1181    96.0%  chr3   -    98345628  98346788   1161
browser new tab details rn7_dna  1076     1  1179  1181    95.5%  chr14  +      198244    199411   1168
browser new tab details rn7_dna  1075     1  1176  1181    96.2%  chr14  -    40808966  40810153   1188
browser new tab details rn7_dna  1072     2  1177  1181    95.7%  chr4   -    86251931  86253109   1179
browser new tab details rn7_dna  1069     1  1179  1181    95.7%  chr2   +    15484791  15485976   1186
browser new tab details rn7_dna  1066     1  1177  1181    95.9%  chr2   -     6192343   6193522   1180
browser new tab details rn7_dna  1065     1  1179  1181    95.3%  chr10  -    98813588  98814773   1186
browser new tab details rn7_dna  1063     1  1177  1181    95.5%  chr9   +    58083406  58084588   1183
browser new tab details rn7_dna  1061     1  1177  1181    95.7%  chr14  +    40633811  40634990   1180
browser new tab details rn7_dna  1059     1  1179  1181    94.6%  chrX   +   126965499 126966664   1166
browser new tab details rn7_dna  1058     1  1179  1181    95.9%  chrX   +    70801618  70802804   1187
browser new tab details rn7_dna  1057     1  1177  1181    95.5%  chr18  -    16273597  16274793   1197
browser new tab details rn7_dna  1057     1  1177  1181    95.4%  chr3   +    13501089  13502285   1197
browser new tab details rn7_dna  1055     1  1179  1181    95.2%  chr13  -    59484160  59485343   1184
browser new tab details rn7_dna  1055     1  1179  1181    95.2%  chr10  -    25193241  25194426   1186
browser new tab details rn7_dna  1055     1  1179  1181    94.9%  chr4   +     7620272   7621438   1167
browser new tab details rn7_dna  1054     1  1179  1181    95.0%  chr2   +    60847974  60849147   1174
browser new tab details rn7_dna  1052     1  1176  1181    95.3%  chr5   -    36225831  36227013   1183
browser new tab details rn7_dna  1052     1  1179  1181    94.4%  chr13  -    34334349  34335522   1174
browser new tab details rn7_dna  1052     1  1179  1181    95.4%  chr7   +    95450615  95451800   1186
browser new tab details rn7_dna  1047     1  1177  1181    95.4%  chr10  +    66803713  66804896   1184
browser new tab details rn7_dna  1046     1  1177  1181    94.9%  chr4   +   161924879 161926039   1161
browser new tab details rn7_dna  1045     1  1175  1181    95.0%  chr1   +   221248329 221249499   1171
browser new tab details rn7_dna  1044    21  1177  1181    95.5%  chr8   +    71664952  71666119   1168
browser new tab details rn7_dna  1042     1  1179  1181    95.3%  chr11  -    71700118  71701308   1191
browser new tab details rn7_dna  1042     1  1177  1181    94.9%  chr10  -    75962403  75963593   1191
browser new tab details rn7_dna  1042     1  1177  1181    94.7%  chrX   +    31634048  31635234   1187
browser new tab details rn7_dna  1042     1  1177  1181    94.7%  chr9   +    49272459  49273647   1189
browser new tab details rn7_dna  1040    19  1178  1181    95.8%  chr18  -    47844105  47845279   1175
browser new tab details rn7_dna  1039     1  1176  1181    94.6%  chr14  +   103937552 103938719   1168
browser new tab details rn7_dna  1036     1  1174  1181    94.9%  chr12  -    13267282  13268458   1177
browser new tab details rn7_dna  1036     1  1172  1181    94.6%  chr2   +    94165331  94166508   1178
browser new tab details rn7_dna  1035     1  1177  1181    94.6%  chr1   +   185016406 185017572   1167
browser new tab details rn7_dna  1032     1  1177  1181    95.0%  chr19  +    17898997  17900177   1181
browser new tab details rn7_dna  1031     1  1164  1181    95.1%  chr16  +    15370315  15371464   1150
browser new tab details rn7_dna  1030     1  1177  1181    94.2%  chr14  -    45034623  45035819   1197
browser new tab details rn7_dna  1030    19  1177  1181    95.1%  chr4   +    28453840  28455012   1173
browser new tab details rn7_dna  1026    24  1180  1181    95.1%  chr1   -    23807964  23809120   1157
browser new tab details rn7_dna  1026     1  1177  1181    94.3%  chrX   +   105466508 105467665   1158
browser new tab details rn7_dna  1026     1  1177  1181    95.0%  chr3   +   144636102 144637280   1179
browser new tab details rn7_dna  1026     1  1139  1181    95.8%  chr20  +    31384133  31385275   1143
browser new tab details rn7_dna  1024     1  1178  1181    93.8%  chr13  +     1965521   1966699   1179
browser new tab details rn7_dna  1023    25  1177  1181    95.1%  chr14  -     1401491   1402642   1152
browser new tab details rn7_dna  1023    19  1177  1181    94.8%  chr2   +   183913265 183914421   1157
browser new tab details rn7_dna  1023     1  1168  1181    94.6%  chr14  +    11247923  11249095   1173
browser new tab details rn7_dna  1022     1  1177  1181    94.5%  chr3   -   129269799 129270965   1167
browser new tab details rn7_dna  1022     1  1174  1181    95.3%  chr20  -    32795375  32796564   1190
browser new tab details rn7_dna  1022     1  1177  1181    94.3%  chr1   -   218714782 218715962   1181
browser new tab details rn7_dna  1022     1  1164  1181    94.4%  chr14  +     3055075   3056227   1153
browser new tab details rn7_dna  1021     1  1174  1181    94.2%  chr5   +    11793524  11794695   1172
browser new tab details rn7_dna  1020     1  1168  1181    94.1%  chr6   -    72328649  72329803   1155
browser new tab details rn7_dna  1019     1  1177  1181    94.0%  chr5   -     8497749   8498921   1173
browser new tab details rn7_dna  1019     1  1138  1181    95.6%  chr3   +   131934128 131935265   1138
browser new tab details rn7_dna  1018     1  1177  1181    94.1%  chr8   +   112339715 112340886   1172
browser new tab details rn7_dna  1016     1  1175  1181    94.2%  chr7   -    31389825  31390992   1168
browser new tab details rn7_dna  1016    20  1175  1181    94.5%  chr17  -    83129232  83130402   1171
browser new tab details rn7_dna  1015     1  1177  1181    93.9%  chr9   -   108470114 108471300   1187
browser new tab details rn7_dna  1013     1  1177  1181    93.8%  chrX   -   143320185 143321373   1189
browser new tab details rn7_dna  1013     1  1179  1181    93.9%  chr7   -     8895610   8896798   1189
browser new tab details rn7_dna  1013    20  1177  1181    94.4%  chr5   -    95958296  95959441   1146
browser new tab details rn7_dna  1013     1  1176  1181    93.8%  chr4   -   124333111 124334296   1186
browser new tab details rn7_dna  1012    20  1177  1181    93.9%  chr6   +    62524834  62525989   1156
browser new tab details rn7_dna  1011     1  1176  1181    93.5%  chr9   -    83365090  83366261   1172
browser new tab details rn7_dna  1011    31  1177  1181    94.4%  chr6   -    61865750  61866903   1154
browser new tab details rn7_dna  1010     1  1176  1181    93.6%  chr8   +    93369451  93370663   1213
browser new tab details rn7_dna  1010    50  1176  1181    95.0%  chr5   +   148831784 148832889   1106
browser new tab details rn7_dna  1009     1  1174  1181    93.4%  chr6   +    36958497  36959682   1186
browser new tab details rn7_dna  1009     1  1177  1181    93.7%  chr17  +    54343497  54344682   1186
browser new tab details rn7_dna  1007     1  1177  1181    93.8%  chr8   -    31614571  31615746   1176
browser new tab details rn7_dna  1006     1  1179  1181    94.0%  chr11  -    84649971  84651156   1186
browser new tab details rn7_dna  1003     1  1175  1181    93.0%  chr13  +    41965865  41967049   1185
browser new tab details rn7_dna  1001    66  1177  1181    95.3%  chr7   -   117379180 117380285   1106
browser new tab details rn7_dna  1001    19  1177  1181    94.5%  chrX   +   114320598 114321763   1166
browser new tab details rn7_dna   999     1  1177  1181    94.5%  chr2   -    20395138  20396310   1173
browser new tab details rn7_dna   998    28  1177  1181    94.4%  chrX   -    85986244  85987393   1150
browser new tab details rn7_dna   998     1  1177  1181    93.2%  chr1   -   216611914 216613105   1192
browser new tab details rn7_dna   997    50  1162  1181    95.0%  chr15  -    77442302  77443418   1117
browser new tab details rn7_dna   996     1  1177  1181    93.0%  chr15  -    97128700  97129885   1186
browser new tab details rn7_dna   990    18  1168  1181    93.4%  chr1   -   161819612 161820768   1157
browser new tab details rn7_dna   989     1  1177  1181    92.5%  chr16  -    35263900  35265077   1178
browser new tab details rn7_dna   989     1  1177  1181    92.4%  chr1   -   129758265 129759453   1189
browser new tab details rn7_dna   987     1  1167  1181    93.5%  chr9   -      603412    604567   1156
browser new tab details rn7_dna   985     1  1177  1181    94.0%  chr1   -   175984716 175985904   1189
browser new tab details rn7_dna   984    20  1179  1181    93.5%  chr13  -    96691207  96692344   1138
browser new tab details rn7_dna   984     1  1115  1181    94.2%  chr4   +   121901662 121902750   1089
browser new tab details rn7_dna   982    18  1176  1181    93.6%  chr8   +    79174262  79175424   1163
browser new tab details rn7_dna   982     1  1107  1181    94.8%  chr6   +   103937933 103939043   1111
browser new tab details rn7_dna   982     1  1164  1181    93.0%  chr2   +   175359299 175360475   1177
browser new tab details rn7_dna   981    50  1167  1181    94.5%  chr5   +    27001868  27002990   1123
browser new tab details rn7_dna   981     1  1181  1181    93.0%  chr2   +   210784667 210785861   1195
browser new tab details rn7_dna   977     1  1167  1181    93.3%  chr3   +    55987204  55988386   1183
browser new tab details rn7_dna   974    50  1177  1181    93.3%  chr4   -   116161726 116162860   1135
browser new tab details rn7_dna   974     1  1175  1181    92.5%  chr3   +    69198509  69199681   1173
browser new tab details rn7_dna   974     1  1177  1181    93.3%  chr1   +   172291996 172293174   1179
browser new tab details rn7_dna   973     1  1174  1181    92.5%  chr3   -     6351312   6352487   1176
browser new tab details rn7_dna   971     1  1177  1181    92.0%  chr16  -    69286441  69287608   1168
browser new tab details rn7_dna   971     1  1168  1181    94.1%  chr3   +    43213038  43214211   1174
browser new tab details rn7_dna   971     1  1168  1181    93.0%  chr14  +    88009326  88010591   1266
browser new tab details rn7_dna   971     1  1174  1181    92.3%  chr1   +   238984127 238985309   1183
browser new tab details rn7_dna   968     1  1179  1181    92.1%  chr7   +    35031153  35032338   1186
browser new tab details rn7_dna   968     1  1177  1181    91.6%  chr20  +    35921438  35922625   1188
browser new tab details rn7_dna   966     1  1177  1181    91.6%  chr6   +    85437147  85438332   1186
browser new tab details rn7_dna   965     1  1176  1181    92.0%  chr18  -    39938239  39939408   1170
browser new tab details rn7_dna   961    20  1179  1181    92.6%  chr1   -   100145644 100146801   1158
browser new tab details rn7_dna   960     1  1177  1181    91.3%  chr5   -    77091856  77093045   1190
browser new tab details rn7_dna   960    20  1142  1181    93.9%  chr3   -   105084504 105085644   1141
browser new tab details rn7_dna   960    20  1177  1181    93.1%  chr13  +    21995113  21996266   1154
browser new tab details rn7_dna   959     1  1177  1181    91.5%  chr13  +    67103905  67105076   1172
browser new tab details rn7_dna   956     1  1177  1181    92.0%  chr1   +    49773543  49774726   1184
browser new tab details rn7_dna   953     1  1175  1181    92.7%  chr5   -   101870373 101871559   1187
browser new tab details rn7_dna   951     1  1116  1181    93.6%  chr4   +    17169117  17170212   1096
browser new tab details rn7_dna   950     1  1177  1181    91.5%  chr3   -    40705520  40706691   1172
browser new tab details rn7_dna   950     1  1175  1181    91.1%  chr4   +   110616463 110617631   1169
browser new tab details rn7_dna   946   113  1167  1181    94.9%  chr7   +    11065453  11066508   1056
browser new tab details rn7_dna   946     1  1139  1181    92.5%  chr10  +    67912022  67913137   1116
browser new tab details rn7_dna   945     1  1142  1181    93.4%  chr18  +    67792537  67793673   1137
browser new tab details rn7_dna   942     1  1177  1181    91.9%  chr4   +   182204343 182205471   1129
browser new tab details rn7_dna   940     1  1177  1181    92.3%  chr5   -   125387235 125388413   1179
browser new tab details rn7_dna   940     1  1177  1181    91.9%  chr20  +    40672014  40673187   1174
browser new tab details rn7_dna   939     1  1175  1181    92.3%  chr6   -    11056106  11057278   1173
browser new tab details rn7_dna   939     1  1177  1181    91.0%  chr3   +    41189527  41190722   1196
browser new tab details rn7_dna   939    50  1174  1181    92.9%  chr2   +   190502299 190503413   1115
browser new tab details rn7_dna   934    60  1174  1181    93.2%  chr18  -    60455107  60456245   1139
browser new tab details rn7_dna   933     1  1119  1181    93.5%  chr18  +    31898201  31899338   1138
browser new tab details rn7_dna   932    26  1179  1181    91.9%  chr7   -    71072377  71073499   1123
browser new tab details rn7_dna   932     1  1167  1181    91.2%  chr6   -    52356498  52357666   1169
browser new tab details rn7_dna   932     1  1174  1181    91.4%  chr2   -   151344761 151345913   1153
browser new tab details rn7_dna   931    32  1177  1181    93.2%  chr7   -    22670098  23055481 385384
browser new tab details rn7_dna   925    24  1177  1181    91.2%  chr13  -    40465171  40466315   1145
browser new tab details rn7_dna   924     1  1166  1181    91.5%  chr2   -   228773875 228775062   1188
browser new tab details rn7_dna   922    24  1122  1181    93.7%  chr3   +   127431223 127432312   1090
browser new tab details rn7_dna   921    18  1180  1181    90.7%  chr16  +    32963902  32965062   1161
browser new tab details rn7_dna   920    19  1168  1181    91.3%  chr1   +   156933100 156934232   1133
browser new tab details rn7_dna   919     1  1122  1181    92.8%  chr16  -    78329297  78330540   1244
browser new tab details rn7_dna   919     1  1175  1181    91.3%  chr16  +    53391086  53392274   1189
browser new tab details rn7_dna   916     1  1172  1181    91.8%  chr17  -    77456279  77457441   1163
browser new tab details rn7_dna   915     1  1166  1181    90.9%  chrX   -   123194616 123195797   1182
browser new tab details rn7_dna   915     1  1140  1181    90.7%  chrX   +   124948515 124949664   1150
browser new tab details rn7_dna   910     1  1070  1181    93.5%  chr5   +    19038150  19039205   1056
browser new tab details rn7_dna   909     1  1177  1181    91.9%  chr18  -    64612422  64613595   1174
browser new tab details rn7_dna   908    22  1176  1181    90.1%  chr1   -   121006934 121008086   1153
browser new tab details rn7_dna   907     1  1056  1181    93.6%  chr15  -    17178416  17179466   1051
browser new tab details rn7_dna   905     1  1177  1181    89.9%  chr4   +    72014194  72015372   1179
browser new tab details rn7_dna   903    20  1140  1181    92.2%  chr6   -    67396667  67397791   1125
browser new tab details rn7_dna   903    28  1167  1181    91.1%  chr18  -    39661553  39662697   1145
browser new tab details rn7_dna   901    20  1177  1181    91.1%  chr12  +    13130745  13131906   1162
browser new tab details rn7_dna   900     1  1165  1181    89.8%  chr17  +    44014603  44015768   1166
browser new tab details rn7_dna   892    20  1177  1181    89.2%  chr1   -   101369993 101371211   1219
browser new tab details rn7_dna   892     1  1104  1181    91.4%  chr2   +    48957175  48958269   1095
browser new tab details rn7_dna   883    50  1177  1181    89.8%  chr8   -    91138464  91139589   1126
browser new tab details rn7_dna   880    19  1177  1181    89.6%  chr6   +    80080686  80081855   1170
browser new tab details rn7_dna   875    19  1176  1181    89.9%  chr10  +    77244342  77245506   1165
browser new tab details rn7_dna   873     4  1128  1181    90.6%  chrX   +   127421662 127422768   1107
browser new tab details rn7_dna   873     2  1175  1181    88.5%  chrX   +    42755023  42756187   1165
browser new tab details rn7_dna   871    68  1165  1181    92.3%  chr11  +    67455014  67456021   1008
browser new tab details rn7_dna   870    50  1175  1181    89.5%  chr13  -    75371119  75372232   1114
browser new tab details rn7_dna   865     1  1029  1181    94.0%  chr8   +    54848222  54849473   1252
browser new tab details rn7_dna   861     1  1120  1181    89.2%  chrX   -     9447557   9448673   1117
browser new tab details rn7_dna   857     1  1064  1181    90.6%  chr1   +    58090346  58091414   1069
browser new tab details rn7_dna   856    26  1138  1181    90.3%  chr6   +    73488144  73489259   1116
browser new tab details rn7_dna   851    15  1176  1181    88.8%  chr15  -    89942785  89943903   1119
browser new tab details rn7_dna   846    20  1174  1181    88.7%  chrX   +   124869973 124871132   1160
browser new tab details rn7_dna   842    25  1164  1181    88.8%  chr18  +    80058859  80059991   1133
browser new tab details rn7_dna   838    35  1110  1181    89.9%  chr7   +    85811848  85812926   1079
browser new tab details rn7_dna   832     1  1165  1181    88.1%  chrX   -    91821189  91822359   1171
browser new tab details rn7_dna   824     2  1095  1181    88.3%  chr2   +    12473579  12474658   1080
browser new tab details rn7_dna   784    62  1113  1181    87.7%  chrX   -    62840412  62841455   1044
browser new tab details rn7_dna   743    85  1113  1181    90.0%  chr3   -    96088493  96089524   1032
browser new tab details rn7_dna   743   203  1177  1181    90.7%  chr7   +    12125156  12126112    957
browser new tab details rn7_dna   742   343  1176  1181    94.9%  chrX   -    37840311  37841139    829
browser new tab details rn7_dna   739   228  1122  1181    91.6%  chr5   -     6551722   6552623    902
browser new tab details rn7_dna   738     1   905  1181    90.8%  chr18  -     3019726   3020623    898
browser new tab details rn7_dna   695   400  1175  1181    94.9%  chr2   +   207573815 207574588    774
browser new tab details rn7_dna   687     2   827  1181    93.8%  chr6   -   109431776 109432819   1044
browser new tab details rn7_dna   665     1   780  1181    94.2%  chr3   -    41993963  41994771    809
browser new tab details rn7_dna   662     1   721  1181    96.0%  chr5   +    54794275  54794998    724
browser new tab details rn7_dna   656   459  1179  1181    95.9%  chr11  -    84739656  84740383    728
browser new tab details rn7_dna   648    25   762  1181    94.2%  chr7   -   102774191 102774933    743
browser new tab details rn7_dna   637     1   886  1181    90.9%  chr6   -    52682359  52683235    877
browser new tab details rn7_dna   637   206   916  1181    95.2%  chr17  -    80588979  80589701    723
browser new tab details rn7_dna   586     1   685  1181    93.5%  chr5   -   155809696 155810370    675
browser new tab details rn7_dna   536   588  1177  1181    95.1%  chrX   +   113979732 113980320    589
browser new tab details rn7_dna   347    78   465  1181    94.9%  chr7   -    22670790  22671177    388
browser new tab details rn7_dna   165   591   803  1181    90.7%  chr7   -    23054734  23054926    193
```
7. We will now use primer express to design taqman primer / probe sets for this sequence. This primer / probe set was selected
because it does not amplify any sequence on a sex chromosome using the ucsc in silico pcr tool (see next step)

F: CATGGCCTCCAAGGAGTAAGAA
R: CTCTCTTGCTCTCAGTATCCTTGCT
P: CCTGGACCACCCAGC

8. We will check the F and R primers using the ucsc in silico pcr tool. Note how there are multiple pcr products of varying sizes.
Of all the amplified regions, note how there are 17 genomic regions that have an exact match for the taqman probe sequence CCTGGACCACCCAGC.
These regions are on chromosomes: 12, 14, 20, 2, 5(x3), 8(x2), 11, 13, 18, 20, 3(x2), 4(x2)
Many of the other regions have a 1bp mismatch for the taqman probe 

```
	
>chr12:3783231+3783296 66bp CATGGCCTCCAAGGAGTAAGAA CTCTCTTGCTCTCAGTATCCTTGCT
CATGGCCTCCAAGGAGTAAGAAaccctggaccacccagcccAGCAAGGAT
ACTGAGAGgAAGAGAG
>chr14:103938498+103938568 71bp CATGGCCTCCAAGGAGTAAGAA CTCTCTTGCTCTCAGTATCCTTGCT
CATGGCCTCCAAGGAGTAAGAAaccctggaccacccaccccagcccAGCA
AGGATACTGAGAGCAAGAGAG
>chr14:89089841+89089904 64bp CATGGCCTCCAAGGAGTAAGAA CTCTCTTGCTCTCAGTATCCTTGCT
aATGGCCTCCAAGGAGTAAGAAaacttactacccaccctAGCAAGGATAC
TGAGAGCAAGAGAc
>chr14:83895242+83895312 71bp CATGGCCTCCAAGGAGTAAGAA CTCTCTTGCTCTCAGTATCCTTGCT
CATGGCCTCCAAGGAGTAAGAAaccatggaccaccttccccaccccAGCA
AGGATACTGAGAGCAAGAGAG
>chr14:40634776+40634841 66bp CATGGCCTCCAAGGAGTAAGAA CTCTCTTGCTCTCAGTATCCTTGCT
CATGGCCTCCAAGGAGTAAGAAaccctggaccacccagcccAGCAAGGAT
ACTGAGAGCAAGAGAG
>chr14:11248882+11248952 71bp CATGGCCTCCAAGGAGTAAGAA CTCTCTTGCTCTCAGTATCCTTGCT
CATGGCCTCCAAGGAGTAAGAAaccctggaccacccaccccagcccAGCA
AGGATACTGAGAGCAAGAGAG
>chr14:3056023+3056093 71bp CATGGCCTCCAAGGAGTAAGAA CTCTCTTGCTCTCAGTATCCTTGCT
CATGGCCTCCAAGGAGTAAGAAaccctggaccacccaccccagcccAGCA
AGGATACTGAGAGCAAaAGAG
>chr16:75941758+75941828 71bp CATGGCCTCCAAGGAGTAAGAA CTCTCTTGCTCTCAGTATCCTTGCT
CATGGCCTCCAAGGAGTAAGAAaccctggaccacccaccccagcccAGCA
AGGATACTGAGAGCAAGAGAG
>chr16:18233458+18233528 71bp CATGGCCTCCAAGGAGTAAGAA CTCTCTTGCTCTCAGTATCCTTGCT
CATGGCCTCCAAGGAGTAAGAAaccctggaccacccaccccagcccAGCA
AGGATACTGAGAGCAAGAGAG
>chr16:15371282+15371352 71bp CATGGCCTCCAAGGAGTAAGAA CTCTCTTGCTCTCAGTATCCTTGCT
CATGGCCTCCAAGGAGTAAGAAaccctggaccacccacctcagcccAGCA
AGGATACTGAGAGCAAGAGAG
>chr17:80589821+80590006 186bp CATGGCCTCCAAGGAGTAAGAA CTCTCTTGCTCTCAGTATCCTTGCT
CATGGCCTCCAAGGAGTAAGAAaccctggaccgggttggagatttagctc
agtggtagagcgcttgcctaggaagcgcaaggccctgggttcggtcccca
gctccgaaaaaaagaacccaaaaaaaaaaaaaaagaaaccctggaccacc
caccccagcccAGCAAGGATACTGAGAGCAAGAGAG
>chr18:41528337+41528407 71bp CATGGCCTCCAAGGAGTAAGAA CTCTCTTGCTCTCAGTATCCTTGCT
CATcGCCTCCAAGGAGTAAGAAaccctggaccactcaccccagcccAGCA
AGGATACTGAGAaCAAGAGgc
>chr18:31899175+31899245 71bp CATGGCCTCCAAGGAGTAAGAA CTCTCTTGCTCTCAGTATCCTTGCT
CATGGCCTCCAAGGAGTAAGAAtccctggaccatgcaccccagcccAGCA
AGGATACTGAGAGCAAGAGAG
>chr20:31385101+31385166 66bp CATGGCCTCCAAGGAGTAAGAA CTCTCTTGCTCTCAGTATCCTTGCT
CATGGCCTCCAAGGAGTAAGAAaccctggaccacccagcccAGCAAGGAT
ACTGAGAGCAAGAGAG
>chr19:17899956+17900026 71bp CATGGCCTCCAAGGAGTAAGAA CTCTCTTGCTCTCAGTATCCTTGCT
CAaGGCCTCCAAGGAGTAAGAAaccctggaccacccaccccagcccAGCA
AGGATACTGAGAGCAAGAGAG
>chr1:178106328+178106393 66bp CATGGCCTCCAAGGAGTAAGAA CTCTCTTGCTCTCAGTATCCTTGCT
CATGGCCTCCAAGGAGTAAGAAaccctggacaacccagcccAGCAAGGAT
ACTGAGAGCAAGAGAG
>chr1:172292953+172293023 71bp CATGGCCTCCAAGGAGTAAGAA CTCTCTTGCTCTCAGTATCCTTGCT
CATGGCCTCCAAGGAGTAAGAAaccctggaccacccaccccagcccAGCA
AGGATACTGAGAGCAAGAGAG
>chr2:207574374+207574439 66bp CATGGCCTCCAAGGAGTAAGAA CTCTCTTGCTCTCAGTATCCTTGCT
CATGGCCTCCAAGGAGTAAGAAaccctggaccacccagcccAGCAAGGAT
ACTGAGAGCAAGAGAG
>chr2:183914201+183914271 71bp CATGGCCTCCAAGGAGTAAGAA CTCTCTTGCTCTCAGTATCCTTGCT
CATGGCCTCCAAGGAGTAAGAAaccctggaccacccaccccagcccAGCA
AGGATACTGAGAGCAAGAGAG
>chr2:178958645+178958715 71bp CATGGCCTCCAAGGAGTAAGAA CTCTCTTGCTCTCAGTATCCTTGCT
tATGGCCTCCAAGGAGTAAGAAaccctgaaccacccaccccagcccAGCA
AGGATACTGAGAGCAAGAGAG
>chr2:62738186+62738256 71bp CATGGCCTCCAAGGAGTAAGAA CTCTCTTGCTCTCAGTATCCTTGCT
CATGGCCTCCAAGGAGTAAGAAaccctggaccacccaccccagcccAGCA
AGGATACTGAGAGCAAGAGAG
>chr2:60848922+60848992 71bp CATGGCCTCCAAGGAGTAAGAA CTCTCTTGCTCTCAGTATCCTTGCT
CATGGCCTCCAAGGAGTAAGAAaccctgggccacccaccccagctcAGCA
AGGATACTGAGAGCAAGAGAG
>chr2:15485751+15485821 71bp CATGGCCTCCAAGGAGTAAGAA CTCTCTTGCTCTCAGTATCCTTGCT
CATGGCCTCCAAGGAGTAAGAAaccctggaccacccaccccagcccAGCA
AGGATACTGAGAGCAAGAGAG
>chr3:69199461+69199531 71bp CATGGCCTCCAAGGAGTAAGAA CTCTCTTGCTCTCAGTATCCTTGCT
CATGtCCTCCAAGGAGTAAGAAaccctgggccactcaccccagcctAGCA
AGGATACTGAGAGCAAGAGAG
>chr3:41190500+41190570 71bp CATGGCCTCCAAGGAGTAAGAA CTCTCTTGCTCTCAGTATCCTTGCT
CATGGCCTCCAAGGAGTAAGAAgccctggaccacctaccccagcccAGCA
AGGATACTGAGAGCAAGAGAG
>chr4:7621217+7621287 71bp CATGGCCTCCAAGGAGTAAGAA CTCTCTTGCTCTCAGTATCCTTGCT
CATGGCCTCCAAGGAGTAAGAAaccctggaccacccaccccagcccAGCA
AGGATACTGAGAGCAAGAGAG
>chr5:148832672+148832737 66bp CATGGCCTCCAAGGAGTAAGAA CTCTCTTGCTCTCAGTATCCTTGCT
CATGGCCTCCAAGGAGTAAGAAaccctggaccacccagcccAGCAAGGAT
ACTGAGAGCAAGAaAG
>chr5:137134245+137134315 71bp CATGGCCTCCAAGGAGTAAGAA CTCTCTTGCTCTCAGTATCCTTGCT
CATGGCCTCCAAGGAGTAAGAAaccctggaccacccaccccagcccAGCA
AGGATACTGAGAGCAAGAGAG
>chr5:123952107+123952177 71bp CATGGCCTCCAAGGAGTAAGAA CTCTCTTGCTCTCAGTATCCTTGCT
CAaGaCCTCCAAGGAGTAAGAAaccctggactacccaccccagtccAGCA
AGGATACTGAGgGCAAGAGAG
>chr5:111672932+111672997 66bp CATGGCCTCCAAGGAGTAAGAA CTCTCTTGCTCTCAGTATCCTTGCT
CATGGCCTCCAAGGAGTAAGAAaccctggaccacccagcccAGCAAGGAT
ACTGAGAGCAAGAGAG
>chr5:11794481+11794546 66bp CATGGCCTCCAAGGAGTAAGAA CTCTCTTGCTCTCAGTATCCTTGCT
CATGGCCTCCAAGGAGTAAGAAaccctgaaccacacagcccAGCAAGGAT
ACTGAGAcCAAGAGAG
>chr6:80081632+80081702 71bp CATGGCCTCCAAGGAGTAAGAA CTCTCTTGCTCTCAGTATCCTTGCT
CATGttCTCCAAGGAGTAAGAAacactggaccatccatcccagcccAGCA
AGGATACTGAGAGCAAGAGAa
>chr7:35032112+35032182 71bp CATGGCCTCCAAGGAGTAAGAA CTCTCTTGCTCTCAGTATCCTTGCT
CATGGCCTCCAAGGAGTAAGAAaccctggactactcaccccagtcgAGCA
AGGATACTGAGAGaAAaAGAG
>chr8:93370442+93370512 71bp CATGGCCTCCAAGGAGTAAGAA CTCTCTTGCTCTCAGTATCCTTGCT
CATGGCCTCCAAGGAGTAAGAAaccctggaccacccacccgagcccAGCA
AGGATACTGAGAGCAAGAGAG
>chr8:71665898+71665968 71bp CATGGCCTCCAAGGAGTAAGAA CTCTCTTGCTCTCAGTATCCTTGCT
CATGGCCTCCAAGGAGTAAGAAaccctggaccacccaccccagcccAGCA
AGGATACTGAGAGCAAGAGAG
>chr8:50292903+50292968 66bp CATGGCCTCCAAGGAGTAAGAA CTCTCTTGCTCTCAGTATCCTTGCT
CATGGCtTCCAAGGAGTAAGAAatcctggaccacccaccccAGCAAGGAT
ACTGAGAGCAAGAGAG
>chr8:42072520+42072590 71bp CATGGCCTCCAAGGAGTAAGAA CTCTCTTGCTCTCAGTATCCTTGCT
CATGGCCTCCAAGGAGTAAGAAaccctggaccacccaccccagcccAGCA
AGGATACTGAGAGCAAGgGAG
>chr8:41717372+41717437 66bp CATGGCCTCCAAGGAGTAAGAA CTCTCTTGCTCTCAGTATCCTTGCT
CATGGCCTCCAAGGAGTAAGAAaccctggaccacccagcccAGCAAGGAT
ACTGAGAGCAAGAGAG
>chr8:26017460+26017530 71bp CATGGCCTCCAAGGAGTAAGAA CTCTCTTGCTCTCAGTATCCTTGCT
CATGGCCTCCAAGGAGTAAGAAaccctggaccacccaccgcagcccAGCA
AGGATACTGAGAGCAAGAGAG
>chr9:49273425+49273495 71bp CATGGCCTCCAAGGAGTAAGAA CTCTCTTGCTCTCAGTATCCTTGCT
CATGGCCTCCAAGGAGTAAGAAaccctggaccacccaccccagcccAGCA
AGGATACTGAGAGCAAGAGAG
>chr9:48088979+48089049 71bp CATGGCCTCCAAGGAGTAAGAA CTCTCTTGCTCTCAGTATCCTTGCT
CATGGCCTCCAAGGAGTAAGAAaccctggaccacccaccccagcccAGCA
AGGATACTGAGAGCAAGAGAG
>chrX:114321543+114321613 71bp CATGGCCTCCAAGGAGTAAGAA CTCTCTTGCTCTCAGTATCCTTGCT
CATGGCCTCCAAGGAGTAAGAAactcaggaccacccaccccagcacAGCA
AGGATACTGAGgGCAAGAGAG
>chrX:113980106+113980171 66bp CATGGCCTCCAAGGAGTAAGAA CTCTCTTGCTCTCAGTATCCTTGCT
CATGGCCTCCAAGGAGTAAGAAaccctggaccaccaagcctAGCAAGGAT
ACTGAGAGCAAGAGAG
>chr10:98813742-98813812 71bp CATGGCCTCCAAGGAGTAAGAA CTCTCTTGCTCTCAGTATCCTTGCT
CATGGCCTCCAAGGAGTAAGAAaccctggaccacccaccccagcccAGCA
AGGATACTGAGAGCAAGAGAG
>chr11:84650124-84650189 66bp CATGGCCTCCAAGGAGTAAGAA CTCTCTTGCTCTCAGTATCCTTGCT
CATGGCCTCCAAGGAGTAAGAAaccctggaccacccaccccAGCAAGGAT
ACTGAGAGCAAGAGAG
>chr11:68857896-68857961 66bp CATGGCCTCCAAGGAGTAAGAA CTCTCTTGCTCTCAGTATCCTTGCT
CATGGCCTCCAAGGAGTAAGAAaccctggaccacccagcccAGCAAGGAT
ACTGAGAGCAAGAGAG
>chr13:96691362-96691432 71bp CATGGCCTCCAAGGAGTAAGAA CTCTCTTGCTCTCAGTATCCTTGCT
CATGGCCTCCAAGGAGTAAGAAaccctggaccacccaccccagcccAGCA
AGGATACTGAGAGCAAGAGAG
>chr13:83870870-83870935 66bp CATGGCCTCCAAGGAGTAAGAA CTCTCTTGCTCTCAGTATCCTTGCT
CATGGCtTCCAAGGAGTAAGAAaccctggaccacccagcccAGCAAGGAT
ACTGAGAGCAAGAGAG
>chr13:34334498-34334562 65bp CATGGCCTCCAAGGAGTAAGAA CTCTCTTGCTCTCAGTATCCTTGCT
CATGGCCTCCAAGGAGTAAGAAacccggaccacccagcccAGCAAGGATA
CTGAGAGCAAGAGAG
>chr14:45034779-45034849 71bp CATGGCCTCCAAGGAGTAAGAA CTCTCTTGCTCTCAGTATCCTTGCT
CATGGCCTCCAAGGAGTAAGAAaccctggatcacccaccccagcccAGCA
AGGATACTGAGAGCAAGAGAG
>chr14:40809117-40809187 71bp CATGGCCTCCAAGGAGTAAGAA CTCTCTTGCTCTCAGTATCCTTGCT
CATGGCCTCCAAGGAGTAAGAAaccctggaccactcaccccagcccAGCA
AGGATACTGAGAGCAAGAGAG
>chr16:45938826-45938896 71bp CATGGCCTCCAAGGAGTAAGAA CTCTCTTGCTCTCAGTATCCTTGCT
CATGGCCTCCAAGGAGTAAGAAaccctggaccacccaccccaccccAGCA
AGGATACTGAGAGCAAGAGAG
>chr18:61627109-61627174 66bp CATGGCCTCCAAGGAGTAAGAA CTCTCTTGCTCTCAGTATCCTTGCT
CATGGCCTCCAAGGAGTAAGAAaccctggaccacccagcccAGCAAGGAT
ACTGAGAGCAAGAGAG
>chr18:49339446-49339511 66bp CATGGCCTCCAAGGAGTAAGAA CTCTCTTGCTCTCAGTATCCTTGCT
CATGGCCTCCAAGGAGTAAGAAaccctggaccaccaagcccAGCAAGGAT
ACTGAGAGCAAGAGAG
>chr18:13677281-13677351 71bp CATGGCCTCCAAGGAGTAAGAA CTCTCTTGCTCTCAGTATCCTTGCT
CATGGCCTCCAAGGAGTAAGAAaccctggacaacccacctcagcccAGCA
AGGATACTGAGAGCAgGAGAG
>chr20:30915133-30915198 66bp CATGGCCTCCAAGGAGTAAGAA CTCTCTTGCTCTCAGTATCCTTGCT
CATGGCCTCCAAGGAGTAAGAAaccctggaccacccagcccAGCAAGGAT
ACTGAGAGCAAGAGAG
>chr1:218714935-218715005 71bp CATGGCCTCCAAGGAGTAAGAA CTCTCTTGCTCTCAGTATCCTTGCT
tATGGCCTCCAAGGAGTAAGAAaccctggaccacccaccccagcccAGCA
AGGATACTGAGAGCAAGAGAG
>chr1:175984869-175984939 71bp CATGGCCTCCAAGGAGTAAGAA CTCTCTTGCTCTCAGTATCCTTGCT
CATGGCCTCCAAGGAGTAAGAAaccctggatcacccacccccgcccAGCA
AGGATACTGAGAGCAAGAGAG
>chr2:191327597-191327667 71bp CATGGCCTCCAAGGAGTAAGAA CTCTCTTGCTCTCAGTATCCTTGCT
CATGGtCTCCAAGGAGTAAGAAaccctggaccacccaccccaccccAGCA
AGGATACTGAGAaCAAGAGgG
>chr3:129269951-129270016 66bp CATGGCCTCCAAGGAGTAAGAA CTCTCTTGCTCTCAGTATCCTTGCT
CATGGCCTCCAAGGAGTAAGAAaccctggaccacccagccaAGCAAGGAT
ACTGAGAGCAAGAGAG
>chr3:98345781-98345846 66bp CATGGCCTCCAAGGAGTAAGAA CTCTCTTGCTCTCAGTATCCTTGCT
tATGGCCTCCAAGGAGTAAGAAaccctggaccacccagcccAGCAAGGAT
ACTGAGAGCAAGAGAG
>chr4:157962510-157962575 66bp CATGGCCTCCAAGGAGTAAGAA CTCTCTTGCTCTCAGTATCCTTGCT
CATGGCCTCCAAGGAGTAAGAAaccctggaccacccagcccAGCAAGGAT
ACTGAGAGCAAGAGAG
>chr4:130314800-130314865 66bp CATGGCCTCCAAGGAGTAAGAA CTCTCTTGCTCTCAGTATCCTTGCT
CATGGCCTCCAAGGAGTAAGAAaccctggaccacccagcccAGCAAGGAT
ACTGAGAGCAAGAGAG
>chr4:86252083-86252148 66bp CATGGCCTCCAAGGAGTAAGAA CTCTCTTGCTCTCAGTATCCTTGCT
CATGGCCTCCAAGGAGTAAGAAaccctggaccacccagactAGCAAGGAT
ACTGAGAGCgAGAGAa
>chr5:95958448-95958518 71bp CATGGCCTCCAAGGAGTAAGAA CTCTCTTGCTCTCAGTATCCTTGCT
CATGGCCTCCAAGGAGTAAGAAaccctggaccatccacccaagcccAGCA
AGGATACTGAGAGCAAGAGAG
>chr5:77092010-77092079 70bp CATGGCCTCCAAGGAGTAAGAA CTCTCTTGCTCTCAGTATCCTTGCT
CATGGCCTCCAAGGAGTAAGAAacttggaccacccaccccagaccAGCAA
GGATACTGAGAGCAAGAGAG
>chr5:69853932-69853997 66bp CATGGCCTCCAAGGAGTAAGAA CTCTCTTGCTCTCAGTATCCTTGCT
CATGGCCTCCAAGGAGTAAGAAaccctggaccacccagcccAGCAAGGAT
ACTGAGAGCAAGAGAG
>chr5:20939797-20939867 71bp CATGGCCTCCAAGGAGTAAGAA CTCTCTTGCTCTCAGTATCCTTGCT
CATGGCtTCCAAGGAGTAAGAAaccctggaccacccacccaagcccAGCA
AGGATACTGAGAGCAAGAGAG
>chr5:8497902-8497967 66bp CATGGCCTCCAAGGAGTAAGAA CTCTCTTGCTCTCAGTATCCTTGCT
CATGGCCTCCAAGGAGTAAGAAaccctggaccatccagcccAGCAAGGAT
ACTGAGAGCAAGAGAG
>chr6:11056261-11056331 71bp CATGGCCTCCAAGGAGTAAGAA CTCTCTTGCTCTCAGTATCCTTGCT
CATGaCCTCCAAGGAGTAAGAAaccccggactacccaccccagcccAGCA
AGGATACTGAGAGCAAGAGAG
>chr8:101206055-101206120 66bp CATGGCCTCCAAGGAGTAAGAA CTCTCTTGCTCTCAGTATCCTTGCT
CATGGCCTCCAAGGAGTAAGAAaccctggaccacccagcccAGCAAGGAT
ACTGAGAGCAAGAGAG
>chrX:85986394-85986464 71bp CATGGCCTCCAAGGAGTAAGAA CTCTCTTGCTCTCAGTATCCTTGCT
CATGGCCTCCAAGGAGTAAGAAaccctggaccacccaccacagcccAGCA
AGGATACTGAGAaCAAGAGAG
>chrX:37840461-37840531 71bp CATGGCCTCCAAGGAGTAAGAA CTCTCTTGCTCTCAGTATCCTTGCT
tATGGCCTCCAAGGAGTAAGAAaccctggaccacccaccccagcccAGCA
AGGATACTGAGAGCAAGAGAG
```


9. Check that the amplicon length is between 50-150 and that the melting temperatures are comparable to other primers in the multiplex design. Also check for self-dimers and cross primer dimers with other primers in the multiplex reaction using the Multiple Primer Analyzer: [link](https://www.thermofisher.com/us/en/home/brands/thermo-scientific/molecular-biology/molecular-biology-learning-center/molecular-biology-resource-library/thermo-scientific-web-tools/multiple-primer-analyzer.html) . Self-dimers are less problematic if not predicted by Primer Express. 
   
```
Name              	Sequence                 	Tm°C	CG%	nt	A	T	C	G	Extinction coefficient(l/(mol·cm)	Molecular weight(g/mol)	nmol	µg/OD260
rn7-chrB-Gapdh-F  	catggcctccaaggagtaagaa   	66.5	50.0	22	8.0	3.0	5.0	6.0	224100.0                         	6777.5                 	4.5 	30.2
rn7-chrB-Gapdh-R  	ctctcttgctctcagtatccttgct	65.4	48.0	25	2.0	11.0	9.0	3.0	209700.0                         	7500.9                 	4.8 	35.8
rn7-basket-Gapdh-P	cctggaccacccagc          	62.0	73.3	15	3.0	1.0	8.0	3.0	133000.0                         	4482.9                 	7.5 	33.7
rn7-chr1-Rpp30-F  	tcatggacctggctttcttgt    	66.1	47.6	21	2.0	9.0	5.0	5.0	185000.0                         	6394.2                 	5.4 	34.6
rn7-chr1-Rpp30-R  	tcgtgccaatcgcctactc      	66.7	57.9	19	3.0	5.0	8.0	3.0	167100.0                         	5699.7                 	6.0 	34.1
rn7-chr1-Rpp30-P  	ccaaagacacagattaa        	49.0	35.3	17	9.0	2.0	4.0	2.0	180400.0                         	5180.5                 	5.5 	28.7
rn7-chrM-Nd1-F    	aacggaaaatcctaggctacataca	64.7	40.0	25	11.0	4.0	6.0	4.0	257800.0                         	7652.1                 	3.9 	29.7
rn7-chrM-Nd1-R    	catatgggcctacgatgttg     	63.1	50.0	20	4.0	6.0	4.0	6.0	191700.0                         	6148.1                 	5.2 	32.1
rn7-chrM-Nd1-P    	ctacgcaaaggcc            	51.4	61.5	13	4.0	1.0	5.0	3.0	123200.0                         	3928.6                 	8.1 	31.9
rn7-chrM-Nd4-F    	tcgcccacggcttaacc        	67.6	64.7	17	3.0	3.0	8.0	3.0	149300.0                         	5091.3                 	6.7 	34.1
rn7-chrM-Nd4-R    	tcgttcgtagttggtgtttgct   	65.9	45.5	22	1.0	11.0	3.0	7.0	199000.0                         	6769.5                 	5.0 	34.0
rn7-chrM-Nd4-P    	cctcactcttattctgc        	50.6	47.1	17	2.0	7.0	7.0	1.0	142600.0                         	5047.3                 	7.0 	35.4


```

```
                Self-Dimers:

1 dimer for: rn7-chrM-Nd4-F
5-tcgcccacggcttaacc->
           | |||| |
         <-ccaattcggcacccgct-5


               Cross Primer Dimers:

rn7-chrB-Gapdh-F with rn7-chrB-Gapdh-R
rn7-chrB-Gapdh-F
5-ctctcttgctctcagtatccttgct->
     |||| |||   | |  |    
  <-aagaatgaggaacctccggtac-5

rn7-chrB-Gapdh-F with rn7-chr1-Rpp30-R
rn7-chrB-Gapdh-F
5-catggcctccaaggagtaagaa->
               ||||| |  
             <-ctcatccgctaaccgtgct-5

rn7-chr1-Rpp30-P with rn7-chrM-Nd4-P
rn7-chr1-Rpp30-P
5-ccaaagacacagattaa->
           |||| |||
        <-cgtcttattctcactcc-5

rn7-chrM-Nd1-F with rn7-chrM-Nd1-R
rn7-chrM-Nd1-F
5-aacggaaaatcctaggctacataca->
       || ||| |||||       
    <-gttgtagcatccgggtatac-5



```










