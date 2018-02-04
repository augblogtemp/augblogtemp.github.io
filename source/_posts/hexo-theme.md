---
title: hexo theme
categories:
    - Dev
    - Hexo
tags:
    - Hexo
    - Blog
    - GitHub
    - Node.js
    - Git
date: 2018-01-21 19:20:33
thumbnail: /images/thumbnail/hexo_example.jpg
---
 ***[Hueman](https://github.com/ppoffice/hexo-theme-hueman)***
![hexo_example](hexo_example.jpg)
I've tried variety of themes for Hexo blog, but the best one yet I found was
I will go through how to apply Hexo Hueman theme on the blog.

---
* [Install](#install)
* [Customise](#customise)
	* [Menu](#menu)
	* [About](#about)
	* [Logo](#logo)
	* [Theme colour](#theme-colour)
	* [Highlight](#highlight)
	* [Sidebar](#sidebar)
	* [Thumbnail](#thumbnail)
	* [Favicon](#favicon)
		* [My favicon is not appearing](#my-favicon-is-not-appearing)
	* [Social links](#social-links)
	* [Widgets](#widgets)
	* [Link](#link)
	* [Search](#search)
	* [Comment](#comment)
	* [Share](#share)
	* [Plugins](#plugins)
		* [Google_analytics](#google_analytics)
		* [Open_graph](#open_graph)

---

# install
Go to your blog root folder, then use the following command to download the theme.
```bash
$ git clone https://github.com/ppoffice/hexo-theme-hueman.git themes/hueman
```
Open `/blog_root_folder/_config.yml`  with your preferred text editor and change the following line.
```
old:
    theme:
new:
    theme: hueman
```
Go to `/blog_root_foler/themes/` and rename `_config.yml.example` into `_config.yml` then open it.

If you want to use search function ([Insight search](https://github.com/ppoffice/hexo-theme-hueman/wiki/Search#insight-search))) provided by hueman theme, you have to install `hexo-generator-json-content` with **npm**.

```bash
$ npm install -S hexo-generator-json-content
```

---
# customise
You can customise your blog theme with the `blog_root_folder/themes/_config.yml`.

## menu
![menu_bar](menu.png "menu_bar")
You can add your own menu.
If you add categories in `front-matter` when you write a post, hexo will automatically add your category into menu on the bar. front-matter is located on top of the md file when you create a new post. It includes title, date, and etc.

``` "Example"
menu:
    Home: /hexo-theme-hueman/
    About: /hexo-theme-hueman/about/index.html
	GitHub: https://github.com
```
## about
You can add a page abour yourself in `/about/index.html` but there is no page available by default.If you try to access it with out creating one, you will face 404 page not found error.

## logo
```bash
logo:
    width: 165
    height: 60
    url: images/logo-header.png
```
You can modify url to your own logo image. Image url can be one from web, or you can save image into `/root_folder/source/images/` then access them by `/images/filename.png`

## theme colour
![theme_color](colour.png "colour")
You can modify the colour of your blog.
```
theme_color: '#d35'
```

## highlight
![highlight](highlight.png "highlight")
Highlight setting allow you to adjust colours of your code block. You can use default but you can choose one from `hueman/source/css/_highlight`.
```
highlight: androidstudio
```

## sidebar
You can choose where your sidebar will located.
```
sidebar: left # options: left, right
```

## thumbnail
If this option is true, your blog will have thumbnail for each post you make.
```
thumbnail: true
```
You can add customised thumbnail in front-matter part of your post. Otherwise hexo will add the first photo in the post automatically.
```
title: Hello World
date: 2013/7/13 20:46:25
thumbnail: https://example.com/image.jpg
```

## favicon
Favicon is a little icon located right next to your URL. image type can be .ico or .png
```
favicon: favicon.png
```

### my favicon is not appearing
In most of the cases, if your favicon is not appearing after you made changes to your favicon, this occurs due to stored cache in your browser.
Solutions can be
- Delete cache of your browser
- Use different browser
- Use incognito mode
I prefer incognito mode in chrome to see changes.

## social links
![social links](social.png "social links")
You can add/delete/modify sns links that you use. You can check the icon list in **[FontAwesome](http://fontawesome.io/icons/#brand)**.
```
social_links:
    github: https://github.com/ppoffice/hexo-theme-hueman
    youtube: https://youtube.com
```

## widgets
```
widgets:
    - recent_posts
    - category
    - archive
    - tag
    - tagcloud
    - links
```
You can delete them if you don't want them on your side menu.

## link
You can add your own custom links at bottom of the `_config.yml`
```
# Miscellaneous
miscellaneous:
    links:
        Hexo: http://hexo.io
        custom_Link: http://custom.blah.com
```

## search
![Insight Search](search.png "Insight Search")
To use this function, you have to install `hexo-generator-json-content` prior to activate this.
Also I prefer using Insight search, not sure about other two since they look like chinese search engines.
```
# Search
search:
    insight: true
    swiftype:
    baidu: false
```

## comment
![Disqus](comment.png "Disqus")
This theme provide multiple comment services but I use [Disqus](https://disqus.com/) because others are chinese services. Signup with disqus and get shorname from them, then copt and paste to `_config.yml`
![Site Identity](disqus.png "Site identity")

```
# Comment
comment:
    disqus: futurecreator # copy and paste disqus shortname
    duoshuo:
    youyan:
```

## share
Hueman also provide share option to share the post on sns.
- default
- addtoany
- jiathis (Chinese)
- bdshare (Chinese)
```
# Share
share: addtoany # options: jiathis, bdshare, addtoany, default
```
![Default](share_default.png "Default")
![addtoany](share_addtoany.png "addtoany")

## plugins
They also provide plugin options such as Open Graph, Google analytics and etc.
### google_analytics
```
google_analytics: UA-66666666-6
```
![tracking id](google.png "tracking id")
### open_graph
```
open_graph:
    fb_app_id:
    fb_admins:
    twitter_id:
    google_plus:
```
