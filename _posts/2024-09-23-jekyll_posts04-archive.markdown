---
published: false
permalink: /websetup/jekyll/jekyll_posts04-archive/
layout: archive
author_profile: true
title:  "Posts in Jekyll: 4. posts archive"
excerpt: "Posts Archive page with layout."
date:   2024-09-23 12:13:03 +0200
last_modified_at:   2024-09-29 12:13:03 +0200
classes: wide
header:
  overlay_image: /assets/images/unsplash-image-1.jpg
  caption: "Photo credit: [**Unsplash**](https://unsplash.com)"
  actions:
    - label: "More Info"
      url: "https://unsplash.com"

categories:
  - jekyllposts
tags:
  - jekyll
  - minimal mistakes
---

## Minimal mistakes layouts

The Jekyll theme [minimal mistakes]() comes with 14 prepared layouts. The differences between these layouts is descibed in the Minimal misakes documentation [Layouts](https://mmistakes.github.io/minimal-mistakes/docs/layouts/).

The recommendation from Michael Rose, the author of Minimal mistakes, is to use the Layout _single_ both for _pages_ and _posts_.


### Front matter customisation

Thsi section covers the layout customisations that can be done using keys in the front matter. By default the layout _single_, that we have used so far, have the following front matter layout options:

```
# Top banner image (as in this post)
header:
  overlay_image: /assets/images/unsplash-image-1.jpg
  caption: "Photo credit: [**Unsplash**](https://unsplash.com)"
  actions:
    - label: "More Info"
      url: "https://unsplash.com"

# left column author profile
author_profile: boolean [true/false]

# left column Navigation bar
sidebar:
  nav: "'navbarname'"

# right column table of content layout
  toc : [true/false]
  toc_label: string
  toc_icon: path to icon
  toc_sticky: [true/false] (true = stick to top of screen)

# Concatenation of central and right columns
classes: wide

# comments module
comments: boolean [true/false]

# social media sharing
share: boolean [true/false]

# related posts
related: boolean [true/false]

# show date
show_date: boolean [true/false]

# read time
read_time: boolean [true/false]

# Disqus


```
