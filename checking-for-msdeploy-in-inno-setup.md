---
id: 11979
title: 'Checking for MSDeploy in Inno Setup'
date: '2016-03-09T14:19:42+02:00'
author: 'Jeroen Heijster'
layout: page
guid: 'https://www.jeroenheijster.nl/?page_id=11979'
iawp_total_views:
    - '11'
---

At my work, we use Inno Setup to deploy ASP.NET web packages. With PowerShell we set various parameters and call MSDeploy to deploy the package to IIS. A problem we faced recently was that MSDeploy was not installed on the server. We needed to check before running the wizard if MSDeploy was installed.

Since the normal deploy.cmd from Microsoft already has a detection mechanism, I used that as a basis to create the procedure in Pascal. Since I rarely use Pascal, it took a while to get the proper commands.

In deploy.cmd the registry is checked for the install path of MSDeploy. The cmd file takes into account that there can be multiple entries for MSDeploy. In my case I have “C:\\Program Files\\IIS\\Microsoft Web Deploy\\” and “C:\\Program Files\\IIS\\Microsoft Web Deploy V3\\”. When MSDeploy.exe is found in one or both of those folders, the deployer continues.

In Pascal, I wrote the following procedure to do the same:

This procedure is called in InitializeWizard through CheckMsDeploy();. If MSDeploy is not found, it will show a message dialog with the question if you want to go to the knowledgebase article. If they click yes, the URL will open in their default browser. No matter what the user selects, the installer will exit due to the Abort(); call.

With this procedure, we can enforce that the user already has MSDeploy installed, which will save us with help requests.