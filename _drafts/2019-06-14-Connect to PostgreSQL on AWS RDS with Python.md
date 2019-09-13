---
layout : post
title : Connect to PostgreSQL on AWS RDS with Python
subPath : "2019-06-14/"
---

{% assign filepath = site.gitRepositoryURL | append : site.resourcesPath | append : page.subPath %}
{% assign layoutfilePath = site.gitRepositoryURL | append : "/\_layout/" %}
{% assign projectPath = site.gitRepositoryURL | append : "/"}

&emsp; Hej,Hej! geeks and nerds. In this post I will introduced how to connect to PostgreSQL on AWS RDS with Python. I didn't think about to use AWS RDS at first. I am learning the online course [CS50'S Web Programming with Python and JavaScript](https://courses.edx.org/courses/course-v1:HarvardX+CS50W+Web/course/#block-v1:HarvardX+CS50W+Web+type@chapter+block@3b4d945d89eb40bcad81746770a81c3b). When I tried to do the [project 1](https://docs.cs50.net/web/2018/x/projects/1/project1.html) homework, I wanted to use [Heroku](https://www.heroku.com/), but when I tried to sign up on the website, it said it can't verify whether I was a robot or not. I understand this is a protection system for the website, but I can't find any verification button or input for the verification code. So I gave up. I also don't want to install PostgreSQL on my computer, because sometimes, I use my work computer. Then AWS RDS came to my head. But to be clear, I also didn't run the python code on my computer, the code is running on my AWS EC2 instance.  

### 1.Source Code
&emsp; The source code I am using is from the Harvard CS50 course lecture SQL, you could download from here:<br/>
[source code]({{ filepath | append : "sourceCode.zip"})

### 2.Add CV files to the project
&emsp; To add the CV files to the blog, we need to follow the structure of the project. Here we add file `cv.html` in `_layout` folder. This file is the layout template of the CV. To simplify at the beginning, I didn't set the layout value of this file as default. The `cv.file` uses the structure of the `index.html` from the original CV template you downloaded from the above link. You could check this flie by clicking the link below:
[cv.html]({{ layoutfilePath | append : "cv.html"})
&emsp; The `cv.html` is just the presentation of the CV, I put the content of the CV in `englishcv.md` file. In this file, I defined the `title` varaible to `CV(EN)` which will be showed in the navigation bar as my CV navigation link.
To check this file, click the link below:
[englishcv.md]({{ projectPath | append : "englishcv.md"})
### 3. Problems need to be fixed later
We added CV files in the project, if you try it, it works well. But there are some problems we need to fix later.
- `cv.html`: this file has its own css and js scripts. and it didn't use the default layout, that's why when we redirect to the CV page, there is no navigation bar and footer bar like other blog pages. We need to fix this later.
- `cv.html`: download pdf function is not working so far.
- `cv.html`：go to top function is not working on some browsers like chrome.
