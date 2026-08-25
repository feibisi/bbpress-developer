---
title: "主题兼容性"
post_status: publish
post_name: theme-compatibility
lang: zh
taxonomy:
  category: [bbpress]
  post_tag: [bbp-theme]
source:
  blog_id: 4
  post_id: 58
  guid: "http://import.local/2021/12/24/theme-compatibility/"
---

bbPress 2.x 具有内置主题支持。包括所有必需的元素，例如前端编辑。这意味着所有功能都可以使用，即使主题没有包含特定的 bbPress 模板或代码。
可以使用主题或其他插件覆盖所有 bbPress 兼容。检查 bbp-theme-compat[模板包装器](https://codex.wordpress.org/Function_Reference/get_template_part "主题包装器")以了解正常主题应包含的内容。
自定义 bbPress：
“wp-content/plugins/bbpress/templates/default/”目录包含“bbpress”、“css”、“extras”和“js”目录，以及“bbpress-functions.php”文件.

- “bbpress”目录包含模板部分。将它们中的任何一个复制到主题根目录中名为“bbpress”的目录中，因此它看起来像：`/wp-content/themes/%your-theme%/bbpress/`
- “extras”目录包含可选的根级页面模板，使定制时的生活更轻松；将您要使用或修改的任何内容复制到主题的根目录中。例如。`/wp-content/themes/%your-theme%/`
- “css”目录包含使用默认标记的样式表。将您要修改的任何内容复制到主题根目录中名为“css”的目录中。例如。`/wp-content/themes/%your-theme%/css/`
- 基本上，您可以将整个 'bbpress' 和 'css' 目录从 bbPress 的默认模板目录中复制到您的主题中，而 bbPress 将使用位于您的主题内的目录。很整洁，嗯？
