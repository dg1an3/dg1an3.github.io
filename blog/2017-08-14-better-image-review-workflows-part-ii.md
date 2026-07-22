---
layout: default
title: "Better Image Review Workflows Part II: DICOM Spatial Registrations"
date: 2017-08-14
tags: [arch, data, dicom, imaging, mosaiq, offset]
original_url: http://www.dg1an3.net/2017/08/better-image-review-workflows-part-ii.html
---

I remember meeting with our colleagues at Varian's Imaging Lab a few years back, to discuss (among other things) better ways of using [DICOM Spatial Registration Objects](http://dicom.nema.org/medical/dicom/2016d/output/chtml/part03/sect_C.20.2.html) (SROs) to encode radiotherapy setup corrections.  They had been considering support for some advanced features, like 4D CBCT and dynamic DRR generation.

It was clear that having a reliable DICOM [RT Plan](http://dicom.nema.org/medical/dicom/2016c/output/chtml/part03/sect_A.20.3.html) Instance UID and referenced [Patient Setup module](http://dicom.nema.org/medical/dicom/2016c/output/chtml/part03/sect_C.8.8.12.html) would be immensely useful in interpreting the setup corrections.   But where would this information be stored?  As private attributes in the CBCT slices?  Or in the SRO itself?  The [treatment record](http://dicom.nema.org/medical/dicom/2016c/output/chtml/part03/sect_A.29.3.html) contains this relationship for each treatment field, but there is no way of encoding a reference to a standalone setup image within the treatment record (or so I've been told)

Siemens has, for years now, used a DICOM [Structured Report](http://dicom.nema.org/medical/dicom/current/output/chtml/part03/sect_A.35.html) to encode offset values, in lieu of an SRO, at least for portal images.  I think skipping the SRO entirely was a mistake, but when I look at the state of RT SROs today, it seems in retrospect that a semantically meaningful Structured Report to pull together the other objects (SRO,  treatment record, CBCT slices) would be quite an advanced over current practice.  Looking at some of the defined IODs for structured reports:

  * Mammography CAD Structured Report
  * Chest CAD Structured Report
  * Acquisition Context Structured Report

it does not seem too far fetched to consider an SR encoding relationships among a CBCT or portal image and their context objects.

I've started (again) reading David Clunie's [Structured Report](http://www.dclunie.com/pixelmed/DICOMSR.book.pdf) book, in hopes of gaining more insight in what can (or should not) be encoded using SRs.  It seems like a quite powerful capability--I'm wondering why the RT domain has not made more use of it...
