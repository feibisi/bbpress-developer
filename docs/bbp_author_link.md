---
title: "bbp_author_link"
post_status: publish
post_name: bbp_author_link
lang: en
taxonomy:
  category: [bbpress]
  post_tag: [bbp-hooks]
source:
  blog_id: 4
  post_id: 52
  guid: "http://import.local/2021/12/24/bbp_author_link/"
---

bbp\_author\_link
Codex Home → bbp\_author\_link
Description
The ‘bbp\_author\_link’ function is used to display the most recently active author’s avatar and username linked to their profile
How to use it
$args (optional) – Accepts an array of arguments to configure display ( post\_id, link\_title, type, size )
Uses bbp\_get\_author\_link()
Sample code example
Displays the linked avatar and username for the most recently active author in a forum
1 ) ); ?>
Displays the most recently active user from the topic with an ID of 1
bbp\_get\_forum\_last\_active\_id(), 'size' => 32 ) ); ?>
Displays the most recently active user within the forum and sets their avatar to a size of 32px wide and 32px tall
bbp\_get\_forum\_last\_active\_id(), 'link\_title' => 'Author profile' ) ); ?>
Displays the most recently active user within the forum and sets the title of their linked avatar and username to “Author profile”
bbp\_get\_forum\_last\_active\_id(), 'type' => 'avatar' ) ); ?>
Displays only the most recently active user’s avatar without their display name
bbp\_get\_forum\_last\_active\_id(), 'type' => 'name' ) ); ?>
Displays only the most recently active user’s display name without their avatar
Related
bbp\_reply\_author\_link()
bbp\_topic\_author\_link()
