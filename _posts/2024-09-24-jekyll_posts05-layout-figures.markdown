---
layout: single
permalink: /websetup/jekyll/jekyll_posts04-layouts-figures/
title:  "Posts in Jekyll: 5. figure"
excerpt: "Figures and photo albums using the Jekyll theme Minimal Mistakes."
date: 2024-09-25T11:48:41-04:00
header:
  overlay_color: "#000"
  overlay_filter: "0.5"
  overlay_image: /assets/images/unsplash-image-1.jpg
  actions:
    - label: "Download"
      url: "https://github.com/mmistakes/minimal-mistakes/"
  caption: "Photo credit: [**Unsplash**](https://unsplash.com)"
excerpt: "Image header with overlay_color"
categories:
  - jekyllposts
tags:
  - jekyll
  - minimal mistakes
---

## Minimal Mistakes figure layout

The [Minimal Mistakes Cheat Sheet](https://www.fabriziomusacchio.com/blog/2021-08-11-Minimal_Mistakes_Cheat_Sheet/#images) by Fabrizio Musacchio contains a very good section on how to render images in Minimal Mistakes. There are three different coding options for inserting images in the main text:
- markdown,
- html, and
- liquid.

Among the 3 alternatives I prefer the html coding alterantive. The coding is straight forward and the built-in _figure_ classes (full [default], half and third - for 1, 2 and 3 columns of figures) are sufficent for my needs.

Full width, single column, image:

```
<figure>
  <a href="/assets/images/pixel_tracker_logo_120px.jpg" title="The Pixel Tracker logo" alt="The Pixel Tracker logo">
  <img src="/assets/images/pixel_tracker_logo_120px.jpg" alt=""></a>
  <figcaption>Image caption.</figcaption>
</figure>
```

Half width, two columns, images:

```
<figure class="half">
  <a href="/weekend_stories_pics/2021/2102_Corona_Fruehling/2102 Corona Fruehling 8170-1v (21. Feb. 2021).jpg">
  <img src="/weekend_stories_pics/2021/2102_Corona_Fruehling/2102 Corona Fruehling 8170-1v (21. Feb. 2021).jpg"></a>

  <a href="/weekend_stories_pics/2021/2102_Corona_Fruehling/2102 Corona Fruehling 8171-1v (21. Feb. 2021).jpg">
  <img src="/weekend_stories_pics/2021/2102_Corona_Fruehling/2102 Corona Fruehling 8171-1v (21. Feb. 2021).jpg"></a>

  <figcaption>Gallery with a two image per row grid.</figcaption>
</figure>
```

Third width, three column, images:
```
<figure class="third">
  <a href="/weekend_stories_pics/2021/2102_Corona_Fruehling/2102 Corona Fruehling 8156-1v (16. Feb. 2021).jpg">
  <img src="/weekend_stories_pics/2021/2102_Corona_Fruehling/2102 Corona Fruehling 8156-1v (16. Feb. 2021).jpg"></a>

  <a href="/weekend_stories_pics/2021/2102_Corona_Fruehling/2102 Corona Fruehling 8170-1v (21. Feb. 2021).jpg">
  <img src="/weekend_stories_pics/2021/2102_Corona_Fruehling/2102 Corona Fruehling 8170-1v (21. Feb. 2021).jpg"></a>

  <a href="/weekend_stories_pics/2021/2102_Corona_Fruehling/2102 Corona Fruehling 8171-1v (21. Feb. 2021).jpg">
  <img src="/weekend_stories_pics/2021/2102_Corona_Fruehling/2102 Corona Fruehling 8171-1v (21. Feb. 2021).jpg"></a>

  <a href="/weekend_stories_pics/2021/2102_Corona_Fruehling/2102 Corona Fruehling 8161-1v (21. Feb. 2021).jpg">
  <img src="/weekend_stories_pics/2021/2102_Corona_Fruehling/2102 Corona Fruehling 8161-1v (21. Feb. 2021).jpg"></a>

  <a href="/weekend_stories_pics/2021/2102_Corona_Fruehling/2102 Corona Fruehling 8164-1v (21. Feb. 2021).jpg">
  <img src="/weekend_stories_pics/2021/2102_Corona_Fruehling/2102 Corona Fruehling 8164-1v (21. Feb. 2021).jpg"></a>

  <a href="/weekend_stories_pics/2021/2102_Corona_Fruehling/2102 Corona Fruehling 8175-1v (25. Feb. 2021).jpg">
  <img src="/weekend_stories_pics/2021/2102_Corona_Fruehling/2102 Corona Fruehling 8175-1v (25. Feb. 2021).jpg"></a>

  <figcaption>Gallery with a three image per row grid.</figcaption>
</figure>
```

Centered figure captions: Add the line text-align: center; to the figcaption section in _base.css if you prefer centered figure captions.
