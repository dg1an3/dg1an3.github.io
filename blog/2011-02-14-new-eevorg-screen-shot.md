---
layout: default
title: "New Eevorg screen shot"
date: 2011-02-14
tags: [creative, ideas, viz]
original_url: http://www.dg1an3.net/2011/02/new-eevorg-screen-shot.html
---

After mucking around for some time, I've managed to dust off my old Eevorg code and incorporate it (with minimal bells and whistles) in to a basic MFC application.  We are rendering with interpolation, to support multiple zoom scales across the child hierarchy.

We also have a simple mechanism to back up (showing the parent to the left of the current eevorg).

[![](images/2011-02-14-new-eevorg-screen-shot-r1.png)](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEiDKCF3NdF_isZ0cfepGf7Pj9apgEsp9XA0P6AS_7xiwoV_onjs-XzrhFUCx_RF1IpLnl8bGbAg4GUqB1eSRWsMEGYTfutjxbx1C-1gfYJwoJ7B8S1hyh26J9dls6a-nirb-PonJw/s1600/2011.02.14+Eevorg+Screenshot.PNG)

Still to be done, is to implement:

  * a persistence mechanism
  * some properties (state count, entropy, maybe lookup table, maybe favorite button)
  * filtering of later generations, to eliminate the aliases in the bottom of some of the eevorg
  * implement as an OpenGL rendering (would take care of filtering using texture mipmaps)

Of course, we would like to implement as a web service so that people can use a browser to browse the eevorg.  And eventually maybe an iPhone/iPad app would be pretty nifty too...
