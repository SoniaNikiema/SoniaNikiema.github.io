---
title: "from-github-to-netlify-through-hugo-blogdown"
author: "Sonia Nikiema"
date: '2021-01-02'
categories: []
featured: no
image: 
  caption: ''
  focal_point: ''
  preview_only: no
lastmod: '2021-01-02T13:19:30-08:00'
projects: []
slug: from-github-to-netlify-through-hugo-blogdown
subtitle: ''
summary: ''
tags: []
authors: [Sonia Nikiema]
---

![help_other_learn](/image/help_other_learn.jpg)

# Github Repository

- Create a new repository(add .gitignore (R), readme)
- click on the green clone 
- Copy https link

# RSTUDIO Project

I assume you already has git istalled. if not [ GitHub Quick Tutorial for R and RStudio Projects Data Science](https://www.youtube.com/watch?v=TaDdlrYKWks/). If you already have it installed go to next

```r
File -> New Project -> version control -> git
```
- Paste the https link click on (`keep empty file`)

- Create project
- Before you do anything, staged your (`.igitinore & name.Rproj`). I assume you already has blogdown istalled. if not read [ Alison Hill’s tutorial here is the best place to get started](https://alison.rbind.io/post/2017-06-12-up-and-running-with-blogdown/). If you already have it installed go to next

```r
staged: .igitinore & name.Rproj -> commit ->  push
```

- run 

```r
library(blogdown)
blogdown::new_site()
```


```r
blogdown::stop_server()
```

```r
install_theme("gcushen/hugo-academic", theme_example = TRUE, update_config = TRUE)
```


```r
blogdown::build_site()
```
Be patient and gave it some time to run the above script
                   | EN  
-------------------+-----
  Pages            | 86  
  Paginator pages  |  0  
  Non-page files   | 23  
  Static files     | 10  
  Processed images | 34  
  Aliases          | 16  
  Sitemaps         |  1  
  Cleaned          |  0  

Total in 5720 ms


```r
blogdown::serve_site()
```

```r
blogdown::stop_server()
```

- Start editing your site from (`content/`) then push (`public/`) . Sometime it can be tedious to push (`public/`) through git and commit. Instead go to next

```r
tool -> shell -type: git add public/*
```
It should look like this (`\SoniaNikiema.github.io>git add public/*`)

Then commit and push 

- Edit (`content/home/hero.md`)

- Edit (`content/home/demo.md`) -> will be demo / resume widget

- Edit (`content/home/hero.md`) -> will be demo / first page

- Edit (`content/authors/admin/index.md`) ->will be demo / biography


# Deployed with Netlify

- go to [ Netlify](https://www.netlify.com/) and register with github

```r
New site from git -> Authorize Netlify by Netlify -> Select your blogdown site repository -> click Install -> Enter your Github password -> Click Confirm password
```
- After you confirm password, your working window may disappear, but don't worry go back to your Netlify account and do these steps

```r
New site from git -> Select your blogdown site repository -> Build command(hugo) -> Publish directory(public) -> Click on show advance -> click on New variable -> key(HUGO_VERSION) -> Value() -> Click on Deploy site
```
If the deploy failed don't worry do to next

Go to your Rblogdown and push all necessary files to github and and repete the process on Netlify

```r
New site from git -> Select your blogdown site repository -> Build command(hugo) -> Publish directory(public) -> Click on show advance -> click on New variable -> key(HUGO_VERSION) -> Value() -> Click on Deploy site
```
Once you successfully deployed Then go back to your R project and continue to edit your site

# RSTUDIO Project Big Clean Up

## Edit content/authors/admin

- copy your resume to `static/media/resume.pdf`

## Edit config/menus.toml
 
- Add or remove Navigation Links: To link a homepage widget, specify the URL as a hash `#` followed by the filename of the
desired widget in your `content/home/` folder.
- Insert desire widget in your `content/home/` folder

## Edit config/params.toml
- Disable default address, Geographic coordinates...
- sharing and search engines. Place image in `static/media/` folder and specify image name here
- Avatar is an image that appears next to a user's name.An avatar can be uploaded as an image named `avatar` to each user's profile or fetched from Gravatar.com.

FYI: you can insert all your pictures to `content/home/gallery`

# Create a post

## create post with a code
```r
 blogdown::new_post(title = "my first content", 
                     ext = '.Rmarkdown', 
                     subdir = "post")
```
This takes the path to where you want your post to live, relative to the `content/` folder (so that piece of the path is assumed, rightly so!)

## create post without a code

Go to addins, fill out all information and click done

## insert a image

1. Add image on `static/image/` folder
2. Refer the image using the relative path

```r
![help_other_learn](/image/help_other_learn.jpg)
```
FYI: you can also insert image through `addin->insert image-> download file name(image1)`  

```r
![](image1.jpg)
```

## insert a GIF

1. Find GIF online, (copy image in new tab), then copy the link
2. Refer to the link on your markdown (not a R code Chunk). See example below

```r
![](https://media4.giphy.com/media/2wh5JHFov2nuW16v7u/giphy.gif?cid=ecf05e47noihitsq192nuazi4amcg5raudvf7ohb0zd3xmsc&rid=giphy.gif)
```
## insert an  Emoji emoticons

1. Set `config.toml-> enableEmoji = true`
2. Refer Emoji by its name on Markdown like `:smile` 

We all set!!!
Lunch time :smile:

![](https://media4.giphy.com/media/2wh5JHFov2nuW16v7u/giphy.gif?cid=ecf05e47noihitsq192nuazi4amcg5raudvf7ohb0zd3xmsc&rid=giphy.gif)



