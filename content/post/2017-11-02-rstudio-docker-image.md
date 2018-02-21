---
title: RStudio Docker Image
author: ~
date: '2017-11-02'
slug: rstudio-docker-image
categories: []
tags: []
---

To facilitate the usage of our [single cell RNA-seq analysis course](http://hemberg-lab.github.io/scRNA.seq.course) we provide a Docker image that has all the software installed and all the materials included. So, instead of isntalling all the required `R` package a user could only install [docker](https://docs.docker.com/engine/installation/), download our docker image and run the course exercises inside a docker container. In the past we used to provide a docker image with only simple console `bash` and `R` support. It worked pretty well, the only downside was that users were not able to plot graphs from the interactive `R` session inside the `docker` condainer. I tried to fix this issue but was not successful.

Then I found out about `RStudio-docker`
