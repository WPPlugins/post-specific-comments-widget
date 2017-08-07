=== Post-Specific Comments Widget (PSCW) ===
Contributors: littlepackage
Donate link: https://www.paypal.me/littlepackage
Tags: comment, excerpt, feedback, guest, guestbook, page, post, recent, testimonial, widget, specific, avatar, gravatar
Requires at least: 4
Tested up to: 4.7.2
Stable tag: 1.2.4
License: GPLv3 or later
License URI: http://www.opensource.org/licenses/gpl-license.php

== Description ==

This super lightweight plugin allows you to specify a post/page ID to display the comments for in a widget. This can come in very handy when trying to showcase the comments from a single post or page, such as customer feedback, testimonials, or guestbook. It can also be set to show all comments, with formatting options and optional avatars.

Allows you to list comments in default manner (by Author and Post Title) or by Author and a variable-character excerpt and ellipsis (or other chosen trailing characters). Two new post formats to version 1.1 are (Excerpt) and (Excerpt) - (Author). Version 1.2 added shortcodes so users can create their own formats! Version 1.2.4 adds an Avatar/Gravatar shortcode.

Thanks for downloading; I hope this can help you. If this really helped you, and especially if you can profit from it, please leave feedback or consider sending a dollar or two my way! Paypal link at right.

== Installation ==

1. Upload post-specific-comments-widget.php to the /wp-content/plugins/ directory
2. Activate plugin through the 'Plugins' menu in Wordpress
3. Edit settings under Appearance>Widgets (Hint: add the Post-Specific Comments widget to your sidebar).

The ID number can be found by hovering over the post or page title while in the "All Pages" or "All Posts" list view Wordpress panels. The number will show itself after "post=" in your browser's add-on bar (usually at the lower left hand corner of the screen).

You don't have to limit the comments to one post or page, though. You can show all your posts/pages by typing in the number 0 (zero) instead of a post number.

== Frequently Asked Questions ==

If you have questions, don't hesitate to ask.

= How do I use the shortcodes? = 

If you want to customize the way your comment is printed out, you can use the following shortcodes as placeholders for the intended output: [AUTHOR], [TITLE], [EXCERPT], [DATE].

So for example, if you choose the "other" format, you could then enter "Comment by ~[AUTHOR]~ on [DATE]" and the plugin would magically replace the shortcodes with the author name/link, surrounded by tildes/swiggles, and then the date. 

= How do I use the avatar shortcode? =

[AVATAR] will display a 32px avatar.
[AVATAR 80] will display an 80px avatar.
[AVATAR 128] will display an 128px avatar.
[AVATAR48] and [AVATR 80] will not display avatars because they are not typed correctly.

Avatars will need styling depending on your Wordpress theme. There are ample CSS tags to get them where you want them. Avatar display depends on your avatar settings in Wordpress -> Settings -> Discussion

= How can I remove the .recentcomments a CSS from the header? =

Add the following lines to your (child theme) functions.php file:

`function pscw_remove_recent_comments_style() {
	global $wp_widget_factory;
	remove_action( 'wp_head', array( $wp_widget_factory->widgets['WP_Widget_Recent_Comments'], 'recent_comments_style' ) );  
	remove_action( 'wp_head', array( $wp_widget_factory->widgets['Post_Specific_Comments_Widget'], 'pscw_recent_comments_style' ) );
}  
add_action( 'widgets_init', 'pswc_remove_recent_comments_style' );`


== Screenshots ==

1. Screenshot of the menu settings
2. Screenshot of how to find post/page ID number. In this case the ID is 1696 when hovering over post “Change Password.”

== Upgrade Notice ==

= 1.0.1 = 
Fixes a minor security-related bug. Recommend immediate update. Added feature: excerpt display options. Now use the number 0 instead of the word "all" to show all posts/pages if not showing just one post/page.

= 1.0.2 = 
Fixed issue with Post ID not working in some cases.

== Changelog ==

= 1.2.4 Feb 26 2017 =
* Testing to WP 4.7.2
* Add avatar/gravatar shortcode
* Allow <br /><p><strong><em> html in custom entry
* Tidy code, update readme.txt

= 1.2.3 June 4 2016 =
* Checks for Wordpress 4.5.2
* Update to caching practices

= 1.2.2 December 11 2015 =
* Checks for Wordpress 4.4

= 1.2.1 November 7 2015 =
* unique function added so .recentcomments a CSS can be removed from wp_head

= 1.2.0 August 10 2015 =
* Shortcodes for custom comment output

= 1.1.0 August 7 2015 =
* Wordpress 4.3 ready
* ID tag unique identifier for HTML5
* Two additional formats, title/except and excerpt/author

= 1.0.6 May 3 2015 =
* ID tag fix to prevent page ID duplicates

= 1.0.5 Oct 30 2014 =
* Language files added and l10n code fixes
* Main class fixes

= 1.0.4 Oct 22 2014 =
* Tested with Wordpress 4.0

= 1.0.3 December 13 2013 =
* Tested with Wordpress 3.8
* Helpful screenshot added

= 1.0.2 February 20 2013 =
* Fixed issue with Post ID not working in some cases

= 1.0.1 February 19 2013 =
* Added menu option to set excerpt length and trailing character.

= 1.0 February 14 2013 =
* First version, adapted from "Recent comments widget with comment excerpts," "Wizzart Recent Comments, and "HTML Classified Recent Posts & Comments Widgets"
