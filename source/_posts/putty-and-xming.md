---
title: putty and xming
categories:
  - Dev
  - Tools
tags:
  - Programming
  - SSH
  - putty
  - xming
  - telnet
date: 2016-03-09 09:45:21
thumbnail: /images/thumbnail/putty.png
---
# Tool to access SSH remotely
![putty](putty.png)

---
* [Tool to access SSH remotely](#Tool-to-access-SSH-remotely)
	* [PuTTY](#PuTTY)
		* [Download PuTTY](#Download-PuTTY)
	* [Xming](#Xming)
		* [Download Xming](#Download-Xming)
		* [Setup Xming with PuTTY](#Setup-Xming-with-PuTTY)



---

## PuTTY

{% blockquote PuTTY.org http://www.putty.org/%}
PuTTY is an SSH and telnet client, developed originally by Simon Tatham for the Windows platform. PuTTY is open source software that is available with source code and is developed and supported by a group of volunteers.
{% endblockquote %}

### Download PuTTY
You can download latest PuTTY **[HERE](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html)**.
Depends on which Windows version you use, there are 32-bit and 64-bit versions available.
If you are not sure about which version you need to download, Read this **[FAQ entry](https://www.chiark.greenend.org.uk/~sgtatham/putty/faq.html#faq-32bit-64bit)**.

---

## Xming

{% blockquote Xming https://sourceforge.net/projects/xming/%}
Xming is the leading X Window System Server for Microsoft Windows 8/7/Vista/XP (+ server 2012/2008/2003). It is fully featured, small and fast, simple to install and because it is standalone native Microsoft Windows, easily made portable (not needing a machine-specific installation).
{% endblockquote %}

Basically, Xming is a software to enable your terminal to have graphical output on your local machine.
If you don't set up Xming and access remotely with PuTTY, you won't be able to use graphical softwares.

### Download Xming
You can download Xming **[HERE](https://sourceforge.net/projects/xming/)**

### Setup Xming with PuTTY

Run PuTTY, go under Connection->SSH->X11.
```
Connection
├── ...
├── SSH
|   ├── ...
|   ├── X11  <---
|   ├── ...
├── ...
```
![setup](setup.png)
**Tick** `"Enable X11 forwarding"` then set the `"X display location"` to `localhost:0`

---
