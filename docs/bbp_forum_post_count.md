---
title: "bbp_forum_post_count"
post_status: publish
post_name: bbp_forum_post_count
lang: en
taxonomy:
  category: [bbpress]
  post_tag: [bbp-hooks]
source:
  blog_id: 4
  post_id: 45
  guid: "http://import.local/2021/12/24/bbp_forum_post_count/"
---

bbp\_forum\_post\_count
Codex Home → bbp\_forum\_post\_count
Description
The ‘bbp\_forum\_post\_count’ function is used to display the total count of all replies to topics within a forum and sub forums
How to use it
1
$forum\_id (optional) – Returns count for particular forum id
$total\_count (optional) – Returns total count for all replies in forum and sub forums by default or if true, otherwise returns total count for all replies in a forum not including replies in subforum(s)
Uses bbp\_get\_forum\_post\_count()
Sample code example
1
Displays the total count of all replies within a forum and sub forums
1
Displays the count of all replies within a forum excluding sub forums of parent forum
