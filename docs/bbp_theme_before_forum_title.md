---
title: "bbp_theme_before_forum_title"
post_status: publish
post_name: bbp_theme_before_forum_title
lang: en
taxonomy:
  category: [bbpress]
  post_tag: [bbp-hooks]
source:
  blog_id: 4
  post_id: 33
  guid: "http://import.local/2021/12/24/bbp_theme_before_forum_title/"
---

bbp\_theme\_before\_forum\_title
Codex Home → bbp\_theme\_before\_forum\_title
Description
The ‘bbp\_theme\_before\_forum\_title’ action is used to display content before each forum title on the forum index pages.
Where it can be found
On line 16 of
/bbp-theme-compat/bbpress/loop-single-forum.php
/bbp-themes/bbp-twentyten/bbpress/loop-single-forum.php
How to use it
Since this is an action, we can use add\_action to hook into it.
Sample code example
1234add\_action( 'bbp\_theme\_before\_forum\_title', 'jc\_before\_forum\_title' );function jc\_before\_forum\_title() {     echo 'Hello world!';}
Note: Always remember to prefix your functions to avoid conflicts!
