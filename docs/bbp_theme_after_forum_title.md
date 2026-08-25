---
title: "bbp_theme_after_forum_title"
post_status: publish
post_name: bbp_theme_after_forum_title
lang: en
taxonomy:
  category: [bbpress]
  post_tag: [bbp-hooks]
source:
  blog_id: 4
  post_id: 34
  guid: "http://import.local/2021/12/24/bbp_theme_after_forum_title/"
---

bbp\_theme\_after\_forum\_title
Codex Home → bbp\_theme\_after\_forum\_title
Description
The ‘bbp\_theme\_after\_forum\_title’ action is used to display content after each forum title on the forum index pages.
Where it can be found
On line 20 of
/bbp-theme-compat/bbpress/loop-single-forum.php
/bbp-themes/bbp-twentyten/bbpress/loop-single-forum.php
How to use it
Since this is an action, we can use add\_action to hook into it.
Sample code example
add\_action( 'bbp\_theme\_after\_forum\_title', 'jc\_after\_forum\_title' );
function jc\_after\_forum\_title() {
echo 'Hello world!';
}
Note: Always remember to prefix your functions to avoid conflicts!
