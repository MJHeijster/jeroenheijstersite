---
id: 1827
title: 'Why I think Firefox SHOULD implement EME'
date: '2014-05-16T12:33:09+02:00'
author: 'Jeroen Heijster'
layout: post
guid: 'http://www.jeroenheijster.com/?p=1827'
permalink: /firefox-implement-eme/
metabox:
    - 'a:4:{s:14:"metabox_common";a:1:{s:6:"footer";s:1:"1";}s:17:"metabox_pagetitle";a:8:{s:17:"backgroundcontent";s:1:"2";s:15:"backgroundimage";s:0:"";s:15:"backgroundvideo";a:3:{s:4:"webm";s:0:"";s:3:"mp4";s:0:"";s:3:"ogv";s:0:"";}s:15:"backgroundcolor";s:7:"#575656";s:14:"backgroundhtml";s:0:"";s:4:"size";s:5:"small";s:5:"title";s:40:"Why I think Firefox SHOULD implement EME";s:4:"text";s:183:"As you might''ve read on the internet before now, Firefox will implement EME(Encrypted Media Extensions). While the internet is in uproar about this, I think they do not have a choice.";}s:23:"metabox_featuredcontent";a:2:{s:7:"content";s:1:"0";s:4:"html";s:0:"";}s:12:"metabox_blog";a:3:{s:7:"columns";s:1:"3";s:13:"categoriesbox";s:1:"1";s:7:"sidebar";s:4:"blog";}}'
dsq_thread_id:
    - '2689693936'
fw_options:
    - 'a:1:{i:0;s:0:"";}'
iawp_total_views:
    - '11'
image: /wp-content/uploads/2014/05/mozilla_firefox_logo-825x380.png
categories:
    - Blogs
tags:
    - Firefox
---

*As you might’ve read on the internet before now, Firefox will implement EME(**Encrypted Media Extensions**). While the internet is in uproar about this, I think they do not have a choice.*

### What is EME

EME is a JavaScript API to play encrypted media. This would mainly include videos. You can think about encrypting Netflix and Youtube video’s. With this, they should be able to protect copyrighted materials. For this, the browser needs an extension to communicate with a license server to get keys to enable decryption of the media.

When talking about Netflix, a usage could be that EME would authenticate you as a user, determine your identity and permissions and decide if you’re able to decrypt the file and play it.

The decryption is done by the Content Decryption Module. This is a client side or hardware module. It receives a license from the License (Key) Server and eventually decrypt and decode it.

### Other browsers

Firefox will not be the first to include EME. Internet Explorer 11, Chrome, Safari, Opera and probably some other browsers have already implemented it. Not everyone liked it, but sadly, they have to.

### Why they need to

While most people don’t want EME, Mozilla can’t just ignore it. When they would, users will eventually not be able to view some media. Other sites may even block Firefox from their sites just to protect themselves. Most users won’t temporarily switch to another browser to view one site. If one browser supports most, excluding a few sites the user wants to visit and the other supports them all, the user will switch.

There are some users who will stick to a browser, I’ve seen that with Opera in earlier versions of the browser. Some sites just blocked Opera by showing them a message that the user cannot view the site with Opera and that they should switch to a “decent” browser like Firefox.

This means, for me, that I’m not mad. I won’t stop using Firefox. Firefox has resisted it as long as they could, but what are the alternatives? Do you protest by switching to another browser? Well, you’re out of luck then. The other mayor browsers have already implemented it before… EME is here and it seems like it’s here to stay.