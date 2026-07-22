---
layout: default
title: "Dynamic call graph treemaps"
date: 2009-11-16
tags: [ideas, viz]
original_url: http://www.dg1an3.net/2009/11/dynamic-call-graphs-treemaps.html
---

I'm trying to come up with new visualization techniques for analyzing code.  The static structure diagrams / UML diagrams are all well and fine, but I kind of want something that shows the relationship among objects resulting from the actual code execution.

So I'm looking at whether you can create a tree map, where the tree reflects the call hierarchy of the code with each method as a node, but then the size of each node in the tree map is proportional to the amount of time spent executing that method.  And maybe a very Tufte-esque graph inside each node could reflect consumption of resources (like memory) that were allocated / released during the execution.
