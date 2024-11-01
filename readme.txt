=== WooCommerce RRP ===
Contributors: Brad Davis
Tags: woocommerce, woocommerce-price, wc-admin, woocommerce-admin, woocommerce-product-settings, admin, wp-admin, wordpress-admin
Requires at least: 4.0
Tested up to: 6.5.3
Stable tag: 1.8.0
License: GPLv3 or later
License URI: http://www.gnu.org/licenses/gpl-3.0.html

WooCommerce RRP allows users to add text before the regular price and sale price of a product from within WooCommerce General settings.

== Description ==

WooCommerce RRP allows a users to add text before the regular price and sale price of a product from within WooCommerce General settings. You can also select to have this text displayed on archive templates by simply clicking a select box.

If you would like to change the display text for a certain product, you can use the [WordPress add filter function](http://codex.wordpress.org/Function_Reference/add_filter "Function Reference/add filter"), please see the FAQ for an example.

If you have suggestions for new features, please add your idea in the "Support" area for this plugin.

If WooCommerce RRP has made your life a little easier, please leave a positive review in the "Reviews" area for this plugin.

= Requires WooCommerce to be installed. =

== Installation ==

1. Upload WooCommerce RRP to the `/wp-content/plugins/` directory
2. Activate the plugin through the 'Plugins' menu in WordPress
3. Go to WooCommerce > Settings and add your text to the input areas in "Currency Options". See Screenshots for a visual explanation.

== Frequently Asked Questions ==

= What if I want to change the "Product Price Text" for a certain product? =

This can be done using the built in [WordPress add filter function](http://codex.wordpress.org/Function_Reference/add_filter "Function Reference/add filter"). For example, if we had a product with an id of 96 and we wanted to change the text of the "Product Price Text" field to "Your new Product Price Text, the function would like this:

`
function change_before_regular_price( $woo_rrp_before_price ) {
	global $post;
	if ( '96' == $post->ID ) :
		return 'Your new Product Price Text';
	else :
		return $woo_rrp_before_price;
	endif;
}
add_filter( 'woo_rrp_before_price', 'change_before_regular_price' );
`

= What if I want to change the "Sale Price Text" for a certain product? =

This can be done using the built in WordPress add filter function. For example, if we had a product with an id of 96 and we wanted to change the text of the "Sale Price Text" field to "Your new Sale Price Text, the function would like this:
`
function change_before_sale_price( $woo_rrp_before_sale_price ) {
	global $post;
	if ( '96' == $post->ID ) :
		return 'Your new Sale Price Text';
	else :
		return $woo_rrp_before_sale_price;
	endif;
}
add_filter( 'woo_rrp_before_sale_price', 'change_before_sale_price' );
`

= Can you provide a list of filters that are available and a description of what they control? =

Sure, there are two filters available for you to use:

* woo_rrp_before_price - Controls the text that is displayed before the regular price of a product.
* woo_rrp_before_sale_price - Controls the text that is displayed before the sale price of a product.

= Enabling the "Show Text On Archives" messes up the archive display, can you please fix this? =

You will need to tidy this up using a little CSS styling.

= There isn't any translations of this plugin, can I provide you a translation in my local language to include? =

== Screenshots ==

1. Entering text into the "Product Price Text" will display before the regular price for the product.
2. Here you can see the arrow pointing to the text displayed that you entered in the "Product Price Text" field.
3. Entering text into the "Sale Price Text" will display before the sale price for the product.
4. Here you can see the arrow pointing to the text displayed that you entered in the "Sale Price Text" field.
5. Selecting the "Show Text On Archives" will display the text entered in the "Product Price Text" and "Sale Price Text" fields on archive templates.
6. Here you can see the arrows pointing to the text entered in "Product Price Text" and "Sale Price Text" on an archive.

== Changelog ==

= 1.8.0 =
* Added compatible with High Performance Order Storage (HPOS)
* Tested on WordPress 6.5.3
* Tested on WooCommerce 8.9.0

= 1.7.6 =
* Tested on WordPress 5.9
* Tested on WooCommerce 6.2.0
* Fixed display bug for "Product Price Text" when item is on sale
* Fixed display for "Product Price Text" when product does not have a price
* Changed filter priority to fire later 
* Refactoring functions in render category and single product classes 

= 1.7.5 =
* Updated single product to not output product price text field when price is empty
* Updated category view to not output product price text field when price is empty

= 1.7.4 =
* Tested on WordPress 5.5.1
* Tested on WooCommerce 4.6.1

= 1.7.3 =
* Tested on WordPress 5.2.2
* Tested on WooCommerce 3.7.0

= 1.7.2 =
* Tested on WordPress 5.1
* Tested on WooCommerce 3.5.5

= 1.7.1 =
* Tested on WooCommerce 3.5.3

= 1.7.0 =
* WPCS refactor
* Tested on WordPress 5.0.0
* Tested on WooCommerce 3.5.2

= 1.6 =
* Added translation functions on user input strings
* Added languages folder with po, mo and pot file in en_AU
* Tested on WordPress v4.9.8
* Tested on WooCommerce v3.4.4

= 1.5 =
* Tested on WordPress v4.9.6
* Tested on WooCommerce v3.4.1

= 1.4 =
* Tested on WordPress 4.9
* Tested on WooCommerce 3.2.4
* Added span with class="rrp-price" around before price string
* Added span with class="rrp-sale" around before sale price string

= 1.3 =
* Tested on WordPress 4.8.2
* Tested on WooCommerce 3.2.1
* Add WooCommerce header version check

= 1.2 =
* Tested on WordPress 4.8
* Tested on WooCommerce 3.0.8
* Removed &nbsp; and replaced with whitespace for readers

= 1.1 =
* Added conditional check to price so text only shows if price is not empty

= 1.0 =
* Original commit and released to the world

== Upgrade Notice ==

= 1.0 =
* You should use WooCommerce RRP 1.0 for the convenience of having the ability to add text before the regular and sale price from the WooCommerce Setting UI.
