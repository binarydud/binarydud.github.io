---
layout: post
title: "Installing Django"
date: 2012-06-13 10:19
comments: true
categories: python, django
---
I recently had some people ask questions about installing django

install distribute:

    curl -O http://python-distribute.org/distribute_setup.py
    sudo python distribute_setup.py
    (optional) -  you can remove distribute_setup.py

install pip:

    sudo easy_install pip

install virtualenv:

    sudo pip install virtualenv

activate virtualenv:

    mkdir -p ~/envs
    cd ~/envs
    virtualenv --no-site-packages --distribute django-env
    source ~/envs/django-env/bin/activate

install django

    pip install django

create new django project

    cd ~/
    django-admin.py start project newproj
