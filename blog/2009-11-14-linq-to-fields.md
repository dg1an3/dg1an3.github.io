---
layout: default
title: "LINQ to Fields"
date: 2009-11-14
tags: [ideas, imaging]
original_url: http://www.dg1an3.net/2009/11/linq-to-fields.html
---

I've been looking in to the lambda expression capability in LINQ / C# 3.0, and it occurred to me that it provides the perfect mechanism for implementing a field abstraction that I have been thinking about for a while.  The idea is that an image / volume / region / transform is represented at its most basic level as a lambda which takes a vector is input and produces a scalar, vector, or bool as its output.

The most interesting part is the use of the Expression<> to create expressions trees.  This allows lambdas to be combined in to algebraic expressions to form new lambdas, but the result is an expression tree that can be examined via reflection.  So, one could assemble the lambda that represents some image processing operation, and then an inference could be made to construct a pipeline (for instance, with ITK) that implements the expression.

Then LINQ could be used to construct these expressions, given a set of data objects and possible transformations that could be applied.  Each field entity would have the necessary attributes to describe how it could be combined with other entities, and then the LINQ query would do the combining.
