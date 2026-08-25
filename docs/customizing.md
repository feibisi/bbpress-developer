---
title: "定制"
post_status: publish
post_name: customizing
lang: zh
taxonomy:
  category: [bbpress]
  post_tag: [bbp-theme]
source:
  blog_id: 4
  post_id: 138
  guid: "http://import.local/2021/12/24/customizing/"
---

有很多方法可以通过样式设置或仅向您的站点添加额外功能来自定义您的 bbPress，因此请继续学习如何自定义您的 bbPress 论坛。

### [安装插件](/document/bbpress/installing-plugins/ "您需要了解的有关 bbPress 入门的所有信息")

bbPress 带有许多插件来扩展 bbPress 论坛的功能。无论您是想要更好的支持论坛功能，还是只是通过投票或引用来增强社区体验。您可以在[bbpress.org](https://bbpress.org/plugins/)或[wordpress.org](https://wordpress.org/plugins/search.php?q=bbpress)的插件部分中搜索大量 bbPress 插件。

### 开发插件

您也可以决定为您的 bbPress 论坛创建一个自定义的 bbPress 插件，所以希望这个链接列表能帮助您做到这一点。

- [编写插件](https://codex.wordpress.org/Writing_a_Plugin)
- [插件API](https://codex.wordpress.org/Plugin_API)
- [add\_meta\_box](https://codex.wordpress.org/Function_Reference/add_meta_box)
- [使用操作](/document/bbpress/step-by-step-guide-to-setting-up-a-bbpress-forum-part-4/)和[add\_action](https://codex.wordpress.org/Function_Reference/add_action)
- [使用过滤器](/document/bbpress/step-by-step-guide-to-setting-up-a-bbpress-forum-part-5/)和[add\_filter](https://codex.wordpress.org/Function_Reference/add_filter)
- [钩子列表](http://hookr.io/plugins/bbpress/2.5.6/hooks/#index=a)
- [过滤器列表](http://hookr.io/plugins/bbpress/2.5.6/filters/#index=a)

您还可以分叉或贡献任何现有的 bbPress 插件。

### [安装主题](/document/bbpress/installing-themes/ "您需要了解的有关 bbPress 入门的所有信息")

虽然 bbPress 可以处理大多数主题，但可能需要一些工作才能这样做。安装主题时，建议您找到一个支持 bbPress 的 WordPress 主题。

### 开发主题

无论是为 bbPress 创建子主题还是您自己的自定义主题，创建主题都将为您提供最大的灵活性来自定义 bbPress。

- [创建子主题](https://codex.wordpress.org/Child_Themes)和[子主题和函数文件说明](/developer/bbpress/functions-files-and-child-themes-explained/)
- [主题开发](https://codex.wordpress.org/Theme_Development)
- [主题兼容性](/developer/bbpress/theme-compatibility/)
- [修改主要 bbPress 模板](/developer/bbpress/getting-started-in-modifying-the-main-bbpress-template/)
- [修改模板](/developer/bbpress/amending-bbpress-templates/)
- [bbPress 条件标签](/developer/bbpress/bbpress-conditional-tags/)

自定义的其他步骤
添加代码片段
代码片段通常是一小段代码，可用于调整您的网站或为您的 bbPress 网站添加小而精巧的功能。这些片段需要放置在您的子主题的functions.php 文件或功能插件中。
有一部分用户提交的[代码片段](/developer/bbpress/layout-and-functionality-examples-you-can-use/)应该有助于向您的 bbPress 站点添加一些基本功能或调整。
该[bbPress的论坛](https://bbpress.org/forums/)提供了从社区来帮助您添加任何其他种类的额外功能添加到您的bbPress的网站很多代码片断。因此，您可能希望在论坛中进行搜索并尝试找到您要查找的内容。
许多 bbPress 代码片段可能会发布在许多代码粘贴站点，例如[Github 的 Gist](https://gist.github.com/search?q=bbpress)或[Pastebin](http://pastebin.com/search?cx=013305635491195529773%3A0ufpuq-fpt0&cof=FORID%3A10&ie=UTF-8&q=bbpress&sa.x=0&sa.y=0&sa=Search)，因此这些站点可能值得一看。
设计您的论坛
您可能想要修改 bbPress 的外观，那么 css 就是要走的路！建议从 bbPress 插件中复制 bbpress.css 文件并将其放置在名为“css”的文件夹中的子主题中，或者至少安装一个自定义 css 插件来放置小的 css 片段。希望列出的这些其他链接将帮助您更好地设计您的论坛。
