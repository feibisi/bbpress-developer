---
title: "Custom Capabilities"
post_status: publish
post_name: custom-capabilities
lang: en
taxonomy:
  category: [bbpress]
  post_tag: [bbp-hooks]
source:
  blog_id: 4
  post_id: 119
  guid: "http://import.local/2021/12/24/custom-capabilities/"
---

Custom Capabilities
Codex Home → Custom Capabilities
Whilst bbPress provides a good set of forum roles, with distinct capabilities, you may want to amend these or add new names.
However the latest combination of WordPress and bbPress does not work if the code to do this is in the functions.php file of the child theme (or indeed parent theme!).
If you put this code in a plugin, it seems to work fine.
If you are comfortable in changing files and FTPing them to your site, then visit bbpress role adder – Robin W’s website (rewweb.co.uk) for a plugin and template that should work
Adding new names
At the simplest levels, you can add a new role name and give it existing capabilities
This can be useful just for your own admin purposes, but also if like me you hate the “keymaster” role name, just create a new role and give it keymaster capabilities.
The following code creates three new roles with names ‘name 1′,’name 2′ and ‘name 3′ the first role has participant, the second moderator and the third keymaster.
Simply amend the code to create as many roles with whatever capabilities you need
add\_action (‘wp\_loaded’ , ‘load\_new\_roles’) ;
function load\_new\_roles ()
{
add\_filter( ‘bbp\_get\_dynamic\_roles’, ‘add\_custom\_role’, 1 );
}
function add\_custom\_role( $bbp\_roles )
{
$bbp\_roles[‘my\_custom\_role1’] = array(
‘name’ =>’name 1′,
‘capabilities’ =>bbp\_get\_caps\_for\_role( bbp\_get\_participant\_role() ) // the same capabilities as participants
);
$bbp\_roles[‘my\_custom\_role2’] = array(
‘name’ =>’name 2′,
‘capabilities’ =>bbp\_get\_caps\_for\_role( bbp\_get\_participant\_role() ) // the same capabilities as participants
);
$bbp\_roles[‘my\_custom\_role3’] = array(
‘name’ =>’name 3′,
‘capabilities’ =>bbp\_get\_caps\_for\_role( bbp\_get\_keymaster\_role() ) // the same capabilities as keymaster
);
return $bbp\_roles;
}
Creating new roles
If you want to add a new roles with specific capabilities, then you can add these
The code below adds a role called ‘tutor’ simply change the word tutor wherever it occurs to the name you want and decide what capabilities you want to the role to have.
//code to add tutor role
add\_action ('wp\_loaded' , 'load\_new\_roles') ;
function load\_new\_roles ()
{
add\_filter( 'bbp\_get\_dynamic\_roles', 'add\_new\_roles', 1 );
add\_filter( 'bbp\_get\_caps\_for\_role', 'add\_role\_caps\_filter', 10, 2 );
}
function add\_new\_roles( $bbp\_roles )
{
/\* Add a role called tutor \*/
$bbp\_roles['bbp\_tutor'] = array(
'name' =>'Tutor',
'capabilities' =>custom\_capabilities( 'bbp\_tutor' )
);
return $bbp\_roles;
}
function add\_role\_caps\_filter( $caps, $role )
{
/\* Only filter for roles we are interested in! \*/
if( $role == 'bbp\_tutor' )
$caps = custom\_capabilities( $role );
return $caps;
}
function custom\_capabilities( $role )
{
switch ( $role )
{
/\* Capabilities for 'tutor' role \*/
case 'bbp\_tutor':
return array(
// Primary caps
'spectate' => true,
'participate' => true,
'moderate' => false,
'throttle' => false,
'view\_trash' =>false,
// Forum caps
'publish\_forums' =>false,
'edit\_forums' => false,
'edit\_others\_forums' => false,
'delete\_forums' => false,
'delete\_others\_forums' => false,
'read\_private\_forums' => true,
'read\_hidden\_forums' => false,
// Topic caps
'publish\_topics' => true,
'edit\_topics' => true,
'edit\_others\_topics' => false,
'delete\_topics' => false,
'delete\_others\_topics' => false,
'read\_private\_topics' => true,
// Reply caps
'publish\_replies' => true,
'edit\_replies' => true,
'edit\_others\_replies' => false,
'delete\_replies' => false,
'delete\_others\_replies' => false,
'read\_private\_replies' => true,
// Topic tag caps
'manage\_topic\_tags' => false,
'edit\_topic\_tags' => false,
'delete\_topic\_tags' => false,
'assign\_topic\_tags' => true,
);
break;
default :
return $role;
}
}
The code below adds two roles, tutor and pupil. Using this you should be able to add any number of roles
add\_action ('wp\_loaded' , 'load\_new\_roles') ;
function load\_new\_roles () {
add\_filter( 'bbp\_get\_dynamic\_roles', 'add\_new\_roles', 1 );
add\_filter( 'bbp\_get\_caps\_for\_role', 'add\_role\_caps\_filter', 10, 2 );
}
function add\_new\_roles( $bbp\_roles )
{
/\* Add a role called tutor \*/
$bbp\_roles['bbp\_tutor'] = array(
'name' =>'Tutor',
'capabilities' =>custom\_capabilities( 'bbp\_tutor' )
);
/\* Add a role called pupil \*/
$bbp\_roles['bbp\_pupil'] = array(
'name' =>'Pupil',
'capabilities' =>custom\_capabilities( 'bbp\_pupil' )
);
return $bbp\_roles;
}
function add\_role\_caps\_filter( $caps, $role )
{
/\* Only filter for roles we are interested in! \*/
if( $role == 'bbp\_tutor' )
$caps = custom\_capabilities( $role );
if( $role == 'bbp\_pupil' )
$caps = custom\_capabilities( $role );
return $caps;
}
function custom\_capabilities( $role )
{
switch ( $role )
{
/\* Capabilities for 'tutor' role \*/
case 'bbp\_tutor':
return array(
// Primary caps
'spectate' => true,
'participate' => true,
'moderate' => false,
'throttle' => false,
'view\_trash' =>false,
// Forum caps
'publish\_forums' => false,
'edit\_forums' => false,
'edit\_others\_forums' => false,
'delete\_forums' => false,
'delete\_others\_forums' => false,
'read\_private\_forums' => true,
'read\_hidden\_forums' => false,
// Topic caps
'publish\_topics' => true,
'edit\_topics' => true,
'edit\_others\_topics' => false,
'delete\_topics' => false,
'delete\_others\_topics' => false,
'read\_private\_topics' => true,
// Reply caps
'publish\_replies' => true,
'edit\_replies' => true,
'edit\_others\_replies' => false,
'delete\_replies' => false,
'delete\_others\_replies' => false,
'read\_private\_replies' => true,
// Topic tag caps
'manage\_topic\_tags' => false,
'edit\_topic\_tags' => false,
'delete\_topic\_tags' => false,
'assign\_topic\_tags' => true,
);
/\* Capabilities for 'pupil' role \*/
case 'bbp\_pupil':
return array(
// Primary caps
'spectate' => true,
'participate' => true,
'moderate' => false,
'throttle' => false,
'view\_trash' => false,
// Forum caps
'publish\_forums' => false,
'edit\_forums' => false,
'edit\_others\_forums' => false,
'delete\_forums' => false,
'delete\_others\_forums' => false,
'read\_private\_forums' => true,
'read\_hidden\_forums' => false,
// Topic caps
'publish\_topics' => true,
'edit\_topics' => true,
'edit\_others\_topics' => false,
'delete\_topics' => false,
'delete\_others\_topics' => false,
'read\_private\_topics' => true,
// Reply caps
'publish\_replies' => true,
'edit\_replies' => true,
'edit\_others\_replies' => false,
'delete\_replies' => false,
'delete\_others\_replies' => false,
'read\_private\_replies' => true,
// Topic tag caps
'manage\_topic\_tags' => false,
'edit\_topic\_tags' => false,
'delete\_topic\_tags' => false,
'assign\_topic\_tags' => true,
);
break;
default :
return $role;
}
}
