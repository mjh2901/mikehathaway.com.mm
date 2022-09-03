---
title: "Who Ghost on Github pages"
excerpt: "Ghost can be a simple way to setup a self hosted blog"
collection: "posts"
header:
  teaser: /assets/images/ghost.png
  og_image: /assets/images/ghost.png
  overlay_image: /assets/images/ghost.png
  overlay_filter: 0.5 # same as adding an opacity of 0.5 to a black background
categories:
  - Blog
tags:
  - Ghost
last_modified_at: 2021-09-26T16:20:02-05:00
---

The process of bringing this website online involved a lot of trial and error.  Part of was caused by the normal issues one runs into when self hosting and the rest where a large number of instructions, and scripts designed for older or different operating systems and older versions of node, npm and python refusing to work as documented.    

I started this project with a goal, use GitHub pages to host my ghost site.  Github's webpage hosting is done through https://pages.github.io.  GitHub Pages serves up static content from a GitHub project.  GitHub uses Jekyll a static site generator to create pages, but you are not required to build pages in Jekyll.  After building some sites in Jekyl over the years I have decided its just not for me.  I like my wysiwyg page creation programs, and I want more theme options that do not involve building css from scratch or even a template starting point.  

In comes Ghost a full featured CMS with a lot of fancy features.  Ghost has one very nice trick, it is very simple to get started with.  That learning curve is perfect for someone like me who hales from the land of Drupal, a system that is amazingly difficult to publish a simple webpage.

Ghost turns out to be a much better fit for my workflow.  Building a site in ghost alllows me to create web pages and blog entries visually without needing to write markdown, then render and see what it looks like.  Ghost creates good looking websites with very little design needed, or can be completely customized for an exact look and feel.  How far you want to go with customization is completely up to you, there's no right or wrong approach! The majority of people use one of Ghost's built-in themes to get started, and then progress to something more bespoke later on as their site grows.  

![Foo]({{ '/assets/images/posts/ghost_demo.png' | relative_url }})

My ghost site is self hosted on a rocky linux server running (many rocky linux how to's are in my future) on my home proxmox server.  The issue I ran into is there are a number of web pages and GitHub projects out there dedicated to the process of creating a ghost site, rendering a static version and uploading that version to github pages.  Every one of the projectors and or tutorials has issues.  There is some abandonware, instructions from 2013 and a myriad of other opinings on the process that are just out of date.  I was finally able to cobble together a working process that can be easily (sort of) replicated by others.  

The process uses the ghost command shell to build this site, then get the Ghost Static Site Generator to generate a static version in a folder, and finally Git / GitHub to push the entire mess to a repository.  Github Pages does the rest of the publishing.  I burned through 3 separate scripts and full server installs in variouse processes that in the end did not work for me.  Finally I built my own script to generate the static site and upload it to git hub.  I am hooking this script up with cron to run every 6 hours.  I do not post that often and with this setup I can create a new post remotely and it will eventually get posted to github.  I tend to post on a weekly basis, 6 hours is just not going to hurt, and running that script to publish every hour or even more often is a waste of computing resources and power.  Trust me here in Northern California the cost of power is a big issue.

With so much generously provided by other for me to use and get to this point, I have posted my script, and full instructions on the process on GitHub.

Enjoy the script!

[https://github.com/mjh2901/ghost-on-github](https://github.com/mjh2901/ghost-on-github)