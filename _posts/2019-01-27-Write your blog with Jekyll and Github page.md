---
layout : post
title : Write your blog with Jekyll and Github Pages
imgPathTwo : "2019-01-27/"
---
[//]: # (the path of images is /assets/images/2019-01-27, the first part /assets/images/ is defined in \_config.yml,
[//]: # the second part 2019-01-27/ is the date in the title of the post, for each post, this part is different ,so the
[//]: # images src path is {{imgpath | append : "name of the image" }} eg : {{ imgpath | append : "1.png"}} )
{% assign imgpath = site.imgurl | append : site.imgPathOne | append: page.imgPathTwo %}


Bonjour, geeks and nerds. In this post I will introduce how to write your blog with Jekyll and Github Pages.
There are many tutorials online of Jekyll and Github. If this post can't please you, well, I don't care.
The syllabus of this post :<br/>
| No | Title | Comment |
| :------: | :------: | :------: |
|  1 | Jekyll | Brief introduction |
|  2 | Github Pages | Brief introduction |
|  3 | Deploy Jekyll with minima theme on Github Pages | Brief introduction |

### 1.Jekyll
I highly recommend you to read Jekyll's official step by step tutorial.<br/>
[Jekyll offical step by step tutorial](https://jekyllrb.com/docs/step-by-step/01-setup/)<br/>

### 2.Github Page
I highly recommend you to read the official introduction of Github pages.<br/>
[Github Page](https://pages.github.com/)

### 3.Deply Jekyll with minima theme on Github Pages
  I assume you would have a Jekyll project on your computer if you tried to type the code when you
read the official Jekyll tutorial. When you run it, the first page it showed is ugly and simple, but
at least it worked.
  To make your blog pages pretty, Jekyll provides many themes. The default theme is minima, defined in \_config.yml  
file.Well, there are many other themes you can use, but here I will just use minima as the example.
  An easy way is to fork jekyll/minima repository to your account:
- First you need to login on Github, seach jekyll/mimima like below :
![]({{ imgpath | append : "third1.png"  }})<br/>
- After you jump to the jekyll/mimima page, click fork:
![]({{ imgpath | append : "third2.png"  }})<br/>
- Now you have your own minima repository, if you don't like the name, just change it
![]({{ imgpath | append : "third3.png"  }})<br/>
for me , I clone the minima repository to my local computer and create a new repository called `blogs`,
then clone the `blogs` repository to my local computer, copy all the files in minima repository to the `blogs`
repository, changed some files(you don't need to do this at first), then pushed the local `blogs` repository
to the `blogs` repository on Github(to the master branch directly). Now if you access
the Github page of `blogs` repository, you will see the first page your blog.<br/>
**Note**
*when you name your repository with letters, don't use - or other wired characters, otherwise you may have problem when you try to access the Github page of your repository*
