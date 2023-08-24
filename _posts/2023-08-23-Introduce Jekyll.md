---
layout: post
title: " Introduce Jekyll "
date: 2023-08-23
---

# What is Jekyll

- Jekyll is a static website generator
- It is ruby project.
- It supports Markdown.
- You can run Jekyll in your own computor to setup website server.
- GitHub Pages use Jekyll to provide website service for your repo.

# How GitHub Pages work

- You can update your website content, for example blogs, by updating your repo.
- GitHub Pages will automatically build your content by using Jekyll.

# Jekyll syntax

## Front Matter

The front matter is the first thing in the file and must take the form of valid YAML set between triple-dashed lines.
Here is a basic example:

```yml
---
layout: page
title: "PAGE-TITLE"
permalink: /URL-PATH
---
```

or

```yml
---
layout: post
title: "POST-TITLE"
date: YYYY-MM-DD hh:mm:ss -0000
categories: CATEGORY-1 CATEGORY-2
---
```

Any file that contains a YAML front matter block will be processed by Jekyll as a special file.

# FQA

## baseurl issue

When you setup github page in github, it sets this baseurl to your repo name, for example 'blogs', if your repo is 'blogs'.
You can set this environment variable in \_config.yml file.

```yml
baseurl: "/blogs" # the subpath of your site
```

This will be helpful if you want to test the website in your local machine.
