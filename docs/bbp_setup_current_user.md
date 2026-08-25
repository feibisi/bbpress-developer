---
title: "bbp_setup_current_user"
post_status: publish
post_name: bbp_setup_current_user
lang: zh
taxonomy:
  category: [bbpress]
  post_tag: [bbp-hooks]
source:
  blog_id: 4
  post_id: 169
  guid: "http://import.local/2021/12/24/bbp_setup_current_user/"
---

该bbp\_setup\_current\_user()函数与 WordPress 的set\_current\_user操作相关联。在内部，它只调用bbp\_setup\_current\_user动作，bbPress 使用该动作向希望挂钩 bbPress 用户功能的第三方插件宣布自己。
这有点黑客技巧，因为插件依赖项在 WordPress 中不存在，但它仍然是定位 bbPress 并专门为其创建插件的绝佳方式。
