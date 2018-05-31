---
title: 'Notes on changing the academicpages'
date: 2018-05-26
permalink: /posts/2018/05/academicpages/
tags:
  - Webpage
---


Other than the notes for changing _config.yml and _pages folder that are already on the [academicpages](https://academicpages.github.io/) website, here I write down some notes to further customize your website. 
* Add another tab: add the name and url in navigate.yml then add a file in _pages and set the permalink part to be the same as the one writtem in navigate.yml 
* Change the formats of the Blog Post main page: in _layout, change achive-single.html. Change the format to show time
* Enable search (does not work for now): 
Use jekyll-seo-tag [plugin](https://github.com/jekyll/jekyll-seo-tag): change file `_config.yml` and `Gemfile`. Then add `SEO` in default.html
