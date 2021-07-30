---
author:
  name: Benjamin
  bio: All about Benjamin
image: https://images.unsplash.com/
title: My first Blog Post
description: Learning how to use @nuxt/content to create a blog
img: first-blog-post.jpg
alt: my first blog post
---

# My first blog post

Welcome to my first blog post using content module

<author :author="author"></author>

## This is a heading

This is some more info

### This is a sub heading

This is some more info

### This is another sub heading

This is some more info

## This is another heading

This is some more info

<div class="p-4 mb-4 text-white bg-blue-500">
  This is HTML inside markdown that has a class of note
</div>



<author :author="author"></author>


<info-box>
  <template #info-box>
    This is a vue component inside markdown using slots
  </template>
</info-box>
