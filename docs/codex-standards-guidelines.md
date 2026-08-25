---
title: "Codex Standards & Guidelines"
post_status: publish
post_name: codex-standards-guidelines
lang: en
taxonomy:
  category: [bbpress]
  post_tag: [bbp-hooks]
source:
  blog_id: 4
  post_id: 123
  guid: "http://import.local/2021/12/24/codex-standards-guidelines/"
---

Codex Standards & Guidelines
Codex Home → Participate & Contribute → Codex Standards & Guidelines
Contributing to the Codex
If you are considering contributing to the codex this simple guide is here to help you with the formatting of pages and standards & conventions to follow to keep a set appearance to pages.
The Codex is curated by the bbPress community if you are unsure about the status of an article head over to the forums and post a topic and add the topic tag codex, if you want to follow along with the codex development discussions you can visit this link or subscribe to the codex RSS feed.
Please note: All entries to the Codex are covered by the GNU General Public Licence. All entries may be edited or altered by other contributors.
How to Create a New Codex Article
Log in using your WordPress username and password.
Click on the “Create New Page” link in the sidebar.
You can also copy the example template layout from this template to get started quicker.
Add the Title of your article.
Add the article metas: Versions, Components, Types and Context. Meta boxes are located on the screen’s right sidebar. Note, try to keep these as generalised as possible for example, setting the version to ‘2.5’ is preseumed to include 2.5 and all incremental version such as 2.5.1, 2.5.2, etc.
Add your article in the appropriate codex section in the Page Attributes meta box under the Context box. If you are unsure where you should add your article head over the handbook Table of Contents for a guide or head over to the forums and create a topic with the codex topic tag and we will try to work out the best place for your article.
Add content of your article. Check that it follows the Codex General Guidelines, Codex Conventions, and Formatting guides posted below for your reference.
After you’re done, click on the “Publish” button.
How to Edit/Update an Article in the Codex
Log in using your WordPress username and password.
Navigate to the page you want to edit/update.
Click on the “Edit This Page” link in the sidebar. The link displays for the users having article edit access.
After you have made the edit/update, please double-check that the Versions, Components, Types and Context are correct and updated as well, again try to keep these broadly focused so they are easily discovered.
Click on the “Update” button in the Publish meta box.
General Guidelines
Broad guidelines on writing for the bbPress Codex
When writing articles please use the second-person point of view to address the reader. e.g. “Now navigate to your” Rather than “Now navigate to our“.
When writing technical articles (functions, actions, etc.) please use the draft template you will find in the dashboard, copy and paste it’s body outline markup to your new post.
Please keep styling to a minimum, avoid inline styling of elements unless to provide something like a color highlight if thought necessary to lend further emphasis to a piece of text e.g styling a warning in red Ensure you have backed up your DB. Please use elements sparingly **,  *are typographic conventions and used to embolden text and italicize text for foreign & scientific words/phrases; **,  *are to lend weight or importance to a word or phrase i.e ’em’ is not used simply to visually style text in italics.
Links: External resource links: Provided to the bottom of the article framework is a section for links to external resources, please use this section for any links to resources that help further however please ensure that these links are additional resources and that your article does not depend on them for all or any part of your article explanation, the reasoning here is external links are not guaranteed to always be available and if the article relies on them and they are down then the article is effectively useless for users. Links that are not related directly to the article content are to be avoided and if found will be removed.
Images: Do add images to articles where they help to illustrate your points or explanations, nothing helps illustrate things better than a timely graphic, screen shots of bbPress, BuddyPress, or WordPress screens help to show the reader layouts. As with links please avoid calling remote images, always upload to the media library, and embed. If uploading images please ensure you have the right to do so and are not infringing on any copyrights that may exist. Any images thought to be or that are under copyright will be removed from pages.
Creating pages: When creating pages , please ensure you select a suitable ‘Version’ tag, and optionally select from available ‘Components’ tags & ‘Types’. Please only select a parent category from the available parent sections, We request that authors DO NOT create new pages that act as parent pages for their article/s, this is to ensure the integrity of the codex structure, however it may be possible to expand the structure if thought beneficial, but please make a request for this to one of the Codex curation team members for consideration.
Codex Conventions
Website Example Names: Always use example.com, example.org or example.net wherever you need to state a domain as an example. This is per RFC 2606. For example, pun intented checkout http://example.com, these are reserved domain names intented for this specific purpose and do not link to any particular host or adfarm.
Admin: The main admin user of a WordPress site always has the login admin. (In examples. A login of admin on a live site has negative security implications.).
Using people’s names in examples: When a name is needed for an ordinary, non-admin user, or a person, use Harriet as the first name, and Smith as the last name.
Administration Panels: The WordPress interface is called Administration Panels not admin panels or dashboard. Dashboard is a specific panel within Administration Panels. Individual panels are also called Administration Screens.
WordPress is spelled WordPress: WordPress is spelled with two capital letters: WordPress.
bbPress is spelled bbPress: bbPress is spelled with only a single capital P dangit letter: bbPress.
BuddyPress is spelled BuddyPress: BuddyPress is spelled with two capital letters: BuddyPress.
Formatting Guide
If writing a technical guide please use the template format provided in this draft document ( copy paste to new page ) Codex template – technical examples layout
1. Heading Tags:
When you use h2 as a heading tag a section in the contents sidebar and link will be automatically created for you. Use h3 – h6 for sub headings of sections under the h2’s.
2. Code examples: Surround your code with the appropriate shortcodes
[php] your PHP code [/php]
[html] your HTML code [/html]
Also available are bash, shell, css, diff, patch, js, javascript, plain, text, sql and xml and are used in the same format as the previous examples.
When adding code examples please escape angle brackets with Numeric/Decimal entities rather than ‘Named ones, so use .
3. Lists: Use unordered, ordered and delimited lists where appropriate.
4. File names: Surround file names with the code tags
`index.php`
5. The structure of a technical guide
[Intro]
a brief intro to the guide
[/Intro][Functions]
List the functions, location, params etc.
[/Functions][Your Content]
The content body – explanation/guide.
[/Your content]
[Example Usage]
Provide a simple example of code use – using pre/code tags.
[/Example Usage]
[Additional Resources]
Add any links to off site or internal pages that might help further.
[/Additional Resources]
Flagging articles – adding article header messages
Page may be tagged in the body with two ‘Notes’
1/ This page is a legacy document, at top of page, example, if a page is deemed to be outdated or superseded by bbPress versions, or changes then it may be marked with this code block and the page would be re-assigned under the parent section ‘legacy’

This is Legacy Document, the details in this page have either been updated or are deprecated completely. Legacy Docs are retained for historic reference

2/ This page is in need of updating
A page is considered incomplete or needs to be verified for detail.

This page is incomplete or needs checking and verifying.******
