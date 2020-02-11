---
layout: post
title: Hello World Web Application
excerpt: "Simple hello world web app"
categories: [hello world]
comments: true
image:
  feature: https://i.postimg.cc/L4qgT4fc/image.png
  credit: jackie trenh
  creditlink: #
---
Simple hello world web app

I like to keep it simple and start off with the very basics when learning something new.

Navigate to ec2 service on aws console and launch an instance with the configurations you want.

![image.png](https://i.postimg.cc/L4qgT4fc/image.png)

Use user data to quickly setup an apache web application when launching the instance. You can find this bootstrap script with a quick google search. Read more about this [here](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/user-data.html).



![image.png](https://i.postimg.cc/pTFcQbBK/image.png)

You can create your own security group to be more secure or use the default one that allows all traffic.



![image.png](https://i.postimg.cc/MKVcCs9t/image.png)

After launching, the Hello World! web app should be all set!



![image.png](https://i.postimg.cc/90TMjMYz/image.png)


You can ssh into your instance and verify that the index.html file was created and contains the html code you wrote to it using the 
```cat index.html``` command.

