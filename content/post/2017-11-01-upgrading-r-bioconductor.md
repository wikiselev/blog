---
title: Upgrading R + Bioconductor
author: ~
date: '2017-11-01'
slug: upgrading-r-bioconductor
categories: ["work"]
tags: ["r", "bioconductor", "notes"]
summary: "I have just learnt that Bioconductor developers should __NOT__ always use the development version..."
---

_Consider this post as a personal note to my future self_

I have just learnt that Bioconductor developers should __NOT__ always use the development version. On the [official website](https://bioconductor.org/developers/how-to/useDevel/) it says:

> This means that, from mid-October through mid-April, Bioconductor developers should be developing against R-devel. From mid-April to mid-October, developers should use R-release (actually, the R snapshot from the R-x-y-branch) for Bioconductor development.

So I needed to change my _R_ version from `development` to `release` and I did. And as it usually happens I got into trouble while trying to use some of the R packages. Luckily I found this [nice RStudio post](http://shiny.rstudio.com/articles/upgrade-R.html) on upgrading _R_ and I used some of the recommendations they provide. 

However, then I ran into another problem which was a bit more complicated. When installing some of the packages where _C++_ compilation was required, my __MacOS__ `gcc` installation complained that it couldn't support `OpenMP` flag. I spent quite a lot of time figuiring out how to solve it until I found [this very useful post](http://thecoatlessprofessor.com/programming/openmp-in-r-on-os-x/). By following their recommendations I was able to fix all issues and installed all the necessary packages.
