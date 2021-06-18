---
layout: post
title: "Cpanel List Email accounts from shell"
tags: Cpanel oneliners Email
category: Cpanel
---

### List all email userdata

{% include note.html content="This First one outputs A LOT of data" %}

```bash
for i in $(cat /etc/userdomains | awk '{print $2}'); do uapi --user=$i Email list_pops 2>/dev/null ; done | less
```
---

### List users email Accounts

```bash
for i in $(cat /etc/userdomains | awk '{print $2}'); do uapi --user=$i Email list_pops 2>/dev/null | grep email | awk '{print $2}'| grep @; done
```
---

### List email accounts (including default accounts)

```bash
for i in $(cat /etc/userdomains | awk '{print $2}'); do uapi --user=$i Email list_pops 2>/dev/null | grep email | awk '{print $2}'; done
```
---