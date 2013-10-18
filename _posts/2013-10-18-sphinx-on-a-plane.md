---
layout: "post"
title: "Sphinx on a Plane"
date: "2013-10-15"
comments: true
published: true
---
I've been traveling over the past few weekends. One of the things that I always try to do before getting on the plane is download the sphinx docs of any projects I might be working with. One thing that I love about the static html sphinx build is that it includes a search feature. However, that search feature only works when running the docs from an http server. If you try and use search when opening the files directly, you will get an error that looks something like this `Origin null is not allowed by Access-Control-Allow-Origin`.

A quick fix is to use the builtin http server that comes from python. It serves local files from whatever directory it is launched in. So go into the html folder of your docs build and run `python -m SimpleHTTPServer 8000`. After that you should be able to see the docs by going to http://127.0.0.1:8000. 

One caveat is that you have to change the port for each set of docs you might want to run at a given time.
