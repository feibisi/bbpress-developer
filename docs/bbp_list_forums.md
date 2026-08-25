---
title: "bbp_list_forums"
post_status: publish
post_name: bbp_list_forums
lang: en
taxonomy:
  category: [bbpress]
  post_tag: [bbp-hooks]
source:
  blog_id: 4
  post_id: 32
  guid: "http://import.local/2021/12/24/bbp_list_forums/"
---

bbp\_list\_forums
Codex Home → bbp\_list\_forums
The bbp\_list\_forums function is commonly used to display a list of sub forums. You can customise the returned data by passing the function some arguments.
The bbp\_list\_forums is a function located in includesforumstemplate.php.
To filter this array use:
add\_filter( 'bbp\_before\_list\_forums\_parse\_args', 'your\_filter\_name' );
An example list of arguments
array (
'before' => '

',
'after' => '
',
'link\_before' => '- ',
  'link\_after' => '
',
'count\_before' => ' (',
'count\_after' => ')',
'count\_sep' => ', ',
'separator' => ', ',
'forum\_id' => '',
'show\_topic\_count' => true,
'show\_reply\_count' => true,
)
before
The value you specify for ‘before’ will be put at the start of the returned data.
after
The value you specify for ‘after’ will be put at the end of the returned data.
link\_before
The value you specify for ‘link\_before’ will appear before each row returned in the data.
link\_after
The value you specify for ‘link\_after’ will appear after each row returned in the data.
count\_before
If you have show\_topic\_count or show\_reply\_count set to true, then this will attach itself to the start of each count.
count\_after
If you have show\_topic\_count or show\_reply\_count set to true, then this will attach itself to the end of each count.
count\_sep
The value specified inside count\_sep is what separates each count, for example if you specified a comma the returned count would be: 0,0
separator
The value specified inside separator is what separates each subforum, for example if you specified   
 the returned subforums would be displayed one per line.
forum\_id
If you specify a forum\_id then only child forums of the forum\_id will be returned.
show\_topic\_count
This is a boolean flag, set it to true or false depending on if you want topic counts to be returned.
show\_reply\_count
This is a boolean flag, set it to true or false depending on if you want reply counts to be returned.
Common Code Examples
bbp\_list\_forums(array (
'before' => '|',
'after' => '
',
'link\_before' => ' ', 'link\_after' => ' |',
'separator' => '',
));
Returns a list of forums without the comma between reply and topic counts.
bbp\_list\_forums(array (
'before' => '|',
'after' => '
',
'link\_before' => ' ', 'link\_after' => ' |',
'separator' => '',
'count\_before' => '',
'count\_after' => '',
));
Returns a list of forums without the comma between and the brackets around the reply and topic counts.
