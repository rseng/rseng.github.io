---
title: "Research Software Engineer Community Template"
layout: "project"
image: community-template.png
github: https://github.com/rseng/community-template/
project_url: https://rseng.github.io/community-template/
categories: [discovery, community]
description: "Quickly deploy a community research software engineering site."
badges:
 - type: info
   tag: discovery
 - type: info
   tag: community
tags:
 - discovery
 - community
---

This is a community template for a research software engineer group. It is provided for you
to copy to your GitHub organization to then have a portal for your center.

 - [How Does it Work?](#how-does-it-work) or specifically, what features does the page offer?
 - [Creating Your Community](#creating-your-community) comes down to creating a clone of the respository in the [rseng](https://www.github.com/rseng) GitHub organization.

## How does it work?

The site offers the following features:

 - A site wide search, and "Find an RSE" search to help users find support they need.
 - An optional Twitter feed if your group shares an alias.
 - Individual pages for your site members. Each individual can share a biography and areas of expertise to better offer support to users.

## Creating your Community

You can create your repository from the [template here](https://github.com/rseng/community-template/generate).

### 1. About your Group

You can modify the `pages/about.md`' file to add information about your
center. This will show up on the Community -> About tab.

### 2. Support Your Offer

In the `pages/support.md` you should describe the support that your
group offers. This will be searched by users to find help, so be sure to include
details about the resources and services that your group offers.

### 3. Add People

Any interested RSE at your institution can a page to the `_people`
collections folder. The header of the file should include links, social media,
and descriptors;

```yaml
---
name: Antonio T. Rex
title: Research Software Engineer
url: https://douglascuddletoy.com/shop/fantasy-whimsy/t-rex-s-dinosaur-w-sound/
image: rex.jpg
github: rseng
twitter: dinosaur
---
```

And they are free to write whatever they please in the content area! 
Images should be relative paths specified above, and expected to be in 
`assets/img/people`. A biography and description of expertise is usually appropriate, as the content will be
searchable for users to find support for areas of interest.

### 4. Write Posts

If you want to use your community space to write articles or post news, you can
do so by adding a new markdown file to the `_posts` folder. We've left
a few entries there for you as examples. If you want to add your community
site to any feed syndication that supports xml, there is a feed of posts
exposed at https://localhost:4000/community-template/feed.xml.

### 5. Social Media

If your group has a Twitter alias, define the `twitter` variable in the `_config.yml`
file to show a feed of posts on the right side of the main page. By default this
is disabled, and individual engineers are able to define their own Twitter
aliases in their personal pages.

## Development

To develop the site, clone the repository and then build with jekyll:

```bash
bundle exec jekyll serve
```

## How do I get involved?

This is primarily a GitHub project, so we invite you to collaborate on the
[template code](https://github.com/rseng/community-template).
