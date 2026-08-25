---
title: "bbp_theme_before_forum_description"
post_status: publish
post_name: bbp_theme_before_forum_description
lang: en
taxonomy:
  category: [bbpress]
  post_tag: [bbp-hooks]
source:
  blog_id: 4
  post_id: 37
  guid: "http://import.local/2021/12/24/bbp_theme_before_forum_description/"
---

bbp\_theme\_before\_forum\_description
Codex Home → bbp\_theme\_before\_forum\_description
Description
The ‘bbp\_theme\_before\_forum\_description’ action is used to display content before the description of the forum on forum index pages.
Where it can be found
On line 28 of
/bbp-theme-compat/bbpress/loop-single-forum.php
/bbp-themes/bbp-twentyten/bbpress/loop-single-forum.php
1
How to use it
Since this is an action, we can use add\_action to hook into it.
Sample code example
1234add\_action( 'bbp\_theme\_before\_forum\_description', 'jc\_before\_forum\_description' );function jc\_before\_forum\_description() {     echo 'Hello world!';}
Note: Always remember to prefix your functions to avoid conflicts!
