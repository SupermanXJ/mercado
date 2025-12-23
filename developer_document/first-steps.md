<div class="inner-content">

## First steps

<div class="andes-message andes-message--highlight">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--highlight site-carriers__message-title">

Important:

</div>

<div class="andes-message__text--highlight site-carriers__message-text">

<div>

Size chart is available only for Mexico and Brazil.

</div>

</div>

</div>

</div>

<div class="details__message">

Before creating a size chart, you have to **get all data sheets**
(search the domain of product using the category predictor, validate
available domains to associate size chart, then check the data sheet
domain and finally get the size charts data sheet). In addition, you can
get all size chart created by the user to use with other products.

</div>

So, look at the technical flow to get quality items with size chart
associated:

  
<img src="https://http2.mlstatic.com/storage/developers-site-cms-admin/DevSite/225870374154-flow-moda.png" class="content__image" />

1.  **Get data sheet**: with this documentation.
2.  **[Manage Size
    Chart](https://global-selling.mercadolibre.com/devsite/manage-size-chart)**:
    using all data sheet information.
3.  **[Quality items
    (validations)](https://global-selling.mercadolibre.com/devsite/size-chart-validation)**:
    validate all possible errors and messages of recommendations.
4.  **[Recommendations for Quality
    photo](https://global-selling.mercadolibre.com/devsite/recommendations-for-photo-quality)**:
    check the certifications about your photos.

  

## Define fashion domain to publish

To advance in the publication flow of a fashion article with an
associated size chart, use the [category
predictor](https://global-selling.mercadolibre.com/devsite/category-predictor)
and get the domain\_id on which it will be published.

  

Request:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/marketplace/domain_discovery/search?q=$SEARCH_QUERY
```

Example:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/marketplace/domain_discovery/search?q=Boots for woman
```

Response:

``` language-javascript
[
   {
       "domain_id": "CBT-BOOTS_AND_BOOTIES",
       "domain_name": "Boots and booties",
       "category_id": "CBT414251",
       "category_name": "Boots & Booties",
       "attributes": [
           {
               "id": "GENDER",
               "name": "Gender",
               "value_id": "339665",
               "value_name": "Woman"
           },
           {
               "id": "FABRIC_DESIGN",
               "name": "Fabric design",
               "value_id": "24721100",
               "value_name": "Plain"
           }
       ]
   }
]
```

### Response fields

-   **domain\_id**: The unique identifier of the product domain.
-   **domain\_name**: Human-readable name of the domain.
-   **category\_id**: The category ID where the product will be listed.
-   **category\_name**: Human-readable name of the category.
-   **attributes**: Array of attributes inferred from the search query.

## Available domains for size chart

Then, check if the domain\_id matches with one of available domains to
associate size charts.

  

Request:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/catalog/charts/CBT/configurations/active_domains
```

Response:

``` language-javascript
{
   "domains": [
       { "domain_id": "CBT-SNEAKERS" },
       { "domain_id": "CBT-BOOTS_AND_BOOTIES" },
       { "domain_id": "CBT-LOAFERS_AND_OXFORDS" },
       { "domain_id": "CBT-FOOTBALL_SHOES" },
       { "domain_id": "CBT-SANDALS_AND_CLOGS" },
       { "domain_id": "CBT-T_SHIRTS" },
       { "domain_id": "CBT-PANTS" },
       { "domain_id": "CBT-SHIRTS" },
       { "domain_id": "CBT-DRESSES" },
       { "domain_id": "CBT-SHORTS" },
       { "domain_id": "CBT-LEGGINGS" },
       { "domain_id": "CBT-JACKETS_AND_COATS" },
       { "domain_id": "CBT-SWEATSHIRTS_AND_HOODIES" },
       { "domain_id": "CBT-BLOUSES" },
       { "domain_id": "CBT-PAJAMAS" },
       ...
   ]
}
```

<div class="andes-message andes-message--neutral">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--neutral site-carriers__message-title">

Note:

</div>

<div class="andes-message__text--neutral site-carriers__message-text">

<div>

This is an example of the response. We are constantly adding new
domains, please perform this request regularly to stay updated. The API
currently returns **active domains** including footwear, tops, bottoms,
and other fashion categories.

</div>

</div>

</div>

</div>

  

## Check product specification sheet of domain

Once you have the category and domain identified for the listing, it is
necessary to check the **/domains/$DOMAIN\_ID/technical\_specs** feature
and check the product specification sheet of the domain recognizing the
attributes with **value\_type: grid\_id** and **grid\_row\_id** that
will enable to link the size chart information when creating or editing
a listing.

  

Additionally, it is necessary to recognize those attributes with the
**grid\_template\_required** tag, which will be required for searching
the product specification sheet of the size chart.

<div class="andes-message andes-message--neutral">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--neutral site-carriers__message-title">

Note:

</div>

<div class="andes-message__text--neutral site-carriers__message-text">

<div>

From now on, size charts will have a technical file, which is defined
according to the domain of the item. Based on this data sheet, it is
defined what information must be taken into account when creating the
size chart.

</div>

</div>

</div>

</div>

Request:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/domains/$DOMAIN_ID/technical_specs
```

Example that checks the product specification sheet of CBT-SNEAKERS
domain:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/domains/CBT-SNEAKERS/technical_specs
```

Response with the details of the domain's datasheet:

``` language-javascript
{
   "input": {
       "groups": [
           {
               "id": "MAIN",
               "label": "Main characteristics",
               "relevance": 1,
               "section": "SPECIFICATIONS",
               "ui_config": {},
               "components": [
                   {
                       "component": "COMBO",
                       "label": "Brand",
                       "ui_config": {
                           "hint": "Indicate the actual brand of the product or 'Generic' if it has no brand.",
                           "allow_custom_value": true,
                           "allow_filtering": true
                       },
                       "attributes": [
                           {
                               "id": "BRAND",
                               "name": "Brand",
                               "value_type": "string",
                               "value_max_length": 255,
                               "tags": [
                                   "grid_filter",
                                   "catalog_required",
                                   "required"
                               ],
                               "values": [
                                   { "id": "8716514", "name": "Asics" },
                                   { "id": "14671", "name": "Nike" },
                                   { "id": "14810", "name": "adidas" }
                               ],
                               "hierarchy": "PARENT_PK",
                               "relevance": 1
                           }
                       ]
                   },
                   {
                       "component": "COMBO",
                       "label": "Gender",
                       "ui_config": {
                           "allow_custom_value": false,
                           "allow_filtering": true
                       },
                       "attributes": [
                           {
                               "id": "GENDER",
                               "name": "Gender",
                               "value_type": "list",
                               "tags": [
                                   "grid_template_required",
                                   "grid_filter",
                                   "catalog_required",
                                   "required"
                               ],
                               "values": [
                                   { "id": "339665", "name": "Woman" },
                                   { "id": "339666", "name": "Man" },
                                   { "id": "339668", "name": "Girls" },
                                   { "id": "110461", "name": "Gender neutral" },
                                   { "id": "339667", "name": "Boys" },
                                   { "id": "19159491", "name": "Gender neutral kid" }
                               ],
                               "hierarchy": "PARENT_PK",
                               "relevance": 1
                           }
                       ]
                   }
               ]
           }
       ]
   }
}
```

### Important tags to identify

-   **grid\_template\_required**: Attribute required for size chart
    search (e.g., GENDER).
-   **grid\_filter**: Attribute used to filter size charts.
-   **main\_attribute\_candidate**: Candidate for the main attribute in
    the size chart.
-   **BODY\_MEASURE**: Attribute for body measurements (used in
    TOPS/BOTTOMS).
-   **CLOTHING\_MEASURE**: Attribute for garment measurements (used in
    TOPS/BOTTOMS).
-   **multivalued**: Attribute that accepts multiple values (e.g.,
    FILTRABLE\_SIZE).
-   **unique**: Value must be unique within the size chart.

  

## Check the product specification sheet of the size chart

To create a new size chart we must specify the structure of its
attributes, therefore, it is necessary to make a POST to the
**/domains/$DOMAIN\_ID/technical\_specs?section=grids** feature by
uploading to the body all the attributes recognized when checking the
product specification sheet of the domain with the
**grid\_template\_required** tag.

  

There are two types of size charts:

-   **SPECIFIC**: Custom size chart created by the seller.
-   **BRAND**: Size chart previously established by the brand.

Request:

``` language-javascript
curl -X POST -H 'Authorization: Bearer $ACCESS_TOKEN' -H "Content-Type: application/json" https://api.mercadolibre.com/domains/$DOMAIN_ID/technical_specs?section=grids
```

Example:

``` language-javascript
curl -X POST -H 'Authorization: Bearer $ACCESS_TOKEN' -H "Content-Type: application/json" https://api.mercadolibre.com/domains/CBT-SNEAKERS/technical_specs?section=grids
```

Response:

``` language-javascript
{
   "input": {
       "groups": [
           {
               "id": "SIZE_CHART",
               "label": "Size Guide",
               "relevance": 1,
               "section": "GRIDS",
               "ui_config": {},
               "components": [
                   {
                       "component": "GRID",
                       "label": "Size Guide",
                       "ui_config": {
                           "max_allowed": 75,
                           "allow_custom_value": true,
                           "allow_filtering": false
                       },
                       "components": [
                           {
                               "component": "TEXT_OUTPUT",
                               "label": "Brand",
                               "attributes": [
                                   {
                                       "id": "BRAND",
                                       "name": "Brand",
                                       "value_type": "string",
                                       "tags": ["grid_filter", "catalog_required", "required"]
                                   }
                               ]
                           },
                           {
                               "component": "TEXT_OUTPUT",
                               "label": "Gender",
                               "attributes": [
                                   {
                                       "id": "GENDER",
                                       "name": "Gender",
                                       "value_type": "string",
                                       "tags": ["grid_template_required", "grid_filter", "fixed", "required"],
                                       "values": [
                                           { "id": "339665", "name": "Woman" },
                                           { "id": "339666", "name": "Man" }
                                       ]
                                   }
                               ]
                           },
                           {
                               "component": "LINKED_BY_CONNECTOR_INPUT",
                               "label": "Foot length",
                               "ui_config": { "connector": " - ", "hint": "From - To" },
                               "attributes": [
                                   {
                                       "id": "FOOT_LENGTH",
                                       "name": "Foot length",
                                       "value_type": "number_unit",
                                       "tags": ["required"],
                                       "default_unit_id": "cm"
                                   },
                                   {
                                       "id": "FOOT_LENGTH_TO",
                                       "name": "Foot length to",
                                       "value_type": "number_unit",
                                       "default_unit_id": "cm"
                                   }
                               ]
                           },
                           {
                               "component": "NUMBER_UNIT_INPUT",
                               "label": "BR",
                               "attributes": [
                                   {
                                       "id": "BR_SIZE",
                                       "name": "BR",
                                       "value_type": "number_unit",
                                       "tags": ["main_attribute_candidate"],
                                       "default_unit_id": "BR"
                                   }
                               ]
                           },
                           {
                               "component": "NUMBER_UNIT_INPUT",
                               "label": "MX",
                               "attributes": [
                                   {
                                       "id": "MX_SIZE",
                                       "name": "MX",
                                       "value_type": "number_unit",
                                       "tags": ["main_attribute_candidate"],
                                       "default_unit_id": "MX"
                                   }
                               ]
                           }
                       ]
                   }
               ]
           }
       ]
   },
   "output": {}
}
```

  

## Consulting a size charts data sheet

The size chart data sheet will determine the structure of the attributes
with a size chart in the listing. Following the previous example,
execute a POST with the attributes: type (mandatory, type of chart) and
all the attributes previously recognized with the
**grid\_template\_required** tag as GENDER.

  

Request:

``` language-javascript
curl -X POST -H 'Authorization: Bearer $ACCESS_TOKEN' -H "Content-Type: application/json" https://api.mercadolibre.com/catalog/charts/search
```

### Parameters

-   **domain\_id** (required): The domain identifier without the site
    prefix (e.g., "SNEAKERS" instead of "CBT-SNEAKERS").
-   **site\_id** (required): The site identifier (e.g., "CBT").
-   **seller\_id** (required): The seller's user ID.
-   **type** (optional): Type of size chart. Values: `SPECIFIC`,
    `BRAND`. If omitted, returns all types.
-   **attributes** (required): Array of attributes with
    `grid_template_required` tag (e.g., GENDER).

Example consulting the details of the technical data sheet for a
specific size chart (personalized) and the female gender:

``` language-javascript
{
   "domain_id": "SNEAKERS",
   "site_id": "CBT",
   "type": "SPECIFIC",
   "seller_id": 2487485082,
   "attributes": [
       {
           "id": "GENDER",
           "values": [
               {
                   "id": "339665",
                   "value": "Woman"
               }
           ]
       }
   ]
}
```

Before carrying out research on the size chart, you should consider the
attribute with the **grid\_template\_required** tag in the technical
sheet that defines the POST attributes. Consider that in all cases, you
must send the attributes of: **domain\_id**, **site\_id**,
**seller\_id** are mandatory.  
  
**If in the body of the POST is sent**:  
Without the type field, it will return all the results: specific
(custom) size chart or brands according to the filters sent in the
POST.  
**type=SPECIFIC**: Will return all results: custom size chart sent in
the POST, according to the gender to be sent.  
**type=BRAND**: Will return all results: size chart previously
established by the brand according to the filters sent in the POST.

  
  

**Response** with the detail of the technical data sheet of the size
chart:

<div class="andes-message andes-message--neutral">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--neutral site-carriers__message-title">

Note:

</div>

<div class="andes-message__text--neutral site-carriers__message-text">

<div>

Consider this part example response for the JSON specification in the
[creation of the custom size
chart](https://global-selling.mercadolibre.com/devsite/manage-size-chart#Create-size-chart).

</div>

</div>

</div>

</div>

``` language-javascript
{
   "paging": {
       "total": 2,
       "offset": 0,
       "limit": 100
   },
   "charts": [
       {
           "id": "4339173",
           "names": {
               "CBT": "TEST CHART MEN FOOTWEAR"
           },
           "domain_id": "SNEAKERS",
           "site_id": "CBT",
           "type": "SPECIFIC",
           "seller_id": 2487485082,
           "measure_type": "BODY_MEASURE",
           "main_attribute_id": "M_US_SIZE",
           "secondary_attribute_id": "AR_SIZE",
           "attributes": [
               {
                   "id": "GENDER",
                   "name": "Gender",
                   "values": [
                       {
                           "id": "339666",
                           "name": "Man"
                       }
                   ]
               }
           ],
           "rows": [
               {
                   "id": "4339173:1",
                   "attributes": [
                       {
                           "id": "SIZE",
                           "name": "Size",
                           "values": [
                               {
                                   "name": "5 US",
                                   "struct": { "number": 5.0, "unit": "US" }
                               }
                           ]
                       },
                       {
                           "id": "FOOT_LENGTH",
                           "name": "Foot length",
                           "values": [
                               {
                                   "name": "22 cm",
                                   "struct": { "number": 22.0, "unit": "cm" }
                               }
                           ]
                       },
                       {
                           "id": "AR_SIZE",
                           "name": "AR",
                           "values": [
                               {
                                   "name": "36.5 AR",
                                   "struct": { "number": 36.5, "unit": "AR" }
                               }
                           ]
                       },
                       {
                           "id": "BR_SIZE",
                           "name": "BR",
                           "values": [
                               {
                                   "name": "36 BR",
                                   "struct": { "number": 36.0, "unit": "BR" }
                               }
                           ]
                       },
                       {
                           "id": "MX_SIZE",
                           "name": "MX",
                           "values": [
                               {
                                   "name": "23 MX",
                                   "struct": { "number": 23.0, "unit": "MX" }
                               }
                           ]
                       }
                   ]
               }
           ]
       }
   ]
}
```

### Response fields

-   **paging**: Pagination information with total, offset, and limit.
-   **charts**: Array of size charts matching the search criteria.
-   **id**: Unique identifier of the size chart.
-   **names**: Object with site-specific names for the chart.
-   **measure\_type**: Type of measurement (`BODY_MEASURE` or
    `CLOTHING_MEASURE`).
-   **main\_attribute\_id**: Primary attribute used for size
    identification.
-   **secondary\_attribute\_id**: Secondary attribute for size
    reference.
-   **rows**: Array of size entries in the chart.

If the search does not return results from the suggested tables, the
answer you will get is the following and you must first create a size
chart for the seller:

``` language-javascript
{
   "paging": {
       "total": 0,
       "offset": 0,
       "limit": 100
   },
   "charts": []
}
```

If you perform a search with a domain that is not configured with the
new size chart, you will receive an error.

``` language-javascript
{
   "error": "domain_not_active",
   "message": "Domain CBT-HATS_AND_CAPS is not active to be used in charts.",
   "status": 400
}
```

<div class="andes-message andes-message--highlight">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--highlight site-carriers__message-title">

Important:

</div>

<div class="andes-message__text--highlight site-carriers__message-text">

<div>

The size charts for TOPS and BOTTOMS domains enable working with list
type attributes allowing multiple values (multivalued). For example: for
an id: SIZE attribute with name S - L we allow loading multiple values
in the id: FILTRABLE\_SIZE attribute with name: S, M, L. **The
multivalued experience is now active**.  
  
It will not be possible to create or edit marketplace listings in the
TOPS and BOTTOMS categories without a size chart.  
  
For these new TOPS and BOTTOMS categories, it will only be possible to
create listings from customized size charts (SPECIFIC). You should check
the section on Available domains for size chart.

</div>

</div>

</div>

</div>

When checking the product specification sheet of size charts in TOPS and
BOTTOMS domains, a list data type will be found, which establishes the
possible values of a List. These values must be taken into account when
[creating a customized size
chart](https://global-selling.mercadolibre.com/devsite/manage-size-chart#)
in these domains:

Consult the tech spec to know all filtrable\_size international
available.

Example for filtrable size in T-SHIRT:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/domains/CBT-T_SHIRTS/technical_specs
```

``` language-javascript
"attributes": [{
   "id": "FILTRABLE_SIZE",
   "name": "Equivalencies",
   "value_type": "list",
   "value_max_length": 255,
   "tags": [
       "vip_hidden",
       "hidden",
       "read_only",
       "multivalued",
       "variation_attribute",
       "required"
   ],
   "values": [
       { "id": "12917836", "name": "2XS" },
       { "id": "12917776", "name": "XS" },
       { "id": "12917796", "name": "S" },
       { "id": "12917795", "name": "M" },
       { "id": "12917802", "name": "L" },
       { "id": "12917787", "name": "XL" },
       { "id": "12917846", "name": "2XL" },
       { "id": "12917837", "name": "3XL" },
       { "id": "12917843", "name": "4XL" },
       { "id": "12917842", "name": "5XL" },
       { "id": "12917838", "name": "6XL" },
       { "id": "12917841", "name": "7XL" },
       { "id": "12917845", "name": "8XL" },
       { "id": "12917844", "name": "9XL" },
       { "id": "12917839", "name": "10XL" }
   ],
   "hierarchy": "ITEM",
   "relevance": 2
}]
```

For TOPS and BOTTOMS domains, the creation of size guides specifying
body measurements or garment measurements is allowed. In both cases, you
can recognize them in the technical data sheet through tags
**BODY\_MEASURE** or **CLOTHING\_MEASURE**.

  

Example of the attribute GARMENT\_LENGTH\_FROM used in garment
measurements:

``` language-javascript
"attributes": [
   {
       "id": "GARMENT_LENGTH_FROM",
       "name": "Garment length from",
       "value_type": "number_unit",
       "value_max_length": 255,
       "tags": [
           "CLOTHING_MEASURE",
           "required"
       ],
       "default_unit_id": "cm",
       "units": [
           { "id": "\"", "name": "\"" },
           { "id": "cm", "name": "cm" }
       ],
       "hierarchy": "CHILD_DEPENDENT",
       "relevance": 3
   },
   {
       "id": "GARMENT_LENGTH_TO",
       "name": "Garment length to",
       "value_type": "number_unit",
       "value_max_length": 255,
       "tags": [
           "CLOTHING_MEASURE"
       ],
       "default_unit_id": "cm",
       "units": [
           { "id": "\"", "name": "\"" },
           { "id": "cm", "name": "cm" }
       ],
       "hierarchy": "CHILD_DEPENDENT",
       "relevance": 3
   }
]
```

  

## Errors

Possible API errors when working with size charts, organized by
endpoint:

### Domain Discovery

`GET /marketplace/domain_discovery/search`

| Status\_code | Error code   | Error message                                | Description                         |
|--------------|--------------|----------------------------------------------|-------------------------------------|
| 400          | bad\_request | Required String parameter 'q' is not present | The `q` query parameter is missing. |

  

### Technical Specs

`GET /domains/$DOMAIN_ID/technical_specs`

| Status\_code | Error code | Error message  | Description                          |
|--------------|------------|----------------|--------------------------------------|
| 404          | not\_found | Invalid domain | The specified domain does not exist. |

  

### Search Size Charts

`POST /catalog/charts/search`

| Status\_code | Error code                                  | Error message                                                     | Description                                                                  |
|--------------|---------------------------------------------|-------------------------------------------------------------------|------------------------------------------------------------------------------|
| 400          | domain\_not\_active                         | Domain CBT-HATS\_AND\_CAPS is not active to be used in charts     | The specified domain is not enabled for size charts.                         |
| 400          | chart\_not\_available\_for\_invalid\_domain | Domain CBT-null not active                                        | The `domain_id` parameter is missing in the request body.                    |
| 400          | domain\_not\_active                         | Configuration domain null not found                               | The `site_id` parameter is missing in the request body.                      |
| 400          | filters\_validation\_error                  | Required filter seller\_id is missing from the request            | The `seller_id` parameter is required but missing.                           |
| 400          | invalid\_format                             | Invalid ENUM type field value: INVALID\_TYPE is not a valid value | The `type` parameter has an invalid value. Accepted values: SPECIFIC, BRAND. |

  

**Next**: [Manage size
chart](https://global-selling.mercadolibre.com/devsite/manage-size-chart).

</div>
