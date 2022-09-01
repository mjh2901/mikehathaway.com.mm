---
title: "From Ghost to Jekyll"
excerpt: "No one wants a database."
collection: "posts"
header:
  image: /assets/images/yosemit_cover.png
  og_image: /assets/images/yosemit_cover.png
  overlay_image: /assets/images/yosemit_cover.png
  overlay_filter: 0.5 # same as adding an opacity of 0.5 to a black background
  caption: "Photo credit: [**Unsplash**](https://unsplash.com)"
  teaser: /assets/images/yosemit_cover.png
  actions:
    - label: "More Info"
      url: "https://unsplash.com"
categories:
  - Layout
  - Uncategorized
tags:
  - edge case
  - image
  - layout
last_modified_at: 2022-08-31T16:20:02-05:00
---
Ghost started wanting a databse, Jekyll not so much

{% capture fig_img %}
![Foo]({{ '/assets/images/unsplash-gallery-image-3.jpg' | relative_url }})
{% endcapture %}

<figure>
  {{ fig_img | markdownify | remove: "<p>" | remove: "</p>" }}
  <figcaption>Photo from Unsplash.</figcaption>
</figure>