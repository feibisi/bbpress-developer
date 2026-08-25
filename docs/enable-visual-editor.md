---
title: "启用可视化编辑器"
post_status: publish
post_name: enable-visual-editor
lang: zh
taxonomy:
  category: [bbpress]
  post_tag: [bbp-hooks]
source:
  blog_id: 4
  post_id: 86
  guid: "http://import.local/2021/12/24/enable-visual-editor/"
---

在 bbPress 2.3.1 中，WordPress 的可视化编辑器默认为关闭。要重新打开它，请在插件或主题的 functions.php 文件中尝试以下代码片段：

```
function bbp_enable_visual_editor( $args = array() ) {
    $args['tinymce'] = true;
    return $args;
}
add_filter( 'bbp_after_get_the_content_parse_args', 'bbp_enable_visual_editor' );
```

您还可以通过在函数中添加更多参数来自定义可视化编辑器。
使用下面的此功能仅显示可视化编辑器，而根本不显示 html 编辑器。

```
function bbp_enable_visual_editor( $args = array() ) {
    $args['tinymce'] = true;
    $args['quicktags'] = false;
    return $args;
}
add_filter( 'bbp_after_get_the_content_parse_args', 'bbp_enable_visual_editor' );
```

如果您使用像[TinyMCE Advanced](https://wordpress.org/plugins/tinymce-advanced/)这样的插件，您还可以显示其他媒体按钮，如表情按钮以插入表情。
使用下面的这个函数代替添加新的参数，以便能够添加新的媒体，如表情按钮。

```
function bbp_enable_visual_editor( $args = array() ) {
    $args['tinymce'] = true;
    $args['teeny'] = false;
    return $args;
}
add_filter( 'bbp_after_get_the_content_parse_args', 'bbp_enable_visual_editor' );
```

请注意，如果您在可视化编辑器中禁用 teeny 模式并通过 TinyMCE Advanced 插件允许其他媒体按钮，您可能需要添加到此[功能](https://gist.github.com/ntwb/7797990)并将其放入您的子主题 functions.php 文件中，以允许您的用户使用一些按钮，如表格按钮。
在某些情况下，粘贴到可视化编辑器中的文本会带来不需要的样式和 HTML 标记。您可以使用另一个函数来强制清除粘贴的文本。这将删除诸如杂散 HTML 之类的内容，但保留粗体和斜体等基础知识。

```
function bbp_tinymce_paste_plain_text( $plugins = array() ) {
    $plugins[] = 'paste';
    return $plugins;
}
add_filter( 'bbp_get_tiny_mce_plugins', 'bbp_tinymce_paste_plain_text' );
```
