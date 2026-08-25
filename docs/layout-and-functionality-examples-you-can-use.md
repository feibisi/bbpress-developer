---
title: "布局和功能 - 您可以使用的示例"
post_status: publish
post_name: layout-and-functionality-examples-you-can-use
lang: zh
taxonomy:
  category: [bbpress]
  post_tag: [bbp-hooks]
source:
  blog_id: 4
  post_id: 103
  guid: "http://import.local/2021/12/24/layout-and-functionality-examples-you-can-use/"
---

您可以使用 WordPress 和 bbPress 提供的钩子和过滤器以多种方式自定义和扩展 WordPress 和 bbPress，还可以将一些 CSS 应用到您的论坛或主题。
下面是一些常用的自定义 PHP 和 CSS 代码片段列表，这些代码片段可能对社区用户自定义他们现有的 bbPress 论坛有用。
如果您发现列出的示例似乎不起作用，您想建议另一个有用的示例，或者使用不同/更好的方法来编辑当前的最终功能，然后请进入支持论坛并在论坛[请求和反馈](https://bbpress.org/forums/forum/requests-and-feedback/)。

### [1.更改论坛列表的显示方式](#1-change-how-the-forum-list-displays)

默认看起来像： ![论坛2](/_images/forum2.webp)
改成 ： ![论坛3](/_images/forum3.webp)
默认情况下，此元素使用 CSS 设置样式。

```
#bbpress-forums .bbp-forums-list li {
display: inline;
}
```

将此 CSS 代码片段粘贴到您的子主题的 style.css 并更改display:inline为display:block将实现此布局。
您也可以改用 PHP 代码片段，并将以下函数放入您的子主题 functions.php 文件中。

```
//create vertical list subforum layout
function custom_bbp_sub_forum_list() {
  $args['separator'] = '
';
  return $args;
}
 add_filter('bbp_after_list_forums_parse_args', 'custom_bbp_sub_forum_list' );
```

### [2.从论坛列表中删除话题/回复计数](#2-remove-the-topicreply-count-from-the-forum-list)

默认 ：
![论坛c](/_images/forumc.webp)
更改为：
![论坛b](/_images/forumb.webp)
您可以更改 loop.single.forum.php，如 https://codex.bbpress.org/step-by-step-guide-to-setting-up-a-bbpress-forum-part-3/ 所示或者
将以下内容放入您的子主题functions.php 文件中。

```
function remove_counts() {
    $args['show_topic_count'] = false;
    $args['show_reply_count'] = false;
    $args['count_sep'] = '';
return $args;
}
add_filter('bbp_before_list_forums_parse_args', 'remove_counts' );
```

### [3. 向登录小工具添加“修改个人资料/密码”](#3-adding-an-amend-profilepassword-to-the-login-widget)

虽然您可以单击 bbPress 登录小工具中显示的头像或您的用户名转到您的个人资料，然后从那里单击编辑链接来编辑您的个人资料，但这对您的某些用户来说可能并不那么明显。
安装这个插件[RKK Login Widget](https://gist.github.com/robkk/f558f4abe867ef7b9952)，它几乎与默认的 bbPress Login Widget 完全相同。只需将 (RKK) 登录小工具放置到侧边栏之一，您的登录小工具就会与此类似。
![论坛](/_images/forumd.webp)
根据需要自定义或编辑插件。

### [4. 关闭或更改面包屑](#4-turning-off-or-changing-breadcrumbs)

![](/_images/forume.webp)
要删除论坛中的面包屑，请确保将此功能添加到子主题或功能插件中的 functions.php 文件中。

```
add_filter( 'bbp_no_breadcrumb', '__return_true' );
```

要自定义您要显示的特定面包屑链接的布局，请将其添加到您的子主题 function.php 文件中。

```
function mycustom_breadcrumb_options() {
    // Home - default = true
    $args['include_home']    = false;
    // Forum root - default = true
    $args['include_root']    = false;
    // Current - default = true
    $args['include_current'] = true;

    return $args;
}
add_filter('bbp_before_get_breadcrumb_parse_args', 'mycustom_breadcrumb_options');
```

### [5. 移除论坛搜索功能](#5-remove-search-function-from-forums)

如果您想删除搜索栏（有些人喜欢要么排除它，要么把它放在侧边栏中）
默认情况下，搜索表单将显示如下。
![论坛](/_images/forumh.webp)
这是之后的结果。
![论坛](/_images/forumg.webp)
然后只需更改仪表盘>设置>论坛功能中的设置并取消勾选
Allow forumwide search。

### [6. bbpress后加载样式表](#6-loadthe-style-sheet-after-bbpress)

介绍：当WordPress加载样式表时，它们会先加载所有theme.css文件，然后再加载插件css。这样插件 css 的优先级高于您的 css，唯一可以覆盖它的方法是使用 !important。众所周知，这是一种不好的做法。
此外，您可以在您的主题中创建自己的 bbpress.css ，但这意味着需要处理更多文件（尽管这是最干净的解决方案）。这是执行此操作的另一种方法：
将此代码粘贴到您的子主题functions.php 文件中。

```
/** * load custom bbpress css after bbp default css */ wp_enqueue_style( 'custom-bbpress', get_stylesheet_directory_uri() . '/css/custom-bbpress.css',array('bbp-default'),'1.1','all');
```

### [7. 如何从模板中删除所有面包屑并将它们设置在页面顶部？](#7-how-can-i-remove-all-the-breadcrumbs-from-the-templates-and-set-them-at-the-top-of-the-page)

由 Markic 提交并感谢
简介：我们中的许多人正在使用标题中的现有面包屑系统创建自己的主题。但是 bbPress 有自己的想法在哪里显示面包屑，有时在页面顶部，有时在搜索表单下方，有时在标题下方。这是您可以快速更改的方法。
1. 如果还没有，请在主题的根文件夹中创建“bbpress.php”。
2. 添加

```
<div class="truebreadcrumbs"><?php bbp_breadcrumb(); ?></div>
```

3. 添加此 CSS：

```
div.bbp-breadcrumb {
 display: none; /*this will hide all breadcrumbs*/
 }

.truebreadcrumbs div.bbp-breadcrumb {
 display: block; /*this will display breadcrumbs you've created*/
 }
```

当然，HTML 仍然会生成所有的面包屑，而 css 会隐藏不需要的面包屑，但这是最简单的方法，无需进入模板。

### [8. 将“编辑个人资料”添加到 wordpress 菜单](#8-add-edit-profile-to-a-wordpress-menu)

大多数 bbPress 用户都有侧边栏，并使用小工具来控制登录和个人资料更改。其他人则依赖于用户知道如果点击他们的头像或用户名，那么他们就可以编辑他们的个人资料。
此解决方案允许您将“编辑个人资料”添加到您的 wordpress 菜单中——这仅在用户登录时显示为菜单项。
将以下内容添加到您的函数文件中

```
// Filter wp_nav_menu() to add profile link
add_filter( 'wp_nav_menu_items', 'my_nav_menu_profile_link' );
function my_nav_menu_profile_link($menu) {
    if (!is_user_logged_in())
        return $menu;
    else
        $current_user = wp_get_current_user();
        $user=$current_user->user_nicename ;
        $profilelink = '<li><a href="/forums/users/' . $user . '/edit">Edit Profile</a></li>';
        $menu = $menu . $profilelink;
        return $menu;

}
```

### [9. 将社交媒体联系人添加到 bbPress 个人资料](#9-adding-social-media-contacts-to-bbpress-profile)

感谢 nicmare 提供这个方便的提示。
您可以通过将这些添加到 contactmethods 来添加和删除社交媒体联系人。
以下示例函数添加了 twitter、facebook、google+ 和 youtube，但删除了
目标、yabber 和 yim。

```
function add_extra_contactmethod( $contactmethods ) {
// Add new ones
$contactmethods['twitter'] = 'Twitter';
$contactmethods['facebook'] = 'Facebook';
$contactmethods['googleplus'] = 'Google Plus';
$contactmethods['youtube'] = 'Youtube';

// remove unwanted
unset($contactmethods['aim']);
unset($contactmethods['jabber']);
unset($contactmethods['yim']);

return $contactmethods;
}
add_filter('user_contactmethods', 'add_extra_contactmethod');
```

### [10. 缩短新鲜度的措辞](#10-shorten-freshness-wording)

此代码缩短新鲜度取出分钟
只需将其放入您的函数文件中

```
//function to shorten freshness display from say '1 month, 2 weeks' to '1 month'
function short_freshness_time( $output) {
$output = preg_replace( '/, .*[^ago]/', ' ', $output );
return $output;
}
add_filter( 'bbp_get_time_since', 'short_freshness_time' );
add_filter('bp_core_time_since', 'short_freshness_time');
```

### [11. 简单地在菜单中添加登录/注销](#11-simple-adding-a-loginlogout-to-the-menu)

为用户添加用于登录/注销、注册或恢复其密码的菜单项到您的站点菜单非常有用，尤其是在您决定不使用 bbPress 侧边栏登录小工具的情况下。
将以下 php 代码片段粘贴到您的子主题的 functions.php 文件中。

```
add_filter( 'wp_nav_menu_items', 'rkk_add_auth_links', 10 , 2 );
function rkk_add_auth_links( $items, $args ) {
 if ( is_user_logged_in() ) {
 $items .= '<li><a href="'. wp_logout_url() .'">Log Out</a></li>';
 }
 elseif ( !is_user_logged_in() ) {
 $items .= '<li><a href="'. site_url('wp-login.php') .'">Log In</a></li>';
 $items .= '<li><a href="'. site_url('wp-login.php?action=register') .'">Register</a></li>';
 $items .= '<li><a href="'. site_url('wp-login.php?action=lostpassword') .'">Lost Password</a></li>';
 }
 return $items;
}
```

您可以根据自己的喜好自定义此功能。如果您想将某些 url 链接到自定义前端表单而不是默认的 WordPress 登录表单，您可以进行这样的简单更改，例如。
site\_url('wp-login.php') 对此 site\_url('/login/')
如果您想在注销后重定向到自定义 url。
wp\_logout\_url()把这个改成这个wp\_logout\_url( site\_url('/logout/') )
或者，如果您想在特定菜单中显示这些菜单项，请在 之后的函数中编辑两个条件is\_user\_logged\_in()。
像这样添加到现有的条件中，is\_user\_logged\_in() && $args->theme\_location == 'primary-menu'.
上面的代码将在您的功能条件中显示特定菜单中的菜单项，其中主题位置通常是菜单段。要查找此功能的菜单的 slug/主题位置搜索，通常位于主题 functions.php 文件中register\_nav\_menu()。有关了解 register\_nav\_menu() 函数的更多信息，请参阅 WordPress 指南[导航菜单](https://codex.wordpress.org/Navigation_Menus)。

### [12.添加模态（弹出）登录](#12-adding-a-modal-popuplogin)

这非常好，说明将其添加到菜单中，并根据需要使用登录/注销。
登录看起来像这样
![模态登录3](/_images/modal-login3-300x144.webp)
有不同的风格可供选择，您可以设计自己的风格。
说明可以在这里找到

### [13. 防止关闭的话题变灰](#13-preventing-closed-topics-from-going-grey)

默认情况下，关闭回复的话题是“灰色的”。但通常您只是想停止发帖，最常见的是针对论坛顶部的热门话题。
将此代码添加到主题中的 css 或修改主题 css 文件夹中的 bbpress.css 。

```
#bbpress-forums .status-closed,
#bbpress-forums .status-closed a {
  color: #aaa !important;
}
```

### [14. 添加新的 bbpress 角色](#14-adding-new-bbpress-roles)

您可以添加新的 bbpress 角色，甚至更改其功能。
在最简单的级别上，您可以添加新角色名称并为其赋予现有能力
这仅对您自己的管理目的很有用，但如果像我一样讨厌“keymaster”角色名称，只需创建一个新角色并为其赋予 keymaster 功能。
以下代码创建了三个名为“name 1”、“name 2”和“name 3”的新角色，第一个角色有参与者、第二个主持人和第三个关键管理员。
只需修改代码即可创建具有您需要的任何功能的任意数量的角色

```
function add_custom_role( $bbp_roles ) {

$bbp_roles['my_custom_role1'] = array(
'name' => 'name 1',
'capabilities' => bbp_get_caps_for_role( bbp_get_participant_role() ) // the same capabilities as participants
);
$bbp_roles['my_custom_role2'] = array(
'name' => 'name 2',
'capabilities' => bbp_get_caps_for_role( bbp_get_participant_role() ) // the same capabilities as participants
);
$bbp_roles['my_custom_role3'] = array(
'name' => 'name 3',
'capabilities' => bbp_get_caps_for_role( bbp_get_keymaster_role() ) // the same capabilities as keymaster
);
return $bbp_roles;
}
add_filter( 'bbp_get_dynamic_roles', 'add_custom_role', 1 );
```

### [15. 在 bbpress 角色中添加自定义功能](#15-adding-custom-capabilities-within-bbpress-roles)

 [添加自定义功能](/developer/bbpress/custom-capabilities/) 

### [16. 论坛页面添加说明](#16-adding-description-to-forum-pages)

如果您创建一个带有描述的论坛，这只会显示在主索引页面上，而不显示在类别页面或论坛页面上
从：
![说明1](/_images/description1-300x106.webp)
到 ：
![说明2](/_images/description2-300x119.webp)
将以下内容添加到您的函数文件中。

```
//filter to add description after forums titles on forum index
function rw_singleforum_description() {
  echo '<div class="bbp-forum-content">';
  echo bbp_forum_content();
  echo '</div>';
}
add_action( 'bbp_template_before_single_forum' , 'rw_singleforum_description');
```

我还添加了这个自定义 CSS。将此添加到您的子主题的 style.css 文件中，以将其放置在面包屑下。

```
#bbpress-forums div.bbp-forum-content {
  clear: both !important;
  margin-left: 0 !important;
  padding: 0  !important;
}
```

### [17. 将订阅移至右侧](#17-move-subscribe-to-right-hand-side)

改变
![订阅1](/_images/subscribe12-300x77.webp)
到：
![订阅2](/_images/subscribe21-300x75.webp)
将以下内容放入您的 style.css

```
/*styling to move 'Subscribe' to right hand side */
.single-forum .subscription-toggle  {
    float:right !important ;
}
```

如果您只想将其稍微向右移动，则可以使用此自定义 CSS。根据您的喜好调整 5px。

```
/*styling to move 'Subscribe' to right hand side */
.single-forum .subscription-toggle  {
    padding-left: 5px !important ;
}
```

### [18. 防止用户更改他们的显示名称](#18-prevent-users-changing-their-display-name)

用户可以在 bbpress 个人资料页面中更改他们的显示名称。一些论坛希望阻止这种情况以阻止用户隐藏他们的身份。
要关闭此功能，您需要编辑默认文件之一并将其保存到您的主题中。
在您的主题中创建一个 bbpress 文件夹。
wp-content/themes/%yourtheme%/bbpress
其中 %yourtheme% 是您的主题名称
然后导航到
wp-content/plugins/bbpress/templates/default/bbpress/form-user-edit.php
并将此文件复制到您在上面创建的 bbpress 文件夹中
bbpress 现在将使用这个而不是默认值。
编辑这个新文件并取出第 33 到 45 行
即取出以下内容

```
<div>
            <label for="nickname"><?php _e( 'Nickname', 'bbpress' ); ?></label>
            <input type="text" name="nickname" id="nickname" value="<?php bbp_displayed_user_field( 'nickname', 'edit' ); ?>" class="regular-text" tabindex="<?php bbp_tab_index(); ?>" />
        </div>
        <div>
            <label for="display_name"><?php _e( 'Display Name', 'bbpress' ) ?></label>
            <?php bbp_edit_user_display_name(); ?>
        </div>
        <?php do_action( 'bbp_user_edit_after_name' ); ?>
```

这将删除设置昵称和更改显示名称的功能。

### [19. 链接到一个随机的单个话题](#19-linking-to-a-random-single-topic)

这是一个非常漂亮的功能，允许用户通过单击链接浏览随机话题。
如果您启用了它，它会挂在主要主题之前，否则它还会创建一个名为 [ntwb-bbpress-random-single-topic] 的简码，允许您将其放入小工具或 WordPress 帖子中。

```
// bbPress - Random Single Topic
function ntwb_bbpress_random_single_topic() {
    if ( bbp_has_topics( array( 'orderby' => 'rand', 'posts_per_page' => 1 ) ) ) {

        while ( bbp_topics() ) : bbp_the_topic();

            ?>
            <a class="bbp-topic-permalink" href="<?php bbp_topic_permalink(); ?>">Random Topic</a>
            <?php

        endwhile;
    }
}
// Hook into action
add_action('bbp_template_before_lead_topic','ntwb_bbpress_random_single_topic');
// Add it as a shortcode [ntwb-bbpress-random-single-topic]
add_shortcode('ntwb-bbpress-random-single-topic', 'ntwb_bbpress_random_single_topic');
```

### [20. 重命名用户角色名称](#20-renaming-user-role-names)

此功能允许您重命名 bbPress 预定义的用户角色。
只需将“我的自定义 \*\*\* 角色名称”更改为您喜欢的内容即可。

```
add_filter( 'bbp_get_dynamic_roles', 'ntwb_bbpress_custom_role_names' );

function ntwb_bbpress_custom_role_names() {
    return array(

        // Keymaster
        bbp_get_keymaster_role() => array(
            'name'         => 'My Custom Keymaster Role Name',
            'capabilities' => bbp_get_caps_for_role( bbp_get_keymaster_role() )
        ),

        // Moderator
        bbp_get_moderator_role() => array(
            'name'         => 'My Custom Moderator Role Name',
            'capabilities' => bbp_get_caps_for_role( bbp_get_moderator_role() )
        ),

        // Participant
        bbp_get_participant_role() => array(
            'name'         => 'My Custom Participant Role Name',
            'capabilities' => bbp_get_caps_for_role( bbp_get_participant_role() )
        ),

        // Spectator
        bbp_get_spectator_role() => array(
            'name'         => 'My Custom Spectator Role Name',
            'capabilities' => bbp_get_caps_for_role( bbp_get_spectator_role() )
        ),

        // Blocked
        bbp_get_blocked_role() => array(
            'name'         => 'My Custom Blocked Role Name',
            'capabilities' => bbp_get_caps_for_role( bbp_get_blocked_role() )
        )
    );
}
```

### [21.在论坛索引后显示5个最近的话题](#21-show-5-recent-topics-after-forum-index)

此功能在您的论坛索引后显示最新的 5 个话题。

```
// Add Recent Topics to BBPress
function recent_bbpress_topics() { { ?>
 <?php
 if ( bbp_has_topics( array( 'author' => 0, 'show_stickies' => false, 'order' => 'DESC', 'post_parent' => 'any', 'posts_per_page' => 5 ) ) )
 bbp_get_template_part( 'bbpress/loop', 'topics' );
 ?>
<?php }}
// Hook into action
add_action('bbp_template_after_forums_index','recent_bbpress_topics');
```

### [22. 仅显示 1 个修订日志话题和回复](#22-showonly-1-revision-log-on-topics-and-replies)

使用此功能清理您的修订日志。

```
// Only return one entry for revision log otherwise it gets cluttered
function bbp_trim_revision_log( $r='' ) {
 $arr = array( end( $r ));
 reset( $r );

 return( $arr );
}

add_filter( 'bbp_get_reply_revisions', 'bbp_trim_revision_log', 20, 1 );
add_filter( 'bbp_get_topic_revisions', 'bbp_trim_revision_log', 20, 1 );
```

### [23.显示bbPress论坛搜索无处不在](#23-showthe-bbpress-forum-search-everywhere)

在单个论坛和单个话题上方显示论坛搜索，但不在 bbPress 个人资料上。

```
//display bbPress search form above sinle topics and forums
function rk_bbp_search_form(){

    if ( bbp_allow_search()) {
        ?>
        <div class="bbp-search-form">

            <?php bbp_get_template_part( 'form', 'search' ); ?>

        </div>
        <?php
    }
}

add_action( 'bbp_template_before_single_forum', 'rk_bbp_search_form' );
add_action( 'bbp_template_before_single_topic', 'rk_bbp_search_form' );
```

### [24. 显示 bbPress 主题的状态标签](#24-show-status-labels-for-bbpress-topics)

这些功能中的每一个都将帮助您根据当前主题的状态添加特定的标签或图标。
在每个话题旁边显示粘性标签。

```
function rk_sticky_topics() {

   if ( bbp_is_topic_sticky() && !bbp_is_topic_closed() )
      echo '<span class="sticky">[Sticky]</span>';
}

add_action( 'bbp_theme_before_topic_title', 'rk_sticky_topics' );
```

在每个话题旁边显示封闭标签。

```
function rk_closed_topics() {

   if ( bbp_is_topic_closed() && !bbp_is_topic_sticky() )
      echo '<span class="closed">[Closed]</span>';
}

add_action( 'bbp_theme_before_topic_title', 'rk_closed_topics' );
```

如果该话题的回复超过 25 条，则显示热标签。
（您可以将 25 更改为任何您想要的）

```
function rk_hot_topics() {
   $reply_count = bbp_get_topic_reply_count();

   if ( $reply_count > 25 )
      echo '<span class="hot">[Hot]</span>';
}

add_action( 'bbp_theme_before_topic_title', 'rk_hot_topics' );
```

如果某个话题已关闭且有粘性，则显示“公告”标签。

```
function rk_announcement_topics() {

   if ( bbp_is_topic_sticky() && bbp_is_topic_closed() )
      echo '<span class="announcement">[Announcement]</span>';
}

add_action( 'bbp_theme_before_topic_title', 'rk_announcement_topics' );
```

创建话题后一小时内显示“新”标签。
将偏移量更改为您想要的任何值，但请确保数量以秒为单位。
例如 60\*60\*1 = 3600 seconds ，这是 1 小时的秒数。

```
function rk_new_topics() {
$offset = 60*60*1;

   if ( get_post_time() > date('U') - $offset )
      echo '<span class="new">[New]</span>';
}

add_action( 'bbp_theme_before_topic_title', 'rk_new_topics' );
```

您可以通过在图标字体 HTML 中添加以显示图标来输入图标。
无论您在哪里看到这个

```
echo '<span class="example">[Example]</span>';
```

您可以轻松地将其更改为此。
在这里，我使用了 Dashicons 图标字体集中的随机字体。

```
echo '<span class="example"><span class="dashicons dashicons-admin-post"></span>[Example]</span>';
```

如果您要使用基本的 HTML 插入图标的方式，您可以使用这个小 CSS 片段来设置它们的样式。

```
#bbpress-forums li.bbp-topic-title span.dashicons {
  float: left;
  margin-right: 5px;
}
```

您也可以仅使用 CSS 在话题标题之前或之后插入自定义图标字体。
这是来自该站点的 Dashicons 示例。
此 CSS 代码在置顶帖之前的话题图标之前显示置顶图标。
ul.sticky 和 ​​ul.super-sticky 都是该话题的帖子类，您可以利用和自定义更多帖子类。

```
#bbpress-forums ul.sticky li.bbp-topic-title a.bbp-topic-permalink:before,
#bbpress-forums ul.super-sticky li.bbp-topic-title a.bbp-topic-permalink:before {
  font: normal 16px/1 'dashicons';
  content: '\f450';
  margin-right: 5px;
  float: left;
  padding-top: 3px;
  color: #bb0;
}
```

### [25.限制用户访问WordPress后端](#25-restricting-user-access-to-the-wordpress-backend)

添加此 PHP 代码片段以仅允许只能编辑帖子的用户访问 WordPress 后端。

```
/**
 * Redirect back to homepage and not allow access to
 * WP backend for Subscribers.
 */
function rkk_redirect_admin(){
    if ( ! current_user_can( 'edit_posts' ) ){
        wp_redirect( site_url() );
        exit;
    }
}
add_action( 'admin_init', 'rkk_redirect_admin' );
```

您可能还想为参与者禁用 WordPress 工具栏。

```
/**
 * Disable toolbar on the frontend of your website
 * for subscribers.
 */
function rkk_disable_admin_bar() {
    if( ! current_user_can('edit_posts') )
        add_filter('show_admin_bar', '__return_false');
}
add_action( 'after_setup_theme', 'rkk_disable_admin_bar' );
```

您也可以安装[WP Admin No Show](https://wordpress.org/plugins/wp-admin-no-show/)来执行此类操作。

### [26.创建一个bbPress特定的侧边栏](#26-creating-a-bbpress-specific-sidebar)

没有插件
注册您的新侧边栏
将此添加到您的子主题functions.php文件中

```
function rkk_widgets_init() {

    register_sidebar( array(
        'name' => __( 'bbPress Sidebar', 'rkk' ),
        'id' => 'bbp-sidebar',
        'description' => __( 'A sidebar that only appears on bbPress pages', 'rkk' ),
        'before_widget' => '<aside id="%1$s" class="widget %2$s">',
        'after_widget' => '</aside>',
        'before_title' => '<h3 class="widget-title">',
        'after_title' => '</h3>',
    ) );
    }

add_action( 'widgets_init', 'rkk_widgets_init' );
```

现在在您的子主题中编辑您的 sidebar.php 文件，并选择仅在 bbPress 页面上用 bbPress 侧边栏替换的侧边栏。
此示例使用的是直接来自话题 25 的代码。我们使用条件is\_bbPress 在 bbPress 页面上显示我们想要的侧边栏，并使用!is\_bbpress在 bbPress 页面上不显示我们想要替换的侧边栏。

```
<?php if ( is_active_sidebar( 'sidebar-1' ) && !is_bbpress() ) : ?>

        <div id="widget-area" class="widget-area" role="complementary">
        <?php dynamic_sidebar( 'sidebar-1' ); ?>
        </div><!-- .widget-area -->

<?php elseif ( is_active_sidebar( 'bbp-sidebar' ) && is_bbpress() ) : ?>

    <div id="secondary" class="widget-area" role="complementary">
    <?php dynamic_sidebar( 'bbp-sidebar' ); ?>
    </div><!-- .widget-area -->

<?php endif; ?>
```

现在转到仪表盘>外观>小工具，现在您将看到一个名为“bbPress Sidebar”的新侧边栏。
添加 bbPress 小工具后，它应该看起来像这样。

![论坛1](/_images/forum1.webp)

带插件
使用以下任何插件都可以获得特定于 bbPress 的侧边栏。如果您认为您发现的内容不够好，我相信还有更多插件可以执行此类功能。
[限制小工具](https://wordpress.org/plugins/restrict-widgets/)
[小工具逻辑](https://wordpress.org/plugins/widget-logic/)
[bbPress WP 调整](https://wordpress.org/plugins/bbpress-wp-tweaks/)

### [27. 登录后自定义重定向](#27-custom-redirect-after-login)

要更改用户登录后重定向到的页面，有像[Peter's Login Redirect](https://wordpress.org/plugins/peters-login-redirect/) 这样的WordPress 插件可以处理重定向，或者您可以使用和自定义此 php 代码片段来实现相同的功能。
下面的 PHP 代码片段会将具有 Admin 用户角色的用户重定向到 WordPress 后端，并将其他任何人重定向到您网站的首页。

```
/**
* WordPress function for redirecting users on login based on user role
*/
function my_login_redirect( $url, $request, $user ){
if( $user && is_object( $user ) && is_a( $user, 'WP_User' ) ) {
if( $user->has_cap( 'administrator' ) ) {
$url = admin_url();
} else {
$url = home_url();
}
}
return $url;
}
add_filter('login_redirect', 'my_login_redirect', 10, 3 );
```
