---
layout: post
tags: ChromeOS ProtonVPN VPN
title:  "Using ProtonVPN on ChromeOS"
pin: true
---

So you looking to be able to use your protron vpn subscription on your chromebook.

Well you won't be able to just import one of the .ovpn files as there is now way to directly.

1. You will need to convert the files first to an onc file. The easiest way I have found to convert the files is to use https://github.com/thomkeh/ovpn2onc.

	Note if you want you can download the ovpn2onc.html localy if you prefer.

2. Now that you have an onc file you can import it by going to chrome://net-internals.

3. Then click on import onc.

4. From there you will have to add you openvpn creds before you connect for the first time.
