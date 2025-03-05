---
layout: single
permalink: /websetup/jekyll/jekyll_posts02-categories/
author_profile: true
toc: true
title:  "Posts in Jekyll: 2. categories"
excerpt: "Front matter options for organising posts in categories, forcing urls and omitting posts."
date: 2024-09-21 12:13:03 +0200
last_modified_at: 2024-09-29 12:13:03 +0200
categories:
  - jekyllposts
tags:
  - jekyll
  - minimal mistakes
---

## Posts and categories

This post follows the previous [Posts in Jekyll: 1. basics][this-blog-1] in this blog. The previous post showed how to set the key _categories_ in the front matter of a post file:

```
layout: single
author_profile: true
itle:  "Posts in Jekyll: 1. basics"
excerpt: "How to set front matter in Jekyll posts and basic options for layout and content using the theme Minimal Mistakes."
date:   2024-09-20 12:13:03 +0200
last_modified_at:   2024-09-24 12:13:03 +0200
categories:
  - jekyllposts
tags:
  - jekyll
  - minimal mistakes
```
You do not need to set any category, but you can also set any number of _categories_ you wish, e.g:

```
...
categories:
  - jekyllposts
  - mmistakes
...
```
{: .no-copy}

Categories is a hierarchical way to group posts together. That it is a grouping mechanism is probably obvious. But that it is achieved by a hierarchy is not very clear. When a site is generated (<span class='terminal'>bundle exec jekyll serve</span>) the order of the categories determine the structure of the site. For example, the filename of this post is
```
YYYY-MM-DD-jekyll_posts02-categories.md
```
{: .no-copy}

When generated as a static page, the html file (that is always named <span class='file'>index.html</span>) will be created in a sub-folder:

```
jekyll_posts02-categories/index.html
```
{: .no-copy}

If your front matter does not define any _categories_ (or _permalink_), the sub-folder will end up directly under the root:

```
./jekyll_posts02-categories/index.html
```
{: .no-copy}

If you have a single _categories_ defined (like for this very post), the sub-folder will end up in a folder named as this single _categories_:

```
./jekyllposts/jekyll_posts02-categories/index.html
```
{: .no-copy}

If you have two (or more) _categories_ listed in the front matter a complete hierarchy following the order of the _categories_ will be generated. For the example above with two _categories_, the path (url) to the site html file will thus be:

```
./jekyllposts/mmistakes/jekyll_posts02-categories/index.html
```
{: .no-copy}

### Forcing a URL

If you want to customise the organisation of the urls of your posts you force the path under the root by setting the key _permalink_ in the post front matter. The following _permalink_ key:

```
permalink: /jekyllsposts/2_categories/
```
{: .no-copy}

will force this file to the path:

```
./jekyllsposts/2_categories/index.html
```
{: .no-copy}

For details on setting _permalink_ in the <span class='file'>\_config.yml</span>, please visit the [Jekyll doc Permalinks][jekyll-permalinks].

### Excluding a post from publication

You can exclude any individual post from being published with the site by setting the key _published_ to _false_ (not illustrated!):

```
published: false
```
{: .no-copy}

### Gather posts with same categories

You can use Jekyll's extended [Liquid][liquid] language for gathering posts that share a _categories_ item. The [posts front page of this blog](/jekyllposts) explains how this is done.

### Resources

[This blog - 1. basics][this-blog-1]

[Jekyll - Permalinks][jekyll-permalinks]

[Liquid][liquid]

[this-blog-1]: /jekyllposts/jekyll_posts01-basics/

[jekyll-permalinks]: https://jekyllrb.com/docs/permalinks/

[liquid]: https://shopify.github.io/liquid/
