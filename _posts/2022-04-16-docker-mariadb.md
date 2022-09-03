---
title: "Docker, MariaDB, phpMyAdmin"
excerpt: "Install MariaDB and phpMyAdmin using Docker & Portainer"
collection: "posts"
header:
  teaser: /assets/images/docker.jpg
  og_image: /assets/images/docker.jpg
  overlay_image: /assets/images/docker.jpg
  overlay_filter: 0.5 # same as adding an opacity of 0.5 to a black background
categories:
  - Blog
tags:
  - Ghost
# last_modified_at: 2021-09-26T16:20:02-05:00
---

### Install MariaDB and phpMyAdmin using Docker & Portainer

The LAMP stack is probably the most referred to stack for apps in setting up a web server.  Linux, Apache, MySQL, and PHP are the backbone or the basis of the backbone for most web applications out there.  A lot of admins get started installing this basic setup.   With Docker the app is broken up into pieces, a container for MySQL and Container for the app etc...
Most Docker deployments require a database set up in the deployment script.  The problem with this is if you are going to run multiple application containers with multiple databases the initial installers will just set up a new database server each time to the point where you have multiple MySQL servers containers on one machine.   Here we are going to set up one database server (MariaDB) and a GUI management system for the database (phpMyAdmin) they will run on their own internal network.  In future deployment posts, I will adjust the deployment scripts to use this one database server instead of spawning new ones.  For some containers, this is easy for others it's a pain.  
This article assumes you already have a Linux server running the latest version of Docker and Portainer.  Portainer is used to manage Docker containers and gives a good GUI for docker.  There is a tutorial to set up Docker and Portainer combo here.
We will go through several steps to create our MySQL / MariaDB environment.  First we will create a separate network in docker, then install MariaDB followed by phpMyAdmin to give us an interface for managing the databases.
Step 1:  Log into Portainer, Select Networks then select "+ Add network"

![Foo]({{ '/assets/images/posts/ghost_demo.png' | relative_url }})