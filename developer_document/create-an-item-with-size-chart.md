<div class="inner-content">

## Create Item with associate size chart

<div class="andes-message andes-message--highlight">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--highlight site-carriers__message-title">

Important:

</div>

<div class="andes-message__text--highlight site-carriers__message-text">

<div>

For all domains the size chart association format is the same.

</div>

</div>

</div>

</div>

## Associate size chart to an item

To associate a size chart to listings within the required domains, you
will have to execute a POST on the items, sending the new attributes of
type **SIZE\_GRID\_ID**, the size chart which we want to associate the
item or variation and **SIZE\_GRID\_ROW\_ID** with reference to the row
in the size chart. The **size\_grid\_id** and **size\_grid\_row\_id**
fields are new attributes in the payload at item creation.

  

-   **size\_grid\_id**: is the ID of the size chart that was created.
-   **size\_grid\_row\_id**: is the ID of the grid row.
-   The user that creates the item must be the same one that created the
    chart.
-   The **chart gender** must be corresponding **to item gender**.
-   It is **not possible to associate a chart without row\_id
    associated**.

### Required fields

The following fields are required when creating an item with size chart:

-   **sites\_to\_sell**: Array with site\_id and logistic\_type
-   **title**: Item title (maximum 60 characters)
-   **category\_id**: Category identifier
-   **price**: Item price
-   **currency\_id**: Currency code (e.g., USD)
-   **condition**: Item condition (new, used)
-   **pictures**: Array of picture URLs
-   **sale\_terms**: Warranty and sale terms
-   **attributes**: Including SIZE\_GRID\_ID, BRAND, GENDER, MODEL
-   **PACKAGE\_WEIGHT**, **PACKAGE\_LENGTH**, **PACKAGE\_WIDTH**,
    **PACKAGE\_HEIGHT**: Package dimensions

  

In the creation of the footwear article, the attributes of the size
guide number created in the previous steps must be included. It should
be inserted in the attribute block, following the example below:

  

-   **SIZE\_GRID\_ID**:
-   **id**: the new field "SIZE\_GRID\_ID".
-   **value\_name**: the ID (number) of the guide.

``` language-javascript
"attributes": [
   {
       "id": "SIZE_GRID_ID",
       "value_name": "664737"
   },
```

We also need to associate the size guide rows with the variations of the
article being created. In other words, each variation must be associated
with a row from the size table. Therefore, the "SIZE\_GRID\_ROW\_ID"
field should be included in the variation attributes:

  

-   **SIZE\_GRID\_ROW\_ID**:
-   **id**: the new field "SIZE\_GRID\_ROW\_ID".
-   **value\_name**: the ID (number) of the guide + ":" + the
    corresponding row number in the size table. For example apply to
    footwear:

