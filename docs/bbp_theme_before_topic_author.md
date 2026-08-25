---
title: "bbp_theme_before_topic_author"
post_status: publish
post_name: bbp_theme_before_topic_author
lang: en
taxonomy:
  category: [bbpress]
  post_tag: [bbp-hooks]
source:
  blog_id: 4
  post_id: 51
  guid: "http://import.local/2021/12/24/bbp_theme_before_topic_author/"
---

bbp\_theme\_before\_topic\_author
Codex Home → bbp\_theme\_before\_topic\_author
Description
The ‘bbp\_theme\_before\_topic\_author’ action is used to display content before the author’s avatar and name in a forum
How to use it
Since this is an action, we can use add\_action to hook into it.
Sample code example
1234add\_action( 'bbp\_theme\_before\_topic\_author', 'jc\_before\_topic\_author' );function jc\_before\_topic\_author() {     echo 'Hello world!';}
Note: Always remember to prefix your functions to avoid conflicts!
