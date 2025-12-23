<div class="inner-content">

## Category predictor

<div class="details__message">

Before publishing a product, you have to predict in which category you
should publish products. It helps sellers and developers recognize the
category domain and required attributes to be filled, improving the
listing quality when uploading a product to Mercado Libre.

</div>

<table class="andes-table">
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead class="andes-table__head">
<tr class="header andes-table__row">
<th class="andes-table__header andes-table__header--left">Resource</th>
<th class="andes-table__header andes-table__header--left">Description</th>
<th class="andes-table__header andes-table__header--left">Example</th>
</tr>
</thead>
<tbody class="andes-table__body">
<tr class="odd andes-table__row">
<td class="andes-table__column andes-table__column--left"><strong>https://api.mercadolibre.com/sites</strong></td>
<td class="andes-table__column andes-table__column--left">Retrieves information about the sites where Mercado Libre runs.</td>
<td class="andes-table__column andes-table__column--left"><a href="#modal1">GET</a>
<div id="modal1" class="modalmask">
<div class="modalbox movedown">
<a href="#close" class="go-back">Go back</a> <a href="#close" class="close" title="Close">X</a>
<h3 id="get-all-sites.">Get all sites.</h3>
<pre class="language-javascript details__code-terminal-json"><code>curl -X GET -H &#39;Authorization: Bearer $ACCESS_TOKEN&#39; http://api.mercadolibre.com/sites</code></pre>
<h3 id="response">Response:</h3>
<pre class="language-javascript details__code-terminal-json"><code>[
    {
        &quot;default_currency_id&quot;: &quot;UYU&quot;,
        &quot;id&quot;: &quot;MLU&quot;,
        &quot;name&quot;: &quot;Uruguay&quot;
    },
    {
        &quot;default_currency_id&quot;: &quot;HNL&quot;,
        &quot;id&quot;: &quot;MHN&quot;,
        &quot;name&quot;: &quot;Honduras&quot;
    },
    {
        &quot;default_currency_id&quot;: &quot;EUR&quot;,
        &quot;id&quot;: &quot;MPT&quot;,
        &quot;name&quot;: &quot;Portugal&quot;
    },
    {
        &quot;default_currency_id&quot;: &quot;DOP&quot;,
        &quot;id&quot;: &quot;MRD&quot;,
        &quot;name&quot;: &quot;Dominicana&quot;
    },
    {
        &quot;default_currency_id&quot;: &quot;ARS&quot;,
        &quot;id&quot;: &quot;MLA&quot;,
        &quot;name&quot;: &quot;Argentina&quot;
    },
    {
        &quot;default_currency_id&quot;: &quot;MXN&quot;,
        &quot;id&quot;: &quot;MLM&quot;,
        &quot;name&quot;: &quot;Mexico&quot;
    },
    {
        &quot;default_currency_id&quot;: &quot;CRC&quot;,
        &quot;id&quot;: &quot;MCR&quot;,
        &quot;name&quot;: &quot;Costa Rica&quot;
    },
    {
        &quot;default_currency_id&quot;: &quot;BOB&quot;,
        &quot;id&quot;: &quot;MBO&quot;,
        &quot;name&quot;: &quot;Bolivia&quot;
    },
    {
        &quot;default_currency_id&quot;: &quot;PEN&quot;,
        &quot;id&quot;: &quot;MPE&quot;,
        &quot;name&quot;: &quot;Perú&quot;
    },
    {
        &quot;default_currency_id&quot;: &quot;USD&quot;,
        &quot;id&quot;: &quot;MSV&quot;,
        &quot;name&quot;: &quot;El Salvador&quot;
    },
    {
        &quot;default_currency_id&quot;: &quot;PYG&quot;,
        &quot;id&quot;: &quot;MPY&quot;,
        &quot;name&quot;: &quot;Paraguay&quot;
    },
    {
        &quot;default_currency_id&quot;: &quot;NIO&quot;,
        &quot;id&quot;: &quot;MNI&quot;,
        &quot;name&quot;: &quot;Nicaragua&quot;
    },
    {
        &quot;default_currency_id&quot;: &quot;VES&quot;,
        &quot;id&quot;: &quot;MLV&quot;,
        &quot;name&quot;: &quot;Venezuela&quot;
    },
    {
        &quot;default_currency_id&quot;: &quot;CUP&quot;,
        &quot;id&quot;: &quot;MCU&quot;,
        &quot;name&quot;: &quot;Cuba&quot;
    },
    {
        &quot;default_currency_id&quot;: &quot;USD&quot;,
        &quot;id&quot;: &quot;MEC&quot;,
        &quot;name&quot;: &quot;Ecuador&quot;
    },
    {
        &quot;default_currency_id&quot;: &quot;CLP&quot;,
        &quot;id&quot;: &quot;MLC&quot;,
        &quot;name&quot;: &quot;Chile&quot;
    },
    {
        &quot;default_currency_id&quot;: &quot;GTQ&quot;,
        &quot;id&quot;: &quot;MGT&quot;,
        &quot;name&quot;: &quot;Guatemala&quot;
    },
    {
        &quot;default_currency_id&quot;: &quot;COP&quot;,
        &quot;id&quot;: &quot;MCO&quot;,
        &quot;name&quot;: &quot;Colombia&quot;
    },
    {
        &quot;default_currency_id&quot;: &quot;BRL&quot;,
        &quot;id&quot;: &quot;MLB&quot;,
        &quot;name&quot;: &quot;Brasil&quot;
    },
    {
        &quot;default_currency_id&quot;: &quot;PAB&quot;,
        &quot;id&quot;: &quot;MPA&quot;,
        &quot;name&quot;: &quot;Panamá&quot;
    }
]</code></pre>
<a href="https://global-selling.mercadolibre.com/devsite/set-categories-for-your-products-global-selling">Learn more.</a>
</div>
</div></td>
</tr>
</tbody>
<tbody class="andes-table__body">
<tr class="odd andes-table__row">
<td class="andes-table__column andes-table__column--left"><strong>https://api.mercadolibre.com/sites/$SITE_ID/listing_types</strong></td>
<td class="andes-table__column andes-table__column--left">Returns different exposure levels associated with all listing types in Mercado Libre.</td>
<td class="andes-table__column andes-table__column--left"><a href="#modal3">GET</a>
<div id="modal3" class="modalmask">
<div class="modalbox movedown">
<a href="#close" class="go-back">Go back</a> <a href="#close" class="close" title="Close">X</a>
<h3 id="get-listing-exposures-by-site">Get listing exposures by site</h3>
<pre class="language-javascript details__code-terminal-json"><code>curl -X GET -H &#39;Authorization: Bearer $ACCESS_TOKEN&#39; http://api.mercadolibre.com/sites/CBT/listing_types</code></pre>
<h3 id="response-1">Response:</h3>
<pre class="language-javascript details__code-terminal-json"><code>[
  {
    &quot;site_id&quot;: &quot;CBT&quot;,
    &quot;id&quot;: &quot;gold_pro&quot;,
    &quot;name&quot;: &quot;Premium&quot;
  },
  {
    &quot;site_id&quot;: &quot;CBT&quot;,
    &quot;id&quot;: &quot;gold_special&quot;,
    &quot;name&quot;: &quot;Classic&quot;
  },
  {
    &quot;site_id&quot;: &quot;CBT&quot;,
    &quot;id&quot;: &quot;free&quot;,
    &quot;name&quot;: &quot;Free&quot;
  }
]</code></pre>
</div>
</div></td>
</tr>
</tbody>
<tbody class="andes-table__body">
<tr class="odd andes-table__row">
<td class="andes-table__column andes-table__column--left"><strong>https://api.mercadolibre.com/sites/$SITE_ID/categories</strong></td>
<td class="andes-table__column andes-table__column--left">Returns available categories in the site.</td>
<td class="andes-table__column andes-table__column--left"><a href="#modal6">GET</a>
<div id="modal6" class="modalmask">
<div class="modalbox movedown">
<a href="#close" class="go-back">Go back</a> <a href="#close" class="close" title="Close">X</a>
<h3 id="get-the-category-tree-by-site.">Get the category tree by site.</h3>
<pre class="language-javascript details__code-terminal-json"><code>curl -X GET -H &#39;Authorization: Bearer $ACCESS_TOKEN&#39; https://api.mercadolibre.com/sites/CBT/categories</code></pre>
<h3 id="response-2">Response:</h3>
<pre class="language-javascript details__code-terminal-json"><code>[
    {
        &quot;id&quot;: &quot;CBT1071&quot;,
        &quot;name&quot;: &quot;Animals and Pets&quot;
    },
    {
        &quot;id&quot;: &quot;CBT1367&quot;,
        &quot;name&quot;: &quot;Antiques and Collectibles&quot;
    },
    {
        &quot;id&quot;: &quot;CBT5726&quot;,
        &quot;name&quot;: &quot;Appliances&quot;
    },
    {
        &quot;id&quot;: &quot;CBT1368&quot;,
        &quot;name&quot;: &quot;Art, Craft and School Supplies&quot;
    },
    {
        &quot;id&quot;: &quot;CBT1384&quot;,
        &quot;name&quot;: &quot;Babies&quot;
    },
    {
        &quot;id&quot;: &quot;CBT1246&quot;,
        &quot;name&quot;: &quot;Beauty and Personal Care&quot;
    },
    {
        &quot;id&quot;: &quot;CBT3025&quot;,
        &quot;name&quot;: &quot;Books, Magazines and Comics&quot;
    },
    {
        &quot;id&quot;: &quot;CBT1039&quot;,
        &quot;name&quot;: &quot;Cameras and Accessories&quot;
    },
    {
        &quot;id&quot;: &quot;CBT1743&quot;,
        &quot;name&quot;: &quot;Cars, Motorcycles and Others&quot;
    },
    {
        &quot;id&quot;: &quot;CBT1051&quot;,
        &quot;name&quot;: &quot;Cell Phones and Phones&quot;
    },
    {
        &quot;id&quot;: &quot;CBT1430&quot;,
        &quot;name&quot;: &quot;Clothing and Accessories&quot;
    },
    {
        &quot;id&quot;: &quot;CBT1648&quot;,
        &quot;name&quot;: &quot;Computers&quot;
    },
    {
        &quot;id&quot;: &quot;CBT1144&quot;,
        &quot;name&quot;: &quot;Consoles and Video Games&quot;
    },
    {
        &quot;id&quot;: &quot;CBT1500&quot;,
        &quot;name&quot;: &quot;Construction&quot;
    },
    {
        &quot;id&quot;: &quot;CBT1000&quot;,
        &quot;name&quot;: &quot;Electronics, Audio and Video&quot;
    },
    {
        &quot;id&quot;: &quot;CBT1403&quot;,
        &quot;name&quot;: &quot;Food and Drinks&quot;
    },
    {
        &quot;id&quot;: &quot;CBT1132&quot;,
        &quot;name&quot;: &quot;Games and Toys&quot;
    },
    {
        &quot;id&quot;: &quot;CBT409431&quot;,
        &quot;name&quot;: &quot;Health and Health Supplies&quot;
    },
    {
        &quot;id&quot;: &quot;CBT1574&quot;,
        &quot;name&quot;: &quot;Home, Furniture and Garden&quot;
    },
    {
        &quot;id&quot;: &quot;CBT1499&quot;,
        &quot;name&quot;: &quot;Industries and Offices&quot;
    },
    {
        &quot;id&quot;: &quot;CBT3937&quot;,
        &quot;name&quot;: &quot;Jewels and Watches&quot;
    },
    {
        &quot;id&quot;: &quot;CBT1168&quot;,
        &quot;name&quot;: &quot;Music, Movies and Series&quot;
    },
    {
        &quot;id&quot;: &quot;CBT1182&quot;,
        &quot;name&quot;: &quot;Musical Instruments&quot;
    },
    {
        &quot;id&quot;: &quot;CBT1459&quot;,
        &quot;name&quot;: &quot;Real Estate&quot;
    },
    {
        &quot;id&quot;: &quot;CBT1540&quot;,
        &quot;name&quot;: &quot;Services&quot;
    },
    {
        &quot;id&quot;: &quot;CBT9304&quot;,
        &quot;name&quot;: &quot;Souvenirs, Favours and Parties&quot;
    },
    {
        &quot;id&quot;: &quot;CBT1276&quot;,
        &quot;name&quot;: &quot;Sports and Fitness&quot;
    },
    {
        &quot;id&quot;: &quot;CBT2547&quot;,
        &quot;name&quot;: &quot;Tickets&quot;
    },
    {
        &quot;id&quot;: &quot;CBT407134&quot;,
        &quot;name&quot;: &quot;Tools&quot;
    },
    {
        &quot;id&quot;: &quot;CBT5725&quot;,
        &quot;name&quot;: &quot;Vehicle Accessories&quot;
    },
    {
        &quot;id&quot;: &quot;CBT1953&quot;,
        &quot;name&quot;: &quot;Other categories&quot;
    }
]</code></pre>
<a href="https://global-selling.mercadolibre.com/devsite/set-categories-for-your-products-global-selling">Learn more.</a>
</div>
</div></td>
</tr>
</tbody>
<tbody class="andes-table__body">
<tr class="odd andes-table__row">
<td class="andes-table__column andes-table__column--left"><strong>https://api.mercadolibre.com/categories/$CATEGORY_ID</strong></td>
<td class="andes-table__column andes-table__column--left">Returns information about a category.</td>
<td class="andes-table__column andes-table__column--left"><a href="#modal7">GET</a>
<div id="modal7" class="modalmask">
<div class="modalbox movedown">
<a href="#close" class="go-back">Go back</a> <a href="#close" class="close" title="Close">X</a>
<h3 id="get-category-details.">Get category details.</h3>
<pre class="language-javascript details__code-terminal-json"><code>curl -X GET -H &#39;Authorization: Bearer $ACCESS_TOKEN&#39; https://api.mercadolibre.com/categories/CBT5849</code></pre>
<h3 id="response-3">Response:</h3>
<pre class="language-javascript details__code-terminal-json"><code>{
    &quot;id&quot;: &quot;CBT5849&quot;,
    &quot;name&quot;: &quot;Cables&quot;,
    &quot;picture&quot;: null,
    &quot;permalink&quot;: null,
    &quot;total_items_in_this_category&quot;: 0,
    &quot;path_from_root&quot;: [
        {
            &quot;id&quot;: &quot;CBT1039&quot;,
            &quot;name&quot;: &quot;Cameras and Accessories&quot;
        },
        {
            &quot;id&quot;: &quot;CBT5849&quot;,
            &quot;name&quot;: &quot;Cables&quot;
        }
    ],
    &quot;children_categories&quot;: [
        {
            &quot;id&quot;: &quot;CBT38186&quot;,
            &quot;name&quot;: &quot;Audio &amp; Video&quot;,
            &quot;total_items_in_this_category&quot;: 0
        },
        {
            &quot;id&quot;: &quot;CBT70303&quot;,
            &quot;name&quot;: &quot;Other&quot;,
            &quot;total_items_in_this_category&quot;: 0
        },
        {
            &quot;id&quot;: &quot;CBT38188&quot;,
            &quot;name&quot;: &quot;USB&quot;,
            &quot;total_items_in_this_category&quot;: 0
        }
    ],
    &quot;attribute_types&quot;: &quot;attributes&quot;,
    &quot;settings&quot;: {
        &quot;adult_content&quot;: false,
        &quot;buying_allowed&quot;: true,
        &quot;buying_modes&quot;: [
            &quot;auction&quot;,
            &quot;buy_it_now&quot;
        ],
        &quot;catalog_domain&quot;: &quot;CBT-PHOTOGRAPHY_ACCESSORIES_AND_SPARE_PARTS&quot;,
        &quot;coverage_areas&quot;: &quot;not_allowed&quot;,
        &quot;currencies&quot;: [
            &quot;USD&quot;
        ],
        &quot;fragile&quot;: false,
        &quot;immediate_payment&quot;: &quot;required&quot;,
        &quot;item_conditions&quot;: [
            &quot;new&quot;
        ],
        &quot;items_reviews_allowed&quot;: false,
        &quot;listing_allowed&quot;: false,
        &quot;max_description_length&quot;: 50000,
        &quot;max_pictures_per_item&quot;: 12,
        &quot;max_pictures_per_item_var&quot;: 10,
        &quot;max_sub_title_length&quot;: 70,
        &quot;max_title_length&quot;: 60,
        &quot;maximum_price&quot;: null,
        &quot;minimum_price&quot;: 1,
        &quot;mirror_category&quot;: null,
        &quot;mirror_master_category&quot;: null,
        &quot;mirror_slave_categories&quot;: [],
        &quot;price&quot;: &quot;required&quot;,
        &quot;reservation_allowed&quot;: &quot;not_allowed&quot;,
        &quot;restrictions&quot;: [],
        &quot;rounded_address&quot;: false,
        &quot;seller_contact&quot;: &quot;not_allowed&quot;,
        &quot;shipping_options&quot;: [
            &quot;carrier&quot;,
            &quot;custom&quot;
        ],
        &quot;shipping_profile&quot;: &quot;optional&quot;,
        &quot;show_contact_information&quot;: false,
        &quot;simple_shipping&quot;: &quot;optional&quot;,
        &quot;stock&quot;: &quot;required&quot;,
        &quot;sub_vertical&quot;: &quot;cameras&quot;,
        &quot;subscribable&quot;: false,
        &quot;tags&quot;: [],
        &quot;vertical&quot;: &quot;consumer_electronics&quot;,
        &quot;vip_subdomain&quot;: &quot;articulo&quot;,
        &quot;buyer_protection_programs&quot;: null,
        &quot;status&quot;: &quot;enabled&quot;
    },
    &quot;meta_categ_id&quot;: null,
    &quot;attributable&quot;: false,
    &quot;date_created&quot;: &quot;2019-09-03T14:22:51.000Z&quot;
}</code></pre>
<a href="https://global-selling.mercadolibre.com/devsite/set-categories-for-your-products-global-selling">Learn more.</a>
</div>
</div></td>
</tr>
</tbody>
<tbody class="andes-table__body">
<tr class="odd andes-table__row">
<td class="andes-table__column andes-table__column--left"><strong>https://api.mercadolibre.com/categories/$CATEGORY_ID/attributes</strong></td>
<td class="andes-table__column andes-table__column--left">Displays attributes and rules over them in order to describe the items that are stored in each category.</td>
<td class="andes-table__column andes-table__column--left"><a href="#modal8">GET</a>
<div id="modal8" class="modalmask">
<div class="modalbox movedown">
<a href="#close" class="go-back">Go back</a> <a href="#close" class="close" title="Close">X</a>
<h3 id="get-category-attributes.">Get category attributes.</h3>
<pre class="language-javascript details__code-terminal-json"><code>curl -X GET -H &#39;Authorization: Bearer $ACCESS_TOKEN&#39; https://api.mercadolibre.com/categories/CBT5849/attributes</code></pre>
<h3 id="response-4">Response:</h3>
<pre class="language-javascript details__code-terminal-json"><code>[
    {
        &quot;id&quot;: &quot;BRAND&quot;,
        &quot;name&quot;: &quot;Brand&quot;,
        &quot;tags&quot;: {
            &quot;catalog_required&quot;: true
        },
        &quot;hierarchy&quot;: &quot;PARENT_PK&quot;,
        &quot;relevance&quot;: 1,
        &quot;value_type&quot;: &quot;string&quot;,
        &quot;value_max_length&quot;: 255,
        &quot;attribute_group_id&quot;: &quot;OTHERS&quot;,
        &quot;attribute_group_name&quot;: &quot;Others&quot;
    },
    {
        &quot;id&quot;: &quot;MODEL&quot;,
        &quot;name&quot;: &quot;Model&quot;,
        &quot;tags&quot;: {
            &quot;catalog_required&quot;: true
        },
        &quot;hierarchy&quot;: &quot;PARENT_PK&quot;,
        &quot;relevance&quot;: 1,
        &quot;value_type&quot;: &quot;string&quot;,
        &quot;value_max_length&quot;: 255,
        &quot;attribute_group_id&quot;: &quot;OTHERS&quot;,
        &quot;attribute_group_name&quot;: &quot;Others&quot;
    },
    {
        &quot;id&quot;: &quot;GTIN&quot;,
        &quot;name&quot;: &quot;Universal product code&quot;,
        &quot;tags&quot;: {
            &quot;multivalued&quot;: true,
            &quot;variation_attribute&quot;: true,
            &quot;used_hidden&quot;: true,
            &quot;validate&quot;: true
        },
        &quot;hierarchy&quot;: &quot;PRODUCT_IDENTIFIER&quot;,
        &quot;relevance&quot;: 1,
        &quot;type&quot;: &quot;product_identifier&quot;,
        &quot;value_type&quot;: &quot;string&quot;,
        &quot;value_max_length&quot;: 255,
        &quot;tooltip&quot;: &quot;How do I recognize it? It is an 8 to 14 digit number next to the barcode, on the product box or on its label.&quot;,
        &quot;attribute_group_id&quot;: &quot;OTHERS&quot;,
        &quot;attribute_group_name&quot;: &quot;Others&quot;,
        &quot;hint&quot;: &quot;It may be an EAN, UPC or another GTIN.&quot;
    },
    {
        &quot;id&quot;: &quot;ITEM_CONDITION&quot;,
        &quot;name&quot;: &quot;Item condition&quot;,
        &quot;tags&quot;: {
            &quot;hidden&quot;: true
        },
        &quot;hierarchy&quot;: &quot;ITEM&quot;,
        &quot;relevance&quot;: 2,
        &quot;value_type&quot;: &quot;list&quot;,
        &quot;values&quot;: [
            {
                &quot;id&quot;: &quot;2230284&quot;,
                &quot;name&quot;: &quot;New&quot;
            }
        ],
        &quot;attribute_group_id&quot;: &quot;OTHERS&quot;,
        &quot;attribute_group_name&quot;: &quot;Others&quot;
    },
    {
        &quot;id&quot;: &quot;SELLER_SKU&quot;,
        &quot;name&quot;: &quot;SKU&quot;,
        &quot;tags&quot;: {
            &quot;hidden&quot;: true,
            &quot;variation_attribute&quot;: true
        },
        &quot;hierarchy&quot;: &quot;ITEM&quot;,
        &quot;relevance&quot;: 1,
        &quot;value_type&quot;: &quot;string&quot;,
        &quot;value_max_length&quot;: 255,
        &quot;attribute_group_id&quot;: &quot;OTHERS&quot;,
        &quot;attribute_group_name&quot;: &quot;Others&quot;
    }
]</code></pre>
<a href="https://global-selling.mercadolibre.com/devsite/set-categories-for-your-products-global-selling">Learn more.</a>
</div>
</div></td>
</tr>
</tbody>
<tbody class="andes-table__body">
<tr class="odd andes-table__row">
<td class="andes-table__column andes-table__column--left"><strong>https://api.mercadolibre.com/sites/$SITE_ID/listing_types/$LISTING_TYPE_ID</strong></td>
<td class="andes-table__column andes-table__column--left">Retrieves the configuration for a specific listing type.</td>
<td class="andes-table__column andes-table__column--left"><a href="#modal11">GET</a>
<div id="modal11" class="modalmask">
<div class="modalbox movedown">
<a href="#close" class="go-back">Go back</a> <a href="#close" class="close" title="Close">X</a>
<h3 id="get-listing-type-details.">Get listing type details.</h3>
<pre class="language-javascript details__code-terminal-json"><code>curl -X GET -H &#39;Authorization: Bearer $ACCESS_TOKEN&#39; https://api.mercadolibre.com/sites/CBT/listing_types/gold_pro</code></pre>
<h3 id="response-5">Response:</h3>
<pre class="language-javascript details__code-terminal-json"><code>{
    &quot;id&quot;: &quot;gold_pro&quot;,
    &quot;not_available_in_categories&quot;: [
        &quot;CBT1743&quot;,
        &quot;CBT1459&quot;,
        &quot;CBT1540&quot;
    ],
    &quot;configuration&quot;: {
        &quot;name&quot;: &quot;Premium&quot;,
        &quot;listing_exposure&quot;: &quot;highest&quot;,
        &quot;requires_picture&quot;: true,
        &quot;max_stock_per_item&quot;: 99999,
        &quot;deduction_profile_id&quot;: null,
        &quot;differential_pricing_id&quot;: null,
        &quot;duration_days&quot;: {
            &quot;buy_it_now&quot;: 7300,
            &quot;auction&quot;: null,
            &quot;classified&quot;: null
        },
        &quot;immediate_payment&quot;: {
            &quot;buy_it_now&quot;: true,
            &quot;auction&quot;: false,
            &quot;classified&quot;: false
        },
        &quot;mercado_pago&quot;: &quot;mandatory&quot;,
        &quot;listing_fee_criteria&quot;: {
            &quot;min_fee_amount&quot;: 0,
            &quot;max_fee_amount&quot;: 0,
            &quot;percentage_of_fee_amount&quot;: 0,
            &quot;currency&quot;: &quot;USD&quot;
        },
        &quot;sale_fee_criteria&quot;: {
            &quot;min_fee_amount&quot;: 0,
            &quot;max_fee_amount&quot;: 0,
            &quot;percentage_of_fee_amount&quot;: 0,
            &quot;currency&quot;: &quot;USD&quot;
        }
    },
    &quot;exceptions_by_category&quot;: []
}</code></pre>
</div>
</div></td>
</tr>
<tr class="even andes-table__row">
<td class="andes-table__column andes-table__column--left"><strong>https://api.mercadolibre.com/domains/$DOMAIN_ID/technical_specs</strong></td>
<td class="andes-table__column andes-table__column--left">Returns detailed technical information of the domain.</td>
<td class="andes-table__column andes-table__column--left"><a href="#modal12">GET</a>
<div id="modal12" class="modalmask">
<div class="modalbox movedown">
<a href="#close" class="go-back">Go back</a> <a href="#close" class="close" title="Close">X</a>
<h3 id="obtains-information-of-the-domain.">Obtains information of the domain.</h3>
<pre class="language-javascript details__code-terminal-json"><code>curl -X GET -H &#39;Authorization: Bearer $ACCESS_TOKEN&#39; https://api.mercadolibre.com/domains/CBT-JACKETS_AND_COATS/technical_specs</code></pre>
<h3 id="response-6">Response:</h3>
<pre class="language-javascript details__code-terminal-json"><code>{
    &quot;input&quot;: {
        &quot;groups&quot;: [{
            &quot;id&quot;: &quot;MAIN&quot;,
            &quot;label&quot;: &quot;Main characteristics&quot;,
            &quot;relevance&quot;: 1,
            &quot;section&quot;: &quot;SPECIFICATIONS&quot;,
            &quot;ui_config&quot;: {},
            &quot;components&quot;: [{
                &quot;component&quot;: &quot;COMBO&quot;,
                &quot;label&quot;: &quot;Brand&quot;,
                &quot;ui_config&quot;: {
                    &quot;hint&quot;: &quot;Indicate the actual brand of the product or &#39;Generic&#39; if it has no brand.&quot;,
                    &quot;allow_custom_value&quot;: true,
                    &quot;allow_filtering&quot;: true
                },
                &quot;attributes&quot;: [{
                    &quot;id&quot;: &quot;BRAND&quot;,
                    &quot;name&quot;: &quot;Brand&quot;,
                    &quot;value_type&quot;: &quot;string&quot;,
                    &quot;value_max_length&quot;: 255,
                    &quot;tags&quot;: [
                        &quot;catalog_listing_required&quot;,
                        &quot;grid_filter&quot;,
                        &quot;catalog_required&quot;,
                        &quot;required&quot;
                    ],
                    &quot;hierarchy&quot;: &quot;PARENT_PK&quot;,
                    &quot;relevance&quot;: 1
                }],
                &quot;unified_units&quot;: []
            }]
        }]
    },
    &quot;output&quot;: {
        &quot;main_title&quot;: &quot;Main characteristics&quot;,
        &quot;groups&quot;: []
    }
}</code></pre>
</div>
</div></td>
</tr>
</tbody>
</table>

  

