---
layout : post
title : Write Your Blog with Jekyll and Github Pages
categories: [Jekyll, Github Pages]
tags: [Jekyll, Github Pages, minima]
---
[//]: # defined a way to access images related to the post easier.
{% include post-imagepath.md %}

Bonjour, geeks and nerds. In this post I will introduce how to write your blog with Jekyll and Github Pages.
There are many tutorials online of Jekyll and Github. If this post can't please you, well, I don't care.
The syllabus of this post:  

No | Title | Comment
:------: | :------: | :------:
1 | Jekyll | Brief introduction
2 | Github Pages | Brief introduction
3 | Deploy Jekyll with minima theme on Github Pages | introduction of how to deploy jekyll with minima theme on Github

### 1.Jekyll
I highly recommend you to read Jekyll's official step by step tutorial.  
[Jekyll official step by step tutorial](https://jekyllrb.com/docs/step-by-step/01-setup/)  

### 2.Github Pages
I highly recommend you to read the official introduction of Github pages.  
[Github Pages](https://pages.github.com/)

### 3.Deploy Jekyll with minima theme on Github Pages
I assume you would have a Jekyll project on your computer if you tried to type the code when you
read the official Jekyll tutorial. When you run it, the first page it showed is ugly and simple, but
at least it worked.  

To make your blog pages pretty, Jekyll provides many themes. The default theme is minima, defined in **_config.yml** file. Well, there are many other themes you can use, but here I will just use minima as the example.  

An easy way is to fork jekyll/minima repository to your account:
- First you need to login in Github, search jekyll/mimima like below:
>
![]({{ images[0] }})  

- After you jump to the jekyll/mimima page, click fork:
>
![]({{ images[1] }})

- Now you have your own minima repository, if you don't like the name, just change it
>
![]({{ images[2] }})  

**Note:**  
*when you name your repository with letters, don't use - or other wired characters, otherwise you may have problem when you try to access the Github page of your repository*
