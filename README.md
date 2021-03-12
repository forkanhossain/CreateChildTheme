# createChildTheme
Here I am going to show how to create child theme in WordPress. If you face any problem for creating child theme in your main theme, I am willing to help you. Feel free to contact with me. Thanks

#At First You need to CREATE A FOLDER IN wp-content/themes
# A child theme needs three things: its own folder, a style sheet and a functions.php file.

# 1) A Child theme name should be as the parent theme name appeanding with -child. For example if you want to create child theme of twentyfifteen, it's child theme name will be twentyfifteen-child.
# 2) Simple tyle sheet style.css with these below code: 
# Feel free to copy it and make your own adjustments
/*
Theme Name: Twenty Fifteen Child
Theme URI: http://example.com/twenty-fifteen-child/
description: >-
Twenty Fifteen Child Theme
Author: Forakn Hossain
Author URI: http://example.com
Template: twentyfifteen
Version: 1.0.0
License: GNU General Public License v2 or later
License URI: http://www.gnu.org/licenses/gpl-2.0.html
Tags: light, dark, two-columns, right-sidebar, responsive-layout, accessibility-ready
Text Domain: twenty-fifteen-child
*/

# IMPLEMENTING CUSTOM STYLES, you need to add custom css from here
#If you want to know more details you can visit WordPress Instructions: https://developer.wordpress.org/themes/advanced-topics/child-themes/

# 3) Need to create functions.php file with your custom functions if you have. Otherwise no need to add anything but file should have in your child theme folder.

#Theme Thumbnail: ADD THEME IMAGE while activating your theme, you need to add a PNG image with the name screenshot.png. The recommended size is 880 × 660 pixels. Other image formats such as JPEG and GIF would also work

# OVERRIDING PARENT THEME FILES you need add these files in the child theme and override code accordingly.
# Recommended way to load the parent’s style sheet — and the reason why we created functions.php earlier — is to use wp_enqueue_style(). This WordPress function safely adds style sheet files to a WordPress theme.
The corresponding code looks like this:
<code>
add_action( 'wp_enqueue_scripts', 'enqueue_parent_styles' );

function enqueue_parent_styles() {
   wp_enqueue_style( 'parent-style', get_template_directory_uri().'/style.css' );
}
</code>

