---
title: "bbp_get_forum_topic_count"
post_status: publish
post_name: bbp_get_forum_topic_count
lang: en
taxonomy:
  category: [bbpress]
  post_tag: [bbp-hooks]
source:
  blog_id: 4
  post_id: 41
  guid: "http://import.local/2021/12/24/bbp_get_forum_topic_count/"
---

bbp\_get\_forum\_topic\_count
Codex Home → bbp\_get\_forum\_topic\_count
Description
The ‘bbp\_get\_forum\_topic\_count’ function is used to return the total topic count of a forum including sub forums.
How to use it
1
$forum\_id (optional) – Returns count for particular forum id
$total\_count (optional) – Returns the total topic count with true including sub forums or just topics within that forum with false
Used by bbp\_forum\_topic\_count() for displaying counts
Sample code example
1
Returns the total count of all topics within the current forum and sub forums
1
Returns the total count of all topics within the forum with an ID of 1
1
Returns the count of topics within the current forum not including topics in sub forums
