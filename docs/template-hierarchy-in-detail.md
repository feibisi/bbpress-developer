---
title: "详细的模板层次结构"
post_status: publish
post_name: template-hierarchy-in-detail
lang: zh
taxonomy:
  category: [bbpress]
  post_tag: [bbp-theme]
source:
  blog_id: 4
  post_id: 139
  guid: "http://import.local/2021/12/24/template-hierarchy-in-detail/"
---

[撰写中…]

### 用户个人资料模板

single-user-[nicename].php // 单用户 nicename
single-user-[user\_id].php // 单用户 ID
single-user.php // 单用户
user.php // 用户

### 用户资料编辑模板

single-user-edit-[nicename].php // 单用户编辑 nicename
single-user- edit- [user\_id].php // 单用户编辑 ID
single-user-edit.php // 单用户编辑
user-edit. php // 用户编辑
user.php

### 用户收藏夹模板

single-user-favorites-[nicename].php // 单用户收藏 nicename
single-user-favorites-[user\_id].php // 单用户收藏 ID
favorites-[nicename].php // 收藏夹 nicename
favorites-[user\_id] .php // 收藏夹 ID
favorites.php // 收藏夹
user.php

### 用户订阅模板

single-user-subscriptions-[nicename].php // 单用户
single-user-subscriptions-[user\_id].php // 单用户
subscriptions-[nicename].php // 订阅 nicename
subscriptions-[user\_id] .php // 订阅 ID
subscriptions.php // 订阅
user.php

### 视图模板

single-view-[view\_id].php // 单视图 ID
view-[view\_id].php // 视图 ID
single-view.php // 单视图
view.php

### 搜索模板

page-forum-search.php // 单次搜索
forum-search.php // 搜索

### 单个论坛模板

single-[forum].php// 单个论坛

### 论坛存档模板

archive-[forum].php // 论坛存档

### 论坛编辑模板

single-[forum]-edit.php // 单个论坛编辑

### 单个话题模板

single-[topic].php

### 话题存档模板

archive-[topic].php // 话题存档

### 话题编辑模板

single-[topic]-edit.php // 单个话题编辑

### 话题拆分模板

single-topic-split.php // 话题拆分

### 话题合并模板

single-[topic]-merge.php // 话题合并

### 单个回复模板

single-[reply].php

### 回复编辑模板

single-[reply]-edit.php // 单个回复编辑

### 回复移动模板

single-[reply]-move.php // 回复移动

### 话题标签模板

taxonomy-[tt\_slug].php // 单话题标签 slug
taxonomy-[tt\_id].php // 单话题标签 ID

### 话题标签编辑模板

taxonomy-[tt\_slug]-edit.php // 单话题标签编辑 slug
taxonomy-[tt\_id]-edit.php // 单话题标签编辑 ID
