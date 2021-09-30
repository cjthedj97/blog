---
layout: post
title: Exim testing commands
tags: Testing
category: Exim Commands
---

#### Test delivery to a specific email account

`exim -bt user@example.com`

#### Send a message directly though exim

`exim -v receipient@example.com`

```
From: sender@example.com
Subject: Foobar
Text Text Text
```

Press ctrl+d to send

#### Testing Sender Verify

`exim -bvs sender@example.com`

Debug version

`exim -d -bvs sender@example.com`