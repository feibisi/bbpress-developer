---
title: "bbp_forum_row_actions"
post_status: publish
post_name: bbp_forum_row_actions
lang: en
taxonomy:
  category: [bbpress]
  post_tag: [bbp-hooks]
source:
  blog_id: 4
  post_id: 39
  guid: "http://import.local/2021/12/24/bbp_forum_row_actions/"
---

bbp\_forum\_row\_actions
Codex Home → bbp\_forum\_row\_actions
Description
The ‘bbp\_forum\_row\_actions’ action is used to display content within forum topic rows for functions such as administrative shortcuts.
Where it can be found
Line 453 and 454
/includes/forums/template.php
function bbp\_forum\_row\_actions() {
do\_action( 'bbp\_forum\_row\_actions' );
}
Line 48
/templates/default/bbpress/loop-single-forum.php
How to use it
Since this is an action, we can use add\_action to hook into it.
Sample code example
add\_action( 'bbp\_forum\_row\_actions', 'jc\_forum\_row\_actions' );
function jc\_forum\_row\_actions($action) {
$action = edit\_post\_link( 'Edit forum' );
return $action;
}
This will display a link to edit each forum, if a user is logged in and able to make edits.
Note: Always remember to prefix your functions to avoid conflicts!
