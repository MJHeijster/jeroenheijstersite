---
id: 245
title: 'CloudFlare &#8211; Boost your site'
date: '2012-06-01T15:57:48+02:00'
author: 'Jeroen Heijster'
layout: post
guid: 'http://www.jeroenheijster.com/?p=245'
permalink: /cloudflare/
al2fb_facebook_image_id:
    - '246'
al2fb_facebook_excerpt:
    - 'CloudFlare protects and accelerates any website online. Once your website is a part of the CloudFlare community, its web traffic is routed through our intelligent global network.'
al2fb_facebook_link_picture:
    - 'meta=http://www.jeroenheijster.com/wp-content/uploads/2012/06/335031-cloudflare-logo-300x171.jpg'
al2fb_facebook_link_id:
    - '621480209_10150971535745210'
al2fb_facebook_link_time:
    - '2012-06-01T17:06:47+00:00'
dsq_thread_id:
    - '710824347'
fw_options:
    - 'a:1:{i:0;s:0:"";}'
iawp_total_views:
    - '8'
image: /wp-content/uploads/2012/06/335031-cloudflare-logo.jpg
categories:
    - Blogs
tags:
    - Cloudflare
    - community
    - computer
    - cookie
    - discussion
    - DNS
    - 'DNS server'
    - Featured
    - 'Google Analytics'
    - 'intelligent global network'
    - site
    - web
    - 'web traffic'
    - website
---

*CloudFlare protects and accelerates any website online. Once your website is a part of the CloudFlare community, its web traffic is routed through our intelligent global network.*

I’ve been using CloudFlare for some time now and I really like it. It is free to use with a paid plan for the more advanced options. I’ll try to explain why I use it.

### Attack-blocker

If you’ve hosted a forum and/or a comments platform you’re probably aware there are spammers and other abusers on the internet. These are annoying and you have to try really hard to stop them from posting and removing the damage.

CloudFlare actually filters out those bots and evil persons as you can see below:

[![](/wp-content/uploads/2012/06/illustration-small.png "illustration-small")](/wp-content/uploads/2012/06/illustration-small.png)

If someone is flagged as an attacker in the CloudFlare system, they have a chance to go through using a CAPTCHA. Since 99% of the attackers are automatic bots, you should be safe.

### Faster

While using CloudFlare, images, javascript and other web resources are cached. Through [CDN](http://en.wikipedia.org/wiki/Content_delivery_network) the content is delivered faster AND you save resources on your server. As a server owner, this is a win-win situation.

[![](/wp-content/uploads/2012/06/2012-06-01_15h41_04.png "2012-06-01_15h41_04")](/wp-content/uploads/2012/06/2012-06-01_15h41_04.png)

### Analytics

Build into CloudFlare are also Analytics, they are pretty basic but it shows you what you need to know. If you want more statistics, use Google Analytics.

[![](/wp-content/uploads/2012/06/analytics-traffic.png "analytics-traffic")](/wp-content/uploads/2012/06/analytics-traffic.png) [![](/wp-content/uploads/2012/06/analytics-threats.png "analytics-threats")](/wp-content/uploads/2012/06/analytics-threats.png)

### Implementation

Implementing CloudFlare is easy, you sign up on <http://www.cloudflare.com>, it scans your site for all the DNS records and you transfer your DNS server for your domain name to the assigned DNS servers of CloudFlare. That’s it, it just takes a couple of minutes and your site is safer.