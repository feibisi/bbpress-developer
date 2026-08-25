---
title: "开始修改主要 bbPress 模板"
post_status: publish
post_name: getting-started-in-modifying-the-main-bbpress-template
lang: zh
taxonomy:
  category: [bbpress]
  post_tag: [bbp-theme]
source:
  blog_id: 4
  post_id: 83
  guid: "http://import.local/2021/12/24/getting-started-in-modifying-the-main-bbpress-template/"
---

**此页面的目标受众是基本熟悉编辑 WordPress 主题模板的人。**
如果您只是选择 bbPress 并且想要对正在呈现的模板进行一些基本更改，例如删除 WordPress 评论代码或任何仅应在博客文章中显示的帖子元，那么请按照本指南进行操作。
在 bbPress 的普通安装中，该插件会从您当前活动的 WordPress 主题中查找以下模板，并将论坛“注入”到它找到的第一个模板中。
它将找到具有下面列出的名称的任何页面模板。

- plugin-bbpress.php
- bbpress.php
- forums.php
- forum.php
- generic.php
- page.php
- single.php
- singular.php
- index.php

对于 WordPress 主题，最常见的是将论坛代码注入 page.php 文件。要找到确切的文件，请安装插件[What The File](https://wordpress.org/plugins/what-the-file/)并转到您网站的 bbPress 论坛部分并检查您的 WordPress 工具栏，看看要修改的确切文件是什么。
然后您可以复制您找到的文件并将其重命名为上面列出的任何文件名，并确保它位于您的主题根目录中。
wp-content/themes/%mytheme%/bbpress.php 其中 %mytheme% 是您当前活动主题的名称。
建议使用子主题，以免在下次更新主题时丢失任何更改。
毕竟，您可以自定义新的 bbpress.php 文件以删除任何不需要的代码/设计您的 bbPress 论坛，bbPress 插件应该选择该模板并使用该自定义模板呈现其所有页面。
示例模板
**不要只是将此代码复制并粘贴到空白模板中。所有的主题都不一样。将其用作指南。**
请阅读代码中的注释。

```
php
 
/*
*
* The template for displaying all bbPress pages
*
* This is the template that displays all bbPress pages by default.
* Please note that this is the template of all bbPress pages
* and that other 'pages' on your WordPress site will use a
* different template.
*
* @package WordPress
* @subpackage Theme
*/
 
 
/*
Self explanatory its a functions that gets your header template.
*/
 
get_header(); ?
 
 
php
/*
Surrounding Classes for the site
 
These are different every theme and help with structure and layout
 
These could be SPANs or DIVs and with entirely different classes.
*/
?

php
/*
Start the Loop
*/
?
 
php while ( have_posts() ) : the_post(); ?
 
 
php
/*
This is the start of the page and also the insertion of the post classes.
 
Post classes are very handy to style your forums.
*/
?

>
 
 
php
/*
This is the title wrapped in a header tag
 
and a class to better style the title for your theme
*/
?
 

# php the_title(); ?

 
 
php
/*
This is the content wrapped in a div
 
and class to better style the content
*/
?

php the_content(); ?

 
 
php
/*
End of Page
*/
?

php endwhile; // end of the loop. ?

 
 
php
/*
This is code to display the sidebar and the footer.
 
Remove the sidebar code to get full-width forums.
 
This would also need CSS to make it actually full width.
*/
?
 
php get_sidebar(); ?
php get_footer(); ?
```

为 bbPress 论坛呈现自定义模板代码的另一种方法是在PHP if 语句中使用条件标记，例如is\_bbpress()。
这是一个例子。

```
php if ( is_bbpress() ) : ?

This content should show if it is bbPress

php else : ?

This should show if it is not bbPress

php endif; ?
```
