# House keeping gene design rules
A lot of the design is based on aging study: **Age-Related Gene Expression Signature in Rats Demonstrate Early, Late, and Linear Transcriptional Changes from Multiple Tissues** [link](https://pubmed.ncbi.nlm.nih.gov/31533046/).

We focus on kidney tissues.

Using the bulk RNAseq data from the above paper, we would like to design primers using genes that:
- Do not vary too much between ages
- Do not vary too much between samples
- Do not locate on chrX (for RAGE study, we report change in chrX copy numbers)--Hprt1 locates on chrX.

# Reference gene comparison
We have a list of popular reference genes from literature. Based on the bulk RNAseq data (sampled from kidneys of rats of different ages), we have the following plots.

Note that Ppial4d and LOC100911252 (PREDICTED: Rattus norvegicus peptidyl-prolyl cis-trans isomerase A-like) are highly-similar to Ppia. Therefore we included them here to check whether any off-target effect by our primers will lead to undesired amplification.
1. Normalized counts of popular reference genes ![alt text](<Normalized counts of reference genes.png>)
2. Adjusted R-square of vst-normalized expression vs age ![alt text](<Reference gene adjusted R square.png>)
3. Fitted coefficient of vst-normalized expression vs age ![alt text](<Reference gene fitted coefficient.png>)
4. Coefficient of variation across all the samples from all ages ![alt text](<Reference gene CV all ages.png>)
5. Coefficient of variation among different ages ![alt text](<Reference gene CV across ages.png>)

Based on above plots, we can choose top two house keeping genes:
- Ipo8 (abundant)
- Ppia (it turns out that Ppial4d and LOC100911252 are both very stable as well. It's ok to amplify all three together as they are highly similar)

Also, We include Actb for the sake of comparison.