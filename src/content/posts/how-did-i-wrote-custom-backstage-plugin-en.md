---
title: How did I wrote a custom backstage plugin
published: 2024-11-18T02:39:03+00:00
description: 'Hello'
updated: ''
tags:
  - typescript
  - backstage
draft: true
pin: 0
toc: true
lang: 'en'
abbrlink: ''
---

## new
I joined a new company since i wrote the last blog post. At the new company I am working on a microservice where we can deploy infrasture as using resuable pulumi code.But this post I'll be focusing on a task i recently did which is how did i write a custom backstage plugin. Our company already had a backstage backend. they already built it but i was assigned to create a plugin. I was able to do the task with help of a medium blog post and with lots of help from chatgpt.(which didnt give me a good output)
But i had to spend lot of time figuring out how to follow the default backstage patterns and the custom change our team did so when we deploy the new feature it wont affect the deployments. So I hope someone will find this post very helpful.

## our goal
we will write a small backstage plugin together. Plugin has get and post endpoints, and a plugin own database with migration files.

