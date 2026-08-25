---
title: "bbp_theme_before_forum_freshness_link"
post_status: publish
post_name: bbp_theme_before_forum_freshness_link
lang: en
taxonomy:
  category: [bbpress]
  post_tag: [bbp-hooks]
source:
  blog_id: 4
  post_id: 47
  guid: "http://import.local/2021/12/24/bbp_theme_before_forum_freshness_link/"
---

bbp\_theme\_before\_forum\_freshness\_link
Codex Home → bbp\_theme\_before\_forum\_freshness\_link
Description
The ‘bbp\_theme\_before\_forum\_freshness\_link’ action is used to display content before the forum freshness link
How to use it
Since this is an action, we can use add\_action to hook into it.
Sample code example
1234add\_action( 'bbp\_theme\_before\_forum\_freshness\_link', 'jc\_before\_forum\_freshness\_link' );function jc\_before\_forum\_freshness\_link() {     echo 'Hello world!';}
Note: Always remember to prefix your functions to avoid conflicts!
