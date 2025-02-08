---
id: 11981
title: 'Checking for MSDeploy in Inno Setup'
date: '2016-03-09T14:24:52+02:00'
author: 'Jeroen Heijster'
layout: post
guid: 'https://www.jeroenheijster.nl/?p=11981'
permalink: /checking-for-msdeploy-in-inno-setup/
dsq_thread_id:
    - '4647348417'
image: /wp-content/uploads/2016/03/2016-03-09_13h24_32.png
categories:
    - Blogs
    - Tutorial
tags:
    - inno
    - msdeploy
    - setup
---

At my work, we use Inno Setup to deploy ASP.NET web packages. With PowerShell we set various parameters and call MSDeploy to deploy the package to IIS. A problem we faced recently was that MSDeploy was not installed on the server. We needed to check before running the wizard if MSDeploy was installed.

Since the normal deploy.cmd from Microsoft already has a detection mechanism, I used that as a basis to create the procedure in Pascal. Since I rarely use Pascal, it took a while to get the proper commands.

In deploy.cmd the registry is checked for the install path of MSDeploy. The cmd file takes into account that there can be multiple entries for MSDeploy. In my case I have “C:\\Program Files\\IIS\\Microsoft Web Deploy\\” and “C:\\Program Files\\IIS\\Microsoft Web Deploy V3\\”. When MSDeploy.exe is found in one or both of those folders, the deployer continues.

In Pascal, I wrote the following procedure to do the same:

```
procedure CheckMsDeploy();
var
  Names: TArrayOfString;
  I: Integer;
  installPath: String;
  ErrCode: integer;
  begin
   MSDeployInstalled := False;
  if RegGetSubkeyNames(HKEY_LOCAL_MACHINE, 'SOFTWARE\Microsoft\IIS Extensions\MSDeploy', Names) then
  begin
    for I := 0 to GetArrayLength(Names)-1 do
		begin
			if RegQueryStringValue(HKEY_LOCAL_MACHINE, 'SOFTWARE\Microsoft\IIS Extensions\MSDeploy\' + Names[I], 'InstallPath', installPath) then
			  begin
				if FileOrDirExists(installPath + 'MSDeploy.exe') = True then
				MSDeployInstalled := True;
			end
		end  
	end;
	if MSDeployInstalled <> True then
		if MsgBox('MSDeploy was not found on this machine. This is required for the setup. Would you like to go to knowledgebase article http://go.microsoft.com/?linkid=9278654 ?', mbConfirmation, MB_YESNO) = IDYES
		  then begin
			ShellExec('open', 'http://go.microsoft.com/?linkid=9278654',
			  '', '', SW_SHOW, ewNoWait, ErrCode);
       Abort();
    end;
end;
```

This procedure is called in InitializeWizard through CheckMsDeploy();. If MSDeploy is not found, it will show a message dialog with the question if you want to go to the knowledgebase article. If they click yes, the URL will open in their default browser. No matter what the user selects, the installer will exit due to the Abort(); call.

With this procedure, we can enforce that the user already has MSDeploy installed, which will save us with help requests.