## Get the category prediction

Make a GET request with a product title (in english) to predict one
article at a time, recognize the category\_id and the required
attributes to list a product. Keep in mind that the answer will be made
up of a list of predictions from the provided title, the first being the
one with the highest prediction accuracy.

<div class="andes-message andes-message--neutral">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--neutral site-carriers__message-title">

Note:

</div>

<div class="andes-message__text--neutral site-carriers__message-text">

<div>

This request has a limit 400 request per minute.

</div>

</div>

</div>

</div>

### Mandatory parameter

**q**: the title of the product to be predicted, must be completely in
english language.

Request:

``` language-javascript
curl -H 'Authorization: Bearer $ACCESS_TOKEN' -X GET https://api.mercadolibre.com/marketplace/domain_discovery/search?q=$Q
```

Example:

``` language-javascript
curl -H 'Authorization: Bearer $ACCESS_TOKEN' -X GET https://api.mercadolibre.com/marketplace/domain_discovery/search?q=blue%20shoes%20for%20winter%20adult%20woman
```

Response:

``` language-javascript
[
    {
        "domain_id": "CBT-SNEAKERS",
        "domain_name": "Sneakers",
        "category_id": "CBT9561",
        "category_name": "Shoes",
        "attributes": [
            {
                "id": "GENDER",
                "name": "Gender",
                "value_id": "339666",
                "value_name": "Man"
            },
            {
                "id": "AGE_GROUP",
                "name": "Age group",
                "value_id": "6725189",
                "value_name": "Adults"
            },
            {
                "id": "MAIN_COLOR",
                "name": "Main color",
                "value_id": "2450293",
                "value_name": "Blue"
            }
        ]
    },
    {
        "domain_id": "CBT-SNEAKERS",
        "domain_name": "Sneakers",
        "category_id": "CBT438485",
        "category_name": "Shoes",
        "attributes": [
            {
                "id": "GENDER",
                "name": "Gender",
                "value_id": "339666",
                "value_name": "Man"
            },
            {
                "id": "AGE_GROUP",
                "name": "Age group",
                "value_id": "6725189",
                "value_name": "Adults"
            },
            {
                "id": "MAIN_COLOR",
                "name": "Main color",
                "value_id": "2450293",
                "value_name": "Blue"
            }
        ]
    },
    {
        "domain_id": "CBT-FOOTWEAR",
        "domain_name": "Footwear",
        "category_id": "CBT415193",
        "category_name": "Other",
        "attributes": []
    }
]
```

