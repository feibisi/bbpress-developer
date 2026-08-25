---
title: "bbp_forum_reply_count"
post_status: publish
post_name: bbp_forum_reply_count
lang: en
taxonomy:
  category: [bbpress]
  post_tag: [bbp-hooks]
source:
  blog_id: 4
  post_id: 43
  guid: "http://import.local/2021/12/24/bbp_forum_reply_count/"
---

bbp\_forum\_reply\_count
Codex Home → bbp\_forum\_reply\_count
Description
The ‘bbp\_forum\_reply\_count’ function is used to display the total count of all replies to topics within a forum and sub forums
How to use it
1
$forum\_id (optional) – Returns count for particular forum id
$total\_count (optional) – Returns total count for all replies in forum and sub forums by default and returns total count for all replies in forum but not sub forums if true, must set $forum\_id to work if true
Uses bbp\_get\_forum\_reply\_count()
Sample code example
1
Displays the total count of all replies within a forum and sub forums
1
Displays the count of all replies within a forum and not sub forums with a forum ID of 1
