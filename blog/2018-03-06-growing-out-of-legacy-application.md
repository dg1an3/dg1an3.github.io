---
layout: default
title: "Growing out of a legacy application"
date: 2018-03-06
original_url: http://www.dg1an3.net/2018/03/growing-out-of-legacy-application.html
---

Trying to grow out of a dated legacy application is no small feat, and there is undoubtedly a cottage industry dedicated to consulting on how to do just that.

The most effective pattern I've encountered for this is the [Strangler Application](https://www.martinfowler.com/bliki/StranglerApplication.html), so named from some kind of tree seen down under.  But it seems that there are better and worse ways of approaching a Strangler application.

I think Fowler's captures the key aspects: a proper Strangler application needs both a static data strategy ("asset capture") and a dynamic behavior strategy ("event interception").  And it is important that both parts need to be involved in a _two-way_  strategy for getting data and events back and forth.  Fowler stresses the strategic importance of this two-way strategy, as it creates flexibility for determining the order of asset capture.  Words to live by...
