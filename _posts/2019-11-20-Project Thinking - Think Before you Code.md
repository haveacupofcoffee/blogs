---
layout : post
title : Project Thinking - Think Before You Code
categories: [Python, AWS]
tags: [Python/Flask, AWS]
---
[//]: # defined a way to access images related to the post easier.
{% include post-imagepath.md %}

[1]:https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_ConnectToInstance.html
[2]:https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_ConnectToPostgreSQLInstance.html

### 1.Introduction
Hola! geeks and nerds. In this post I will talk about 2 projects that I am
thinking to do recently. I like the new Planet of the Apes series movie. I still
remember the scene when Caesar told his son: **"Think before you act, son"** in
the second movie **Dawn of the Planet of the Apes**.  
>
![]({{ images[0] }})

In the programming world, the reference changes to "Think before you code". And
if you google it, you will find many posts to explain this principle. I won't
talk about it in this post, it goes beyond my brain.  

This post is about thinking 2 projects and see how far I could go. In the other
words, this is a challenge for myself.
- Each Project may integrate some of the skills I know, like python(Flask and
  Django framework, extension packages like numpy, pandas and matplotlib),
  JavaScript, SQL/NoSQL, AWS(API Gateway, Lambda, EC2 etc.)
- Each Project may have several stages, from one stage to another stage, I want
  to try to explain why using cloud services is convenient if there is a chance,
  what features of a programming language I can use to make the code more clear
  and how to solve the problems I met. So at beginning, the project maybe very simple.
- During this process, I also want to train my brain to get better understanding
  about these skills.

### 2.Project 1 - A simple python SQL/NoSQL client
When I use AWS RDS for study purpose, I need to download related client software
to connect to the database like AWS suggested.

[Connecting to a DB Instance Running the MySQL Database Engine][1]{:target="\_blank"}    
[Connecting to a DB Instance Running the PostgreSQL Database Engine][2]{:target="\_blank"}  

For one reason I would like to keep my compute lean. For another reason, it is a
good practice to integrate with AWS services. In my thought, this simple SQL/NoSQL
client will only support for several key SQL/NoSQL commands. This project may
include below stages:
1. Stage 1: only supports for several MySQL key commands, run with CLI (Command Line Interface),
   only use Python with AWS MySQL.
2. Stage 2: supports for AWS PostgreSQL, Amazon DynamoDB, may involve code refactoring.
3. Stage 3: integrate with  Amazon API Gateway, AWS Lambda, JavaScript, HTML, make
   an online SQL/NoSQL client.
4. Stage 4: No clue so far.

### 3.Project 2 - A project with no name so far
I am not sure if I should call this a project or a solution. I want to put
python plots or excel plots in the blog when I write some posts related to Data Science.
But I also want to include some AWS cloud services in this solution. So the requirements
are not very clear now, it's just a blur idea. But I think I could go somewhere with this idea.  

Let's see what will happen!
