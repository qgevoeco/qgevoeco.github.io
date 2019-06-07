
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




<!-- 
## 
[Update projects](https://github.com/qgevoeco)
-->


