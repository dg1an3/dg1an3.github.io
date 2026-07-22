---
layout: default
title: "Better Image Review User Experience"
date: 2017-03-17
tags: [arch, imaging, soa, viz]
original_url: http://www.dg1an3.net/2017/03/better-image-review-experience.html
---

In my [previous post](http://www.dg1an3.net/2016/04/how-to-make-image-review-better.html), I mentioned three aspects of image review that can be improved.  The first of these is improvements in the user experience during image review.

The increased use of image-guidance during the course of treatment represents a significant source of knowledge about the delivery, but also an additional burden on daily routines.  The subjective tedium of working through a list of images can be lightened by enhancing aspects of the review user experience.

Usability concerns that can be addressed include:

  * Color schemes that are better adjusted for visual analysis, for instance with darker colors
  * Animated transitions to facilitate visual parsing of state changes, such as pop-up toolbars and changes in image selection
  * Use of spatial layout to convey semantic relationships, as in thumbnail and carousel presentations of images in temporal succession
  * Progressive rendering and dynamic resizing of image elements, to minimize variations in the availability of network resources

Combining these techniques in a single workspace can produce a compelling user experience for image review.

A number of architectural patterns are used to support these techniques.  Examples of these patterns are contained in the [PheonixRt.Mvvm](http://github.com/dg1an3/PheonixRt.Mvvm) prototype.
