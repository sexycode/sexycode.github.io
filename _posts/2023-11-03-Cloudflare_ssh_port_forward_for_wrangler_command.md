---
title : "Cloudflare ssh port forward for wrangler command"
#excerpt : ""

categories:
   - Blog
tags:
   - Blog
---


- my development : Windows PC , Linux PC

	1. when i execute wrangler login in Linux PC through putty 


```
 ⛅️ wrangler 3.15.0
 -------------------
 Attempting to login via OAuth...
 Opening a link in your default browser: https://dash.cloudflare.com/oauth2/auth?response_type=code&client_id=aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa&redirect_uri=http%3A%2F%2Flocalhost%3A8976%2Foauth%2Fcallback&scope=account%3Aread%20user%3Aread%20workers%3Awrite%20workers_kv%3Awrite%20workers_routes%3Awrite%20workers_scripts%3Awrite%20workers_tail%3Aread%20d1%3Awrite%20pages%3Awrite%20zone%3Aread%20ssl_certs%3Awrite%20constellation%3Awrite%20ai%3Aread%20offline_access&state=ZEML51TpIXjf-SgpfGQAu7VEMp93EI1~&code_challenge=KFit0wGCzlFfyW0KPlfIPDkLcL8CSqdPY-sjA-64vag&code_challenge_method=S256
```

	2. i clicked above link in my Windows PC
	3. select "Allow" in chrome 
	4. but login failed

- you should port forward in putty

![putty_ssh_port_forward](/assets/images/putty_ssh_port_foward.png)

- andthen you can successfully logged in in Linux PC
