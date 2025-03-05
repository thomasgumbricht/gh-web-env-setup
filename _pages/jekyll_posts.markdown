---
layout: single
author_profile: true
permalink: /websetup/jekyll/jekyllposts/
title: "Jekyll posts"
toc: false
sidebar:
  nav: "jekylldocs"
toc: true
---
<!-- If there is a title in the front matter it is of cat #, thus start those docs at ## level
-->

## Posts - a quick tutorial

1. Create the _post_ document in the folder _\_posts_, name it logically,
2. set _posts_ primary keys either:
     * in <span class='file'>\_config.yml</span>, or
     * as front matter in the _posts_ document itself,
3. set the _title_ and the creation _date_ in the front matter,
4. (optionally) include an _excerpt_ key for announcing content,
5. add other options in the front matter, including overriding the <span class='file'>\_config.yml</span> _defaults_.

For more details read on or visit the [Jekyll document on Posts](https://jekyllrb.com/docs/posts/).

## Karttur's categorised posts

This document is itself of the scope [pages](../jekyllpages/) type. It is the front page (or root) of the posts with _categories_ set to to _jekyllposts_ (but is not itself categorised at all). To end up in the root directory of the posts categorised as _jekyllposts_, the front matter key _permalink_ is set to _/jekyllposts/_. The complete front matter of this page thus looks like this (for details on how this defines the layout see the [pages](../jekyllpages/) document in this site):

```
layout: single
author_profile: true
permalink: /jekyllposts/
title: "Blog on creating and customising jekyll posts"
toc: false
sidebar:
  nav: "jekylldocs"
```
{: .no-copy}

To list the posts categorised as _jekyllposts_, the following liquid searches the site and then generates the list of posts seen below - interestingly enough it is not possible to show the liquid syntax - even inside the markers for "text only" the liquid is executed. The text below is the generated html code from the liquid I tried to display:

```
<ul>
  {% for post in site.categories.jekyllposts %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a>
      {{ post.excerpt }}
    </li>
  {% endfor %}
</ul>
```

Instead I took a screen dump and the image below shows the liquid code that generated the above html (figure 1).

<figure style="width: 450px">
  <img src="/assets/images/jekyll-liquid-site-categories.png" alt="">
  <figcaption>Figure 1. Jekyll liquid code that generated the outcome above.</figcaption>
</figure>

### Navigation link

This page is also linked in the top navigation bar of all pages of the blog. This is achieved by the following lines in _navigation.yml_:

```
- title: "Posts"
  url: /jekyllposts/
  description: jekyll posts as part of your site
```

### Posts of categery jekyllposts

<ul>
  {% for post in site.categories.jekyllposts %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a>
      {{ post.excerpt }}
    </li>
  {% endfor %}
</ul>
