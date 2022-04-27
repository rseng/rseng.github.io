---
title: "The Research Software Ecosystem"
layout: "project"
image: rsepedia-ecosystem.png
github: https://github.com/rseng/rsepedia-analysis/
project_url: https://rseng.github.io/rsepedia-analysis/
description: "Automated analysis of the Research Software Encyclopedia ecosystem."
categories: [definition, software, taxonomy, ecosystem, analysis]
badges:
 - type: info
   tag: analysis
 - type: info
   tag: software
tags:
 - definition
 - software
---

## The Research Software Ecosystem

> An automated analysis to summarize and understand important software underlying our community software.


This project provides an automated analysis that uses the [Research Software Engineering Community Database](https://rseng.github.io/software) and software to generate high level metrics to describe the ecosystem. We use [CiteLang](https://github.com/vsoch/citelang) to parse dependency files and generate the analysis.

 - [Research Software Ecosystem](https://rseng.github.io/rsepedia-analysis/)
 - [Twitter Announcement](https://twitter.com/vsoch/status/1518381076447580160)

The underlying motivation is to show the underlying libraries that are driving research software in our community.
It shouldn't be surprising that many of them are related to data structures or formats, and web requests,
and not "domain-specific" and we tend to think of for research software. This set of analyses and
software also wants to champion new ideas or approaches for evaluating the value of a research
software engineer. The current metric, the academic publication, is not good enough or easy enough
for us to sustain. It selects for those with the time and priviledge to stop and write a paper.
We need to be valued based on what we actually do, and not an extra step that is required
and only possible for a subset. 

