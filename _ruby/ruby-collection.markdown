---
title:  "Ruby collection"
layout: single
permalink: /websetup/ruby/ruby-collection
author_profile: true
---

This introduction on how to install and setup Ruby for Jekyll is written as a Jekyll Collection. In reality that only means that each document is saved inside a folder named *_ruby*, and that I defined a collection called *ruby* in the <span class='file'>\_config.yml</span> file:

```
collections:
  ruby:
    order:
      - ruby-collection.markdown
      - ruby-versions.markdown
      - ruby-installation.markdown
      - ruby-update.markdown
    output: true
    permalink: /websetup/jekyll/ruby/
```
{: .no-copy}

As seen from the collections example above, you can set the order of the documents in the collection. To publish a collection in your <span class='file'>\_site</span> folder, you must set _output_ to _true_. Setting _permalink_ is optional.

For this collection on Ruby I choose the _layout_ to be _single_, defined the _permalink_ and set _author_profile_ to _true_. The front matter of this document thus looks like this:

```
---
title:  "Ruby versions"
layout: single
permalink: /websetup/ruby/ruby-versions
author_profile: true
---
```
{: .no-copy}
