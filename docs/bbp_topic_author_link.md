---
title: "bbp_topic_author_link"
post_status: publish
post_name: bbp_topic_author_link
lang: en
taxonomy:
  category: [bbpress]
  post_tag: [bbp-hooks]
source:
  blog_id: 4
  post_id: 109
  guid: "http://import.local/2021/12/24/bbp_topic_author_link/"
---

bbp\_topic\_author\_link
Codex Home → bbp\_topic\_author\_link
Description
The ‘bbp\_topic\_author\_link’ function is used to display the current topic author’s user role, avatar and username linked to their profile
Where is it used
Templates: content-single-topic-lead.php
How to use it
$args (optional) – Accepts an array of arguments to configure display ( post\_id, link\_title, type, size, sep, show\_role )
Uses bbp\_get\_topic\_author\_link()
Sample code example
Displays the linked avatar and username for the current topic author
'  
', 'show\_role' => true ) ); ?>
Displays the current topic author and user role separated by an HTML   
 element
'  
', 'show\_role' => true, 'size' => 32 ) ); ?>
Displays the current topic author and user role separated by an HTML   
 element and sets their avatar to a size of 32px wide and 32px tall
'  
', 'show\_role' => false, 'type' => 'avatar' ) ); ?>
Displays only the current topic author user’s avatar without their display name or user role
'  
', 'show\_role' => false, 'type' => 'name' ) ); ?>
Displays only the current topic author user’s display name without their avatar or user role
Related
bbp\_author\_link()
bbp\_reply\_author\_link()
bbp\_show\_lead\_topic()
