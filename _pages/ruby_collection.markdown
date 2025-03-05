---
layout: collection
title: "Ruby collection"
excerpt: Setting up Ruby, creating and customising jekyll collections
author_profile: true
permalink: /websetup/ruby/
collection: ruby
entries_layout: grid
classes: wide
toc: false
sidebar:
  nav: "jekylldocs"
toc: false
---
<!-- If there is a title in the front matter it is of cat #, thus start those docs at ## level
-->

The Ruby collection is both an example of a [Jekyll collection][jekyll_collection] and an instruction for how to setup [Ruby][ruby] - the programming language in which Jekyll is written.

## Collections - a quick tutorial

1. Create a folder named "underscore"+"collection name" (*_\<collection-name\>*),
2. Edit <span class='file'>\_config.yml</span> to include this collection and its permalink,
3. Create a _pages_ scope for linking to the collection items, set the _layout_ to _collection_, and _collection_ to *_\<collection-name\>*
4. add other options in the front matter of the _pages_ scope, including overriding the <span class='file'>\_config.yml</span> _defaults_.
5. create the collection documents in the collection folder *_\<collection-name\>*, the front matter can be cut down to title only.

For more details read on or visit the [Jekyll document on Collections](https://jekyllrb.com/docs/collections/).

## Karttur's collections

This document is itself of the scope [pages](../jekyll/jekyllpages/) type. It is the front page (or root) of the _collection_ called _ruby_. To end up in the root directory of the _ruby_ collection, the front matter key _permalink_ is set to _/ruby/_. The complete front matter of this page thus looks like this (for details on how this defines the layout see the [pages](../jekyll/jekyllpages/) document in this site):

```
layout: collection
title: "Ruby collection"
excerpt: Setting up Ruby, creating and customising jekyll collections
author_profile: true
permalink: /websetup/ruby/
collection: ruby
entries_layout: grid
classes: wide
toc: false
sidebar:
  nav: "jekylldocs"
toc: false
```
{: .no-copy}

The setting above generates a grid layout (_entries_layout: grid_) from the markdown documents in the collection folder (_collection: ruby_). You do not need to add any other code.

## Resources

[Jekyll collection][jekyll_collection]

[Ruby programming language][ruby]

[jekyll_collection]: https://jekyllrb.com/docs/collections/

[ruby]: https://www.ruby-lang.org/en/

## Jekyll collection content
