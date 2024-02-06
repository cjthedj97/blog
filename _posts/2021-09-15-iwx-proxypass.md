---
layout: post
title: Revese proxy with apache on Interworx 
tags: IWX Interworx
category: Interworx
---

> Note you will already need to have the domain added to siteworx.
{: .prompt-info }

With the domain in siteworx you can add an apache include directly as the user.

The path that apache looks for files is below
`/home/user/var/domain/apache/*.conf`

So if the account was example and the domain was example.com we would probally want to create the file at `/home/example/var/example.com/apache/proxy.conf`.

Assuming the service listens on port 3000 the configuration would look like the following: 

```
ProxyPass / http://127.0.0.1:3000/
ProxyPassReverse / http://127.0.0.1:3000/
```