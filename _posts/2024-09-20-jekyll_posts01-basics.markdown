---
layout: single
permalink: /blog/websetup/
author_profile: true
toc: true
title:  "Working environment setup for static website"
excerpt: "Setting up the Karttur.com website with Ruby, Jekyll and the theme Minimal mistakes."
date:   2024-11-18 11:13:03 +0200
last_modified_at:   2024-11-18 11:13:03 +0200
toc: true
categories:
  - home/websetup
tags:
  - website builder
  - jekyll
  - Minimal Mistakes
---

# Working environment for static websites

This blog introduces [Jekyll](https://jekyllrb.com) for building static websites for blogs, portfolios, articles, photos etc. Jekyll takes textfiles written in [markdown](https://www.markdownguide.org/getting-started/) and converts them to web-pages. One great advantage with Jekyll is that [GitHub](https://github.com) supports free hosting of Jekyll pages. This in essence means that you can build a website and host it for free using Jekyll and deploying on GitHub.

## Jekyll Pages, Posts and Collections

In Jekyll, the organisation of published documents included in a site can use one of three scopes: _pages_, _posts_ and _collections_. The basic scope behind _pages_, _posts_ and _collections_ are:

- **pages**: for single documents not part of any blog, series or other compilation, but that can be the portal for any such compilation,
- **posts**: a compilation of associated texts where the temporal sequence (date) is regarded (i.e. blog), and
- **collections**: a compilation of associated texts without temporal sequence.

In this blog I have used all three scopes and at the same time tried to make it into a manual for how to setup and publish a website using [Jekyll](https://jekyllrb.com).

Jekyll is written in the programming language [Ruby](https://www.ruby-lang.org/en/). Ruby is an open source language were bits and pieces ("packages") are written and published as "gems". How to setup Ruby and its gems is overhauled in the [Ruby collection](/websetup/ruby). How to create different layouts and contents for web sites using Jekyll is the topic of the [Introduction Pages](/websetup/jekyll/jekyllpages) and the [Jekyll Posts](/websetup/jekyll/jekyllposts).

## Jekyll themes

The community engaged in developing Ruby Gems for Jekyll is extensive and active. This means that there are many gems available for converting _markdown_ text files to web-pages. There are hundreds of different Jekyll _themes_ to choose from - each generate a different layout from the same basic text (with some additional tweaks required). Many of the themes are Open Source, but there are also themes that comes with a fee.

[GitHub officially supports about a dozen or so theme](https://pages.github.com/themes/), but you can deploy any theme on GitHub - you might just have to tweak it a bit extra.

The site [Best Jekyll Themes](https://www.bestjekyllthemes.com) has collected about 200 of the most popular Jekyll themes. Other galleries with Jekyll themes include:

- [GitHub.com #jekyll-theme repos](https://github.com/topics/jekyll-theme)
- [jamstackthemes.dev](https://jamstackthemes.dev/ssg/jekyll/)
- [jekyllthemes.org](http://jekyllthemes.org)
- [jekyllthemes.io](https://jekyllthemes.io)
- [jekyll-themes.com](https://jekyll-themes.com)

## Karttur's Jekyll setup

This blog is about setting up Karttur's website using [Jekyll](https://jekyllrb.com) and the theme [Minimal Mistakes](https://mmistakes.github.io/minimal-mistakes/) by Michael Rose. The blog also covers some tricks and tips and how to customise a theme.
