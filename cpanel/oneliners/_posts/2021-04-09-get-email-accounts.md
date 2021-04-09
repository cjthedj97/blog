---
layout: post
title: "List Email accounts (cpanel) one-liners"
tags: Cpanel oneliners Email
---

### List all email userdata

{% include note.html content="This outputs A LOT of data" %}

```
for i in $(cat /etc/userdomains | awk '{print $2}'); do uapi --user=$i Email list_pops 2>/dev/null ; done | less
```
---

### List users email Accounts

```
for i in $(cat /etc/userdomains | awk '{print $2}'); do uapi --user=$i Email list_pops 2>/dev/null | grep email | awk '{print $2}'| grep @; done
```
---

### List email accounts (including default accounts)

```
for i in $(cat /etc/userdomains | awk '{print $2}'); do uapi --user=$i Email list_pops 2>/dev/null | grep email | awk '{print $2}'; done
```
---
