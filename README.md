Hexo-Theme-Freemind
===

![screenshots](http://wzpan.github.io/hexo-theme-freemind-blog/images/screenshots.png)

Freemind aims at fully taking advantages of Bootstrap.

* [Demo](http://hahack.com/hexo-theme-freemind-blog/)
* [Q&A](http://hahack.com/hexo-theme-freemind-blog/2014/03/16/qna/)
* [Tag Plugins](http://hahack.com/hexo-theme-freemind-blog/2014/03/16/tag-plugins/)
* [Color Themes](http://hahack.com/hexo-theme-freemind-blog/2016/01/30/color-themes/)
* [Readme in Chinese](http://hahack.com/codes/hexo-theme-freemind/)

## Requirements ##

* Hexo >= 3.0
* [hexo-tag-bootstrap](https://github.com/wzpan/hexo-tag-bootstrap) >= 0.0.8 (optional)

## Features ##

* **Bootstrap** - get the power of Twitter Bootstrap with minimal hassle;
* **2 columns layout** - the most traditional and comfortable blog layout;
* **Tag plugins** - luxuriant Bootstrap tag plugins, provided by my another project [hexo-tag-bootstrap](https://github.com/wzpan/hexo-tag-bootstrap). Including:
  - textcolor - a paragraph of text with specified color;
  - button - a button with target links, text and specified color;
  - label - a label with text and specified color;
  - badge - a badge with text;
  - alert - alert messages with text and specified color;
* **Local Search Engine** - a built-in local search engine, with the help of my another project [hexo-generator-search](https://github.com/paichyperiondev/hexo-generator-search).
* **Color Themes** - luxuriant Bootswatch color themes for choice;
* **Pin to top** - able to pin any article to the top of the first index page;
* **Built-in Comment System** - a comment system based on my another project [comment.js](https://github.com/wzpan/comment.js).

![color themes](http://wzpan.github.io/hexo-theme-freemind-blog/images/color-themes.gif)

## Install ##

1) install theme:

``` sh
$ git clone https://github.com/wzpan/hexo-theme-freemind.git themes/freemind
```

2) install [hexo-tag-bootstrap](https://github.com/wzpan/hexo-tag-bootstrap) (*optional*):

``` sh
$ npm install hexo-tag-bootstrap --save
```

3) install [hexo-generator-search](https://github.com/paichyperiondev/hexo-generator-search) (*optional*):

``` sh
$ npm install hexo-generator-search --save
```

4) install [hexo-recommended-posts](https://github.com/huiwang/hexo-recommended-posts) (*optional*):

``` sh
$ npm install hexo-recommended-posts --save
```

5) Create pages

Freemind offers you the customized Categories, Tags and About pages. But you need to manually create these page at your 'source' folder.

For example, to create a `Categories` page, you may create a `index.html` file at `source/categories/` folder with the following contents:

```
title: Categories
layout: categories
---
```

Tags and About pages are created in a similar way, except that the layouts are `tags` and `page` respectively.

Alternatively you can create About page using the following command:

``` sh
$ hexo new page about
```

Note that only About page can be created in that way.

## Enable ##

Modify `theme` setting in your `_config.yml` to `freemind`.

## Update ##

``` sh
$ cd themes/freemind
$ git pull
```

## Configuration ##

```
slogan: Yet another bootstrap theme.

theme: bootstrap
inverse: true
# whether to show h2 and h3 titles in excerpts
show_title_in_excerpt: false

menu:
  - title: Archives
    url: archives
    intro: All the articles.
    icon: fa fa-archive
  - title: Categories
    url: categories
    intro: All the categories.
    icon: fa fa-folder
  - title: Tags
    url: tags
    intro: All the tags.
    icon: fa fa-tags
  - title: About
    url: about
    intro: About me.
    icon: fa fa-user

links:
  - title: My Github
    url: http://www.github.com/wzpan
    intro: My Github account.
    icon: fa fa-github
  - title: My LinkedIn
    url: http://www.linkedin.com/in/hahack
    intro: My Linkin account.
    icon: fa fa-linkedin

widgets:
- search
- recent_comments
- category
- tagcloud
- recent_posts
- links

rss: atom.xml
favicon: favicon.png
fancybox: true
duoshuo_shortname:

# Recommended posts
# Dependency: https://github.com/huiwang/hexo-recommended-posts
recommended_posts:
  enabled: false

# analytics
google_analytics:
  enable: false
  siteid:
baidu_tongji:
  enable: false
  siteid:

# Search
swiftype_key:

# share button
bdshare: true
jiathis: false

# built-in comment system
comment_js:
  type: "github"
  user: "your-account"
  repo: "your-repo"
  client_id: "xxxxxx"
  client_secret: "xxxxxx"
  count: 5
```

* **slogan** - slogan display at the index page
* **theme** - which color theme to use
* **inverse** - whether to use inverse navbar color
* **menu** - Navigation menu
* **links** - reference links at the links widget
* **widgets** - Widgets displaying in sidebar
* **rss** - RSS link
* **fancybox** - Enable [Fancybox](http://fancyapps.com/fancybox/)
* **duoshuo_shortname** - DuoShuo ID, if you prefer to use duoshuo instead of Disqus
* **recommended_posts** - Enable recommended posts
* **analytics** - Analytics ID. Supports both Google Analytics and Baidu Tongji.
* **swiftype_key** - Swifttype key to enable local searching. Leave it blank or comment this line if you want to use build-in local search engine.
* **bdshare** - Baidu share button at the bottom of article.
* **jiathis** - jiathis share button at the bottom of article.
* **comment_js** - settings for [comment.js](http://github.com/wzpan/comment.js).
  * `type`: the site as the backend. Currently supports Github and OSChina.
  * `user`: your site's user account.
  * `repo`: your repo for comment issue tracking.
  * `client_id`(optional but recommended): the client id of your OAuth App.
  * `client_secret`(optional but recommended): the client secret of your OAuth App.
  * `count`(optional): the maximize length of the comment list. Default value is 5.


If you prefer to use disqus, the setting of disqus should be placed at your **root** `_config.yml`:

```
# Disqus
disqus_shortname:
```

## Front-Matter ##

There are some new front-matter settings in Freemind that you can use to decorate your articles.

* **description** - a short description about the articles that will be display at the top of the post
* **feature** - sets a feature image that will be show at the index page
* **toc** - renders a table of contents
* **top** - pin the article to top if it is set to `true`
* **issue_id** - comment.js `issue_id` for explicitly point out which Github issue should be connect to your post. For most situations you don't need it unless the post doesn't link to the issue you want.

For example:

```
title: Tag Plugins
date: 2014-03-16 10:17:16
tags: plugins
categories: Docs
description: Introduce tag plugins in freemind.
feature: images/tag-plugins/plugins.jpg
toc: true
---
```

## License ##

This theme is provided under [MIT License](http://opensource.org/licenses/MIT).

## People Using Freemind ##

see [Examples](https://github.com/wzpan/freemind/wiki/Examples).

## Credits ##

* The theme is built based on [Twitter-Bootstrap 3.1.1](getbootstrap.com/3.1.1/);
* The beautiful icons are from [Font Awesome](http://fortawesome.github.io/Font-Awesome/icons/).
* Build-in color themes are from [Bootswatch](bootswatch.com).
