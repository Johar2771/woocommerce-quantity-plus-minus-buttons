# woocommerce-quantity-plus-minus-buttons
Simple code and plugin to add plus-minus buttons to WooCommerce product quantity
# WooCommerce Quantity Plus Minus Buttons

This guide helps you add quantity increment/decrement (+/-) buttons on WooCommerce product pages.

## Option 1: Use a Code Snippet

Here’s a basic method to add plus-minus buttons with PHP and jQuery:

```php
// Add this to your functions.php
function custom_quantity_input_buttons() {
   if (is_product()) {
      ?>
      <script>
         jQuery(document).ready(function($){
            $('input.qty').after('<button class="plus">+</button>');
            $('input.qty').before('<button class="minus">-</button>');

            $('body').on('click', '.plus', function(){
               var input = $(this).prev('input.qty');
               input.val(parseInt(input.val()) + 1);
            });

            $('body').on('click', '.minus', function(){
               var input = $(this).next('input.qty');
               var val = parseInt(input.val()) - 1;
               if(val > 0) input.val(val);
            });
         });
      </script>
      <?php
   }
}
add_action('wp_footer', 'custom_quantity_input_buttons');

## Option 2: Use a Plugin (No Code)

Want a cleaner solution? Try the [WooCommerce Quantity Plus Minus]([url](https://woocommerce.com/products/quantity-buttons-for-woocommerce/)) Plugin.

This plugin automatically adds quantity buttons on product, cart, and shop pages — no code needed.
