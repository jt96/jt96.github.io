---
layout: post
title: HTML Cloud Resume
excerpt: "Resume written in HTML built on cloud services"
categories: [resume, aws]
comments: true
image:
  feature: #
  preview: https://i.postimg.cc/Y9GBt9Gy/image.png
  credit: Jackie Trenh
  creditlink: #
---

I was looking around for AWS projects I could work on to add to my portfolio and I came across the Cloud Resume Challenge created by Forrest Brazeal. A quick summary of the <br />challenge is writing your resume in HTML and building it upon several AWS services such as S3, CloudFront, Route 53, DynamoDB, Lambda and API Gateway as exposure to the cloud was the main goal.

The first step was to write my resume in HTML and CSS. I am not an expert in HTML in anyway, so thankfully I found a nice template created by <a href="https://www.sonjastrieder.com/">Sonja Strider</a> which included CSS styling too. <br />From there, all I needed to do was fill in the resume with my information. 

Next, I got my resume online by deploying as an Amazon S3 static website. I created an S3 bucket with my future website domain name (jackietrenh.com) and uploaded my HTML file <br />to the bucket, updated my bucket policies to allow the static site to be accessed from the web, enabled static website hosting in properties, and I'm almost all set. <br />I still needed to setup my site to use HTTPS for security. 

This was done with CloudFront. Now this part got a bit tricky for me. Following the steps on <a href="https://aws.amazon.com/blogs/networking-and-content-delivery/amazon-s3-amazon-cloudfront-a-match-made-in-the-cloud/">here</a>, I assigned a new CloudFront distribution to my S3 bucket. <br />For some reason, my CloudFront distribution kept redirecting to my S3 bucket's endpoint URL instead of distribution's. Turns out it was <br />just DNS being slow and took a couple hours of waiting for the DNS to propogate and my website to be up and running.

Finally!
<img align="left" src="https://i.postimg.cc/DwFs94J5/image.png">
<br clear="all" />

Now I needed to point a custom DNS domain name to the CloudFront distribution, so my website could be accessed at a normal URL instead of the something <br />like d3k3661kq54jkb.cloudfront.
I used Route53 to register my domain name jackietrenh.com. The domain cost $12 and it's good for a year.

<img align="left" src="https://i.postimg.cc/XY7vRgJx/image.png">
<br clear="all" />

Once registered, I needed to add the alternate domain names to my CloudFront distribution and request an SSL certificate for the domain names through <br />AWS Certificate Manager. This didn't work for me at first because I needed to request the certificate in the us-east-1 region, but I had requested it in the us-west-2 region.. <br />I also needed the S3 bucket name to match the domain name which is why I mentioned creating the bucket in my future domain name earlier.

<img align="left" src="https://i.postimg.cc/k4cXtDXM/image.png">
<br clear="all" />

Once successfully added to my CloudFront distribution, I could now access the site through my custom domain name. <br />I also added a CNAME record to route www.jackietrenh.com to the same site.

Voila!

<img align="left" src="https://i.postimg.cc/Y9GBt9Gy/image.png">
<br clear="all" />

The last thing I needed to do was implement a viewer count at the bottom of my resume. I created <br />a DynamoDB table that used a primary key and some attributes for my visits.

<img align="left" src="https://i.postimg.cc/hGQ2j7sx/image.png">
<br clear="all" />

Needed a way to update the counter so I created a function in Lambda written in Python and connected <br />an API Gateway to the function so it will be triggered whenever the API endpoint is called.

<img align="left" src="https://i.postimg.cc/NM3FcZMm/lambda-api-gateway.png">
<br clear="all" />

Now I just had to call the API whenever the page is loaded and I did that by adding a line of  JavaScript and using it to "fetch" the API.

Finally have some views!

<img align="left" src="https://i.postimg.cc/LsZMp5ZQ/view-count.png">
<br clear="all" />

Overall, this was a great challenge that provided a lot of exposure to cloud services and a bit of programming. I plan on integrating <br />workflows and CI/CD pipelines to this project and will update this post when complete. Huge thanks to Forrest Brazeal for creating this challenge and I'm <br />very excited to continue learning about the cloud and everything it has to offer!

<br clear="all" /><br clear="all" /><br clear="all" />
This resume website was built during the <a href="https://dev.to/forrestbrazeal/the-cloud-resume-challenge-503g">#CloudResumeChallenge</a>
