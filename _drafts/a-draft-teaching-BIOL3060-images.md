---
layout: class
title: "BIOL 3060 Principles of Ecology"
categories: teaching
comments: true
tags: [sample, images, test]
excerpt: "Survey of the major fields within the discipline of Ecology"
---

Here are some examples of what a post with images might look like. If you want to display two or three images next to each other responsively use `figure` with the appropriate `class`. Each instance of `figure` is auto-numbered and displayed in the caption.

{% include toc.html %}

## Markdown images

An image located at another location on the internet
![sample image](https://placehold.it/900x450.gif "placeholder")

An image located within this site
![sample image 2](/images/bio-photo.jpg "local file placeholder")

An image that is a link
[![sample image](https://placehold.it/900x450.gif)](https://placehold.it "A simple image placeholder service.")

## Figure tag (for images or video)

### One

<figure>
	<a href="https://placehold.it/900x450.gif"><img src="https://placehold.it/900x450.gif"></a>
	<figcaption>Image caption.</figcaption>
</figure>

### Two in a row

Apply the `half` class like so to display two images side by side that share the same caption.

```html
<figure class="half">
	<img src="{{ site.url }}/images/image-filename-1.jpg">
	<img src="{{ site.url }}/images/image-filename-2.jpg">
	<figcaption>Caption describing these two images.</figcaption>
</figure>
```

And you'll get something that looks like this:

<figure class="half">
	<a href="https://placehold.it/1200x600.gif"><img src="https://placehold.it/900x450.gif"></a>
	<a href="https://placehold.it/1200x600.gif"><img src="https://placehold.it/900x450.gif"></a>
	<figcaption>Two images.</figcaption>
</figure>

### Three in a row

Apply the `third` class like so to display three images side by side that share the same caption.

```html
<figure class="third">
	<img src="{{ site.url }}/images/image-filename-1.jpg">
	<img src="{{ site.url }}/images/image-filename-2.jpg">
	<img src="{{ site.url }}/images/image-filename-3.jpg">
	<figcaption>Caption describing these three images.</figcaption>
</figure>
```

And you'll get something that looks like this:

<figure class="third">
	<img src="https://placehold.it/900x450.gif">
	<img src="https://placehold.it/900x450.gif">
	<img src="https://placehold.it/900x450.gif">
	<figcaption>Three images.</figcaption>
</figure>


### Images that link to a larger version of the image

<figure class="third">
	<a href="https://placehold.it/1200x600.gif"><img src="https://placehold.it/900x450.gif"></a>
	<a href="https://placehold.it/1200x600.gif"><img src="https://placehold.it/900x450.gif"></a>
	<a href="https://placehold.it/1200x600.gif"><img src="https://placehold.it/900x450.gif"></a>
	<figcaption>Three linked images.</figcaption>
</figure>


## Figure tag with Jekyll-picture-tag


<figure class="half">
  <img
    src="{% picture direct bio-photo.jpg %}"
    alt="local file placeholder">
  <img
    src="{% picture direct bio-photo.jpg %}"
    alt="local file placeholder">
</figure>


```html
<figure class="half">
	<img src="{{ site.url }}{% picture direct bio-photo.jpg %}">
	<img src="{{ site.url }}{% picture direct bio-photo.jpg %}">
</figure>
```

