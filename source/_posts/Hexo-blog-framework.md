---
title: Hexo, blog framework
categories:
  - Dev
  - Hexo
tags:
  - Hexo
  - Blog
  - GitHub
  - Node.js
  - Git
date: 2018-01-11 21:34:23
thumbnail: /images/thumbnail/hexo.jpg
---
![hexo](hexo.JPG)
# Hexo
***[Hexo](https://hexo.io/)*** is a fast, simple and powerful blog framework based on Node.js.

* [Hexo](#Hexo)
	* [Installation](#Installation)
		* [Requirements](#Requirements)
			* [Install Git](#Install-Git)
			* [Install Node.js](#Install-Nodejs)
			* [Install Hexo](#Install-Hexo)
	* [Hexo setup](#Hexo-Setup)
	* [Run](#Run)
	* [Commands](#Commands)



This blog is written in **Markdown**, using **Hexo** and **GitHub Pages** due to following reasons.
 - Support [**Markdown**](http://daringfireball.net/projects/markdown/), allow you to post easily.
 - **Free** hosting from **GitHub Pages**.
 - Users are able to use a wide variety of **Themes**.


----------

## Installation
### Requirements
Hexo requires couple of things installed on your machine to run.

 - [Node.js](https://nodejs.org/en/)
 - [Git](https://git-scm.com/)

If you already installed these, you can skip to [Hexo installation](#Install-Hexo)
#### Install Git
 - Windows: Download & install [git](https://git-scm.com/download/win).
 - Mac: Install it with [Homebrew](http://mxcl.github.com/homebrew/), [MacPorts](http://www.macports.org/) or [installer](http://sourceforge.net/projects/git-osx-installer/).
 - Linux (Ubuntu, Debian): `sudo apt-get install git-core`
 - Linux (Fedora, Red Hat, CentOS): `sudo yum install git-core`

#### Install Node.js
The best way to install Node.js is with [Node Version Manager](https://github.com/creationix/nvm).
Thankfully the creators of nvm provide a simple script that automatically installs nvm:

cURL:
``` bash
$ curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.33.2/install.sh | bash
```
Wget:
``` bash
$ wget -qO- https://raw.githubusercontent.com/creationix/nvm/v0.33.2/install.sh | bash
```
Once nvm is installed, restart the terminal and run the following command to install Node.js:
```bash
$ nvm install stable
```

Alternatively, download and run the [installer](http://nodejs.org/).
#### Install Hexo
Once all the requirements are installed, you can install Hexo with npm:
```bash
$ npm install -g hexo-cli
$ npm install hexo-deployer-git --save
```
---
## Hexo setup
After installing ***Hexo***, you can set up a new folder for your blog.
```bash
$ hexo init <blog_folder_name>
$ cd <blog_folder_name>
$ npm install
```
**Result:**
```bash
.
├── _config.yml   : configuration file for blog
├── package.json  : list of packages in json format
├── scaffolds 	  : scaffolds folder make you able to set up initial seed for post or drafts
├── source 	  : source folder to store markdown files and all other files for blogging
|   ├── _drafts 	
|   └── _posts 		
└── themes 	  : folder to store themes, hexo generate blog based on files in source, and format them with themes
```
---
## Run
After installing, you can run local server to test ***Hexo***
```bash
$ hexo server
```

You can check your server at `localhost:4000` (default port: 4000)

---
## Commands
### New post
Create a new post
```bash
$ hexo new "My New Post"
```
### Generate
Generate static files
``` bash
$ hexo generate
```
OR
```bash
$ hexo g
```

### Deploy to remote sites

``` bash
$ hexo deploy
```
OR
```bash
$ hexo d
```

### More Commands
You can fine more commands in this [Link](https://hexo.io/docs/commands.html).
