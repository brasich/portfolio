---
title: "Welcome"
date: 2021-11-27T10:41:59-05:00
draft: false
categories: ["welcome"]
tags: ["meta"]
---

Testing out the workflow for blogging with Hugo. It's a goal of mine to start writing more and documenting my projects. It's been a real pain trying to find a way to cheaply host a site on my own domain that gives me enough customization to be fun. It seems like this combination of Hugo + Github Pages will be useful, but I'll have to give it some time. 

Currently the process is set up as follows:
+ New posts written in markdown locally
+ Once I'm happy with the content, turn off draft mode and push content to private source repository on GitHub
+ GitHub Actions build pipeline runs to build static site and deploy new `/public` folder to GitHub pages

This was my first time working with automated build pipelines. It really wasn't too terrible to set up (beyond the initial head-scratching around setting up authentication between distinct repositories), and is some helpful hands-on context. As with a lot of these personal projects, digging into the platform world, even at a very shallow depth, really helps with understanding engineering perspectives at work.