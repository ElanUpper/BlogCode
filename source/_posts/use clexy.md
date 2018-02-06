---
title: how to use hexo and apply theme clexy
---

# Quick Start

## Install hexo and yarn
please get help from [Yarn go through](https://www.jianshu.com/p/1cd66bb64004)
and install the hexo, but before do that please install nodejs.
```
npm install -g hexo-cli
```
create a folder called blog, and access this folder. do following step
```
cd blog
hexo init
yarn
git clone https://github.com/mkkhedawat/clexy themes/clexy
yarn remove hexo-renderer-ejs
yarn add hexo-renderer-jade
yarn add hexo-prism-plugin
```
In root's _config.yml :
Change your theme variable to **clexy**
Add prism_plugin options
```
prism_plugin:
  mode: 'preprocess'    # realtime/preprocess
  theme: 'default'
  line_number: false    # default false
```
Make sure that default code highlight plugin is disabled.
```
highlight:
  enable: false
```
**Post Variables**
Add the intro variable to your YAML in your Markdown file.
Comments can be toggled with the comments boolean variable.
Add tag to post using tags variable.
```
---
title: 'Title Name'
date: 2017-06-01 21:56:56
tags:
- tag1
- tag2
intro : 'Enter intro here to display on home page'
comments: false
---
```
**Optional Config**
To configure about author page , add following tags in root's _config.yml. Remove the config key, you don't want.
```
about : {
  name : "Manish Kumar Khedawat",
  intro1 : "Full Stack Developer, Bosch",
  intro2 : "Alumni'14, IIT Kharagpur",
  linkedin : "https://in.linkedin.com/in/mkkhedawat",
  facebook : "https://www.facebook.com/mkkhedawat",
  twitter : "https://twitter.com/mkkhedawat",
  instagram : "https://www.instagram.com/mkkhedawat/",
  email : "writetomansa@gmail.com",
  github : "https://github.com/mkkhedawat",
  stackoverflow : "https://stackoverflow.com/users/1608029/mkkhedawat",
  sourceforge : "https://sourceforge.net/u/mkkhedawat/profile/"
}
```
Add author and keywords meta tag in root's _config.yml to be included for  header file
```
author: Manish Kumar Khedawat
keywords: "pen, notes, coding, developer"
Booting up blog
$ hexo new page "articles"
$ hexo new page "author"
$ hexo new post "Title-1"
$ hexo new post "Title-2"
```
after all steps. the _config.yml like 
```
# Hexo Configuration
## Docs: https://hexo.io/docs/configuration.html
## Source: https://github.com/hexojs/hexo/


# Site
title: 'elan and jem'
date: 2017-06-01 21:56:56
tags:
- memory
intro : 'the memory of us'
comments: false

# URL
## If your site is put in a subdirectory, set url as 'http://yoursite.com/child' and root as '/child/'
url: http://elangem.com/
root: /
permalink: :year/:month/:day/:title/
permalink_defaults:

# Directory
source_dir: source
public_dir: public
tag_dir: tags
archive_dir: archives
category_dir: categories
code_dir: downloads/code
i18n_dir: :lang
skip_render:

# Writing
new_post_name: :title.md # File name of new posts
default_layout: post
titlecase: false # Transform title into titlecase
external_link: true # Open external links in new tab
filename_case: 0
render_drafts: false
post_asset_folder: false
relative_link: false
future: true
highlight:
  enable: false
  line_number: true
  auto_detect: false
  tab_replace:
  
# Home page setting
# path: Root path for your blogs index page. (default = '')
# per_page: Posts displayed per page. (0 = disable pagination)
# order_by: Posts order. (Order by date descending by default)
index_generator:
  path: ''
  per_page: 10
  order_by: -date
  
# Category & Tag
default_category: uncategorized
category_map:
tag_map:

# Date / Time format
## Hexo uses Moment.js to parse and display date
## You can customize the date format as defined in
## http://momentjs.com/docs/#/displaying/format/
date_format: YYYY-MM-DD
time_format: HH:mm:ss

# Pagination
## Set per_page to 0 to disable pagination
per_page: 10
pagination_dir: page

# Extensions
## Plugins: https://hexo.io/plugins/
## Themes: https://hexo.io/themes/
theme: clexy

# Deployment
## Docs: https://hexo.io/docs/deployment.html
deploy:
    type: git
    repo: git@github.com:ElanUpper/ElanUpper.github.io.git
    branch: master
    message: 


about : {
  name : "Elan",
  intro1 : "Developer, Beijing",
  email : "elan.wang01@gmail.com",
  github : "https://github.com/ElanUpper"
}

prism_plugin:
  mode: 'preprocess'    # realtime/preprocess
  theme: 'default'
  line_number: false    # default false
```

## deploy to git
please follow this blog [Hexo GitHub tips](https://www.jianshu.com/p/c9295bacd98b)


