---
title: "The Research Software Engineer Encyclopedia"
layout: "project"
image: rsepedia.png
github: https://github.com/rseng/rse/
project_url: https://rseng.github.io/rse/
description: "A community effort to define criteria and a taxonomy for research software."
categories: [definition, software, taxonomy]
badges:
 - type: info
   tag: definition
 - type: info
   tag: software
tags:
 - definition
 - software
---

## The Research Software Encyclopedia

> A community driven, open source strategy to derive context-specific definitions of research software.

What is research software? Simply stated, research software exists to support
research. If we want to pursue better research, we then must understand it [[3]](#ref).
This leads us to ask some basic question:

 1. What is research software?
 2. What are criteria that might help to identify research software?
 3. How do we organize research software?

While we could make an attempt to derive a holistic definition, this approach 
would be limited in not taking into account the context under which the definition
is considered. For example, needing to define research software to determine
eligibility for a grant is a different scenario than a journal needing
to decide if a piece of software is in scope for publication, and both
are different from an effort to study research software. In all cases, 
the fundamental need for a context-specific definition is not only important in these
scenarios, but also for basic communication. If I am to call something research
software, it's essential that you know the criteria that I am using to consider it,
how highly I consider each of those criteria, and a possibly classification
that I am using to further drive my choices.

## A Context Specific Definition

This effort, paired with [the document that prompted its original thinking](https://docs.google.com/document/d/1wDb0udH9OrFWrMBsAVb8RrUMCKKRHoyEep7yveJ1d0k/edit), takes the stance that it would be
very challenging if not possible to create a single definition for research software.
However, it's very reasonable to derive criteria, or questions that we can easily
answer, that can be used to determine a relative strength of a piece of software
on a dimension of "strongly yes" to "strongly no." We can also derive a taxonomy,
or categorization of research software types that might further filter this decision
making. Both of these classifications, a scoring and location in the taxonomy,
can then be transparently stated and used to answer if a specific piece of software
is indeed research software. Importantly, while the choice of threshold for scoring
and taxonomy filter is subjective, the classification and answers to the criteria
are not. We have a transparent, methodic way to define pieces of software, and we leave
some final definition up to the individual or group that warrants needing the definition.

## Goals

### 1. Community Developed

It's common for self-acclaimed "experts" or people in power to decide how things are going
to be. This initiative aims to be completely transparent, open source, and community driven.
Anyone can contribute to, or give feedback on the taxonomy, criteria, and even the software
in the database. Annotation can happen with prompts from social media or slack communities.

### 2. Automated and Sustainable

It's also often the case that efforts require grant funding, or long term funding of 
servers or databases to provide a resource. This initiative is hosted entirely on open
source version control, and does not require any funding.

### 3. Understanding for Science

An understanding of the qualities of software that are required to support 
this research life-cycle is essential to continue and maximize the potential for discovery. 
In this light, research software is also about people, namely the developers and 
community that utilizes it. If we can better characterize this community to 
better understand how its needs map to research software, we can again better support scientific discovery.

<a id="ref">

[3] C. Goble, "Better Software, Better Research," in IEEE Internet Computing, vol. 18, no. 5, pp. 4-8, Sept.-Oct. 2014, doi: 10.1109/MIC.2014.88.

## How does it work?

By way of separation of tools to allow for participation or development in the subset that is of interest to you, we achieve a holistic space of software, database, and application programming interfaces.

 1. **Taxonomy and Criteria** are served programaticaly from the [Research Software Engineering (rseng)](https://rseng.github.io/rseng) repository. If you want to contribute to either of those, that's the repository you should contribute to.
 2. **Database**: the [Research Software Encyclopedia](https://github.com/rseng/rse) drives generation and update of the database here.
 3. **Update** is automated using [GitHub Workflows](https://github.com/rseng/software/tree/master/.github/workflows).
 4. **Annotate** directly via the [repository interface](https://rseng.github.io/software/) or by [opening an issue](https://github.com/rseng/software/issues/new/choose) or in bulk [on your local machine](https://rseng.github.io/rse/tutorials/annotation/) 
 5. Use the **api** to see [repos](https://rseng.github.io/software/api/repos/index.json), [taxonomy](https://rseng.github.io/software/api/taxonomy/index.json), and [criteria](https://rseng.github.io/software/api/criteria/index.json)

## Resources

Want to watch a fun video that introduces the RSEPedia? You might be interested in "Twas the Night!"

<iframe width="560" height="315" src="https://www.youtube.com/embed/qoTLJ3X23oQ" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

You might also be interested to read about research software directory initiatives:

<iframe width="560" height="315" src="https://www.youtube.com/embed/Rky9OWSzYb0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## How do I get involved?

 - **Contribute to the software showcase**: If you have a library that you care about, you can add a post to the [software showcase](https://rseng.github.io/rseng/blog/).  [Open an issue here](https://github.com/rseng/rseng/issues/) to get started.
 - **Annotate Software** in the [The Research Software Database](https://github.com/rseng/software) on GitHub. There is a [tutorial here](https://rseng.github.io/rse/tutorials/annotation/) and [here](https://rseng.github.io/rse/tutorials/annotation/).
 - **Contribute to the software** at [rseng/rse](https://rseng.github.io/rse). For example, we can improve the search interface, command line tools, or add additional repository and archive parsers.
