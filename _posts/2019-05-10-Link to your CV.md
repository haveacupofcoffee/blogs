---
layout : post
title : Link to your CV
subPath : "2019-05-10/"
---

{% assign filepath = site.gitRepositoryURL | append : site.resourcesPath | append : page.subPath %}
{% assign layoutfilePath = site.gitURL | append : "\_layouts/" %}
{% assign projectPath = site.gitURL | append : "/" %}

&emsp; Hej,Hej! geeks and nerds. In the last post I introduced how to write your blog with Jekyll and Github page. It's time to link to your CV unless you have concerns about your privacy.
&emsp; Since I was using minima theme of Jekyll, one way to do this is writing your CV information in `about.md` file. Then when you click on `about` in the navigation bar, it will show your CV. But it is not clear for the viewers unless you change the name `about` to `CV` or some other names which are obvious to the viewers. Here I will keep `about ` page as I want to put some information about the blog project. I will add a new navigation link near the `about` navigation link to present my CV.
&emsp; To write a CV, the content of the CV is important, but the structure and the appearance is more important. You have to make it organized to give the viewer a great first impression. There are many CV templates online, using them will make your work easier.
### 1.CV template
&emsp; You could download the original CV template I am using from the link below:<br/>
[download the CV template files]({{ filepath | append : "cvtempalte.zip"}})

### 2.Add CV files to the project
&emsp; To add the CV files to the blog, we need to follow the structure of the project. Here we add file `cv.html` in `_layout` folder. This file is the layout template of the CV. To simplify at the beginning, I didn't set the layout value of this file as default. The `cv.file` uses the structure of the `index.html` from the original CV template you downloaded from the above link. You could check this flie by clicking the link below:<br/>
[cv.html]({{ layoutfilePath | append : "cv.html"}})
&emsp; The `cv.html` is just the presentation of the CV, I put the content of the CV in `englishcv.md` file. In this file, I defined the `title` varaible to `CV(EN)` which will be showed in the navigation bar as my CV navigation link.
To check this file, click the link below:<br/>
[englishcv.md]({{ projectPath | append : "englishcv.md"}})
### 3. Problems need to be fixed later
We added CV files in the project, if you try it, it works well. But there are some problems we need to fix later.
- `cv.html`: this file has its own css and js scripts. and it didn't use the default layout, that's why when we redirect to the CV page, there is no navigation bar and footer bar like other blog pages. We need to fix this later.
- `cv.html`: download pdf function is not working so far.
- `cv.html`：go to top function is not working on some browsers like chrome.
