---
date: 2017-01-21T19:57:37Z
title: "Get GSEA done!"
categories: ["work"]
tags: ["GSEA"]
summary: "Thousands of times I've heard of the Gene Set Enrichment Analysis or GSEA. Thousands of times I tried to run it and thousands of times I failed..."
---

## Introduction

Thousands of times I've heard of the [__Gene Set Enrichment Analysis__](http://software.broadinstitute.org/gsea/index.jsp) or GSEA. Thousands of times I tried to run it and thousands of times I failed!

As lucky as it can get my recent collaborative work required me to run GSEA. I thought this time I will finally figure out how to do it. As usual it didn't work out well...

First of all, there are millions of R tools which can run GSEA analysis. A simple Google search provides quite a large list: [https://www.google.co.uk/search?q=Gene+Set+Enrichment+Analysis+r](https://www.google.co.uk/search?q=Gene+Set+Enrichment+Analysis+r). However, if you read manuals from these tools it is still quite tricky to figure out how to run GSEA.

Additionally, most of the tools are written and explained for microarray data only. In my case I needed to perform GSEA on a mix of microarray and single-cell RNA-Seq data. So I still had no idea how to start.

As usual in these cases it is better to go to the origin and figure out what the definition of GSEA is. It is easy to find the original paper about GSEA: [http://www.pnas.org/content/102/43/15545.full.pdf](http://www.pnas.org/content/102/43/15545.full.pdf). From reading the paper it is clear that in a very primitive way to perform the GSEA one just needs two gene sets, where one is ranked using continuous variable and another one is just a simple gene list. Without going into the details, the goal of GSEA is to determine whether the members of the second set are randomly distributed throughout the first set or primarily found at its top or bottom. I had already prepared both gene sets but still could not find a tool to perform this simple procedure.

Again, going back to the origins, the first GSEA tool developed by the authors of the original publication is available from the Broad Institute webiste: [http://software.broadinstitute.org/gsea](http://software.broadinstitute.org/gsea). I downloaded and ran the tool. However, I was still unable ot get any meaningful result, except getting different uninterpretable errors.

So, when all hopes were lost, I desperately contacted a bioinformatician who was helping my collaborators with the analysis. Apparently he went through similar difficulties with GSEA before, but he was more persistent than I was and he was able to run it using the tool from the Broad Institute. But more importantly he recorded his steps in a manual and kindly shared it with me.

So, after such a long introduction I can finally tell you how to easily run GSEA when you have two gene sets, one of which is ranked using a continuous variable (e.g. log-fold change in expression if the genes are differentially expressed).

## Gene rank file (*.rnk)

The first gene set should be created, ranked by some value and written to a file. The simplest example would be a set of differentially expressed genes ranked by their log-fold change. The file format must be [rnk](http://software.broadinstitute.org/cancer/software/gsea/wiki/index.php/Data_formats#RNK:_Ranked_list_file_format_.28.2A.rnk.29):

{{< figure src="/img/Rnk_format_snapshot.gif" title="" >}}

## Gene file (*.grp)

The second gene set should be just created and written to a file. The file format must be [grp](http://software.broadinstitute.org/cancer/software/gsea/wiki/index.php/Data_formats#GRP:_Gene_set_file_format_.28.2A.grp.29):

{{< figure src="/img/Grp_format_snapshot.gif" title="" >}}

## Run GSEA

1. You can download and launch the software by clicking the __Launch__ button at [http://www.broadinstitute.org/gsea/downloads.jsp](http://www.broadinstitute.org/gsea/downloads.jsp).
2. Click on __Load data__ button in the left menu.
3. Load the two data files (_rnk_ and _grp_).
4. In the main menu at the top click on _Tools_ -> _GseaPreranked_.
5. Click on _Gene sets database_.
6. Click on _Gene sets (grp)_ tab and choose the _grp_ file you have loaded.
7. Click OK.
8. Click on _Ranked list_.
9. Choose the _rnk_ file you have loaded.
10. Set _Collapse dataset to gene symbols_ to __false__.
11. Click on show _Basic Fields_.
12. Change _Enrichment statistic_ to __classic__.
13. Set _Max size: exclude larger sets_ to a value higher than the number of genes in you gene set.
14. Set _Min size: exclude smaller sets_ to __1__ for the peace of mind.
15. Click _Run_ button!

## View the results

1. Click on _Analysis history_ in the left menu.
2. In _Reports_ -> _Current session_ click on your newly created report
3. In _Files produces as part of this analysis_ double click on the html report. The report will open in your browser window.
4. To view a standard GSEA plot click on the _Snapshot of enrichment results_ link:

{{< figure src="/img/gsea_plot.png" title="" >}}

## Conclusions

Hope this manual was helpful for you and hope you have managed to run GSEA analysis on your data. If you know any other GSEA tools please let me know!
