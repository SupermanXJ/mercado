<div class="inner-content">

## Catalog eligibility

## Identify an eligible publication for catalogue

It is important that before publishing, you recognize which publications
created are eligible or can be published in the catalog. For this, you
can use the catalog\_listing\_eligible tag and recognize the posts
easily or opt for the eligibility resources of a post or the multiget to
verify a set of posts.

<div class="andes-message andes-message--neutral">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--neutral site-carriers__message-title">

Note:

</div>

<div class="andes-message__text--neutral site-carriers__message-text">

<div>

At the moment, only certain publications can participate in the catalog
that meet certain requirements such as being new and in the CELLPHONES
domain it is necessary for the phone to be released.

</div>

</div>

</div>

</div>

## Filter items

This filter will differentiate between catalog and marketplace (or
general) publications. For that, you must **use the catalog\_listing
parameter in the search** with the value true or false, depending on
what you want to consult.  
First, we identify all the catalog items of a seller. Keep in mind that
you must pass the corresponding status parameter in case you want to add
a filter such as **status="active"**.

Request:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/users/$USER_ID/items/search?catalog_listing=true
```

Example:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/users/123456789/items/search?catalog_listing=true
```

Catalog items short response:

``` language-javascript
{
   "seller_id":"123456789",
   "query":null,
   "paging":{
      "limit":50,
      "offset":0,
      "total":8
   },
   "results":[
      "CBT123456789",
      "CBT234567890",
      "CBT345678912",
      "CBT456789123",
      "CBT567891234",
      "CBT678912345",
      "CBT789123456",
      "CBT891234567"
   ],
   "orders":[ ],
   "available_orders":[ ]
}
```

Also, you can use the same filter to identify all the seller´s
non-catalog items.

Request:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/users/$USER_ID/items/search?catalog_listing=false
```

Example:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/users/123456789/items/search?catalog_listing=false
```

Marketplace items´ short response:

``` language-javascript
{
   "seller_id":"123456789",
   "query":null,
   "paging":{
      "limit":50,
      "offset":0,
      "total":2902
   },
   "results":[
      "CBT987654321",
      "CBT123789456",
      "CBT456789123",
      "CBT132465798",
      "CBT978645312",
      "CBT312645978",
      "CBT654987321",
      "CBT123789654"
   ],
   "orders":[ ],
   "available_orders":[ ]
}
```

## Eligibility tag for items

Through the search resource, you will be able to identify all the items
of the sellers that are eligible for the catalog with the
**catalog\_listing\_eligible** tag and that are not yet participating in
it. Make the following request to consult them:

Request:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/users/$USER_ID/items/search?tags=catalog_listing_eligible
```

Example:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/users/123456987/items/search?tags=catalog_listing_eligible
```

Short response:

``` language-javascript
{
    "seller_id": "123456987",
    "query": null,
    "paging": {
        "limit": 50,
        "offset": 0,
        "total": 1
    },
    "results": [
        "CBT123456789"
    ],
    "orders": [ ],
    "available_orders": [ ]
}
```

The search response returns all seller's items with the
**catalog\_listing\_eligible tag**.

Eligible item example:

``` language-javascript
{
   "id":"CBT123456789",
   "site_id":"CBT",
   "title":"Test item, please don't buy --kc:off",
   "subtitle":null,
   "seller_id":123456987,
   "category_id":"CBT3530",
   "official_store_id":null,
   "price":50,
   "base_price":50,
   "original_price":null,
   "currency_id":"USD",
   "initial_quantity":1,
   "available_quantity":1,
   "sold_quantity":0,
   "sale_terms":[ ],
   "buying_mode":"buy_it_now",
   "listing_type_id":"free",
   "start_time":"2020-02-17T16:30:39.000Z",
   "stop_time":"2020-04-17T04:00:00.000Z",
   "condition":"used",
   "permalink":"https://articulo.mercadolibre.com.ar/CBT-839616438-test-item-please-don't-buy-kcoff-_JM",
   "thumbnail":"http://mla-s1-p.mlstatic.com/951410-CBT40807113659_022020-I.jpg",
   "secure_thumbnail":"https://mla-s1-p.mlstatic.com/951410-CBT40807113659_022020-I.jpg",
   "pictures":[ ],
   "video_id":null,
   "descriptions":[ ],
   "accepts_mercadopago":true,
   "non_mercado_pago_payment_methods":[ ],
   "shipping":{ },
   "international_delivery_mode":"none",
   "seller_address":{ },
   "seller_contact":null,
   "location":{ },
   "geolocation":{ },
   "coverage_areas":[ ],
   "attributes":[ ],
   "warnings":[ ],
   "listing_source":"",
   "variations":[ ],
   "status":"active",
   "sub_status":[ ],
   "tags":[
      "catalog_listing_eligible",
      "good_quality_picture",
      "test_item",
      "immediate_payment"
   ],
   "warranty":null,
   "catalog_product_id":null,
   "domain_id":"CBT-UNCLASSIFIED_PRODUCTS",
   "parent_item_id":null,
   "differential_pricing":null,
   "deal_ids":[ ],
   "automatic_relist":false,
   "date_created":"2020-02-17T16:30:40.000Z",
   "last_updated":"2020-02-17T16:34:12.000Z",
   "health":0.4,
   "catalog_listing":false
}
```

