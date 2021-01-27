---
layout: article
title: "Beetle name tags - Hi, I'm Gus"
categories: articles
date: 2020-11-18T17:24:00
modified:
comments: true
tags: [science, research, methods, code]
excerpt: "Make QR codes to keep track of individuals"
---

In our beetle research we often produce many thousands of individuals that all must be kept track of, well, individually. One of the biggest logistical nightmares we have faced is assigning unique IDs that can be easily and accurately read again in the future. Generating IDs is no sweat, my 4 year old can do that up to 632. The tricky part is reading handwriting, which after getting hurriedly written on a small surface and smudged, is no better than a 4 year old.

In this post, I am going to walk through how to use a [small shell script we wrote](https://github.com/qgevoeco/qgevoeco-lab-code/blob/main/Beetle-lab-methods/QRcode.sh) to create pages upon pages of QR codes and give a little information about how we use these in our labs research.

{% include toc.html %}


## Preparation and key aspects of the code
The script to generate QR codes is just a collection of commands that can be executed on the command line in a terminal. These are all bundled into a shell script, that can be executed to run this simple terminal program, and is [located in our research group's repository](https://github.com/qgevoeco/qgevoeco-lab-code/blob/main/Beetle-lab-methods/QRcode.sh).

The code relies on two packages:

  - [qrencode](https://fukuchi.org/works/qrencode/) (also known as `libqrencode`) to generate the QR codes
  - [ImageMagick ](https://imagemagick.org/index.php) to concatenate and convert the raw QR code images into printable sheets (8.5 in. x 11 in.).

These will need to be installed before running the shell script.

 
__Note:__ the shell script generates a temporary folder, in the current working directory, in which to place `.png` QR code files. The program then stitches these together and deletes this temporary folder (and all of the files within).


### Getting setup
Note, the following steps are for either Mac or Linux (e.g., Ubuntu) operating systems. We have not yet looked into how to implement this program on Windows.


  - Install [`qrencode`](https://fukuchi.org/works/qrencode/)
    - __Mac:__ run in a terminal
```
brew install qrencode
```

    - __Ubuntu Linux:__ run in a terminal
```
sudo apt install qrencode
```
    
  - Install [``]()
    - Often already installed on Linux/Mac (typically not already installed on Windows)
    - Type the following to find out if this is already installed:
```
magick identify -version
```
    - If it is not already installed, then:
      - __Mac:__ run in a terminal
```
brew install imagemagick
```
      
      - __Ubuntu Linux:__ run in a terminal
```
sudo apt install imagemagick
```
      
  - Download the shell script [`QRcode.sh`](https://github.com/qgevoeco/qgevoeco-lab-code/blob/main/Beetle-lab-methods/QRcode.sh)
    - To call from the command line, ensure the file is executable
  
### Code highlights


## Creating QR codes

## Using QR codes in the lab


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

