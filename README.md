# Making Gene Trees
This is the workflow we used to create my gene trees.

# Making your .fasta file.
## Gather the genes you need to build your tree.
If you can, try to find at least 20 references for each gene. Below are two databases you can pull genes from:
Uniprot:
[
](https://www.uniprot.org/uniprotkb?query=narH&facets=annotation_score%3A5)https://www.uniprot.org/uniprotkb?query=narH&facets=annotation_score%3A5

(Make sure the rating on Uniprot is a 4/5 or 5/5!)

KEGG:

[
](https://www.genome.jp/kegg/kegg2.html)https://www.genome.jp/kegg/kegg2.html

Pulling genes from your data set. Here we are pulling from our annotations.tsv DRAM output. Here, we are using the KO ID to find the gene:

```
awk -F "\t" '$11=="K00370"' annotations.tsv | awk -F "\t" '{print $1}'
```

Then we need to pull the amino acid (AA) sequence from the genes.faa DRAM output:

```
grep -A 2 CT_B1_Sept_N_S_A_2021_B_bin.12_k121_693270_12 genes.faa
```




