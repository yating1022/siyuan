---
layout: home

hero:
  name: "Fruits Blog"
  text: "Fruits的AI学习笔记"
  tagline: "记录技术 · 分享思考"
  image:
    src: /logo.png
    alt: Fruits Blog
---

<script setup>
import BlogArchive from '../.vitepress/views/BlogArchive.vue'
</script>

<BlogArchive :hide-header="true" />