### Response fields

**domain\_id**: ID of the predicted domain.  
**domain\_name**: name of the predicted domain.  
**category\_id**: ID of the predicted category.  
**category\_name**: name of the predicted category.  
**attributes**: list of attributes for the predicted category.

  

## Categories of Global Selling

Request:

``` language-javascript
curl -H 'Authorization: Bearer $ACCESS_TOKEN' -X GET https://api.mercadolibre.com/sites/CBT/categories
```

Response:

``` language-javascript
[
  {
    "id": "CBT1071",
    "name": "Animals and Pets"
  },
  {
    "id": "CBT1367",
    "name": "Antiques and Collectibles"
  },
  {
    "id": "CBT5726",
    "name": "Appliances"
  },
  {
    "id": "CBT1368",
    "name": "Art, Craft and School Supplies"
  },
  {
    "id": "CBT1384",
    "name": "Babies"
  },
  {
    "id": "CBT1246",
    "name": "Beauty and Personal Care"
  },
  {
    "id": "CBT3025",
    "name": "Books, Magazines and Comics"
  },
  {
    "id": "CBT1039",
    "name": "Cameras and Accessories"
  },
  {
    "id": "CBT1743",
    "name": "Cars, Motorcycles and Others"
  },
  {
    "id": "CBT1051",
    "name": "Cell Phones and Phones"
  },
  {
    "id": "CBT1430",
    "name": "Clothing and Accessories"
  },
  {
    "id": "CBT1648",
    "name": "Computers"
  },
  {
    "id": "CBT1144",
    "name": "Consoles and Video Games"
  },
  {
    "id": "CBT1500",
    "name": "Construction"
  },
  {
    "id": "CBT1000",
    "name": "Electronics, Audio and Video"
  },
  {
    "id": "CBT1403",
    "name": "Food and Drinks"
  },
  {
    "id": "CBT1132",
    "name": "Games and Toys"
  },
  {
    "id": "CBT409431",
    "name": "Health and Health Supplies"
  },
  {
    "id": "CBT1574",
    "name": "Home, Furniture and Garden"
  },
  {
    "id": "CBT1499",
    "name": "Industries and Offices"
  },
  {
    "id": "CBT3937",
    "name": "Jewels and Watches"
  },
  {
    "id": "CBT1168",
    "name": "Music, Movies and Series"
  },
  {
    "id": "CBT1182",
    "name": "Musical Instruments"
  },
  {
    "id": "CBT1459",
    "name": "Real Estate"
  },
  {
    "id": "CBT1540",
    "name": "Services"
  },
  {
    "id": "CBT9304",
    "name": "Souvenirs, Favours and Parties"
  },
  {
    "id": "CBT1276",
    "name": "Sports and Fitness"
  },
  {
    "id": "CBT2547",
    "name": "Tickets"
  },
  {
    "id": "CBT407134",
    "name": "Tools"
  },
  {
    "id": "CBT5725",
    "name": "Vehicle Accessories"
  },
  {
    "id": "CBT1953",
    "name": "Other categories"
  }
]
```

