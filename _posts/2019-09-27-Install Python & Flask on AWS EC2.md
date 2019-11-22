---
layout : post
title : Install Python & Flask on AWS EC2 with Bash Script
categories: [Python/Flask, AWS]
tags: [Python/Flask, AWS EC2, Script]
---
[//]: # defined a way to access images related to the post easier.
{% include post-imagepath.md %}

### 1.Introduction
Hola! Geeks and nerds. In this post I will introduce how to install python3 and
flask on EC2. I know I have written a similar post before
[Run Your First Flask Application on AWS EC2]({% post_url 2019-01-20-Run Your first flask program on AWS EC2 %}).
But when I followed the steps, I met some new problems, like openssl version
is too old for pip that you can't run `pip3` command. I don't have much space
on my computer SSD and I really don't want to install VM on my computer as it's
too heavy. So I used AWS EC2 as an example. It's free(Has one year free program)
and very convenient.

### 2.Outline
1. How to install openssl  
When you install flask with `pip3` command, if you have the problem below, you
need to install a new version of openssl. You could find answer of how to
install openssl in this post.    
>
![]({{ images[0] }})  

2. A bash script you could use to install python3 and flask when you launch an
EC2 instance or after you launch an EC2 instance.

*Note: Remember to run all commands or the bash script with root user*
### 3.How to install openssl
Before you install openssl, use `openssl version` to check if the system has a
default version of openssl. If the system doesn't have a default openssl or the
version is too old, install a newer version of openssl. You could find openssl
release version from [openssl webpage](https://www.openssl.org/source/). Here I
am using the version *1.1.1d*.  
>
```
wget https://www.openssl.org/source/openssl-1.1.1d.tar.gz
tar -zxvf openssl-1.1.1d.tar.gz
cd openssl-1.1.1d
./config
make
make install
```

Back up the old version `openssl` command, if the system doesn't have a default
openssl that had been installed. Skip this step.
>
```
mv /usr/bin/openssl /usr/bin/openssl.bak
```

link to the new `openssl` command, the default installing directory is **/usr/local/bin**
>
```
ln -s /usr/local/bin/openssl /usr/bin/openssl
```

change system configuration  
>
```
echo "/usr/local/lib64" >> /etc/ld.so.conf
ldconfig -v
```

After you finish, run `openssl version` to check if the new version of openssl
has been installed successfully.

### 4. A bash script to do the job
To make the job easier, here I provide a bash script to do the job. Make sure
the linux system you are using supports `yum` command. Otherwise you need to
change the `yum` command in the script.  

You could download the script file from here
[pythonflaskinstallbashscript](https://my-samplecode.s3.ca-central-1.amazonaws.com/bashscript/pythonflaskinstall.sh).  

You could choose to execute the bash script when you launch an EC2 instance. On
Step3: Configure Instance Details, at the bottom of the page choose the file you
want to execute when you launch EC2 instance.  
>
![]({{ images[1]  }})  

*Note: Even you choose this way, it will still take 10-20 minutes(maybe shorter,
maybe longer) to prepare the environment.*  

You could use commands below to check if python and flask are installed successfully.  
>
```
openssl version
python3 --version
flask --version
```