![](https://http2.mlstatic.com/storage/developers-site-cms-admin/197533002790-Captura-de-Tela-2024-03-04-a-s-14.43.00.png)  

``` language-javascript
"attributes": [
   {
       "id": "SIZE_GRID_ROW_ID",
       "value_name": "664737:1"
   },
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

The item's SIZE must exist in the size\_grid\_id, meaning the SIZE value
must exist in the SIZE\_GRID\_ROW\_ID. The form associate size chart
this same to footwear and tops & bottoms.

</div>

</div>

</div>

</div>

## Create item with size chart

Request:

``` language-javascript
curl -X POST -H 'Authorization: Bearer $ACCESS_TOKEN' -H "Content-Type: application/json" https://api.mercadolibre.com/global/items -d '{
   "sites_to_sell": [
       {
           "site_id": "MLM",
           "logistic_type": "remote"
       }
   ],
   "title": "Test Sneaker with Size Chart",
   "category_id": "CBT3724",
   "price": 25,
   "currency_id": "USD",
   "condition": "new",
   "listing_type_id": "gold_pro",
   "pictures": [
       {"source": "https://http2.mlstatic.com/D_644516-CBT51699767208_092022-O.jpg"}
   ],
   "sale_terms": [
       {
           "id": "WARRANTY_TYPE",
           "value_id": "6150835",
           "value_name": "No warranty"
       }
   ],
   "attributes": [
       {"id": "SIZE_GRID_ID", "value_name": "4339173"},
       {"id": "BRAND", "value_name": "Generic"},
       {"id": "GENDER", "value_id": "339666"},
       {"id": "MODEL", "value_name": "Generic Model"},
       {"id": "PACKAGE_WEIGHT", "value_name": "1 kg"},
       {"id": "PACKAGE_LENGTH", "value_name": "30 cm"},
       {"id": "PACKAGE_WIDTH", "value_name": "20 cm"},
       {"id": "PACKAGE_HEIGHT", "value_name": "15 cm"},
       {"id": "ITEM_CONDITION", "value_id": "2230284", "value_name": "New"}
   ],
   "variations": [
       {
           "attribute_combinations": [
               {"id": "COLOR", "value_name": "Black"},
               {"id": "SIZE", "value_name": "5 US-M"}
           ],
           "price": 25,
           "available_quantity": 10,
           "picture_ids": ["https://http2.mlstatic.com/D_644516-CBT51699767208_092022-O.jpg"],
           "attributes": [
               {"id": "SIZE_GRID_ROW_ID", "value_name": "4339173:1"}
           ]
       }
   ]
}'
```

Response: **200 OK**

  

``` language-javascript
{
   "item_id": "CBT3169302956",
   "seller_id": 2487485082,
   "site_id": "CBT",
   "site_items": [
       {
           "item_id": "MLM2615766915",
           "seller_id": 2488208976,
           "site_id": "MLM",
           "logistic_type": "remote"
       }
   ]
}
```

### Response fields

-   **item\_id**: The created CBT item ID.
-   **seller\_id**: The seller's ID.
-   **site\_id**: The origin site (CBT).
-   **site\_items**: Array of items created in destination sites.
-   **site\_items\[\].item\_id**: The item ID in the destination site.
-   **site\_items\[\].seller\_id**: The seller ID in the destination
    site.
-   **site\_items\[\].site\_id**: The destination site ID (MLM, MLB,
    MLC, MCO).
-   **site\_items\[\].logistic\_type**: The logistic type configured.

## Create item with multiple variations

You can create an item with multiple size variations, each associated
with a different row in the size chart:

  

Request:

``` language-javascript
curl -X POST -H 'Authorization: Bearer $ACCESS_TOKEN' -H "Content-Type: application/json" https://api.mercadolibre.com/global/items -d '{
   "sites_to_sell": [
       {
           "site_id": "MLM",
           "logistic_type": "remote"
       }
   ],
   "title": "Test Sneaker Multiple Variations",
   "category_id": "CBT3724",
   "price": 30,
   "currency_id": "USD",
   "condition": "new",
   "listing_type_id": "gold_pro",
   "pictures": [
       {"source": "https://http2.mlstatic.com/D_644516-CBT51699767208_092022-O.jpg"},
       {"source": "https://http2.mlstatic.com/D_862503-CBT51700450573_092022-O.jpg"}
   ],
   "sale_terms": [
       {
           "id": "WARRANTY_TYPE",
           "value_id": "6150835",
           "value_name": "No warranty"
       }
   ],
   "attributes": [
       {"id": "SIZE_GRID_ID", "value_name": "4326431"},
       {"id": "BRAND", "value_name": "Generic"},
       {"id": "GENDER", "value_id": "339665"},
       {"id": "MODEL", "value_name": "Generic Model"},
       {"id": "PACKAGE_WEIGHT", "value_name": "1 kg"},
       {"id": "PACKAGE_LENGTH", "value_name": "30 cm"},
       {"id": "PACKAGE_WIDTH", "value_name": "20 cm"},
       {"id": "PACKAGE_HEIGHT", "value_name": "15 cm"},
       {"id": "ITEM_CONDITION", "value_id": "2230284", "value_name": "New"}
   ],
   "variations": [
       {
           "attribute_combinations": [
               {"id": "COLOR", "value_name": "Black"},
               {"id": "SIZE", "value_name": "7 US-W"}
           ],
           "price": 30,
           "available_quantity": 5,
           "picture_ids": ["https://http2.mlstatic.com/D_644516-CBT51699767208_092022-O.jpg"],
           "attributes": [
               {"id": "SIZE_GRID_ROW_ID", "value_name": "4326431:1"}
           ]
       },
       {
           "attribute_combinations": [
               {"id": "COLOR", "value_name": "Black"},
               {"id": "SIZE", "value_name": "8 US-W"}
           ],
           "price": 30,
           "available_quantity": 5,
           "picture_ids": ["https://http2.mlstatic.com/D_644516-CBT51699767208_092022-O.jpg"],
           "attributes": [
               {"id": "SIZE_GRID_ROW_ID", "value_name": "4326431:2"}
           ]
       },
       {
           "attribute_combinations": [
               {"id": "COLOR", "value_name": "Blue"},
               {"id": "SIZE", "value_name": "9 US-W"}
           ],
           "price": 30,
           "available_quantity": 5,
           "picture_ids": ["https://http2.mlstatic.com/D_862503-CBT51700450573_092022-O.jpg"],
           "attributes": [
               {"id": "SIZE_GRID_ROW_ID", "value_name": "4326431:3"}
           ]
       }
   ]
}'
```

## Verify created item

After creating an item, you can verify it was created correctly with the
size chart associated:

  

Request:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/marketplace/items/$ITEM_ID
```