For a second level categories, or information related to specific
categories, you have to use the Categories resource, sending the
category Id as a URL parameter. The next example shows the "Beauty and
Personal Care" category:

Example:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/categories/CBT1246
```

Response:

``` language-javascript
{
  "id": "CBT1246",
  "name": "Beauty and Personal Care",
  "picture": "http://resources.mlstatic.com/category/images/d1c445e9-f3bb-49e8-8cd3-3cfa81e57cf9.png",
  "permalink": null,
  "total_items_in_this_category": 0,
  "path_from_root": [
    {
      "id": "CBT1246",
      "name": "Beauty and Personal Care"
    }
  ],
  "children_categories": [
    {
      "id": "CBT417575",
      "name": "Beard & Mustache Care",
      "total_items_in_this_category": 0
    },
    {
      "id": "CBT417770",
      "name": "Beauty Treatments",
      "total_items_in_this_category": 0
    },
    {
      "id": "CBT29884",
      "name": "Foot, Hand & Nail Care",
      "total_items_in_this_category": 0
    },
    {
      "id": "CBT455174",
      "name": "Hair & Styling Appliances",
      "total_items_in_this_category": 0
    },
    {
      "id": "CBT1263",
      "name": "Hair Care",
      "total_items_in_this_category": 0
    },
    {
      "id": "CBT43673",
      "name": "Hair Removal",
      "total_items_in_this_category": 0
    },
    {
      "id": "CBT431642",
      "name": "Hair Salon Listings",
      "total_items_in_this_category": 0
    },
    {
      "id": "CBT1248",
      "name": "Makeup",
      "total_items_in_this_category": 0
    },
    {
      "id": "CBT1275",
      "name": "Other",
      "total_items_in_this_category": 0
    },
    {
      "id": "CBT454712",
      "name": "Perfumes & Fragrances",
      "total_items_in_this_category": 0
    },
    {
      "id": "CBT393366",
      "name": "Personal Care",
      "total_items_in_this_category": 0
    },
    {
      "id": "CBT431646",
      "name": "Pharmacy",
      "total_items_in_this_category": 0
    },
    {
      "id": "CBT1253",
      "name": "Skin Care",
      "total_items_in_this_category": 0
    }
  ],
  "attribute_types": "attributes",
  "settings": {
    "adult_content": false,
    "buying_allowed": true,
    "buying_modes": [
      "auction",
      "buy_it_now"
    ],
    "catalog_domain": "CBT-BEAUTY_AND_PERSONAL_CARE_SUPPLIES",
    "coverage_areas": "not_allowed",
    "currencies": [
      "USD"
    ],
    "fragile": false,
    "immediate_payment": "required",
    "item_conditions": [
      "new"
    ],
    "items_reviews_allowed": false,
    "listing_allowed": false,
    "max_description_length": 50000,
    "max_pictures_per_item": 12,
    "max_pictures_per_item_var": 10,
    "max_sub_title_length": 70,
    "max_title_length": 60,
    "max_variations_allowed": 100,
    "maximum_price": null,
    "maximum_price_currency": "USD",
    "minimum_price": 1,
    "minimum_price_currency": "USD",
    "mirror_category": null,
    "mirror_master_category": null,
    "mirror_slave_categories": [
    ],
    "price": "required",
    "reservation_allowed": "not_allowed",
    "restrictions": [
    ],
    "rounded_address": false,
    "seller_contact": "not_allowed",
    "shipping_options": [
      "carrier",
      "custom"
    ],
    "shipping_profile": "optional",
    "show_contact_information": false,
    "simple_shipping": "optional",
    "stock": "required",
    "sub_vertical": "health_beauty",
    "subscribable": false,
    "tags": [
    ],
    "vertical": "consumer_goods",
    "vip_subdomain": "articulo",
    "buyer_protection_programs": null,
    "status": "enabled"
  },
  "channels_settings": [
    {
      "channel": "mp-merchants",
      "settings": {
        "buying_modes": [
          "buy_it_now"
        ],
        "immediate_payment": "required",
        "minimum_price": 1,
        "status": "enabled"
      }
    }
  ],
  "meta_categ_id": null,
  "attributable": false,
  "date_created": "2018-04-25T08:12:56.000Z"
}
```

As you can see, you get the "path\_from\_root" and children\_categories
attributes. Use these attributes to browse through the category tree and
find the specific category for your item.

  

## Category detail

Make a request to a specific category will allow you to know the
information and specific description of it. Below you will find the
description of some of these attributes.

Request:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/categories/$CATEGORY_ID
```

