# Remove price ranges on collection pages
This quick guide shows how to remove price ranges that are shown on the collection pages of your Shopify theme.
This code is intended for use with all themes provided by We are Underground which at present include:

Icon
Testament
Fashionopolism
Mr Parker
Vantage
Epic

This will return the minimum price for a product however it is important to understand that in changing this your customers may feel mislead when selecting through variants within your store and seeing higher prices than expected.

In themes > Customize theme > theme options choose: Edit HTML / CSS
on the next page choose the Snippets folder and select: product-listing.liquid.

Locate the following code:

```html
<div class="prod-price">{% if product.price_varies %} {{ 'products.general.from' | t }} {{ product.price_min | money }} - {{ product.price_max | money }} {% else %}{{ product.price | money }}{% endif %}</div>

Replace that with this:


<div class="prod-price">{% if product.price_varies %}{{ product.price_min | money }}{% else %}{{ product.price | money }}{% endif %}</div>
```

Click save when done.
