---
title: "bbp_loaded"
post_status: publish
post_name: bbp_loaded
lang: en
taxonomy:
  category: [bbpress]
  post_tag: [bbp-hooks]
source:
  blog_id: 4
  post_id: 19
  guid: "http://import.local/2021/12/24/bbp_loaded/"
---

bbp\_loaded
Codex Home → bbp\_loaded
The ‘bbp\_loaded’ action is hooked onto WordPress’s ‘plugins\_loaded’ action with default priority 10 in:
/includes/core/actions.php
It’s one of several ‘piggy-back’ actions intended to help load code only when bbPress is active. It’s used to execute code early in the WordPress load order.
How it's hooked
add\_action( 'plugins\_loaded', 'bbp\_loaded', 10 );
Where it's used
add\_action( 'bbp\_loaded', 'bbp\_constants', 2 );
add\_action( 'bbp\_loaded', 'bbp\_boot\_strap\_globals', 4 );
add\_action( 'bbp\_loaded', 'bbp\_includes', 6 );
add\_action( 'bbp\_loaded', 'bbp\_setup\_globals', 8 );
add\_action( 'bbp\_loaded', 'bbp\_setup\_option\_filters', 10 );
add\_action( 'bbp\_loaded', 'bbp\_setup\_user\_option\_filters', 12 );
add\_action( 'bbp\_loaded', 'bbp\_register\_theme\_packages', 14 );
add\_action( 'bbp\_loaded', 'bbp\_filter\_user\_roles\_option', 16 );
