---
layout: default
title: "<retro> What is Image Quality? </retro>"
date: 2018-03-05
original_url: http://www.dg1an3.net/2018/03/what-is-image-quality.html
---

[![](images/2018-03-05-what-is-image-quality-r1.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEiQZ8aKuEONsZJ0HmEPS6Noidc4rMNMdq5STThEuJpB5sFphK7erpm7OlGiMwVWOoDV_DXSMiaruiTcJ69pXbSQMX3IUT-h57tVMzw5iEKMuorvsVXzrB294bGYYjCZEEqsYYDe8Q/s1600/eyeball.png)

_originally[on LinkedIn](https://www.linkedin.com/pulse/what-image-quality-derek-lane)_

I saw a talk at AAPM 2015 by Kyle Myers (from the FDA's [Office of Science and Engineering Laboratories](http://www.fda.gov/AboutFDA/CentersOffices/OfficeofMedicalProductsandTobacco/CDRH/CDRHOffices/ucm115989.htm)) about the Channelized Hotelling Observer ([Barrett et al 1993](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC47653/)), which is a parametric model of visual performance based on spatial frequency selective channels in areas [V1 and V2](https://www.researchgate.net/profile/Daniel_Felleman/publication/21420306_Information_Processing_in_the_Primate_Visual_System_An_Integrated_System_Perspective/links/54e50d5d0cf276cec1730786.pdf).

She was discussing the use of the CHO model for selecting optimal CBCT reconstruction parameters, but I ran across an obvious application of the technique to the problem of JPEG 2000 parameter selection ([Zhang et al 2004](https://labs.psych.ucsb.edu/eckstein/miguel/research_pages/pdfpapers/ZhangIEEE04.pdf)).

It reminded me of the RDP plugin prototype I had developed a few years back, which demonstrated the ability to dynamically adjust compression performance during medical image review on an RDP or Citrix session. My prototype could also benefit from optimizing the CHO confidence interval (though it used JPEG XR instead of JPEG 2000), but possibly more interesting is the ability to predict the presentation parameters to be delivered over the channel, such as zoom/pan, window/level, or other radiometric filters to be applied to the image. It could also be used to determine when certain regions of the parameter space are _not_ feasible for image review, because the confidence interval collapses (for instance, if you set window width=1).

So if anyone asks "What is Image Quality", you can tell them: "Image Quality = Maximized CHO Confidence Interval" (or maximized CHO Area Under Curve). Got it?

P.S. there is very nice Matlab implementation of the CHO model in a package called [IQModelo](http://didsr.github.io/IQmodelo/), with some examples of calculating CI and AUC.
