---
layout : post
title : Install Python & Flask on AWS EC2
imgPathTwo : "2019-09-27/"
---

{% assign imgpath = site.gitRepositoryURL | append : site.imgPathOne | append: page.imgPathTwo %}

### 1.Introduction
&emsp; Hola! geeks and nerds. In this post I will introduce how to install python3 and flask on EC2. I know I have written a similar post before([Run your first flask application on AWS EC2](https://haveacupofcoffee.github.io/blogs/2019/01/20/Run-Your-first-flask-program-on-AWS-EC2.html)), but when I follow the steps, I met some problems. Like openssl version is too old for pip3 that you can't run pip3 commands. I don't have much space on my computer SSD and I really don't want to install VM on my computer as it's too heavy. So I used AWS EC2 as an example. It's free(Has one year free program) and very convenient.

### 1.Outline
1) How to install openssl <br/>
&emsp; when you install flask with pip3 commands, if you have the problem below, you need to install a new version of openssl. You could find answer how to install openssl in this post.
![]({{ imgpath | append : "img1.png"  }})<br/>
2) A bash script you could use to install python3 and flask when you launch an EC2 instance or after you launched an EC2 instance.

*Note: Remember to run all commands or bash script with root user*
### 2.How to install openssl
&emsp; Before you install openssl, use `openssl version` to check if the system has a default version of openssl.If the system doesn't have a default openssl or the version is too old, install a newer version of openssl. You could find openssl release version from https://www.openssl.org/source/, here I am using the version 1.1.1d.
```
wget https://www.openssl.org/source/openssl-1.1.1d.tar.gz
tar -zxvf openssl-1.1.1d.tar.gz
cd openssl-1.1.1d
./config
make
make install
```
Back up the old version openssl command, if the system doesn't have a default openssl that had been installed. Skip this step.
```
mv /usr/bin/openssl /usr/bin/openssl.bak
```
link to the new openssl command, the default installing folder is /usr/local/bin
```
ln -s /usr/local/bin/openssl /usr/bin/openssl
```
change system configuration
```
echo "/usr/local/lib64" >> /etc/ld.so.conf
ldconfig -v
```
After you finish, run `openssl version` to check if the new version of openssl has been installed successfully.

### 3. A bash script to do the job
&emsp;To make the job easier, here I provide a bash script to do all the job. Make sure the linux system you are using supports `yum` command. Otherwise you need to change the `yum` command in the script.<br/>
&emsp;You could download the script file from here [pythonflaskinstallbashscript](https://my-samplecode.s3.ca-central-1.amazonaws.com/bashscript/pythonflaskinstall.sh)<br/>
&emsp; You could choose to execute the bash script when you launch an EC2 instance. On Step3:Configure Instance Details, at the bottom page choose the file you wanna to execute when you launch EC2 instance.
![]({{ imgpath | append : "img2.png"  }})<br/>
*Note: Even you choose this way, still it will take 10-20 minutes(maybe shorter, maybe longer) to prepare the environment*<br/>
&emsp; You could use
```
openssl version
python3 --version
flask --version
```
to check if python and flask are installed successfully.
