---
layout: article
title: "A Post with Images"
categories: articles
date: 2019-06-04T17:24:00
modified:
comments: true
tags: [sample, images, test]
excerpt: "Examples and code for displaying images in posts."
---

Here are some examples of what a post with images might look like. If you want to display two or three images next to each other responsively use `figure` with the appropriate `class`. Each instance of `figure` is auto-numbered and displayed in the caption.

{% include toc.html %}

## Markdown images

An image located at another location on the internet
![sample image](http://placehold.it/900x450.gif "placeholder")

An image located within this site
![sample image 2](/images/bio-photo.jpg "local file placeholder")

An image that is a link
[![sample image](http://placehold.it/900x450.gif)](http://placehold.it "A simple image placeholder service.")

## Figure tag (for images or video)

### One

<figure>
	<a href="http://placehold.it/900x450.gif"><img src="http://placehold.it/900x450.gif"></a>
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
	<a href="http://placehold.it/1200x600.gif"><img src="http://placehold.it/900x450.gif"></a>
	<a href="http://placehold.it/1200x600.gif"><img src="http://placehold.it/900x450.gif"></a>
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
	<img src="http://placehold.it/900x450.gif">
	<img src="http://placehold.it/900x450.gif">
	<img src="http://placehold.it/900x450.gif">
	<figcaption>Three images.</figcaption>
</figure>


### Images that link to a larger version of the image

<figure class="third">
	<a href="http://placehold.it/1200x600.gif"><img src="http://placehold.it/900x450.gif"></a>
	<a href="http://placehold.it/1200x600.gif"><img src="http://placehold.it/900x450.gif"></a>
	<a href="http://placehold.it/1200x600.gif"><img src="http://placehold.it/900x450.gif"></a>
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

