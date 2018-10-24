---
layout: post
title:  "5 Free Ways to improve your static site"
date:   2018-10-17 09:28:44 -0400
categories: tech
header: webdev.jpeg
header_title: Image free courtesy of pexels.com
header_alt: Web development
---
Static sites are becoming much more common now and are quite simple to make, particularly with the help of a static site generator like Jekyll. They are also cheaper to host (this site is hosted for free with Github pages), easier to keep secure, and faster than most of the more commonly used tools like Wordpress.

However, they usually lack a lot of features that people would expect out of the box. Since they are static and do not have a database or a backend scripting language adding features like comment systems or forms is not as straight forward as it is on Wordpress or other systems.

However, using external services it is possible to add these features simply by signing up for them and putting a script tag in your code. Do be warned that you are giving control of your data to these third party services though and their servers will store your user's data not yours. All the following services are free or atleast have a free plan available to help you get started and determine if the service is right for you. 

### 1. Disqus
<strong>Disqus</strong> is heavily used for comment systems and is becoming more and more prevalent on the web now a days. It is probably one of the first systems I would suggest you setup once you make a static website. It also has very good spam protection, so gone will be the days of having to go through and remove hundreds of spam comments from your site.  While their free plan is ad supported, if your site is a personal blog or is non-commercial you are able to get an ad free experience on your site for free.

For more information on their pricing you can go <a href="https://disqus.com/pricing/" target="_blank">here</a>.

### 2. Google Analytics
<strong>Google Analytics</strong> is used by many organizations to get detailed information on how many people are visiting their sites. It can be useful for tracking many things including the bounce rate of your site, what sites your visitors came from and how long they stayed to name a few.

<div style="width: 100%;">
    <img style="width: 100%;" src="/assets/googleanalytics.jpg" title="An example screenshot of a Google Analytics dashboard" alt="">
    <strong>An example screenshot of a Google Analytics dashboard</strong>
</div>

Setting up Google Analytics is quite easy if you already have a Google account. Simply add your website as a property and then put the code snippet you are given on your site.

### 3. Formspree
<strong>Formspree</strong> is a free service that lets you embed contact forms on your static site. They offer the backend and will send the email for you. This is a better alternative to using Google Forms because your users do not have to leave your site. Their free plan includes 50 submissions per form per month. If you want more you have to upgrade to Gold which costs $12/month. For more information visit <https://formspree.io/>

### 4. Mailchimp
MailChimp lets you setup email lists for your site. This is particularly useful if you run a blog or site in which you frequently release new content and want people to be able to subscribe.

MailChimp offers code snippets that you can configure to collect emails in forms. They offer a wide range of form styles; including popovers, forms that appear at the bottom (much less obtrusive) and embedded forms.

MailChimp's free plan allows you to build an email list of 2000 subscribers and send 12,000 emails/month. 

### 5. Email Obfuscation
Email obfuscation is important. Many bots scour websites looking for exposed email addresses to sell. If you list email addresses on your site or just have a contact address you should definitely obfuscate the emails. A simple way to do this is replace it with a script that will only display the email when javascript runs. The script shouldn't have the full email as a string literal in it though, because it could be easily extracted then. This [https://www.albionresearch.com/misc/obfuscator.php](site) will generate the javascript code for an email link. 

This should protect the address from a fair amount of bots. However, no method is foolproof so I recommend keeping up with what is going on and looking into new ways as they come out. Unfortunately it is a constant race, but even an older method can protect the addresses from some spam.