## Validate eligibility to catalog

The following examples show how to validate the eligibility of an
existing publication to link to a new catalog publication with
synchronized stock that has an associated **catalog\_product\_id**.

Request:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/items/$ITEM_ID/catalog_listing_eligibility
```

Example with variations:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/items/CBT123456789/catalog_listing_eligibility
```

Response:

``` language-javascript
{
   "id": "CBT123456789",
   "site_id": "CBT",
   "domain_id": "CBT-CELLPHONES",
   "user_product_id": "CBTU3295251399",
   "buy_box_eligible": true,
   "reason": null,
   "status": "READY_FOR_OPTIN",
   "variations": [ ],
   "site_items": [
       {
           "id": "MLM856092927",
           "site_id": "MLM",
           "domain_id": "MLM-CELLPHONES",
           "user_product_id": "MLMU3301082428",
           "buy_box_eligible": false,
           "reason": "item_catalog_product_id_null",
           "status": "CATALOG_PRODUCT_ID_NULL",
           "variations": [ ],
           "site_items": [ ]
       },
       {
           "id": "MLM856092926",
           "site_id": "MLM",
           "domain_id": "MLM-CELLPHONES",
           "user_product_id": "MLMU3301082429",
           "buy_box_eligible": true,
           "reason": null,
           "status": "READY_FOR_OPTIN",
           "variations": [
               {
                   "id": 1312323,
                   "status": "READY_FOR_OPTIN",
                   "buy_box_eligible": true
               },
               {
                   "id": 1312444,
                   "status": "READY_FOR_OPTIN",
                   "buy_box_eligible": true
               }
           ],
           "site_items": [ ]
       }
   ]
}
```

Example without variations:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN'https://api.mercadolibre.com/items/CBT1234/catalog_listing_eligibility
```

Response:

``` language-javascript
{
   "id": "CBT1234",
   "site_id": "CBT",
   "domain_id": "CBT-CELLPHONES",
   "user_product_id": "CBTU3295251400",
   "buy_box_eligible": true,
   "reason": null,
   "status": "READY_FOR_OPTIN",
   "variations": [ ],
   "site_items": [
       {
           "id": "MLM321",
           "site_id": "MLM",
           "domain_id": "MLM-CELLPHONES",
           "user_product_id": "MLMU3301082430",
           "buy_box_eligible": false,
           "reason": "item_catalog_product_id_null",
           "status": "CATALOG_PRODUCT_ID_NULL",
           "variations": [ ],
           "site_items": [ ]
       },
       {
           "id": "MLM322",
           "site_id": "MLM",
           "domain_id": "MLM-CELLPHONES",
           "user_product_id": "MLMU3301082431",
           "buy_box_eligible": true,
           "reason": null,
           "status": "READY_FOR_OPTIN",
           "variations": [ ],
           "site_items": [ ]
       }
   ]
}
```

### Considerations

-   If the item does not have variations, the eligibility will be
    expressed through the first level buy\_box\_eligible field in the
    json of the response and the variations section will be empty.
-   If the item has variations, the eligibility of each of them will be
    expressed within the variations section, which will contain an array
    per variation with a buy\_box\_eligible field for each of them.

### Description of fields

**id**: ID of the publication we are consulting.  
**site\_id**: ID of the site to which the item belongs.  
**domain\_id**: ID of the domain to which the item belongs.  
**user\_product\_id**: Unique identifier for the user's product
association. Format follows the pattern {SITE\_ID}U{numeric\_id} (e.g.,
CBTU3295251399, MLMU3301082428).  
**buy\_box\_eligible**: indicates whether the item/variation is enabled
or not to participate in the catalog.  
**variations**: are all the variations that an item has. Each one will
have associated a status and a value for the buy\_box\_eligible field.  
**status**: defines the situation of the traditional item with respect
to the catalog. The different states may be:  

**Eligible**:

-   **READY\_FOR\_OPTIN**: the item can be published in the catalog.

**Not eligible**:

-   **ALREADY\_OPTED\_IN**: the traditional item being queried already
    has an associated catalog item.
-   **CLOSED**: the item is in a condition that can no longer be sold.
-   **PRODUCT\_INACTIVE**: the item is associated with a product that
    has not yet been catalog-enabled or the item does not yet have a
    catalog\_product\_id assigned.
-   **NOT\_ELIGIBLE**: There is a business rule that prevents the item
    from applying to the catalog. (ex: a used cellphone, a cellphone
    without releasing).
-   **CATALOG\_PRODUCT\_ID\_NULL**: the item does not have a
    catalog\_product\_id assigned yet. The reason field will show
    "item\_catalog\_product\_id\_null".

If you query for a competing catalog item, the status will be
**COMPETING**.

  

## Multiple publications

To check if multiple publications are eligible for catalog, make a
single request. You must incorporate the ids parameter in the url, in
addition to request the multiget resource, as follows:

Request:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/multiget/catalog_listing_eligibility?ids=$ITEM_ID,$ITEM_ID
```

