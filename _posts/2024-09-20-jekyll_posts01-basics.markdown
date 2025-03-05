---
layout: single
permalink: /websetup/jekyll/jekyll_posts01-basics/
author_profile: true
toc: true
title:  "Posts in Jekyll: 1. basics"
excerpt: "How to set front matter in Jekyll posts and basic options for layout and content using the theme Minimal Mistakes."
date:   2024-09-20 12:13:03 +0200
last_modified_at:   2024-09-24 12:13:03 +0200
toc: true
categories:
  - jekyllposts
tags:
  - jekyll
  - Minimal Mistakes
---

## Posts

Post files must be located in the <span class='file'>\_posts</span> folder of your Jekyll site. This docuemnt if itself an example of a _post_, setup using the theme [Minimal Mistakes](https://mmistakes.github.io/minimal-mistakes).

The name of a post file must start with a date followed by a hyphen ("-") using this format:

```
YYYY-MM-DD-file_name.md
```
{: .no-copy}

### _\_config.yml_ and front matter

Posts are mostly used for blogs that are published over time and should have both _date_, _title_ and preferably also an _excerpt_ key in the post file front matter (otherwise the first paragraph is used as excerpt - see the [Jekyll document on Posts](https://jekyllrb.com/docs/posts/)):

```
title:  "Posts in Jekyll: 1. basics"
excerpt: "How to set front matter in Jekyll posts and basic options for layout and content using the theme Minimal Mistakes."
date: 2024-09-20 12:13:03 +0200
last_modified_at: 2024-09-20 12:13:03 +0200
```
{: .no-copy}

The keys for _date_ and _last_modified_at_ are optional, but I prefer to include them to keep track of when I made the latest changes. For more details on displaying post dates see the Minimal Mistakes posts [Layout: Post Date Enabled][mmistakes-layout-post-date] and [Layout: Post Date Disabled][mmistakes-layout-post-date-disabled].

For posts, the author of the theme [Minimal Mistakes][mmistakes-posts]recommends the following settings in <span class='file'>\_config.yml</span> (I added the _show_date_ key):

```
defaults:
  # _posts
  - scope:
      path: ""
      type: posts
    values:
      layout: single
      author_profile: true
      show_date: true
      read_time: true
      share: true
      related: true
```
{: .no-copy}

Transferred to the front matter of the _posts_ document itself this becomes:

```
layout: single
author_profile: true
show_date: true
read_time: true
share: true
related: true
```
{: .no-copy}

Combined with the post local keys, the complete front matter then becomes:

```
layout: single
author_profile: true
read_time: true
share: true
related: true
title:  "Posts in Jekyll: 1. basics"
excerpt: "How to set front matter in Jekyll posts and basic options for layout and content using the theme Minimal Mistakes."
date:   2024-09-20 12:13:03 +0200
last_modified_at: 2024-09-20 12:13:03 +0200
```
{: .no-copy}

Key values set in the _posts_ file front matter has precedence over values set in <span class='file'>\_config.yml</span> if a key:value pair is set in both.

Posts usually also have keys for _categories_ and _tags_. Each post can belong to multiple categories and have multiple tags. In the theme [Minimal Mistakes](https://mmistakes.github.io/minimal-mistakes/aciform/antiquarianism/arrangement/asmodeus/broder/buying/championship/chastening/disinclination/disinfection/dispatch/echappee/enphagy/edge-case-many-categories/), the categories and tags are shown towards the end of a post.

#### Table of content

To set a table of content in a post, follow the same syntax as outlined for [pages](/jekyllpages/index.html#table-of-content).

## Resources

[Jekyll page on posts][jekyll-posts]

[Minimal Mistakes - posts][mmistakes-posts]

[Minimal Mistakes - layout: post date enabled][mmistakes-layout-post-date]

[Minimal Mistakes - layout: post date disabled][mmistakes-layout-post-date-disabled]

[jekyll-posts]: https://jekyllrb.com/docs/posts/

[mmistakes-posts]: https://mmistakes.github.io/minimal-mistakes/docs/posts/

[mmistakes-layout-post-date]: https://mmistakes.github.io/minimal-mistakes/layout-post-date/

[mmistakes-layout-post-date-disabled]: https://mmistakes.github.io/minimal-mistakes/layout-post-date-disabled/
