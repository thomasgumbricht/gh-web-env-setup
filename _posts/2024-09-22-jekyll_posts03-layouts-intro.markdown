---
layout: single
permalink: /websetup/jekyll/jekyll_posts03-layouts-intro/
author_profile: true
title:  "Posts in Jekyll: 3. layouts"
excerpt: "Introduction to layout options for the theme Minimal Mistakes."
date:   2024-09-22 12:13:03 +0200
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
  - Minimal Mistakes
---

## Minimal Mistakes layouts

The Jekyll theme [Minimal Mistakes]() comes with more than a dozen prepared layouts. The differences between these layouts are described in the [Minimal Mistakes documentation Layouts][mmistakes-layouts].

The recommendation from Michael Rose, the author of Minimal Mistakes, is to use the Layout _single_ both for _pages_ and _posts_.

### Minimal Mistakes layouts

The template GitHub repository of the Jekyll Minimal Mistakes theme contains these layouts.

- archive
- archive-taxonomy
- categories
- category
- collection
- compress
- default
- home
- posts
- search
- single
- splash
- tag
- tags

The [Minimal Mistakes documents][mmistakes-layouts] explain the diffrences between these layouts. Below is a summary of the main types.

#### Archive layout

Essentially the same as _single_ with markup adjustments and some modules removed. For details see [Minimal Mistakes - Archive layouts][mmistakes-layouts#archive].

#### Home page layout

A derivative archive page layout to be used as a simple home page. It is built to show a paginated list of recent posts based off of the pagination settings in <span class='file'>\_config.yml</span>. The html [root document](/) for this entire site is built using the layout _home_. The bottom of that document lists the _posts_ by default. For details the the [Minimal Mistakes docs on home page layout][mmistakes-layouts#home].

#### Splash page layout

The splash layout generated full width pages without margins but three equally wide feature blocks. The Minimal Mistakes layout document contains a detailed section on [Splash page layout][mmistakes-layouts#splash]. The [next post](../jekyll_posts04-layouts-splash/) in this blog is built using splash.

#### Search page layout

Search page layout is a page with a search form included by default as explained in the Minimal Mistakes section on [Search page layout][mmistakes-layouts#search]. A _search_ layout document is typically a _pages_ scope (rather than a post).

### Front matter customisation

This section covers the layout customisations that can be done using keys in the front matter. By default the layout _single_, that we mostly have used so far, have the following front matter layout options:

```
# Top banner image (as in this post)
header:
  overlay_image: /assets/images/unsplash-image-1.jpg
  caption: "Photo credit: [**Unsplash**](https://unsplash.com)"
  actions:
    - label: "More Info"
      url: "https://unsplash.com"

# left column author profile (as in this post):
author_profile: boolean [true/false]

# left column Navigation bar
sidebar :
  nav: "'navbarname'"

# right column table of content layout:
toc : [true/false]
toc_label: string
toc_icon: path to icon
toc_sticky: [true/false] (true = stick to top of screen)

# Concatenation of central and right columns
# If combine dwith toc, toc is mobed to the top of the concatenated column
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

# Disqus (I have to understand this to write anything)
???
```

### Sidebars

The Minimal Mistakes default layout consists of a central main column with two sidebars; a left sidebar that can host author details and/or a customised navigation bar, and a right sidebar where a table of content can be added. The Minimal Mistakes layout documents include details about the [Sidebars][mmistakes-layouts#sidebars].

The right margin of the layout _single_ is by default reserved for a table of content (see the [post on pages in this site][this-pages]). You can free space for the main content (central column) by setting the key _classes_ to _wide_ in the front matter of the file you want customise:

```
classes: wide
```

If you have also requested a _toc_:

```
classes: wide
toc: true
```

The table of contents will appear in the new, concatenated, central column just after the _title_ and any _show_date_ or _read_time_.

### Custom head and footer

The Minimal Mistakes documents include hints for how to create [Custom head and footer][mmistakes-layouts#custom-head-and-footer].

### Resources

[Minimal Mistakes layouts][mmistakes-layouts]

[Minimal Mistakes cheat sheet][mmistakes-cheat-sheet]

[mmistakes-layouts]: https://mmistakes.github.io/minimal-mistakes/docs/layouts/

[mmistakes-layouts#archive]: https://mmistakes.github.io/minimal-mistakes/docs/layouts/#archive-layout

[mmistakes-layouts#taxonomy-archives]: https://mmistakes.github.io/minimal-mistakes/docs/layouts/#taxonomy-archives

[mmistakes-layouts#home]: https://mmistakes.github.io/minimal-mistakes/docs/layouts/#home-page-layout

[mmistakes-layouts#splash]: https://mmistakes.github.io/minimal-mistakes/docs/layouts/#splash-page-layout

[mmistakes-layouts#search]: https://mmistakes.github.io/minimal-mistakes/docs/layouts/#search-page-layout

[mmistakes-layouts#sidebars]: https://mmistakes.github.io/minimal-mistakes/docs/layouts/#sidebars

[mmistakes-layouts#custom-head-and-footer]: https://mmistakes.github.io/minimal-mistakes/docs/layouts/#custom-head-and-footer

[mmistakes-cheat-sheet]: https://www.fabriziomusacchio.com/blog/2021-08-11-Minimal_Mistakes_Cheat_Sheet/

[this-pages]: /jekyllpages