Example:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/multiget/catalog_listing_eligibility?ids=CBT818878419,CBT820167922
```

Response:

``` language-javascript
[
   {
       "code": 200,
       "body": {
           "id": "CBT123456",
           "site_id": "CBT",
           "domain_id": "CBT-CELLPHONES",
           "user_product_id": "CBTU3295251401",
           "buy_box_eligible": true,
           "reason": null,
           "status": "READY_FOR_OPTIN",
           "variations": [ ],
           "site_items": [
               {
                   "id": "MLM123456",
                   "site_id": "MLM",
                   "domain_id": "MLM-CELLPHONES",
                   "user_product_id": "MLMU3301082432",
                   "buy_box_eligible": false,
                   "reason": "item_catalog_product_id_null",
                   "status": "CATALOG_PRODUCT_ID_NULL",
                   "variations": [ ],
                   "site_items": [ ]
               },
               {
                   "id": "MLM123457",
                   "site_id": "MLM",
                   "domain_id": "MLM-CELLPHONES",
                   "user_product_id": "MLMU3301082433",
                   "buy_box_eligible": true,
                   "reason": null,
                   "status": "READY_FOR_OPTIN",
                   "variations": [ ],
                   "site_items": [ ]
               }
           ]
       }
   },
   {
       "code": 200,
       "body": {
           "id": "CBT123457",
           "site_id": "CBT",
           "domain_id": "CBT-CELLPHONES",
           "user_product_id": "CBTU3295251402",
           "buy_box_eligible": true,
           "reason": null,
           "status": "READY_FOR_OPTIN",
           "variations": [ ],
           "site_items": [
               {
                   "id": "MLM1234568",
                   "site_id": "MLM",
                   "domain_id": "MLM-CELLPHONES",
                   "user_product_id": "MLMU3301082434",
                   "buy_box_eligible": false,
                   "reason": "item_catalog_product_id_null",
                   "status": "CATALOG_PRODUCT_ID_NULL",
                   "variations": [ ],
                   "site_items": [ ]
               },
               {
                   "id": "MLM1234569",
                   "site_id": "MLM",
                   "domain_id": "MLM-CELLPHONES",
                   "user_product_id": "MLMU3301082435",
                   "buy_box_eligible": true,
                   "reason": null,
                   "status": "READY_FOR_OPTIN",
                   "variations": [ ],
                   "site_items": [ ]
               }
           ]
       }
   }
]
```

### Response fields

**code**: it´s the HTTP status code that the query returns with each
item\_id, if there is no error it must be 200.  
**body**: body of the message that returns this request to the
eligibility API.

  

**Next**: [Product
search](https://global-selling.mercadolibre.com/devsite/products-search-gs).

</div>
