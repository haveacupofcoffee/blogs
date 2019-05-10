---
layout : post
title : Link to your CV
imgPathTwo : "2019-05-10/"
---
[//]: # (the path of images is /assets/images/2019-01-27, the first part /assets/images/ is defined in \_config.yml, the second part 2019-05-10/ is the date in the title of the post, for each post, this part is different ,so the images src path is {{filepath | append : "name of the image" }} eg : {{ imgpath | append : "1.png"}} )
{% assign filepath = site.imgurl | append : site.imgPathOne | append: page.imgPathTwo %}

&emsp; Hej,Hej! geeks and nerds. In the last post I introduced how to write your blog with Jekyll and Github page. It's time to link to your CV unless you have concerns about your privacy.
&emsp; Since I was using minima theme of Jekyll, one way to do this is writing your CV information in `about.md` file. Then when you click on `about` in the navigation bar, it will show your CV. But it is not clear for the viewers unless you change the name `about` to `CV` or some other names which are obvious to the viewers. Here I will keep `about ` page as I want to put some information about the blog project. I will add a new navigation link near the `about` navigation link to present my CV.
&emsp; To write a CV, the content of the CV is important, but the structure and the appearance is more important. You have to make it organized to give the viewer a great first impression. There are many CV templates online, using them will make your work easier.
### 1.CV template
&emsp; You could download the original CV template I am using from the link below:
[download the CV template files]({{filepath | append : "cvtempalte.zip"})

### 2.Add CV files to the project


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
