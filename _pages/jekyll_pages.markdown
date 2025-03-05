---
layout: single
author_profile: true
permalink: /websetup/jekyll/jekyllpages/
title: "Jekyll pages"
excerpt: "How to set front matter in Jekyll pages and options for pages layout and content using the theme Minimal Mistakes."
toc: true
sidebar:
  nav: "jekylldocs"
categories_:
 - jekyll
tag:
  - jekyll
  - homebrew
---

## Pages - a quick tutorial

1. Create the _pages_ document in the folder _\_pages_, name it logically,
2. set _pages_ primary keys either:
     * in <span class='file'>\_config.yml</span>, or
     * as front matter in the _pages_ document itself,
3. set the path to the new _pages_ document front matter as the parameter _permalink_,
4. set the parameter _title_ in the front matter,
5. add other options in the front matter, including overriding the <span class='file'>\_config.yml</span> _defaults_.

For more details read on or visit the [Jekyll document on Pages][jekyll-pages].

This article itself is an example of a _page_, created using the theme [Minimal Mistakes][mmistakes-home].

## Pages

As _pages_ are unitary documents, unassociated with other documents in the same site, they are typically published in separate sub-folders (= sub-directories). Sub-folders that contain only a single <span class='file'>index.html</span> file. The path to the sub-folder from the site root is typically given in the front matter by the key (parameter) _permalink_. This also means that a _pages_ markdown document can be put anywhere, it is the parameter _permalink_ that defines where the resulting html file ends up in the published web-site. One example is to put the <span class='file'>about.markdown</span> document in the root folder, but set its permalink to either _pages_ or _about_.

### _\_config.yml_ and front matter

To be linked properly the front matter of a page only needs to contain keys for _permalink_ and a _title_:

```
permalink: /jekyllpages/
title: "Pages in Jekyll"
```
{: .no-copy}

For the theme [Minimal Mistakes](mmistake-pages/) this is the recommended setting for _pages_ in <span class='file'>\_config.yml</span>:

```
defaults:
  # _pages
  - scope:
      path: ""
      type: pages
    values:
      layout: single
      author_profile: true
```
{: .no-copy}

Transferred to the front matter of the _pages_ document itself this becomes:

```
layout: single
author_profile: true
```
{: .no-copy}

Combined with the _permalink_ and _title_ keys, the complete front matter then becomes:

```
layout: single
author_profile: true
permalink: /jekyllpages/
title: "Pages in Jekyll"
```

Key values set in the _pages_ file front matter has precedence over values set in <span class='file'>\_config.yml</span> if a key:value pair is set in both.

#### Table of content

Editing <span class='file'>\_config.yml</span> you can add additional elements, like a table of content (_toc_) as in this example page:

```
defaults:
  # _pages
  - scope:
      path: ""
      type: pages
    values:
      layout: single
      author_profile: true
      toc: true
```

Minimal Mistakes even allows you to [set the title and logo for the toc][mmistake-toc].

You can also add the key _toc_ for individual _pages_ documents:

```
layout: single
author_profile: true
permalink: /jekyllpages/
title: "Pages in Jekyll"
toc:true
```

Again, if the _toc_ key is set in both the <span class='file'>\_config.yml</span> and the document own front matter, the latter will take precedence.

## Linking to your pages

In this example the <span class='file'>index.html</span> generated from the _pages.md_ file will end up in the site under the path:

```
./jekyllpages/index.html
```

This url is not linked to your site root (front/home) page. The options for directing site visitors to your single page include:

1. as a main menu item,
2. adding a customised sidebar navigation,  or
3. as an explicit url link in the root page (or any page on your site).

### Main menu

The main menu is defined in the file <span class='file'>./_data/navigation.yml</span>.

If your site does not contain the file <span class='file'>./_data/navigation.yml</span> it is instead found in the "gem" that your jekyll theme is based on. To find the "gem", open the terminal that contains your site and execute the command:

<span class='terminal'>$ bundle info minimal-mistakes</span>.

The terminal should then report something like:

```
* minimal-mistakes-jekyll (4.26.2)
Summary: A flexible two-column Jekyll theme.
Homepage: https://github.com/mmistakes/minimal-mistakes
Path: /Users/thomasgumbricht/.gem/ruby/3.3.5/gems/minimal-mistakes-jekyll-4.26.2
```
{: .no-copy}