Response: **200 OK** or **206 Partial Content**

  

The response will include the **SIZE\_GRID\_ID** in the attributes and
**SIZE\_GRID\_ROW\_ID** in each variation's attributes.

## Result items with size chart

The publication result in Mercado Libre is that:

![](https://http2.mlstatic.com/storage/developers-site-cms-admin/197532645444-Captura-de-Tela-2024-03-04-a-s-14.48.02.png)

<div class="andes-message andes-message--neutral">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--neutral site-carriers__message-title">

Notes:

</div>

<div class="andes-message__text--neutral site-carriers__message-text">

<div>

After the creation of the item we run an automation that makes an update
to the rows of the size chart for each site.  
The international size chart becomes a local guide for publication on
the site.

</div>

</div>

</div>

</div>

![](https://http2.mlstatic.com/storage/developers-site-cms-admin/197532636089-Captura-de-Tela-2024-03-04-a-s-14.48.10.png)

## Validations

-   **Title length**: The item title must not exceed 60 characters for
    certain categories.
-   **Unique variations**: Each variation must have a unique combination
    of attributes. Duplicate variations (same COLOR and SIZE) are not
    allowed.

## Errors

### Size Chart Errors

| Status code | Error code                            | Error message                                       | Description                                                    |
|-------------|---------------------------------------|-----------------------------------------------------|----------------------------------------------------------------|
| `400`       | `missing.fashion_grid.grid_id.values` | Size Chart: attribute \[SIZE\_GRID\_ID\] is missing | The SIZE\_GRID\_ID attribute is required but was not provided. |
| `422`       | `size_grid.id.not_found`              | Size chart: Size chart not found                    | The SIZE\_GRID\_ID provided does not exist or is invalid.      |
| `400`       | `invalid.fashion_grid.size.values`    | Attribute \[SIZE\] is not valid                     | The SIZE value does not exist in the size chart rows.          |

### Item Validation Errors

| Status code | Error code                  | Error message                                                             | Description                                                                    |
|-------------|-----------------------------|---------------------------------------------------------------------------|--------------------------------------------------------------------------------|
| `400`       | `body.required_fields`      | The body does not contains the following properties \[...\]               | Required fields are missing. Check the list of required fields above.          |
| `400`       | `body.invalid_fields`       | Attribute \[field\] is not valid                                          | A field has an invalid value (e.g., invalid category\_id, site\_id, or price). |
| `400`       | `item.title.length.invalid` | Category does not support titles greater than 60 characters long          | The title exceeds the maximum allowed length of 60 characters.                 |
| `400`       | `attributes.duplicated`     | Variation attribute is duplicated                                         | Two or more variations have the same attribute combination (COLOR + SIZE).     |
| `400`       | `picture.id.invalid`        | Invalid pictures.id                                                       | The picture URL or ID provided is invalid.                                     |
| `400`       | `bad_request`               | syntax\_error: invalid character looking for beginning of value           | The request body contains invalid JSON.                                        |
| `404`       | `not_found`                 | Item with id {ITEM\_ID} not found                                         | The item ID does not exist when trying to GET an item.                         |
| `400`       | `item_not_modifiable`       | Cannot delete listing because one or more site listing related are active | Cannot close an item that has active listings in destination sites.            |

**Next**:
[Validations](https://global-selling.mercadolibre.com/devsite/size-chart-validation)

</div>
