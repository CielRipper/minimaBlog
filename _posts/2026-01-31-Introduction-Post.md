---
layout: post
title: "Introduction Post"
date: 2026-01-31
author: 
 - Jaxon Treadwell
---

This is my first post on my Jekyll blog for Database and Web Systems. The main goal of this post is to document how my setup went and what I learned while getting everything running.

## What was new to me
A few parts of this lab were new (or at least new in a “real dev workflow” way):

- Setting up Ruby + Bundler + Jekyll on Windows and making sure it all worked from the terminal
- Learning how Jekyll uses files like _config.yml to control the site
- Understanding how GitHub Pages deploys automatically once commits are pushed

## What I struggled with
The biggest struggle was definitely configuration and environment stuff:

- Getting Ruby/Bundler recognized correctly depending on what terminal I was using
- YAML being extremely picky (commenting out settings and indentation broke things)
- Making sure I was running bundler commands from the correct folder (so it could find the Gemfile)

## What still doesn’t fully make sense (yet)
I’m still building the “big picture” understanding of:

- How Jekyll decides what to render from _posts/, _layouts/, and _includes
- What parts of the theme are controlled by _config.yml vs the actual layout files

I’m planning to figure this out more as I write more posts and customize the theme.

## What I’m looking forward to
I’m looking forward to using this blog like a small dev journal:

- Writing posts quickly in Markdown
- Tracking what I learn over the semester
- Making small improvements to the styling/layout over time

## Useful links
Here are a couple links I used while working on this setup:

- [Jekyll Documentation](https://jekyllrb.com/docs/)
- [Markdown Guide](https://www.markdownguide.org/basic-syntax/)
