---
id: 1815
title: 'Project My Screen not working'
date: '2014-04-23T11:50:22+02:00'
author: 'Jeroen Heijster'
layout: post
guid: 'http://www.jeroenheijster.com/?p=1815'
permalink: /project-screen-working/
metabox:
    - 'a:4:{s:14:"metabox_common";a:1:{s:6:"footer";s:1:"1";}s:17:"metabox_pagetitle";a:8:{s:17:"backgroundcontent";s:1:"2";s:15:"backgroundimage";s:0:"";s:15:"backgroundvideo";a:3:{s:4:"webm";s:0:"";s:3:"mp4";s:0:"";s:3:"ogv";s:0:"";}s:15:"backgroundcolor";s:7:"#575656";s:14:"backgroundhtml";s:0:"";s:4:"size";s:5:"small";s:5:"title";s:29:"Project My Screen not working";s:4:"text";s:35:"A quick solution to get it working.";}s:23:"metabox_featuredcontent";a:2:{s:7:"content";s:1:"0";s:4:"html";s:0:"";}s:12:"metabox_blog";a:3:{s:7:"columns";s:1:"3";s:13:"categoriesbox";s:1:"1";s:7:"sidebar";s:4:"blog";}}'
dsq_thread_id:
    - '2632609102'
iawp_total_views:
    - '9'
image: /wp-content/uploads/2014/04/2014-04-23_11h56_23.png
categories:
    - Blogs
tags:
    - 'Screen application'
    - 'Windows Phone'
---

While trying out Project My Screen for Windows Phone 8.1, I had the problem that it only showed a black screen and did not ask my phone to connect. This is due to old drivers. Other sites told me to remove the drivers and just replug it. The solution, however, requires a couple of steps more.

When you have the issue, try these steps:

1. Uninstall the Project My Screen application
2. Go to Device Manager in your Control Panel of Windows
3. Under Portable Devices, right click your phone and click Uninstall.
4. Under Universal Serial Bus Devices, you should have 3 “WinUsb Device”‘s. Right click them one at a time and check the “Delete the driver software for this device” checkbox if possible.
5. Unplug your Windows Phone 8.1 device
6. Reinstall the Project My Screen application
7. After the installation plug your phone in again and start the Project My Screen application. You should now receive a popup to allow screen projection.