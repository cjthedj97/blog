---
layout: post
title: "One liner to bulk add ipv6 addresses from a range"
tags: ipv6 cpanel
---

{% include warning.html content="This guide is is not complete on setting up ipv6 on cpanel rather this is one part of it." %}

Cpanel can be bit of a pain if you want to assign a site a specific Ip from a range of Ipv6 addresses.

As you can't actually do this if you just add the one big range.

Instead it is best to add addresses as individual /128 but who has time to sit there and add them.

That is where a one liner like this can be handy.

Note: You will want to replace `Prefix` in the command before you run the below command.


```
for i in {1..500}; do whmapi1 --output=jsonpretty ipv6\_range\_add range='Prefix::'$i'/128' name='IPv6Address'$i ; done
```