---
layout: post
title: Hello World Web Application
excerpt: "Simple hello world web app"
categories: [hello world]
comments: true
image:
  feature: #
  preview: https://i.postimg.cc/L4qgT4fc/image.png
  credit: Jackie Trenh
  creditlink: #
---
Simple hello world web app

I like to keep it simple and start off with the very basics when learning something new.

Navigate to ec2 service on aws console and launch an instance with the configurations you want.

<img align="left" src="https://i.postimg.cc/L4qgT4fc/image.png">
<br clear="all" />

Use user data to quickly setup an apache web application when launching the instance. You can find this bootstrap script with a quick google search. Read more about this [here](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/user-data.html).



<img align="left" src="https://i.postimg.cc/vHgmJc3x/image.png">
<br clear="all" />

You can create your own security group to be more secure or use the default one that allows all traffic.



<img align="left" src="https://i.postimg.cc/MKVcCs9t/image.png">
<br clear="all" />

After launching, the Hello World! web app should be all set!





<img align="left" src="https://i.postimg.cc/90TMjMYz/image.png">
<br clear="all" />


You can ssh into your instance and verify that the index.html file was created and contains the html code you wrote to it using the 
```cat index.html``` command.


