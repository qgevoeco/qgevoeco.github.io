
# qgevoeco.github.io
The Wolak Research Group at Auburn University: https://qgevoeco.github.io

# Overview of this repository and what produces the website

There are 2 main types of branches in this repository, because this website is built using Jekyll:

  - The first is the one that contains all of the files that **are the website**. This is generally always the `master` branch. 

  - The next types of branches (e.g., `preJekyll-src`) are the raw files for making a website in Jekyll. So these files **will not**, in general, show up as a nice website in a browser unless you somehow interface with Jekyll.

All changes to the content and styling happen within the second type of branch (e.g., `preJekyll-src`). These files then get run through Jekyll on a personal computer, and Jekyll spits out the files for a website into the `_site` folder. The contents of `_site` then get copied into the `master` branch when it is time to update the website.

# Instructions for Updating

**Be sure to make changes to a branch other than `master` (e.g., in `preJekyll-src`).**

## Add/Update Group Members

  - Add/Update member in [_data/group-members.yml](https://github.com/qgevoeco/qgevoeco.github.io/blob/preJekyll-src/_data/group-members.yml): click on the "edit" (pencil) icon to edit
    - copy and paste the following template in the appropriate section (see `title:` as either `Postdocs`, `Graduate Students`, etc.) of the file, and replace **all** placeholders *or* **delete** any irrelevant lines:

```
  - name: Sewall Wright
    role: Postdoctoral Researcher
    start-date: 1889
    end-date: 1988 # Only if you have FINISHED
    bio: >
        Guinea pig eraser effectiveness.
    avatar: # valid avatar image placed in `/images` or with `http:` URL
    email: <ifyouwant@auburn.edu>
    web: http://theotherwrightbrother.com # NOT http://qgevoeco.github.io
    cv: Wright_CV_2019.pdf # file located in `/people/`
    github: shiftingbalance
    twitter: beyondthegrave
    coadvisor: Matt's personalities all count as 1 advisor # otherwise someone else
    coadvisor-url: http://blah.blah
```

    - If nothing is given for `avatar:`, but you do fill-in a GitHub username, your GitHub avatar will be used.
    If you want a different image as your `avatar:`
        - Name your image `LastnameFirstname.png` (or `.jpg`) and either send this to me or run the following in a terminal (must have Image Magick installed)


```
FILE="WolakMatthew.png"
## First resize
convert $FILE \
        -resize x600 -resize '600x<' -resize 50% \
        -gravity center -crop 300x300+0+0 +repage \
    ./cropped_$FILE
## Now cut out the circle
convert ./cropped_$FILE \( -size 300x300 xc:none -fill white -draw "circle 150,150 150,0" \)\
        -compose copy_opacity \
        -composite \
    ./circle_$FILE
```

        - Now, add this to the [images](https://github.com/qgevoeco/qgevoeco.github.io/tree/preJekyll-src/images) folder (with file named "circle_LastnameFirstname.png") and add the file name to the `avatar:` line in your section of [_data/group-members.yml](https://github.com/qgevoeco/qgevoeco.github.io/blob/preJekyll-src/_data/group-members.yml)




## Add A Post: News or Posts

  - In your local version (e.g., cloned) of the `qgevoeco/qgevoeco.github.io` repository on your own computer, go to the `preJekyll-src` branch [_drafts](https://github.com/qgevoeco/qgevoeco.github.io/tree/preJekyll-src/_drafts) folder, open one of the `a-draft-...md` files, __immediately save as a new file__.
    - My __convention__ is to only save it in the `_drafts` folder with a short and descriptive title, where words are separated by dashes (e.g., `original-post-file-name.md`). I keep the filename this way until it is no long in preparation (see end for how the filename must be constructed to be a valid post filename).

  - Edit the file with the information you want to include. Use the other templates in the `_drafts` folder or previous `News` or `Posts`, located in [_posts](https://github.com/qgevoeco/qgevoeco.github.io/tree/preJekyll-src/_posts) or [_posts/news](https://github.com/qgevoeco/qgevoeco.github.io/tree/preJekyll-src/_posts/news), as examples for how to code different objects in the markdown syntax. See the next section about images, specifically.
    - Be sure to edit the header, giving `tags` that would be good words to categorize/order the post/news item and an `excerpt` that would be a short snippit that might entice someone to click the link to see the entire post.
    - Consider including a `feature` and/or `teaser` image for a short and wide banner or representative picture to be used in re-posts or the main page. See the formatting note about these in the next section about images...

### Images
  - All accompanying images should be placed within the [images](https://github.com/qgevoeco/qgevoeco.github.io/tree/preJekyll-src/images) folder. There are 2 ways to include images, explained below. Briefly, the first uses the image as it is formatted in `images`. For the second method, place your file in `images/_fullsize` and let `Jekyll` create several different sizes of the image and let each viewer's browser and screen size determine which sized image is loaded. 
    - (1) If you want to __use the image as is__ the file should go directly into the `images` folder. The code to insert these images can be one of:

        - Markdown images

```
![sample image](/images/bio-photo.jpg "image text description")
```

        - Figure tags (2 in a row)

```html
<figure class="half">
	<img src="{{ site.url }}/images/image-filename-1.jpg">
	<img src="{{ site.url }}/images/image-filename-2.jpg">
	<figcaption>Caption describing these two images.</figcaption>
</figure>
```

        - Figure tags, linking to larger versions of the 3 images

```html
<figure class="third">
	<a href="http://placehold.it/1200x600.gif"><img src="http://placehold.it/900x450.gif"></a>
	<a href="http://placehold.it/1200x600.gif"><img src="http://placehold.it/900x450.gif"></a>
	<a href="http://placehold.it/1200x600.gif"><img src="http://placehold.it/900x450.gif"></a>
	<figcaption>Three linked images.</figcaption>
</figure>
```
 
    - (2) If you want to use the `Jekyll-picture-tag`, then place the "raw" image file inside [images/_fullsize](https://github.com/qgevoeco/qgevoeco.github.io/tree/preJekyll-src/images/_fullsize). Be sure to use the `Jekyll-picture-tag` [liquid](https://jekyllrb.com/docs/liquid/) code illustrated below.
        - Figure tags (2 images), with `Jekyll-picture-tag`

```html
<figure class="half">
	<img src="{{ site.url }}{% picture direct bio-photo.jpg %}">
	<img src="{{ site.url }}{% picture direct bio-photo.jpg %}">
</figure>
```


#### Teaser and Feature Images

In the YAML header (the code at the very top of the file between the two sets of `---`), you can include teaser and feature images:
```
---
image:
  teaser: image1.jpg
  feature: feature-image2.jpg
---
```

The `teaser` is used in the homepage, `News`, and/or `Posts` page to display a list of all potential items. This is also the image that accompanies the post if it was to be shared on social media (I think). 

A `feature` image is one that is displayed at the top of the page and is very wide and very short (e.g., the entrance to AU's Jule Collins Smith Museum of Fine Art in the [News>REU poster session 2019](https://qgevoeco.com/news/JorgeREUposter2019/) post). This needs to be edited by you (or me) to have the right aspect ratio or dimensions (currently 990 px wide and 180 px high). Please name the file with `feature-` to begin the filename (e.g., `feature-whateveryouwant.jpg`).

Both of these types of images should be placed in `images` (and _not_ `images/_fullsize`). In other words, you cannot use the `Jekyll-picture-tag` plugin to manage teaser or feature images.


### Prepare to post
  - __Delete__ any irrelevant lines left over from the draft template.
  - When you are happy with the post:
    - Rename the file by _prepending_ the filename with the date (e.g., `YYYY-MM-DD-original-post-file-name.md`)
    - Copy this file into the correct/appropriate sub-folder of `_posts`
  - Commit the changes to your local repository and submit a [Pull Request](https://help.github.com/en/articles/creating-a-pull-request) to the `preJekyll-src` branch of the `qgevoeco/qgevoeco.github.io` repository.
  - The pull request will be reviewed, and if everything is OK the changes will be incorporated into the website!
  - Consider sharing the post on social media via the buttons at the bottom of the post you just created!




