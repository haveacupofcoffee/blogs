---
layout : post
title : Run your first flask application on AWS EC2
imgPathTwo : "2019-01-20/"
---
[//]: # (the path of images is /assets/images/2019-01-20, the first part /assets/images/ is defined in \_config.yml,
[//]: # the second part 2019-01-20/ is the date in the title of the post, for each post, this part is different ,so the
[//]: # images src path is {{imgpath | append : "name of the image" }} eg : {{ imgpath | append : "1.png"}} )
{% assign imgpath = site.gitRepositoryURL | append : site.imgPathOne | append: page.imgPathTwo %}

Hej,Hej, geeks and nerds. This is an introduction about how to run your
first flask application on AWS EC2.Since cloud service is very popular nowadays
and AWS offers free trial service for individuals. So you are going to use AWS EC2
as your server and your computer as client to access the flask applicaton deployed on EC2.

### 1.Start with AWS EC2
To use AWS EC2, follow the guide below:
[https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EC2_GetStarted.html#ec2-connect-to-instance-linux](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EC2_GetStarted.html#ec2-connect-to-instance-linux)<br/>
Here I am using AMI as below, as you can see, there are many tools which have been installed already.
![]({{ "1.png" | prepend: imgpath }})
Choose the free Instance:
![]({{ "2.png" | prepend: imgpath }})
Make sure HTTP and SSH is available for connection
![]({{ "3.png" | prepend: imgpath }})
Then launch the instance, you may need to create a new key pair for security if
you don't have one when you launch it.

### 2. Gitbash
To access the AWS EC2 instance we just created, you need a tool that supports
SSH conneciton. Here I am using Git Bash, it is just one feature of Git.
You could download Git from website [https://git-scm.com/downloads](https://git-scm.com/downloads) according to
the OS you are using on your computer. After you install Git, you could type
git in your seach bar or right click on the desktop and choose Git Bash Here.
![]({{ "4.png" | prepend: imgpath }})
Now you can access AWS EC2 instance by type ssh command as below:
![]({{ "5.png" | prepend: imgpath }})
The `myaws.pem` file is my key pair file, need to put the absolute path of this
file here if you didn't move into the parent folder of this pem file.

### 3. Magic Python
You may remember when I chose AMI for AWS EC2， I mentioned that it contained
some tools' packeges already. Python is one of them. If you type `python --version`,
it shows the version of python. Here the pre-installed python version is `2.7.14` as shown below.
![]({{ "6.png" | prepend: imgpath }})
I will use the latest version of python3 here. There are many ways to install
python under Linux. Here I will use the `wget` command to download python 3.7.2
package then install it. Before you install python, I recommand you to change to
`root` user with command `sudo su`(The images below may not show that I was using root user).
- download
`wget wget https://www.python.org/ftp/python/3.7.2/Python-3.7.2.tgz`
- unzip
`tar -zxvf Python-3.7.2.tgz`
- Configure
```
cd Python-3.7.2  
./configure
```
Note : you may meet the "no acceptable C compiler found in $PATH " error as below :
![]({{ "7.png" | prepend: imgpath }})<br/>
In this case , you need to install C compilers first:
`yum install make gcc gcc-c++`
![]({{ "8.png" | prepend: imgpath }})<br/>
Then run `./configure` again.
when you run `./configure`, you need to answer a question. Type `y`.
![]({{ "9.png" | prepend: imgpath }})<br/>
- compile and install
```
make
make install
```
after you finish, type `python3 --version` in the command line. You should see the new python version you installed.
![]({{ "10.png" | prepend: imgpath }})<br/>
If it shows command not found error. You need to edit the PATH variable.
For me my python3 command is in the path `/usr/local/bin`, so I need to add this path to PATH variable. One way to do this:
`vim ~/.bashrc`
then add `export PATH=/usr/local/bin:$PATH` at the end of the file, save the file.
then run the command `source ~/.bashrc`, then try `python3 --version`  

### 4. flask framework
   Flask is a framework used to develope Web applicatons with Python. You could install flask
in a virtual environment. But here I will just install it directly. I need to remind you that you may have
two verions of python installed in your system, and you want to work on flask with the newest python3. So you need to install
flask with command `python3 -m pip install flask`(use user root)
Then try `flask --version` to check if you installed flask successfully.<br/>
![]({{ "11.png" | prepend: imgpath }})<br/>

### 5. Run your first flask applicaton
To run your first flask application, you need to have an flask applicaton first, here I created a python file
named `hellotest.py`:
{% highlight ruby %}
from flask import Flask

app = Flask(__name__)

@app.route("/")
def index() :
    return "<h1>Hello world!</h1>"

@app.route("/user/<name>")
def user(name):
    return "<h1>hello,{}</h1>".format(name)

{% endhighlight %}
first run command `export FLASK_APP=hellotest.py`, then run `flask run -h 0.0.0.0 -p 80`,
it shows information like below:<br/>
![]({{ "12.png" | prepend: imgpath }})<br/>

Then open a browser in your computer and access the flask applicaton with AWS EC2 IPv4 public IP address(for me its http://35.183.77.241/ ):
![]({{ "13.png" | prepend: imgpath }})<br/>   
![]({{ "14.png" | prepend: imgpath }})<br/> 
Voila！ You did it, now you can get your ass on the boat and enjoy the journey of flask!
