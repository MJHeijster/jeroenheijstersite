---
id: 1062
title: 'Cordova/PhoneGap NO TRANSPORT/NetworkError with Ajax in Windows Phone.'
date: '2013-05-08T16:00:49+02:00'
author: 'Jeroen Heijster'
layout: post
guid: 'http://www.jeroenheijster.com/?p=1062'
permalink: /cordova-no-transport-ajax-windows-phone/
al2fb_facebook_excerpt:
    - 'When developing for multiple platforms, a framework might be nice. One of those frameworks is Cordova a.k.a. PhoneGap. When using jQuery Mobile, I stumbled upon the problem that I couldn''t do an ajax request to an API in Windows Phone. The same code did work for Android. After searching for a while, I found out that this problem is known and that it will not be fixed. There is, however, a workaround.'
video_post_embed:
    - ''
link_post_caption:
    - ''
link_post_url:
    - ''
al2fb_facebook_image_id:
    - '1202'
al2fb_facebook_link_id:
    - '621480209_10151585344600210'
al2fb_facebook_link_time:
    - '2013-05-08T14:00:58+00:00'
al2fb_facebook_link_picture:
    - 'meta=http://www.jeroenheijster.com/wp-content/uploads/2013/05/jqm-300x128.png'
dsq_thread_id:
    - '1272394409'
metabox:
    - 'a:4:{s:14:"metabox_common";a:1:{s:6:"footer";s:1:"1";}s:17:"metabox_pagetitle";a:8:{s:17:"backgroundcontent";s:1:"2";s:15:"backgroundimage";s:0:"";s:15:"backgroundvideo";a:3:{s:4:"webm";s:0:"";s:3:"mp4";s:0:"";s:3:"ogv";s:0:"";}s:15:"backgroundcolor";s:7:"#575656";s:14:"backgroundhtml";s:0:"";s:4:"size";s:5:"small";s:5:"title";s:26:"NO TRANSPORT/NetworkError ";s:4:"text";s:27:"With Ajax in Windows Phone.";}s:23:"metabox_featuredcontent";a:2:{s:7:"content";s:1:"0";s:4:"html";s:0:"";}s:12:"metabox_blog";a:3:{s:7:"columns";s:1:"3";s:13:"categoriesbox";s:1:"1";s:7:"sidebar";s:4:"blog";}}'
iawp_total_views:
    - '8'
image: /wp-content/uploads/2013/05/jqm1-750x510.png
categories:
    - Blogs
tags:
    - Ajax
    - 'jQuery Mobile'
    - 'Windows Phone'
---

*When developing for multiple platforms, a framework might be nice. One of those frameworks is Cordova a.k.a. PhoneGap. When using jQuery Mobile, I stumbled upon the problem that I couldn’t do an ajax request to an API in Windows Phone. The same code did work for Android. After searching for a while, I found out that this problem is known and that it will not be fixed. There is, however, a workaround.*

# What’s happening

In Windows Phone cross-domain ajax calls are blocked.

# How to solve

The bug was reported back in 2011 for jQuery. They decided not to fix it for jQuery Mobile. Instead they suggested to use **$.support.cors = true;**.

This does solve the problem for the calls.

# Example code

<div class="wp-block-kevinbatdorf-code-block-pro cbp-has-line-numbers" data-code-block-pro-font-family="Code-Pro-JetBrains-Mono" style="font-size:.875rem;font-family:Code-Pro-JetBrains-Mono,ui-monospace,SFMono-Regular,Menlo,Monaco,Consolas,monospace;--cbp-line-number-color:#adbac7;--cbp-line-number-width:calc(2 * 0.6 * .875rem);line-height:1.25rem;--cbp-tab-width:2;tab-size:var(--cbp-tab-width, 2)"><span style="display:flex;align-items:center;padding:16px 0 0 16px;width:100%;text-align:left;background-color:#22272e"><span style="background:#9eadbd;padding:0.3rem 0.5rem 0.2rem;border-radius:1rem;font-size:0.8em;line-height:1;height:1.25rem;text-align:center;display:inline-flex;align-items:center;justify-content:center;color:#22272e">JavaScript</span></span><span aria-label="Copy" class="code-block-pro-copy-button" data-code="$.support.cors = true;

