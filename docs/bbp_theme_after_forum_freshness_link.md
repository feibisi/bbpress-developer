---
title: "bbp_theme_after_forum_freshness_link"
post_status: publish
post_name: bbp_theme_after_forum_freshness_link
lang: en
taxonomy:
  category: [bbpress]
  post_tag: [bbp-hooks]
source:
  blog_id: 4
  post_id: 50
  guid: "http://import.local/2021/12/24/bbp_theme_after_forum_freshness_link/"
---

bbp\_theme\_after\_forum\_freshness\_link
Codex Home → bbp\_theme\_after\_forum\_freshness\_link
Description
The ‘bbp\_theme\_after\_forum\_freshness\_link’ action is used to display content after the forum freshness link
How to use it
Since this is an action, we can use add\_action to hook into it.
Sample code example
add\_action( 'bbp\_theme\_after\_forum\_freshness\_link', 'jc\_after\_forum\_freshness\_link' );
function jc\_after\_forum\_freshness\_link() {
echo 'Hello world!';
}
Note: Always remember to prefix your functions to avoid conflicts!
