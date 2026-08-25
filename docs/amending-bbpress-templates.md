---
title: "修改 bbPress 模板"
post_status: publish
post_name: amending-bbpress-templates
lang: zh
taxonomy:
  category: [bbpress]
  post_tag: [bbp-theme]
source:
  blog_id: 4
  post_id: 129
  guid: "http://import.local/2021/12/24/amending-bbpress-templates/"
---

bbPress 有许多模板可以改变论坛的显示方式，您可以更改这些模板以完全改变论坛的显示方式。
您会在以下位置找到这些模板
`wp-content/plugins/bbpress/templates/default/bbpress/`
论坛的索引从使用开始
`content-archive-forum.php`
如果您打开它，您会看到他们使用函数 bbp\_get\_template\_part 调用了另一个模板
`php bbp_get_template_part( 'loop', 'forums'); ?`
（这转化为 loop-forums.php）
这反过来又叫
`php bbp_get_template_part( 'loop', 'single-forum'); ?`
（这转化为loop-single-forum）
等等。
如果您需要更改 bbpress 模板，那么您真的应该在子主题中执行此操作，否则主题升级将覆盖它。
有关如何设置子主题的信息，请参阅
[子主题和函数文件说明](/developer/bbpress/functions-files-and-child-themes-explained/)
更改模板
在您的主题中创建一个 bbPress 文件夹：
`wp-content/%yourthemename%/bbpress`
其中 `%yourthemename%` 是您的主题名称。
然后进入
`wp-content/plugins/bbpress/templates/default/bbpress/`
将您想要更改的任何文件复制到主题中的 bbPress 文件夹中。bbPress 现在将使用此文件而不是默认文件，您可以修改此文件。