Example:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/categories/CBT11796
```

Response:

``` language-javascript
{
   "id":"CBT11796",
   "name":"Footwear",
   "picture":null,
   "permalink":null,
   "total_items_in_this_category":0,
   "path_from_root":[
      {
         "id":"CBT1430",
         "name":"Clothing and Accessories"
      },
      {
         "id":"CBT1455",
         "name":"Baby Clothes & Shoes"
      },
      {
         "id":"CBT11796",
         "name":"Footwear"
      }
   ],
   "children_categories":[

   ],
   "attribute_types":"variations",
   "settings":{
      "adult_content":false,
      "buying_allowed":true,
      "buying_modes":[
         "auction",
         "buy_it_now"
      ],
      "catalog_domain":"CBT-BABIES_FOOTWEAR",
      "coverage_areas":"not_allowed",
      "currencies":[
         "USD"
      ],
      "fragile":false,
      "immediate_payment":"required",
      "item_conditions":[
         "new"
      ],
      "items_reviews_allowed":false,
      "listing_allowed":true,
      "max_description_length":50000,
      "max_pictures_per_item":12,
      "max_pictures_per_item_var":10,
      "max_sub_title_length":70,
      "max_title_length":60,
      "maximum_price":null,
      "minimum_price":1,
      "mirror_category":null,
      "mirror_master_category":null,
      "mirror_slave_categories":[

      ],
      "price":"required",
      "reservation_allowed":"not_allowed",
      "restrictions":[

      ],
      "rounded_address":false,
      "seller_contact":"not_allowed",
      "shipping_modes":[
         "custom",
         "not_specified"
      ],
      "shipping_options":[
         "custom",
         "carrier"
      ],
      "shipping_profile":"optional",
      "show_contact_information":false,
      "simple_shipping":"optional",
      "stock":"required",
      "sub_vertical":"clothes",
      "subscribable":false,
      "tags":[

      ],
      "vertical":"apparel",
      "vip_subdomain":"articulo",
      "buyer_protection_programs":null,
      "status":"enabled"
   },
   "meta_categ_id":null,
   "attributable":false,
   "date_created":"2019-09-10T14:12:56.000Z"
}
```

## Download categories

In case of not being able to use the category predictor, you can
[download the category
tree](https://global-selling.mercadolibre.com/devsite/category-dump-global-selling).

  

## HTTP response code references

### Successful responses

| Code       | Description                                         |
|------------|-----------------------------------------------------|
| **200 OK** | Request was successful. Returns the requested data. |

### Error responses

| Code    | Error       | Description                                                                                    |
|---------|-------------|------------------------------------------------------------------------------------------------|
| **400** | Bad Request | Site ID or Query is empty. The `q` parameter is required for category prediction.              |
| **403** | Forbidden   | Unexpected error validating API access. Check that your access token is valid and not expired. |
| **404** | not\_found  | Resource not found. The site ID or category ID does not exist.                                 |

### Error response examples

**400 Bad Request** - Empty query parameter:

``` language-javascript
{
  "message": "Site ID or Query is empty",
  "error": "Bad Request",
  "status": 400,
  "cause": "Bad Request",
  "cause_list": [
    {
      "msg": "Bad Request"
    }
  ]
}
```

**403 Forbidden** - Invalid or expired access token:

``` language-javascript
{
  "message": "Unexpected error validating API access",
  "error": "Forbidden",
  "status": 403,
  "cause": "Forbidden",
  "cause_list": [
    {
      "msg": "Forbidden"
    }
  ]
}
```

**404 Not Found** - Invalid site ID:

``` language-javascript
{
  "message": "Resource /sites/INVALID_SITE/domain_discovery/search not found.",
  "error": "not_found",
  "status": 404,
  "cause": []
}
```

**404 Not Found** - Category not found:

``` language-javascript
{
  "message": "Category not found: CBT999999999",
  "error": "not_found",
  "status": 404,
  "cause": []
}
```

</div>
