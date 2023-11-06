---
title : "WSL ubuntu auto start on windows boot"
#excerpt : ""

categories:
   - Blog
tags:
   - Blog
---



- make vbs script on start program


```
C:\Users\YOURUSERNAME\AppData\Roaming\Microsoft\Windows\Start Menu\Programs\Startup
```

- make simple vbs file 


```
set ws=CreateObject("Wscript.shell")
ws.run "wsl -d Ubuntu-18.04", 0
```

- reboot and check command 


```
wsl -l -v
```
