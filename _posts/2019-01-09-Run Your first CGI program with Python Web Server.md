---
layout : post
title : Run your first CGI program with python web server
---
Allo, geeks and nerds. This is an introduction about how to run your
first CGI program with Python Web Server. Here I am using python3.
We all know ( Maybe you don't know) the process below of creating a
CGI program and running it.

Create a folder called cgi-bin,  Here I put
it in the folder C:\Python\Python-web.

![](/assets/images/2018-12-18/1-1.jpg)

Create a file main.py, put it in the folder
cgi-bin, so the Absolute Path of this file is
C:\Python\Python-web\cgi-bin\mian.py.

source code of mian.py :
{% highlight ruby %}
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
{% endhighlight %}

Open cmd shell, change the current directory to
C:\Python\Python-web as below :
![](/assets/images/2018-12-18/1-2.jpg)

Then type python -m http.server --cgi 8002, start python web server.
(please install python3 first)
![](/assets/images/2018-12-18/1-3.jpg)

Open a browser, type http://localhost:8002/cgi-bin/main.py
or http://127.0.0.1:8002/cgi-bin/main.py
![](/assets/images/2018-12-18/1-4.jpg)

Bingo! You get it. Cool right? Have a cup of coffee and taste your victory.

After your coffee, lets think one step deeper. What do you think the
result would be if I do some changes here.

1)copy folder cgi-bin, name the copy as cgi, then change the current
directory to  C:\Python\Python-web in cmd shell, start the python
http.server, then run the porgram: http://localhost:8002/cgi/main.py

2)copy folder cgi-bin, name the copy as htbin, then change the
current directory to  C:\Python\Python-web in cmd shell, start
the python http.server, then run the porgram:
http://localhost:8002/htbin/main.py

3)change the current directory to  C:\Python\Python-web\cgi-bin in
cmd shell, start the python http.server, then run the program :
http://localhost:8002/htbin/main.py

4)create a new folder with name cgi( you can name it as what you
want)  under the folder cgi-bin, move the file main.py under the
folder cgi,  then change the current directory to  C:\Python\Python-web
in cmd shell, start thepython http.server, then run the porgram:
http://localhost:8002/cgi-bin/cgi/main.py

Does the coffee taste a litte bit bitter after your tried the
exmaples above?  Why does it show the source code of the mian.py
file in the browser for examples 1 and 3. Why example 2 and 4
are still right?

Well, Let us see what is happenning here.  When we run the command
python -m http.server --cgi 8002, acutally we were running the server.py
file provide by python3. This file is in the folder where you installed
python3. For me the file path is as below.
![](/assets/images/2018-12-18/1-5.jpg)

Let's open the file server.py, and search for /cgi-bin or /htbin,
we find a variable with name cgi-directories.
![](/assets/images/2018-12-18/1-6.jpg)

Then we search cgi_directories, and find this:
![](/assets/images/2018-12-18/1-7.jpg)

That's why we need to start the python web server under the parent
folder of cgi-bin or htbin. The url could be in format
localhost:8002/cgi-bin/* or localhost:8002/htbin/*.

Okay. Now you know how to run your first simple CGI program with
python web server. Warm your coffee and Enjoy!
