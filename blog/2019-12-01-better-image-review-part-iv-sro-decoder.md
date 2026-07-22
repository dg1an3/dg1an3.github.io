---
layout: default
title: "SRO Decoder Ring QA Worklist"
date: 2019-12-01
original_url: http://www.dg1an3.net/2019/12/better-image-review-part-iv-sro-decoder.html
---

And in the sledgehammer solution department--as mentioned in the previous post, the problem of mapping SRO meaning is insidious.  Confusion about patient positions (as in the this post) is bad enough.  So why not use machine learning here as well?

Given an SRO and an offset, train an ML model to recognize the input-output relationship.  Notebook link is here.

To turn the notebook in to a production service, we made the following adaptations:

  * Fable ElmishFatline front end on IPFS
  * Flask RESTful Web App on azure
  * Train through notebook
  * Weights in IPFS

A few contextual pieces of information that still need work:

  *  what about association to site?
  *  iView: Applying shift after first field--how to enter with TPO that won't associate with second field?
