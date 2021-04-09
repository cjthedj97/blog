---
title: ' Common mistakes - DNS'
layout: post
---

# Common mistakes - DNS

{% include note.html content="Work in progress - new mistakes will be added as I come across them." %}

Have you ever heard

> It's not DNS
> There's no way it's DNS
> It was DNS 

Well, today we are going to look into the most common issues I see as a Linux Systems Admin.

**1.)** Setting DNS resolvers to 127.0.0.1 to on a server that you are **NOT** running a recursive resolver.

Running a recursive is resolver isn't the same thing as running authoritative name servers.

Say your own example.com and have name servers ns1.example.com and ns2example.com setup.

You configure these name servers at your registrar.

As the domain's primary DNS servers you now have authoritative name servers.

That doesn't mean your name servers have been configured as a recursive resolver.

A recursive resolver is a DNS server that will do a series on lookups (if needed) to get an address DNS entry.

An example would be 8.8.8.8 (google public DNS).

In fact, it isn't recommended that you run a recursive resolver that is publicly accessible on the internet.

