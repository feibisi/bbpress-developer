---
title: "bbp_theme_before_forum_sub_forums"
post_status: publish
post_name: bbp_theme_before_forum_sub_forums
lang: en
taxonomy:
  category: [bbpress]
  post_tag: [bbp-hooks]
source:
  blog_id: 4
  post_id: 35
  guid: "http://import.local/2021/12/24/bbp_theme_before_forum_sub_forums/"
---

bbp\_theme\_before\_forum\_sub\_forums
Codex Home → bbp\_theme\_before\_forum\_sub\_forums
Description
The ‘bbp\_theme\_before\_forum\_sub\_forums’ action is used to display content before each list of sub forum links.
Where it can be found
On line 22 of
/bbp-theme-compat/bbpress/loop-single-forum.php
/bbp-themes/bbp-twentyten/bbpress/loop-single-forum.php
1
How to use it
Since this is an action, we can use add\_action to hook into it.
Sample code example
1234add\_action( 'bbp\_theme\_before\_forum\_sub\_forums', 'jc\_before\_sub\_forum\_list' );function jc\_before\_sub\_forum\_list() {     echo 'Hello world!';}
Note: Always remember to prefix your functions to avoid conflicts!
