---
title: "bbp_setup_current_user 被错误调用"
post_status: publish
post_name: bbp_setup_current_user-was-called-incorrectly
lang: zh
taxonomy:
  category: [bbpress]
  post_tag: [bbp-hooks]
source:
  blog_id: 4
  post_id: 170
  guid: "http://import.local/2021/12/24/bbp_setup_current_user-was-called-incorrectly/"
---

当该调试通知被触发 WP\_DEBUG 常量定义为true\*不是\*的bbPress其他试图访问一些关于当前用户和插件之前 $wp->init()和/或init动作已经取消 wp-settings.php 。
该通知是为了提醒您 bbPress 被强制进入可能导致其他（可能严重的）访问控制问题的配置，WordPress 没有钩子可以让 bbPress 正确规避或恢复到安全操作条件。
不幸的是，很难从 bbPress 中确切地确定是什么其他插件导致了这种情况发生，因此bbp\_setup\_current\_user出现在日志中。
此外，没有任何 wp\_set\_current\_user 操作；该wp\_set\_current\_user()功能是在 WordPress 2.0.3 中引入的，set\_current\_user为了向后兼容，该操作仍然存在。
也可以看看：

- [#WP24169](https://core.trac.wordpress.org/ticket/24169)关于定制器也做错了
- [#WP23106](https://core.trac.wordpress.org/ticket/23106)关于添加一个动作以允许插件可靠地连接和修复功能
- 这个 WordPress 加载顺序问题导致了许多[bbPress Trac 票证](https://bbpress.trac.wordpress.org/search?q=bbp_setup_current_user)
