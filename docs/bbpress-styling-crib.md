---
title: "bbPress 样式参考"
post_status: publish
post_name: bbpress-styling-crib
lang: mixed
taxonomy:
  category: [bbpress]
  post_tag: [bbp-theme]
source:
  blog_id: 4
  post_id: 102
  guid: "http://import.local/2021/12/24/bbpress-styling-crib/"
---

本指南将向您展示新 bbPress 论坛的区域，您可以使用 CSS 以及 bbPress 插件中使用的类和选择器来设置每个区域的样式。

### [设计您的论坛](#styling-your-forums)

这些可以添加到您的 css 中，或添加到 bbpress.css 的自定义版本中 – 请参阅[设置 bbpress 论坛的分步指南第 2 部分](/document/bbpress/step-by-step-guide-to-setting-up-a-bbpress-forum-part-2/)了解更多信息。
![论坛婴儿床](/_images/forum-crib.webp)
![论坛](/_images/foruma.webp)
bbPress 论坛中的所有内容
这是用于 bbPress 论坛所有部分的 CSS。根据您的需要增加字体大小。

```
#bbpress-forums {
background: transparent;
clear: both;
margin-bottom: 20px;
overflow: hidden;
font-size: 12px;
}
```

1. 论坛页眉和页脚
这是显示作者、帖子和声音等标签的内容。

```
#bbpress-forums li.bbp-header,
#bbpress-forums li.bbp-footer {
 background: #f3f3f3;
 border-top: 1px solid #eee;
 font-weight: bold;
 padding: 8px;
 text-align: center;
}

#bbpress-forums li.bbp-header {
 background: #eaeaea;
}
```

2. 回复标题

```
#bbpress-forums div.bbp-reply-header {
    background-color: #f4f4f4;
}
```

3.模板通知信息

```
div.bbp-template-notice.info {
    border: #cee1ef 1px solid;
    background-color: #f0f8ff;
}
```

4. 话题/回复背景
赔率，即使如此回复也有交替的颜色

```
#bbpress-forums div.even,
#bbpress-forums ul.even {
 background-color: #fff;
}

#bbpress-forums div.odd,
#bbpress-forums ul.odd {
 background-color: #fbfbfb;
}
```

如果话题很粘或超级粘，那么

```
.bbp-topics-front ul.super-sticky,
.bbp-topics ul.super-sticky,
.bbp-topics ul.sticky,
.bbp-forum-content ul.sticky {
 background-color: #ffffe0 !important;
 font-size: 1.1em;
}
```

自定义关闭话题文本的颜色。

```
#bbpress-forums .status-closed,
#bbpress-forums .status-closed a {
 color: #ccc;
}
```

每个线程的线程回复边距。

```
#bbpress-forums ul.bbp-threaded-replies {
 margin-left: 50px;
}
```

5. 各种文字
这些通常继承自您的主题。
但是，您可以使用修改内容

```
#bbpress-forums .bbp-topic-content,
#bbpress-forums .bbp-reply-content {
    font-size: 12px;
}
```

上面的代码不在 bbpress.css 中，因此如果需要，请添加它，或放入您的 .css 中，请参阅顶部提到的指南以获取更多信息
6. 管理链接

```
span.bbp-admin-links {
 float: right;
 color: #ddd;
}

span.bbp-admin-links a {
 color: #bbb;
 font-weight: normal;
 font-size: 10px;
 text-transform: uppercase;
 text-decoration: none;
}
```

7. 模板通知

```
div.bbp-template-notice,
div.indicator-hint {
 border-width: 1px;
 border-style: solid;
 padding: 0 0.6em;
 margin: 5px 0 15px;
 border-radius: 3px;
 background-color: #ffffe0;
 border-color: #e6db55;
 color: #000;
 clear: both;
}
div.bbp-template-notice a {
 color: #555;
 text-decoration: none;
}
 div.bbp-template-notice a:hover {
 color: #000;
 }
 div.bbp-template-notice.info {
 border: #cee1ef 1px solid;
 background-color: #f0f8ff;
 }
 div.bbp-template-notice.important {
 border: #e6db55 1px solid;
 background-color: #fffbcc;
 }
 div.bbp-template-notice.error,
 div.bbp-template-notice.warning {
 background-color: #ffebe8;
 border-color: #c00;
 }
 div.bbp-template-notice.error a,
 div.bbp-template-notice.warning a {
 color: #c00;
 }
 div.bbp-template-notice p {
 margin: 0.5em 0 6px 0 !important;
 padding: 2px;
 font-size: 12px;
 line-height: 140%;
 }
```

8.从您的主题继承的面包屑和链接颜色
9. 其他造型功能
9.1 提交按钮
正在寻找一种方法来更改 bbpress、更大、颜色中的提交按钮......？

```
#bbpress-forums .submit {
    background-color: #a0668d;
    color: #FFFFFF;
    float: center;
    vertical-align: middle;
    border-radius: 10px;
    height: 35px;
    width: 80px;
    font-size: 18px;
}
```

并更改为您想要的！
10.从最近的话题小工具和新鲜度中删除头像

```
widget_display_topics .bbp-author-avatar {
    display: none ! important;
}

.bbp-topic-freshness-author  .bbp-author-avatar {
    display: none ! important;
}
```
