---
layout: default
title: "RT Image Review Worklist Triage"
date: 2019-11-29
tags: [arch, cache, imaging, mosaiq, soa]
original_url: http://www.dg1an3.net/2019/11/image-review-zombie-apocalypse-part-ii.html
---

In  this [previous post](http://www.dg1an3.net/2017/08/better-image-review-workflows-part-i.html) on better image review workflows, David Clunie's noted zombie apocalypse was imminent as we waited for better predictive models for image review behavior.  Well, the zombie apocalypse never happened.  But I have made some progress in sketching a basic model to analyze usage patterns.

The inputs are:

  * Time of day of physician login / workstation location
  * Time of day of image acquisition
  * Time offfset of image approval
  * Image feature vector, in some latent space of patient geometry

Then these are regressed to get a prediction of likelihood of image being opened on a workstation, at a given time.

What can be done with this prediction?  Caching on the local drive could be accomplished using:

  * Windows Offline Files
  * Dokan library, or similar
  * BDS Storage for local drive

Additionally, memory caching could be used

  * For a WCF-based SoA architectures, memory caching can be implemented either in the client (using a custom binding stack), or in the service as a custom IOperationInvoker.
  * MSQ 3D IRW already implements a memory caching for AVS-based cone beam CTs.

So with some implementation for the actual caching, we can fit the model and produce predictions.  If only we had some test data...

Stay tuned for a demo of the model, possibly with only fake input data.
