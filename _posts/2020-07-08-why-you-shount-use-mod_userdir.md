---
layout: post
tags: Apache Mod_userdir 
title:  "Why you shouldn't use mod_userdir"
pin: true
---

I commonly see people use or want to use _IP/~/username_ on shared servers.

I wouldn't recommend this is because you now created additional work that will be required to make the site live.

* As if you use a CMS you now will have to either blindly change all the instances of the URL in the database or you will be changing then one by one till you are blue in the face.
* Then you can't forget the .htaccess and any other site files that may have hardcoded URLs.
* Finally you could have some issues where the site acts unexceptionally 


Instead, the way we could have avoided these extra steps is by using creating the domain as if it is live then, making an edit to your host file on your computer.

Note: This isn't a guide on how to make a host file edit. If you don't know where to start the following search query should get you started.
https://duckduckgo.com/?q=how+to+make+a+host+file+edit
