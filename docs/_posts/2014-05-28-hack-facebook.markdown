---
layout: default
title:  "How I hacked your unverified facebook accounts !"
author: Abhibandu Kafle
date:   2014-05-28 18:29:40 -0500
tags: poc
category: poc
---

Here’s a little write-up on how I was able to delete any unverified account in facebook. By unverified, I mean those accounts who didnot yet verify their email address linked to facebook.
All (or most) of my bugs have been authentication related to many vendors, this was no different.
Here is how I did it:
The sign up function lets you create a new Facebook account but the response was different when the email was verified vs. when the email for the account was unverified. If you use a Facebook account that already has an account in Facebook (with its email unverified), the response you get is :

![Facebook 1]({{ site.baseurl }}/assets/images/hack-facebook-1.jpg)

When clicked on the “Insert the confirmation code instead” it lets you enter 5-digit number only code.


Lets generate a dictionary from 00000 to 99999.

```for i in range(0,99999):
     print '{0:05d}'.format(i)```
 

Now, straightforward stuff! I fired up Burp Suite, “Swiss army knife” for me.

![Facebook 2]({{ site.baseurl }}/assets/images/hack-facebook-2.JPG)

Notice something peculiar in the last request?
Yep, the response length changes to show that you’ve made the correct guess. (AJAX response in burp response says that).

There was no rate limit on the number of requests you could make.

Some math work :
possible password = 100,000
If  number of requests = 100/sec.
Time taken to figure out the code (worst case scenario) = 15 minutes

The impact?
I could permanently delete any unverified Facebook accounts within 15 minutes. You would try to recover using “password recover” feature but all your friends, PM’s would be gone. You would have to create entirely new account.

All I had to do was squander my bandwidth and keep brute forcing (and sit back and relax).

How did I find out if an account was unverified?
Well, one way was to sign up using that email and see the response (if you are asked to enter confirmation code or not).

For a large number of emails, the other way was to enumerate facebook users first, to find out if the email had a facebook account and then use “Change email address field” to sort out which accounts have facebook associated with it and are still unverified.

A fix was deployed after 8 hours of submission.

and after 3 days, a handsome bounty followed up:

![Facebook 3]({{ site.baseurl }}/assets/images/hack-facebook-3.JPG)

