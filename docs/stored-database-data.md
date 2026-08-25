---
title: "存储的数据库数据"
post_status: publish
post_name: stored-database-data
lang: zh
taxonomy:
  category: [bbpress]
  post_tag: [bbp-hooks]
source:
  blog_id: 4
  post_id: 149
  guid: "http://import.local/2021/12/24/stored-database-data/"
---

### [用户](#users)

所有用户和用户数据都存储在这些表中。

- wp\_users
- wp\_usermeta

### [内容](#content)

bbPress在这些表中安装和存储所有论坛、话题和回复[文章类型](https://codex.wordpress.org/Post_Types)及其数据。

- wp\_posts
- wp\_postmeta

bbPress 设置以\_bbp\_此处为前缀并存储在此处。

- wp\_options

### [标签](#tags)

bbPress 安装话题标签，它们的数据都存储在这些表中。

- wp\_terms
- wp\_term\_relationships
- wp\_term\_taxononmy
