---
date: 2013-11-02T22:14:08Z
title: "easy-Report script for easy R reporting"
---

Coding can be very exciting. And the more excited you are the less you wish to comment your code or to create any simple report about what you have done. It becomes even more complicated if your code produces not just one output file but also a lot of different figures which can change upon changing some of the code parameters (for example when you need to experiment with your parameter set and find the best one and then prove that it was the best). In this case I would spend a lot of time for coding, then for commenting and then for creating a report in a pdf or powerpoint/keynote format. Luckily there are tools that can help with reporting your results in a very efficient way.

I was fascinated by those tools and wrote a script that quickly creates an html and slide reports from an [RMarkdown](http://www.rstudio.com/ide/docs/authoring/using_markdown) file. The tools that I used were two existing R packages: [knitr](https://github.com/yihui/knitr) and [slidify](https://github.com/ramnathv/slidify).

Proper reporting not only helped me a lot in my data analysis but now I also spend a significantly less amount of time for creating my project update reports every couple of weeks (I practically spend no time!)

The script is quite simple and ready to use, so I would highly recommend it to R users of any level.

The script repository is located here (there is also a detailed description on it’s usage):

[https://github.com/wikiselev/easy-Report](https://github.com/wikiselev/easy-Report)

To quickly get the script repository, run the script and see an example report please follow these steps:

```
git clone https://github.com/wikiselev/easy-Report.git
cd easy-Report
Rscript easy-Report.R script.Rmd report
```

After running the code above all output report files will be located in ‘report’ folder. If there was no error you should get the same HTML reports as these two:

[http://wikiselev.github.io/easy-Report/report.html](http://wikiselev.github.io/easy-Report/report.html)

[http://wikiselev.github.io/easy-Report/slides.html](http://wikiselev.github.io/easy-Report/slides.html)

I hope this script will be useful for some of you and very much accelerate your work progress! Please let me know if you have any questions.
