---
layout : post
title : Link to Your CV
categories: [Jekyll]
tags: [Jekyll]
---
{%- assign page_dir = page.date | date: "%Y-%m-%d" | append: "/" -%}
{% assign filepath = site.resourcesPath | append : page_dir | relative_url %}
{% assign layoutfilePath = site.gitURL | append : "\_layouts/" %}
{% assign projectPath = site.gitURL %}

Hej,Hej! Geeks and nerds. In the last post I introduced how to write your blog
with Jekyll and Github pages. It's time to link to your CV unless you have
concerns about your privacy.  

Since I was using minima theme of Jekyll, one way to do this is writing your CV
information in **about.md** file. Then when you click on *about* in the
navigation bar, it will show your CV. But it is not clear for the viewers unless
you change the name *about* to *CV* or some other names which are obvious to the
viewers. Here I will keep *about* page. I will add a new navigation link near
the *about* navigation link to present my CV.  

To write a CV, the content of the CV is important, but the structure and the
appearance are more important. You have to make it organized to give the viewer
a great first impression. There are many CV templates online, using them will
make your work easier.  

### 1.CV template
You could download the original CV template I am using from the link below:  
[Download the CV template files]({{ filepath | append : "cvtempalte.zip"}})  

### 2.Add CV files to the blog
To add the CV files to the blog, we need to follow the structure of jekyll.
Here I add file **cv.html** in **_layout** folder. This file is the layout template
of the CV. To simplify at the beginning, I didn't set the layout value of this
file as default. The **cv.file** uses the structure of the **index.html** from the
original CV template you downloaded from the above link. You could check this
file by clicking the link below:    
[cv.html]({{ layoutfilePath | append : "cv.html"}})  

The **cv.html** is just the presentation of the CV, I put the content of the CV
in **englishcv.md** file. In this file, I defined the *title* variable to *CV(EN)*
which will be shown in the navigation bar as my CV navigation link.  

### 3. Problems need to be fixed later
We added a link to cv in the blog. If you try it, it works well. But there are
some problems we need to fix later.
- `cv.html`: this file has its own css and js scripts. and it didn't use the
default layout, that's why when we redirect to the CV page, there is no
navigation bar and footer bar like other blog pages. We need to fix this later.  
- `cv.html`: download pdf function is not working so far.  
- `cv.html`: go to top function is not working on some browsers like chrome.
