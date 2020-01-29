---
title: My First Blog Post
date: 2017-12-17 00:00:00 Z
permalink: "/my-first-blog-post"
layout: post
excerpt: how this blog was created
images:
- url: "/assets/Cover11th.png"
---

## How this blog was created

1. Fork github repo [adeshpande3/adeshpande3.github.io](https://github.com/adeshpande3/adeshpande3.github.io) and rename it as `username.github.io` where `username` is your github username
 
1. In this repo, edit file `_config.yml` and update name, description (this is what appears below your name on your blog), avatar, footer-links, url. You can edit this file from github itself

1. Create a `_posts` directory at the top level of this repo (if one does not exist). You can do this by `create new file` from the github repo page with the name "/_posts"

1. As the title indicates, this directory will contain your blog posts as separate files. Files should be named using the convention `YYYY-MM-DD-title.md` where spaces in the title name are replace by hyphens (e.g. `2017-12-17-my-first-blog-post.md`)

1. The blog post is written in markdown syntax. I use prose.io as an online markdown editor. After you have composed and previewed your post, take a look at the metadata using the icon on the right. Here you can provide the `excerpt` for your blog post as well as direct link to it in the `permalink` (e.g. "/my-first-blog-post")

1. Once you save your changes in prose.io, it will take a couple of minutes for your posts to show up on `username.github.io`

1. In order to allow comments on your blog, you will have to create a disqus account. Within disqus, select "I want to install Disqus on my site". The website name you provide here is your disqus shortname. After going through this, go back to your github.io repo and update the  `disqus_shortname` variable in the file `_includes/disqus.html`
