---
layout: post
title: "One liner to disable TCP timestamps"
tags: hardening
---

{% include warning.html content="This has not been tested on all linux operating systems use at your own risk." %}

```
grep -q "net.ipv4.tcp_timestamps" /etc/sysctl.conf && echo "net.ipv4.tcp_timestamps = 0" >> /etc/sysctl.conf && sysctl -p || echo "Stopping \"net.ipv4.tcp_timestamps\" is already in file"
```