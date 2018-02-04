---
title: Make new blog with GitHub Page with Hexo
categories:
  - Dev
  - Hexo
tags:
 - Hexo
 - Blog
 - GitHub
 - Node.js
 - Git
date: 2018-01-11 22:45:48
thumbnail: /images/thumbnail/github_page.jpg
---
# Make your own blog

---




* [Make your own blog](#Make-your-own-blog)
	* [Create new GitHub repository](#Create-new-GitHub-repository)
		* [Difference between User and Project Page](#Difference-between-User-and-Project-Page)
	* [Install Hexo](#Install-Hexo)
	* [Settings](#settings)
	* [Write a new post](#Write-a-new-post)



## Create new GitHub repository
![github_page](github_page.jpg)
Firstly, we have to create new repository at GitHub to save all the static files.
Get on to ***[GitHub](https://github.com/)*** and click on `New Repository`

### Difference between User and Project Page

||USER|Project  |
|--|--|--|
|URL|`username.github.io`  |`username.github.io/repository_name`  |

Unless you are willing to make a sub directory under your root domain `username.github.io/example`, name your repository with `username.github.io` or `username.github.com`.
***But both of them will have domain `username.github.io`***

---

## Install Hexo
You can check out the ***[older post](/2018/01/11/Hexo-blog-framework/)*** to install Hexo

---

## Settings
You can manage settings of your blog with `_config.yml` file.
But at the moment, lets set up URL and Deployment first.
```bash _config.yaml
# Site
title: Augusdn	# Title of your blog
subtitle:  Blog of my life # Sub title
description: Blog description # Blog description
author: Augusdn # Name of author
language: en # default language of theme, most of the themes support multi language
timezone: Australia/Sydney # Set Timezone (https://en.wikipedia.org/wiki/List_of_tz_database_time_zones)

# URL
url: https://user_name.github.io/ # Your github page address
root: / # default by / but if you have sub dir, you can choose where it should set root as
permalink: :year/:month/:day/:title/ # default URL for new post. ex) 2018/01/01/new_post
permalink_defaults:

# Deployment
deploy:
  type: git
  repo: https://github.com/user_name/user_name.github.io.git
```

Now, lets try generate static files and push it to GitHub.

```bash
hexo g -d
```

In most of the cases, you can write your post or draft and check on your local server before you push it to remote.
After push, you can check your blog at `user_name.github.io`.
In my situation, it will be [augusdn.github.io](https://augusdn.github.io)

---

## Write a new post
Lets make a new post with following command
```bash
$ hexo new post 'post name'
```
You can check this post file in `[blog_folder]/sources/_posts`
Edit this file as you like, with Markdown Editor, then check with local server.
```bash
$ hexo server
```
Then check your new post at [localhost:4000](localhost:4000)
Confirm your posts and generate, then push it to github.
```bash
hexo g -d
```
