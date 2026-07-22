---
layout: default
title: "ClearCanvas and RT Objects"
date: 2011-10-28
tags: [diy, foss, imaging, viz]
original_url: http://www.dg1an3.net/2011/10/clearcanvas-and-rt-objects.html
---

I'm looking at the source code for [ClearCanvas](http://www.clearcanvas.ca/dnn/) and wondering aloud how hard it would be to modify to store RT objects.  For instance:

  * Current generation DICOM RT SOPs
  * Supplement 74 objects
  * Patient positioning objects
  * Next generation DICOM RT SOPs

Of course, rendering the objects in the Volume.MPR viewer would be especially cool, but one step at a time...maybe registering a replacement for ImageReview3DForm would be a logical next step.
