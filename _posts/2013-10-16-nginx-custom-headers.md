---
layout: post
title: "Custom Headers with NGINX"
date: "2013-10-16"
published: true
comments: true
---

Today I learned something new about custom headers, django and nginx.

We have an endpoint in our django app that uses custom headers to validate a request, ala Amazon AWS requests. Basically, the client creates a hash and sets a header with the value. Then on the server side, we validate that the hash is valid and continue on. 

In development, everything was hunky dory. However, once we started testing in our staging environment, the headers were never getting to our django app. The only difference between the environments was the addition of nginx. After much hair pulling and grousing, we came upon this interesting configuration bit [underscores_in_headers](http://wiki.nginx.org/HttpCoreModule#underscores_in_headers). It turns out that nginx will strip any headers it recieves that contain underscores, unless this flag is turned on.

Moral of the story, don't use headers with underscores or turn on the flag in nginx.