under the reported path look for
```
./_data/navigation.yml
```
{: .no-copy}

Copy this file to your site and the local copy will take precedence over the "gem" file. You can now edit the local copy of <span class='file'>navigation.yml</span> to have the following _main menu_:

```
# main links
main:
  - title: "About"
    url: /about/
  - title: "Front"
    url: /
  - title: "Pages"
    url: /jekyllpages/
```
{: .no-copy}

To add tooltips that appear when the mouse is hoovered over the menu item, edit <span class='file'>navigation.yml</span> and add _description_ keys:

```
# main links
main:
  - title: "About"
    url: /about/
    description: about Karttur
  - title: "Front"
    url: /
    description: Site root
  - title: "Pages"
    url: /jekyllpages/
    description: jekyll pages as part of your site
```
{: .no-copy}

### Custom sidebar navigation

[Minimal Mistakes][mmistake-sidenav] allows you to add a customised sidebar navigation. This requires three steps:
1. name the custom navigation and list the links,
2. edit <span class='file'>navigation.yml</span> with the name and the links, and
3. add the name in either the front matter of individual files or in <span class='file'>\_config.yml</span>.

Here is an example of a customised navigation, named _jekylldocs_, linking to three different urls:

```
jekylldocs:
  - title: Jekyll doc system
    children:
      - title: "Pages"
        url: /jekyllpages/
      - title: "Posts"
        url: /jekyllposts/
      - title: "Collections"
        url: /jekyllcollections/
```
{: .no-copy}

The above code should be written to the local site copy of <span class='file'>navigation.yml</span>.

Then add the following lines to the front matter of the files where you want the sidebar navigation to appear:

```
sidebar:
  nav: "jekylldocs"
```
{: .no-copy}

The complete front matter then becomes something like:

```
layout: single
author_profile: true
permalink: /jekyllpages/
title: "Pages in Jekyll"
excerpt: "How to set front matter in Jekyll pages and options for pages layout and content using the theme Minimal Mistakes."

sidebar:
  nav: "jekylldocs"
```
{: .no-copy}

I add my customisations at the end of the front matter (or <span class='file'>\_config.yml</span>), including a comment. In that way I can find them easily if I want to remove, change or transfer my customisations to new versions of Jekyll or Minimal Mistakes.

Alternatively edit <span class='file'>_config.yml</span> defaults:

```
...
defaults:
  # _pages
  - scope:
      path: ""
      type: pages
    values:
      layout: single
      author_profile: true
      toc: true
      sidebar:
        nav: "jekylldocs"
...
```
{: .no-copy}

### Explicit url link

The last option for linking to a single _pages_ document is to use an explicitly written html tag linking to [Pages in Jekyll](#):

```
[Pages in Jekyll](jekyllpages)
```
{: .no-copy}

Or, using the latest Jekyll syntax that assembles all explicit urls in markdown (.md) files:

```
[Pages in Jekyll][jekyllpages]
...
...
[jekyllpages]: url/to/jekyllpages
```
{: .no-copy}

## Resources

[Jekyll - pages][jekyll-pages]


[Minimal Mistakes][mmistakes-home]

[Minimal Mistakes - configuration][mmistake-config]

[Minimal Mistakes - table of contents][mmistake-toc]

[Minimal Mistakes - sidebar navigation][mmistake-sidenav]

[Minimal Mistakes - nested and mixed lists][mmistake-lists]

[jekyll-pages]: https://jekyllrb.com/docs/pages/

[mmistakes-home]: https://mmistakes.github.io/minimal-mistakes

[mmistake-config]: https://mmistakes.github.io/minimal-mistakes/docs/configuration

[mmistake-toc]: https://mmistakes.github.io/minimal-mistakes/layout-table-of-contents-post/

[mmistake-sidenav]: https://mmistakes.github.io/minimal-mistakes/docs/layouts/#custom-sidebar-navigation-menu

[mmistake-lists]: https://mmistakes.github.io/minimal-mistakes/edge%20case/edge-case-nested-and-mixed-lists/
