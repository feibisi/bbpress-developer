---
title: "bbp_show_lead_topic"
post_status: publish
post_name: bbp_show_lead_topic
lang: en
taxonomy:
  category: [bbpress]
  post_tag: [bbp-hooks]
source:
  blog_id: 4
  post_id: 42
  guid: "http://import.local/2021/12/24/bbp_show_lead_topic/"
---

bbp\_show\_lead\_topic
Codex Home → bbp\_show\_lead\_topic
Description
The ‘bbp\_show\_lead\_topic’ function is an alternate layout style where topics appear as “lead” posts, ahead of replies whereas by default topics are included in the reply loop.
How to use it
When set to $show\_lead = true the ‘Lead Topic’ uses the single topic part content-single-topic-lead.php allowing you to style the lead topic separately from the main reply loop. It’s also useful if you want to add some ads or a simple note to your readers after the lead topic before the replies.
Sample code example
function custom\_bbp\_show\_lead\_topic( $show\_lead ) {
$show\_lead[] = 'true';
return $show\_lead;
}
add\_filter('bbp\_show\_lead\_topic', 'custom\_bbp\_show\_lead\_topic' );
