---
title: 'Notes on changing the minimal mistakes'
date: 2018-05-31
permalink: /posts/2018/05/minimalmistakes/
tags:
  - Webpage
categories:
  - Tools
  - Coding
---

I wrote some notes on how to customize your website. 
* Change the sidebar width: 
	1. If you want to change the image size: goes to `_sass` and change `img` in `_sidebar.scss` to the value you want.
	2. Add an `$right-space` variable to `_variables.scss`
	3. Change the wide option in `_pages.scss`,`_archive.scss` from 0 to `$right-space`.
	4. Add values in `classes: wide` in `_config.yml` to use the wide option.