$.ajax("http://localhost:8081/api.html", {
async: false,
contentType: "text/xml",
data: body,
type: "POST",
success: function (data, textStatus, jqXHR) {
//Handle the api call
},
error: function (jqXHR, textStatus, errorThrown) {
//Handle the error
}
});" role="button" style="color:#adbac7;display:none" tabindex="0"><svg fill="none" stroke="currentColor" stroke-width="2" style="width:24px;height:24px" viewbox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path class="with-check" d="M9 5H7a2 2 0 00-2 2v12a2 2 0 002 2h10a2 2 0 002-2V7a2 2 0 00-2-2h-2M9 5a2 2 0 002 2h2a2 2 0 002-2M9 5a2 2 0 012-2h2a2 2 0 012 2m-6 9l2 2 4-4" stroke-linecap="round" stroke-linejoin="round"></path><path class="without-check" d="M9 5H7a2 2 0 00-2 2v12a2 2 0 002 2h10a2 2 0 002-2V7a2 2 0 00-2-2h-2M9 5a2 2 0 002 2h2a2 2 0 002-2M9 5a2 2 0 012-2h2a2 2 0 012 2" stroke-linecap="round" stroke-linejoin="round"></path></svg></span>```
<span class="line"><span style="color: #ADBAC7">$.support.cors </span><span style="color: #F47067">=</span><span style="color: #ADBAC7"> </span><span style="color: #6CB6FF">true</span><span style="color: #ADBAC7">;</span></span>
<span class="line"></span>
<span class="line"><span style="color: #ADBAC7">$.</span><span style="color: #DCBDFB">ajax</span><span style="color: #ADBAC7">(</span><span style="color: #96D0FF">"http://localhost:8081/api.html"</span><span style="color: #ADBAC7">, {</span></span>
<span class="line"><span style="color: #ADBAC7">async: </span><span style="color: #6CB6FF">false</span><span style="color: #ADBAC7">,</span></span>
<span class="line"><span style="color: #ADBAC7">contentType: </span><span style="color: #96D0FF">"text/xml"</span><span style="color: #ADBAC7">,</span></span>
<span class="line"><span style="color: #ADBAC7">data: body,</span></span>
<span class="line"><span style="color: #ADBAC7">type: </span><span style="color: #96D0FF">"POST"</span><span style="color: #ADBAC7">,</span></span>
<span class="line"><span style="color: #DCBDFB">success</span><span style="color: #ADBAC7">: </span><span style="color: #F47067">function</span><span style="color: #ADBAC7"> (</span><span style="color: #F69D50">data</span><span style="color: #ADBAC7">, </span><span style="color: #F69D50">textStatus</span><span style="color: #ADBAC7">, </span><span style="color: #F69D50">jqXHR</span><span style="color: #ADBAC7">) {</span></span>
<span class="line"><span style="color: #768390">//Handle the api call</span></span>
<span class="line"><span style="color: #ADBAC7">},</span></span>
<span class="line"><span style="color: #DCBDFB">error</span><span style="color: #ADBAC7">: </span><span style="color: #F47067">function</span><span style="color: #ADBAC7"> (</span><span style="color: #F69D50">jqXHR</span><span style="color: #ADBAC7">, </span><span style="color: #F69D50">textStatus</span><span style="color: #ADBAC7">, </span><span style="color: #F69D50">errorThrown</span><span style="color: #ADBAC7">) {</span></span>
<span class="line"><span style="color: #768390">//Handle the error</span></span>
<span class="line"><span style="color: #ADBAC7">}</span></span>
<span class="line"><span style="color: #ADBAC7">});</span></span>
```

</div>