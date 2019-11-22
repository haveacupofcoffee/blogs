---
layout: post
title: Run Your First CGI Program with Python Web Server
categories: [python]
tags: [python, CGI, Python Web Server]
---
[//]: # defined a way to access images related to the post easier.
{%- include post-imagepath.md -%}

Allo, geeks and nerds. This is an introduction about how to run your
first CGI program with Python Web Server. Here I am using python3.
We all know ( Maybe you don't know) the process below of creating a
CGI program and running it.

1. Create a folder called **cgi-bin**,  Here I put it in the folder
**C:\Python\Python-web**.
>C:\Python\Python-web
>>cgi-bin
>
![]({{ images[0] }})

2. Create a file **main.py**, put it in the folder
**cgi-bin**, so the Absolute Path of this file is
**C:\Python\Python-web\cgi-bin\main.py**.
>C:\Python\Python-web
>>cgi-bin
>>>main.py
>
source code of *main.py* :
```
print ("Content-type:text/html")
print ()
print ('<html>')
print ('<head>')
print ('<meta charset="utf-8">')
print ('<title>Hello Word - my first CGI Program</title>')
print ('</head>')
print ('<body>')
print ('<h2>Hello Word!</h2>')
print ('</body>')
print ('</html>')
```

3. Open cmd shell, change the current directory to
**C:\Python\Python-web** as below :
>
![]({{ images[1] }})

4. Type `python -m http.server --cgi 8002`, start python web server.
(please install python3 first)
>
![]({{ images[2] }})

5. Open a browser, type *http://localhost:8002/cgi-bin/main.py*
or *http://127.0.0.1:8002/cgi-bin/main.py*
>
![]({{ images[3] }})

Bingo! You get it. Cool right? Have a cup of coffee and taste your victory.

After your coffee, let's think one step deeper. What do you think the
result would be if I do some changes here.

1. Copy folder **cgi-bin**, name the copy as **cgi**, then change the current
directory to **C:\Python\Python-web** in cmd shell, start the python
http.server, then run:*http://localhost:8002/cgi/main.py*

2. Copy folder **cgi-bin**, name the copy as **htbin**, then change the
current directory to **C:\Python\Python-web** in cmd shell, start the python
http.server, then run:*http://localhost:8002/htbin/main.py*

3. Change the current directory to **C:\Python\Python-web\cgi-bin** in
cmd shell, start the python http.server, then run:*http://localhost:8002/htbin/main.py*

4. Create a new folder with name **cgi** (you can name it as what you
want) under the folder **cgi-bin**, move the file main.py into the folder **cgi**,
then change the current directory to **C:\Python\Python-web**
in cmd shell, start python http.server, then run:*http://localhost:8002/cgi-bin/cgi/main.py*

Does the coffee taste a litte bit bitter after your tried the
exmaples above?  Why does it show the source code of the mian.py
file in the browser for examples 1 and 3. Why examples 2 and 4
are still right?

Well, Let us see what is happening here.  When we run the command
`python -m http.server --cgi 8002`, actually we are running the **server.py**
file provide by python3. This file is in the folder where you installed
python3. For me the file path is as below.
>
![]({{ images[4] }})

Let's open the file *server.py* and search for */cgi-bin* or */htbin*.
We find a variable with name *cgi-directories*.
>
![]({{ images[5] }})

Then we search *cgi_directories* and find this:
>
![]({{ images[6] }})

That's why we need to start the python web server under the parent
folder of **cgi-bin** or **htbin**. The url could be in format *localhost:8002/cgi-bin/*\*
or *localhost:8002/htbin/*\*.  

Okay. Now you know how to run your first simple CGI program with
Python Web Server. Warm your coffee and Enjoy!
