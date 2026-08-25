---
title: "bbp_reply_author_link"
post_status: publish
post_name: bbp_reply_author_link
lang: en
taxonomy:
  category: [bbpress]
  post_tag: [bbp-hooks]
source:
  blog_id: 4
  post_id: 108
  guid: "http://import.local/2021/12/24/bbp_reply_author_link/"
---

bbp\_reply\_author\_link
Codex Home → bbp\_reply\_author\_link
Description
The ‘bbp\_reply\_author\_link’ function is used to display the current reply author’s user role, avatar and username linked to their profile
Where is it used
Templates: loop-single-reply.php loop-search-reply.php
How to use it
1
$args (optional) – Accepts an array of arguments to configure display ( post\_id, link\_title, type, size, sep, show\_role )
Uses bbp\_get\_reply\_author\_link()
Sample code example
1
Displays the linked avatar and username for the current reply author
1 '  
', 'show\_role' => true ) ); ?>
Displays the current reply author and user role separated by an HTML   
 element
1 '  
', 'show\_role' => true, 'size' => 32 ) ); ?>
Displays the current reply author and user role separated by an HTML   
 element and sets their avatar to a size of 32px wide and 32px tall
1 '  
', 'show\_role' => false, 'type' => 'avatar' ) ); ?>
Displays only the current reply author user’s avatar without their display name or user role
1 '  
', 'show\_role' => false, 'type' => 'name' ) ); ?>
Displays only the current reply author user’s display name without their avatar or user role
Related
bbp\_author\_link()
bbp\_topic\_author\_link()
