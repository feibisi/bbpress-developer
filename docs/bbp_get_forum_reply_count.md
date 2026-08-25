---
title: "bbp_get_forum_reply_count"
post_status: publish
post_name: bbp_get_forum_reply_count
lang: en
taxonomy:
  category: [bbpress]
  post_tag: [bbp-hooks]
source:
  blog_id: 4
  post_id: 44
  guid: "http://import.local/2021/12/24/bbp_get_forum_reply_count/"
---

bbp\_get\_forum\_reply\_count
Codex Home → bbp\_get\_forum\_reply\_count
Description
The ‘bbp\_get\_forum\_reply\_count’ function is used to return the total count of all replies to topics within a forum and sub forums
How to use it
$forum\_id (optional) – Returns count for particular forum id
$total\_count (optional) – Returns total count for all replies in forum and sub forums by default and returns total count for all replies in forum but not sub forums if true, must set $forum\_id to work if true
Used by bbp\_forum\_reply\_count()
Sample code example
Returns the total count of all replies within a forum and sub forums
Returns the count of all replies within a forum and not sub forums with a forum ID of 1
