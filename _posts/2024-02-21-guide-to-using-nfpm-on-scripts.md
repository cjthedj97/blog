---
layout: post  
title: Beginner's Guide to Linux Packaging with nFPM
tag: Linux Packaging
---

Are you looking to package up a shell script in Linux for easy distribution and installation? Look no further than nFPM - a simple and powerful tool for creating packages in various formats. In this blog post, we will walk you through the basic steps of using nFPM to package a shell script.

## What is nFPM?
nFPM is a tool that helps you create packages in different formats (such as deb, rpm, apk, etc.) for various package managers. It simplifies the process of packaging software, making it easier for developers to distribute their applications across different Linux distributions.

## Instalation
Before we begin, make sure you have nFPM installed on your system. Please refer to their install directions at https://nfpm.goreleaser.com/install/.

## Packaging a Shell Script

Let's say you have a simple shell script named hello.sh that you want to package using nFPM. Here's a step-by-step guide to help you create a Debian package (.deb), RedHat package (.fpm), Alpine (.apk), and even packages for Arch Linux (.pkg.tar.zst).

**1.** After installing nFPM, create a new directory for your project and cd into it. You will also need to make sure a copy of your script is in this directory.

**2.** Create a Configuration file for nFPM. You can name it nfpm.yaml and add the following content:

```yaml
name: hello
arch: all
platform: linux
version: 1.0.0
section: default
priority: extra
maintainer: Your Name <your.email@example.com>
description: A simple hello world script
contents:
  - src: hello.sh
    dst: /usr/local/bin/hello.sh
```

> Notes: Make sure to modify the content after you copy and paste nfpm.yaml to match the script you are working on.
{: .prompt-info }

**3.** Run the respective command (updating the target path) to generate the desired package type:

Debian Derivatives (this includes Ubuntu)

```bash
nfpm pkg --packager deb
```

RedHat and Derivatives
```bash
nfpm pkg --packager rpm
```

Alpine
```bash
nfpm pkg --packager apk
```

Arch Linux
```bash
nfpm pkg --packager archlinux
```
**4.** Once the package is created bring it over to the system you want to install it on and run the respective install command on the generated package:

Debain and Derivatives
```bash
sudo dpkg -i hello_1.0.0_all.deb
```

RedHat and Derivatives
```bash
sudo rpm -i hello_1.0.0_all.rpm
```

Alpine
```bash
sudo apk add --allow-untrusted hello_1.0.0_all.apk
```

Arch Linux
```bash
sudo pacman -U hello_1.0.0_all.pkg.tar.zst
```

## Conclusion
Packaging software for Linux can be a daunting task, but tools like nFPM make it easier and more manageable. By understanding how packaging works and using tools like nFPM, you can simplify the process of distributing your applications across different Linux distributions and package managers. In this blog post, we covered the basics of using nFPM to package a simple shell script into a Debian package. With nFPM, you can streamline the packaging process and ensure smooth installation for your users. Embrace the power of packaging and make distributing your software a breeze with nFPM. 
