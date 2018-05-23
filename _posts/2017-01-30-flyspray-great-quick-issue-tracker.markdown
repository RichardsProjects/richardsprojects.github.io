---
layout: post
title:  "FlySpray: A great quick Issue Tracker"
date:   2017-01-30 21:28:44 -0400
categories: tech
---
So I wanted to write an article about an issue tracker I have been using called FlySpray. When I created UltimateBackpacks I wanted people to easily be able to post suggestions and bugs in a single place without having to create an account. FlySpray is awesome for this, it is a simple PHP application that is easy to setup and allows for the posting of issues and bugs anonymously. It also has a really easy to use templating system, so I was able to add a Project Wonderful ad spot on the page. You can also configure it to only have one project on it (but it can keep track of more than one project) and make those issues on the front page. This just gives a simpler experience for people looking to use it to track only one project.

However, there is one big problem people should be aware of before they use it. <em>It doesn't have a CAPTCHA system!</em>

<strong>No CAPTCHA system?</strong><br />
That's right there is no CAPTCHA system and if you want anyone to be able to post an issue without an account this is a big issue. I remember trying to load the UltimateBackpacks tracker after not looking at it for a few months and the request eventually just timed out. I decided to check the database and to my surprise there was over 50,000 issues in the database. All of them had links in them and looked like they had been posted SEO bots. After I cleaned out the database within a day there were over a 100 more and I realized I had to find a real solution to this.

<strong>Solution</strong><br />
So the solution here is to implement reCAPTCHA. Google's reCAPTCHA is extremely easy to signup for and implement into your FlySpray site. Once you signup for it they will give you some code to add to the front-end of the site that will display the CAPTCHA. 

<strong>Integrating reCAPTCHA into FlySpray (Frontend)</strong><br />
Add the script tag to the <em>header.tpl</em> file and the div to <em>newtask.tpl</em>. Make sure you modify the template files within your theme. The default theme is CleanFS so by default the path is themes/CleanFS/templates. Now you need to implement the backend.

<strong>Integrating reCAPTCHA into FlySpray (Backend)</strong><br />
I wrote a very simple PHP <a href="https://gist.github.com/RichardB122/219439a2c7bdca63557f27ffb87ae03e">code snippet</a> that checks with reCAPTCHA a while back. I recommend you use this if you are new to PHP or want to save time. Now you are going to need to put that check in the "includes/modify.inc.php" file underneath case "'newtask.newtask':". And rather than wrap all the code to add a task in an if statement I simply added a check if the CAPTCHA was incorrect that gave them an error message and kicked them. <blockquote>if(!$captchaSuccess) {
            Flyspray::show_error('Incorrect CAPTCHA.');
            break;
        }</blockquote>
Unfortunately the blockquote messes up the formatting, but hopefully you get the idea.

<strong>Conclusion</strong><br />
Hopefully this helped you protect your issue tracker against spam, if you have questions feel free to leave a comment.

<strong>Links</strong><br />
<a href="https://bugs.flyspray.org/index.php?do=details&task_id=2105">Issue about this on FlySpray</a><br />
<a href="https://gist.github.com/RichardB122/219439a2c7bdca63557f27ffb87ae03e">My reCAPTCHA PHP code snippet</a><br />
 
