---
layout: post
title:  "Working session - Jekyll"
date:   2021-12-04 11:23:58 -0800
categories: jekyll update working-session
---

# Working sessions

My little sister [Charieal](https://chariael.github.io/) is getting into front-end web stuff, and we've been working for a couple hours every Saturday on different projects.

## Current projects

 - Rebuilding the WordPress website for [Renaissance Choir Sacramento](https://renaissancechoirsacramento.com/), my old choir I joined when I first moved to Sacramento. The choir has changed hands since those days, but I'm still hosting their site in my Digital Ocean site.
   - Chariael has written up instructions for [Setting up a Wordpress instance on Digital Ocean](https://thoughtcolors.wordpress.com/2021/12/04/setting-up-a-virtual-machine-using-digital-ocean/) on her blog.

## Past projects

 - Build a website for [Ousia Music](https://www.ousiamusic.com/) for my friend Philip. He has made a number of books of lute sheet music from the Renaissance era -- both facsimiles of the original books and transcriptions from the original white mensural notation to modern musical notation.

# Jekyll

This brings us to the issue of lab notebooks. I instinctively write notes down in my Sublime text editor. The issue becomes managing a large number of untitled, unsaved notes. It's far better to take notes directly into a blog post or Notion wiki, so our first order of business today was figuring out where to take notes.

After a brief foray into manually editing a static HTML website as a place to store notes, we decided it would take too long to do this for every post, and decided instead to (her) add entries to her existing blog and (me) learn how to deploy a Jekyll site to GitHub Pages.

Jekyll is a Ruby app that creates a static HTML site from markdown pages or other resources. There are lots of extensions, including one to create and manage blog posts. GitHub Pages actually offers a built-in Jekyll service to translate markdown files using pre-installed themes into beautiful pages. I decided to do it the Harder Way.

## Installing Jekyll

Since Jekyll is generating static pages, you don't install it on your web server. Instead, you install it on your local machine, generate the pages, and then upload the pages to the remote server. GitHub Pages is cheating a little, in that they already have Jekyll installed on their end, so all you have to do is

### Prerequisites

#### Ruby

For a Windows machine, the [ruby-lang site recommends](https://www.ruby-lang.org/en/documentation/installation/#rubyinstaller) installing using the [RubyInstaller](https://rubyinstaller.org/). That worked for me.

#### Bundler

Bundler tracks packages and dependencies in Ruby, like npm does for JavaScript apps. After installing Ruby, you can use the built-in package manager `gem` to install [Bundler](https://bundler.io/v2.2/#getting-started) like this:

```bash
gem install bundler
```

## Creating a Jekyll site

GitHub Pages has a decent description of the [site creation process](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/creating-a-github-pages-site-with-jekyll). Basically, you clone your git repository named `<username>.github.io` to your local machine, then do everything in there.

 - Create a project directory
 - Run `jekyll new --skip-bundle .`
 - Modify the `Gemfile` file, 
    - comment out `gem "jekyll"`
    - uncomment `gem "github-pages"`
       - You have to add a specific version number here, like `gem "github-pages", "~> 219", group: :jekyll_plugins` 

## Deploying a Jekyll site

Commit all your changes using your favorite git client, push to the repo, then make sure the repo Settings -> Pages -> is pointed to the appropriate branch and folder that your project is in. After that, you can visit [http://<username>.github.io/](https://masyukun.github.io/) and see the site you made!


