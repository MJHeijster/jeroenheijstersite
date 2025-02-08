---
id: 12090
title: 'Logging hit line number and method'
date: '2019-06-20T11:15:20+02:00'
author: 'Jeroen Heijster'
layout: post
guid: 'http://www.jeroenheijster.nl/?p=12090'
permalink: /logging-hit-line-number-and-method/
iawp_total_views:
    - '18'
image: /wp-content/uploads/2019/06/artificial-intelligence-blur-close-up-546819.jpg
categories:
    - Tutorial
tags:
    - hit
    - line
    - logging
    - method
    - number
---

During debugging I had issues figuring out where my code just stopped. Since I had no debugging methods on that server, I wanted to create a better way of logging than int count=0;Console.WriteLine(count++);

While looking for a way of logging the line number I found the [CompilerServices ](https://docs.microsoft.com/en-us/dotnet/api/system.runtime.compilerservices?view=netframework-4.8)namespace which has a [CallerLineNumber](https://docs.microsoft.com/en-us/dotnet/api/system.runtime.compilerservices.callerlinenumberattribute?view=netframework-4.8) and [CallerMemberName](https://docs.microsoft.com/en-us/dotnet/api/system.runtime.compilerservices.callermembernameattribute?view=netframework-4.8).

Using that, I made this small method to log the method and line number:

<div class="wp-block-kevinbatdorf-code-block-pro cbp-has-line-numbers" data-code-block-pro-font-family="Code-Pro-JetBrains-Mono" style="font-size:.875rem;font-family:Code-Pro-JetBrains-Mono,ui-monospace,SFMono-Regular,Menlo,Monaco,Consolas,monospace;--cbp-line-number-color:#adbac7;--cbp-line-number-width:calc(1 * 0.6 * .875rem);line-height:1.25rem;--cbp-tab-width:2;tab-size:var(--cbp-tab-width, 2)"><span style="display:flex;align-items:center;padding:16px 0 0 16px;width:100%;text-align:left;background-color:#22272e"><span style="background:#9eadbd;padding:0.3rem 0.5rem 0.2rem;border-radius:1rem;font-size:0.8em;line-height:1;height:1.25rem;text-align:center;display:inline-flex;align-items:center;justify-content:center;color:#22272e">C#</span></span><span aria-label="Copy" class="code-block-pro-copy-button" data-code="private void LogLineNumber([System.Runtime.CompilerServices.CallerLineNumber] int lineNumber = 0, [System.Runtime.CompilerServices.CallerMemberName] string caller = null)
{
Console.WriteLine($"Hit line number {lineNumber} for {caller}.");
}" role="button" style="color:#adbac7;display:none" tabindex="0"><svg fill="none" stroke="currentColor" stroke-width="2" style="width:24px;height:24px" viewbox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path class="with-check" d="M9 5H7a2 2 0 00-2 2v12a2 2 0 002 2h10a2 2 0 002-2V7a2 2 0 00-2-2h-2M9 5a2 2 0 002 2h2a2 2 0 002-2M9 5a2 2 0 012-2h2a2 2 0 012 2m-6 9l2 2 4-4" stroke-linecap="round" stroke-linejoin="round"></path><path class="without-check" d="M9 5H7a2 2 0 00-2 2v12a2 2 0 002 2h10a2 2 0 002-2V7a2 2 0 00-2-2h-2M9 5a2 2 0 002 2h2a2 2 0 002-2M9 5a2 2 0 012-2h2a2 2 0 012 2" stroke-linecap="round" stroke-linejoin="round"></path></svg></span>```
<span class="line"><span style="color: #F47067">private</span><span style="color: #ADBAC7"> </span><span style="color: #F47067">void</span><span style="color: #ADBAC7"> </span><span style="color: #DCBDFB">LogLineNumber</span><span style="color: #ADBAC7">([</span><span style="color: #F69D50">System</span><span style="color: #ADBAC7">.</span><span style="color: #F69D50">Runtime</span><span style="color: #ADBAC7">.</span><span style="color: #F69D50">CompilerServices</span><span style="color: #ADBAC7">.</span><span style="color: #F69D50">CallerLineNumber</span><span style="color: #ADBAC7">] </span><span style="color: #F47067">int</span><span style="color: #ADBAC7"> </span><span style="color: #F69D50">lineNumber</span><span style="color: #ADBAC7"> </span><span style="color: #F47067">=</span><span style="color: #ADBAC7"> </span><span style="color: #6CB6FF">0</span><span style="color: #ADBAC7">, [</span><span style="color: #F69D50">System</span><span style="color: #ADBAC7">.</span><span style="color: #F69D50">Runtime</span><span style="color: #ADBAC7">.</span><span style="color: #F69D50">CompilerServices</span><span style="color: #ADBAC7">.</span><span style="color: #F69D50">CallerMemberName</span><span style="color: #ADBAC7">] </span><span style="color: #F47067">string</span><span style="color: #ADBAC7"> </span><span style="color: #F69D50">caller</span><span style="color: #ADBAC7"> </span><span style="color: #F47067">=</span><span style="color: #ADBAC7"> </span><span style="color: #6CB6FF">null</span><span style="color: #ADBAC7">)</span></span>
<span class="line"><span style="color: #ADBAC7">{</span></span>
<span class="line"><span style="color: #ADBAC7">Console.</span><span style="color: #DCBDFB">WriteLine</span><span style="color: #ADBAC7">(</span><span style="color: #96D0FF">$"Hit line number {</span><span style="color: #ADBAC7">lineNumber</span><span style="color: #96D0FF">} for {</span><span style="color: #ADBAC7">caller</span><span style="color: #96D0FF">}."</span><span style="color: #ADBAC7">);</span></span>
<span class="line"><span style="color: #ADBAC7">}</span></span>
```

</div>