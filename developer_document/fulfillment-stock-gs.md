<div class="inner-content">

## Fulfillment stock

<div class="andes-message andes-message--highlight">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--highlight site-carriers__message-title">

Important:

</div>

<div class="andes-message__text--highlight site-carriers__message-text">

<div>

This resource is available in Mexico and Chile where there is
Fulfillment.

</div>

</div>

</div>

</div>

<div class="details__message">

Now you can check the current stock of the items managed by fulfillment,
as well as the operations and movements that modify it.

</div>

## Get the inventory\_id

To query the stock and the operations of the item in fulfillment, you
must first get the inventory\_id which is the code that identifies the
item when it is in fulfillment. For this, consult the inventory\_id
through the /marketplace/items resource.

Request:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/marketplace/items/$ITEM_ID
```

Example:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/marketplace/items/MLM731281338
```

Response:

``` language-javascript
{
   "id": "MLM731281338",
   "site_id": "MLM",
   "date_created": "2019-10-24T13:57:07Z",
   "title": "Precios Cruzados De Teléfono Móvil",
   "descriptions": [],
   "listing_type_id": "gold_pro",
   "permalink": "https://articulo.mercadolibre.com.mx/MLM-731281338-precios-cruzados-de-telefono-movil-_JM",
   "shipping": {
       "mode": "me2",
       "free_shipping": true,
       "logistic_type": "fulfillment"
   },
   "status": "active",
   "sub_status": [],
   "tags": [],
   "warranty": "Sin garantía",
   "catalog_product_id": null,
   "domain_id": "MLM-CELLPHONES",
   "international_delivery_mode": "none",
   "inventory_id": "RJMD90854",
   "category_id": "MLM1055",
   "official_store_id": null,
   "sold_quantity": 54,
   "available_quantity": 425,
   "last_updated": "2020-08-21T20:29:11.137Z",
   "seller_id": 481246451,
   "price": 101,
   "currency_id": "USD",
   "base_exchange_rate": 22.63,
   "user_logistic_type": "fulfillment",
   "owner_id": 0,
   "cbt_item_id": "CBT910331676",
   "variations": [
       {
           "id": 45339522560,
           "price": 101,
           "currency_id": "USD",
           "attribute_combinations": [
               {
                   "id": "COLOR",
                   "name": "Color",
                   "value_id": "52019",
                   "value_name": "Verde oscuro",
                   "value_struct": null,
                   "values": [
                       {
                           "id": "52019",
                           "name": "Verde oscuro",
                           "struct": null
                       }
                   ]
               }
           ],
           "available_quantity": 421,
           "sold_quantity": 54,
           "sale_terms": [],
           "picture_ids": [
               "864698-CBT32645328137_102019",
               "867505-MLM32651561277_102019"
           ],
           "seller_custom_field": null,
           "catalog_product_id": null,
           "inventory_id": "RJMD90854",
           "item_relations": []
       }
   ]
}
```

### Response fields

**id**: The item's unique identifier.  
**site\_id**: The site where the item is listed.  
**inventory\_id**: The code that identifies the item in Fulfillment. Use
this ID to query stock and operations.  
**shipping**: Shipping configuration for the item.

-   **mode**: The shipping mode (e.g., "me2").
-   **free\_shipping**: Whether shipping is free for this item.
-   **logistic\_type**: The logistic type. For Fulfillment items, this
    value is "fulfillment".

**user\_logistic\_type**: The seller's logistic type configuration.  
**variations**: List of item variations. Each variation has its own
inventory\_id.

<div class="andes-message andes-message--neutral">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--neutral site-carriers__message-title">

Note:

</div>

<div class="andes-message__text--neutral site-carriers__message-text">

<div>

When the item has variations, it will have an id of inventory\_id per
variation.

</div>

</div>

</div>

</div>

### Possible errors

| Status | Message           | Error       | Description                                                                                                      |
|--------|-------------------|-------------|------------------------------------------------------------------------------------------------------------------|
| 400    | Invalid Parameter | Bad Request | The item ID format is invalid or empty. Verify that the item ID follows the correct format (e.g., MLM731281338). |
| 404    | Item not found    | not\_found  | The requested item does not exist.                                                                               |

  

## Check the seller's stock

Also, you can check the total stock of a seller in all Fulfillment
warehouses and know the status of the unavailable parts.

### Parameters

| Parameter           | Type    | Required | Description                                                         |
|---------------------|---------|----------|---------------------------------------------------------------------|
| seller\_id          | integer | **Yes**  | The seller's unique identifier.                                     |
| include\_attributes | string  | No       | Include additional attributes in the response. Value: `conditions`. |

  

Request:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/marketplace/inventories/$INVENTORY_ID/stock/fulfillment?seller_id=$SELLER_ID
```

Example:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/marketplace/inventories/TKQK18938/stock/fulfillment?seller_id=481246451
```

Response:

``` language-javascript
{
   "inventory_id": "TKQK18938",
   "total": 20,
   "available_quantity": 5,
   "not_available_quantity": 15,
   "not_available_detail":[
       {
           "status": "damage",
           "quantity": 2
       },
       {
           "status": "lost",
           "quantity": 1
       },
       {
           "status": "noFiscalCoverage",
           "quantity": 5
       },
       {
           "status": "withdrawal",
           "quantity": 5
       },
       {
           "status": "internal_process",
           "quantity": 1
       },
       {
           "status": "transfer",
           "quantity": 1
       }
   ],
   "external_references": [
       {
       "type": "item",
       "id": "MLM790582929",
       "variation_id": 59167987634
     }
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

The query date returns until day -1. In this case, it returns operations
from 06/29 to 07/27, that is, it does not include the 28th.

</div>

</div>

</div>

</div>

### Success response

#### When it returns 200 OK

-   **The requested inventory\_id exists.**
-   **The caller is authorized: the seller\_id in the request is the
    owner of the inventory or belongs to the same merchant hierarchy
    (parent/child). Response body**
-   **Same schema shown in the Response section above.**

  

<div class="andes-message andes-message--neutral">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--neutral site-carriers__message-title">

Notes:

</div>

<div class="andes-message__text--neutral site-carriers__message-text">

<div>

\- seller\_id must be a valid integer; otherwise 400
validation\_error.  
- If the inventory exists but is not associated to the seller or its
hierarchy: 404 not\_found ("The inventory does not exist or is not
associated").  
- If the access token is invalid or the user cannot be identified:
401/403.  

</div>

</div>

</div>

</div>

  

### Response fields

**total**: is the sum of the available\_quantity and
not\_available\_quantity fields.  
**available\_quantity**: quantity of items available for sale.  
**not\_available\_quantity**: total items that are not available for
sale.  
**not\_available\_detail**: detail of the status of the items that are
not available.  

-   **damaged**: total of damaged items (includes damaged seller, meli
    and carrier).
-   **lost**: total items that were lost and not found.
-   **withdrawal**: total items reserved for pick up.

**internal\_process**: total of items reserved by quality processes of
the warehouse.  
**transfer**: total reserved to be transferred deposit.  
**noFiscalCoverage**: total items that are not for sale because they do
not have tax coverage.  
**notSupported**: all items entered are unidentifiable or
unprocessable.  
**external\_references**: information on the relationship of the
inventory with the marketplace publication, and an identification of the
type.  
**type**: type of relationship between publication and stored stock.  
**id**: identifier of the item related to the inventory.  
**variation\_id**: identifier of the variation associated with the
inventory.  

  

### Considerations

-   User wants to modify stock of an item without variations.
    -   PUT sending "available\_quantity" -**Action not allowed.**
-   User wants to modify stock of a particular variation.
    -   PUT sending "available\_quantity" of one or more variations
        -**Action not permitted.**
-   User wants to indicate a further variation of their product.
    -   PUT sending "variations" field with a new variation - **Action
        allowed.**
    -   The value sent in "available\_quantity" is omitted, setting it
        to 0. This allows you to synchronize the deposit stock with the
        Items API.

  

### Errors

Response with error:

``` language-javascript
{
   "status": 403,
   "error": "forbidden",
   "message": "User 281349747 cannot access to seller_product ESZJ28231",
   "cause": []
}
```

### Possible errors

| Status | Message                                              | Error                                    | Description                                                                                                         |
|--------|------------------------------------------------------|------------------------------------------|---------------------------------------------------------------------------------------------------------------------|
| 400    | seller\_id is required                               | bad\_request                             | The seller\_id query parameter is missing. Add the seller\_id query parameter to your request.                      |
| 400    | invalid inventory\_id format                         | bad\_request                             | The inventory\_id format is incorrect. Verify that the inventory\_id follows the correct format (e.g., TKQK18938).  |
| 400    | invalid seller\_id format                            | bad\_request                             | The seller\_id must be a numeric value. Provide a valid numeric seller\_id.                                         |
| 400    | The field inventory\_id has an invalid value         | validation\_error                        | Invalid parameter                                                                                                   |
| 401    | Unauthorized                                         | unauthorized                             | The caller is not authenticated on the platform.                                                                    |
| 403    | The caller is not authorized to access this resource | forbidden                                | The caller is not authorized to access the resource.                                                                |
| 403    | At least one policy returned UNAUTHORIZED            | PA\_UNAUTHORIZED\_RESULT\_FROM\_POLICIES | The caller is not authorized by PolicyAgent. Verify your access token has the required permissions for this seller. |
| 404    | Inventory not found with id: ESZJ28232               | seller\_product\_not\_found              | The requested inventory cannot be found.                                                                            |
| 404    | seller not found or not authorized                   | not\_found                               | The seller does not exist or you are not authorized to access their resources.                                      |
| 404    | Not found                                            | inventory\_not\_associated               | The inventory does not exist or is not associated to the seller or its hierarchy.                                   |
| 429    | Too many request                                     | too\_many\_request                       | The user has exceeded the number of requests allowed per minute.                                                    |
| 500    | Internal server error                                | internal\_error                          | Internal error to get the information.                                                                              |

  

## Check the detail of stock not available

This resource returns additional information about the units stored in
full that are not available for sale, describing certain attributes or
particular conditions of these.

Request:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/marketplace/inventories/$INVENTORY_ID/stock/fulfillment?include_attributes=conditions&seller_id=$SELLER_ID
```

Example:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/marketplace/inventories/YLXH33638/stock/fulfillment?include_attributes=conditions&seller_id=1234
```

Response:

``` language-javascript
{
 "inventory_id": "YLXH33638",
 "total": 20,
 "available_quantity": 5,
 "not_available_quantity": 15,
 "not_available_detail": [
   {
     "status": "damaged",
     "quantity": 2,
     "conditions": [
       {
         "condition": "arrived_damaged",
         "quantity": 1
       },
       {
         "condition": "damaged_in_full",
         "quantity": 1
       }
     ]
   },
   {
     "status": "lost",
     "quantity": 1
   },
   {
     "status": "notSupported",
     "quantity": 3,
     "conditions": [
       {
         "condition": "dimensions_exceeds",
         "quantity": 1
       },
       {
         "condition": "flammable",
         "quantity": 1
       },
       {
         "condition": "multiple_identifier",
         "quantity": 1
       }
     ]
   }
 ]
}
```

damaged, notSupported, lost, withdrawal, no\_fiscal\_coverage,
internal\_process and transfer are the possible statuses.

The statuses with additional information are:

**Damaged**: It provides information on the damaged units stored in the
warehouse that allows integrators to act according to whether they are
damaged in warehouse or if they arrived damaged.  
**Not supported**: Provides information on not supported (NS) products
in stock, that is, products that cannot be put on sale due to an
identification problem or because they belong to unsuitable categories.

Know the conditions by which we identify a product as damaged or does
not meet the requirements to enter the Fulfillment center. It also
applies to products entered and that we subsequently detect a problem.

<div class="content">

<div class="tab">

| Status Not available | Condition            | Product description                                                                    |
|----------------------|----------------------|----------------------------------------------------------------------------------------|
| **damaged**          | arrived\_damaged     | Arrived damaged by seller                                                              |
|                      | damaged\_in\_full    | It is damaged within the warehouse or by the carrier                                   |
| **not supported**    | dimensions\_exceeds  | Exceeds the permitted storage dimensions of the Fulfillment center                     |
|                      | expiration\_problem  | Had a problem related to its expiration                                                |
|                      | package\_problem     | There is no packaging or it is not appropriate for the Fulfillment center              |
|                      | flammable            | It is flammable or explosive                                                           |
|                      | regulation\_problem  | Does not comply with the regulations for the type of product, for example, health seal |
|                      | other                | Any condition not specified in the previous points                                     |
|                      | multiple\_identifier | Has the universal code duplicated (EAN)                                                |
|                      | empty\_identifier    | Has no seller ID/tag or no EAN in the Fulfillment center database                      |
|                      | multiple\_sku        | You have two or more Mercado Libre SKUs                                                |
|                      | invalid\_identifier  | It has the wrong universal code                                                        |
|                      | return\_problem      | It was returned by the buyer for not meeting the quality specified in the sale         |

</div>

</div>

  

## Receive stock notifications from Fulfillment

[Configure your application with Mercado Libre
notifications](https://global-selling.mercadolibre.com/devsite/receive-notifications#marketplace-fbm-stock)
and you will be able to choose the **marketplace\_fbm\_stock** option to
subscribe to fulfillment stock notifications.

  

## Check operations

Get the list of stock operations for a particular inventory\_id.

  

### Parameters

| Parameter                         | Type    | Required | Description                                                                                                                        |
|-----------------------------------|---------|----------|------------------------------------------------------------------------------------------------------------------------------------|
| seller\_id                        | integer | **Yes**  | The seller's unique identifier.                                                                                                    |
| inventory\_id                     | string  | **Yes**  | Comma separated list of inventory identifiers.                                                                                     |
| date\_from                        | string  | **Yes**  | Search start date in ISO 8601 format (`YYYY-MM-DD`). Example: `2024-01-01`.                                                        |
| date\_to                          | string  | **Yes**  | Search end date in ISO 8601 format (`YYYY-MM-DD`). Example: `2024-01-31`. The date range cannot exceed 60 days.                    |
| type                              | string  | No       | Operation type filter (e.g., INBOUND\_RECEPTION, SALE\_CONFIRMATION, ADJUSTMENT, etc.). See [Operations types](#Operations-types). |
| external\_references.shipment\_id | string  | No       | Filter by shipment identifier.                                                                                                     |
| limit                             | integer | No       | Number of records to return per page (max: 1000). Default: 1000.                                                                   |
| scroll                            | string  | No       | Pagination cursor returned from previous request.                                                                                  |
| sort                              | string  | No       | Field identifier and search order.                                                                                                 |

  

<div class="andes-message andes-message--highlight">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--highlight site-carriers__message-title">

Important:

</div>

<div class="andes-message__text--highlight site-carriers__message-text">

<div>

The `date_from` and `date_to` parameters are **mandatory**. The date
range cannot exceed 60 days. The query returns operations up to day -1
(e.g., if `date_to` is 2024-07-28, operations from 07/28 are not
included).

</div>

</div>

</div>

</div>

  

Request:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/marketplace/stock/fulfillment/operations/search?seller_id=$SELLER_ID&inventory_id=$INVENTORY_ID&date_from=$YYYY-MM-DD&date_to=$YYYY-MM-DD
```

Example:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/marketplace/stock/fulfillment/operations/search?seller_id=384324657&inventory_id=DEHW09303&date_from=2024-06-01&date_to=2024-06-30
```

Example with filters:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/marketplace/stock/fulfillment/operations/search?seller_id=384741716&inventory_id=NFWV18668&date_from=2024-06-29&date_to=2024-07-28&type=SALE_CONFIRMATION&external_references.shipment_id=1111
```

Response:

``` language-javascript
{
   "paging": {
       "total": 4,
       "scroll": ""
   },
   "results": [
       {
           "id": 306811273,
           "seller_id": 384324657,
           "inventory_id": "DEHW09303",
           "date_created": "2020-06-18T18:43:26Z",
           "type": "ADJUSTMENT",
           "detail": {
               "available_quantity": -5,
               "not_available_quantity": 5,
               "not_available_detail": [
                   {
                       "status": "lost",
                       "quantity": 5
                   }
               ]
           },
           "result": {
               "total": 100,
               "available_quantity": 95,
               "not_available_quantity": 5,
               "not_available_detail": [
                   {
                       "status": "lost",
                       "quantity": 5
                   }
               ]
           },
           "external_references": []
       },
       {
           "id": 306745917,
           "seller_id": 384324657,
           "inventory_id": "DEHW09303",
           "date_created": "2020-06-18T18:15:13Z",
           "type": "SALE_CANCELATION",
           "detail": {
               "available_quantity": 10,
               "not_available_detail": []
           },
           "result": {
               "total": 100,
               "available_quantity": 100,
               "not_available_quantity": 0,
               "not_available_detail": []
           },
           "external_references": [
               {
                   "type": "shipment_id",
                   "value": "28312959315"
               }
           ]
       },
       {
           "id": 306718974,
           "seller_id": 384324657,
           "inventory_id": "DEHW09303",
           "date_created": "2020-06-18T18:02:33Z",
           "type": "SALE_CONFIRMATION",
           "detail": {
               "available_quantity": -10,
               "not_available_detail": []
           },
           "result": {
               "total": 90,
               "available_quantity": 90,
               "not_available_quantity": 0,
               "not_available_detail": []
           },
           "external_references": [
               {
                   "type": "shipment_id",
                   "value": "28312961122"
               }
           ]
       },
       {
           "id": 306705012,
           "seller_id": 384324657,
           "inventory_id": "DEHW09303",
           "date_created": "2020-06-18T17:55:42Z",
           "type": "INBOUND_RECEPTION",
           "detail": {
               "available_quantity": 100,
               "not_available_detail": []
           },
           "result": {
               "total": 100,
               "available_quantity": 100,
               "not_available_quantity": 0,
               "not_available_detail": []
           },
           "external_references": [
               {
                   "type": "inbound_id",
                   "value": "0001"
               }
           ]
       }
   ],
   "filters": [],
   "available_filters": [],
   "available_sort": [],
   "sort": [],
   "available_sorts": []
}
```

### Rules

-   In the search for operations, the maximum query range is 60 days.
-   The `date_from` and `date_to` parameters are mandatory.
-   Dates must be in ISO 8601 format (`YYYY-MM-DD`).

Example with available filters:

``` language-javascript
"available_filters": [
       {
           "id": "inventory_id",
           "name": "Inventory  id"
       },
       {
           "id": "date_from",
           "name": "Date created from"
       }
]
```

Example with selected filters:

``` language-javascript
"filters": {
       {
          "id": "inventory_id",
           "name": "Inventory  id"
           "values": [
                 "ESZJ28231"
           ]
       }
]
```

### Possible errors

Response with error:

``` language-javascript
{
   "status": 403,
   "message": "User 281349747 cannot access to inventory ESZJ28231",
   "error": "forbidden",
   "cause": []
}
```

### Errors examples

| Status | Message                                        | Error                                    | Description                                                                                                                                                         |
|--------|------------------------------------------------|------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 400    | Some params are invalid                        | bad\_request                             | One or more required parameters are missing or have invalid values. Verify that seller\_id, inventory\_id, date\_from, and date\_to are provided with valid values. |
| 400    | The field 'seller\_id' is required             | validation\_error                        | The seller\_id parameter is not found.                                                                                                                              |
| 400    | The field 'type' has an invalid value          | validation\_error                        | Invalid operation type parameter. See [Operations types](#Operations-types) for valid values.                                                                       |
| 400    | The limit param must be greater than 0         | validation\_error                        | The request limit parameter must be greater than 0.                                                                                                                 |
| 400    | Date range can't be greater than "60" days     | validation\_error                        | The date range exceeds the limit allowed by days.                                                                                                                   |
| 400    | The field date\_from and date\_to are required | validation\_error                        | The date\_from and date\_to fields are mandatory.                                                                                                                   |
| 400    | date\_from cannot be greater than date\_to     | validation\_error                        | The date\_from field cannot be greater than or equal to the date\_to field.                                                                                         |
| 401    | Unauthorized                                   | unauthorized                             | The caller is not authenticated on the platform.                                                                                                                    |
| 403    | Access denied for user                         | forbidden                                | The caller is not authorized to access the resource.                                                                                                                |
| 403    | At least one policy returned UNAUTHORIZED      | PA\_UNAUTHORIZED\_RESULT\_FROM\_POLICIES | The caller is not authorized by PolicyAgent. Verify your access token has the required permissions.                                                                 |
| 429    | Too many request                               | too\_many\_request                       | The user has exceeded the number of requests allowed per minute.                                                                                                    |
| 500    | Internal server error                          | internal\_error                          | Internal error.                                                                                                                                                     |

  

## Search mode by scroll

### Work with scroll + limit

The **scroll** is used to get the list of stock operations for a
particular inventory\_id.

The **limit** is the number of records to return per "page" of results
and **scroll** is the attribute that allows the results to be paged. To
use it you must:

-   Get a scroll field in the result that expires after 5 minutes.
-   Add to the query the scroll obtained in the first GET. If you don't
    use the limit parameter, by default the maximum 1000 results per
    page is set.

Request to check the operations:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/marketplace/stock/fulfillment/operations/search?seller_id=$SELLER_ID&inventory_id=$INVENTORY_ID&date_from=$YYYY-MM-DD&date_to=$YYYY-MM-DD
```

Response:

``` language-javascript
"scroll":"YXBpY29yZS1pdGVtcw==:ZHMtYXBpY29yZS1pdGVtcy0wMQ==:DXF1ZXJ5QW5kRmV0Y2gBAAAAABIu7AgWMXl6anF3SU5SMVNaQXFxTkZubHBqQQ=="
```

We add the scroll obtained in the previous step:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/marketplace/stock/fulfillment/operations/search?seller_id=$SELLER_ID&inventory_id=$INVENTORY_ID&date_from=$YYYY-MM-DD&date_to=$YYYY-MM-DD&scroll=YXBpY29yZS1pdGVtcw==:ZHMtYXBpY29yZS1pdGVtcy0wMQ==:DXF1ZXJ5QW5kRmV0Y2gBAAAAABIu7AgWMXl6anF3SU5SMVNaQXFxTkZubHBqQQ==
```

To continue getting the next pages of results, just do the same GET
until you reach the end. Only when scroll = null means that we reached
the end and there are no more results.

  

## Check operations with ID

You can obtain the details of a particular operation executed on the
stock that the seller has stored in the Fulfillment warehouses.

### Parameters

| Parameter     | Type    | Required | Description                                                                          |
|---------------|---------|----------|--------------------------------------------------------------------------------------|
| operation\_id | string  | **Yes**  | The operation ID identifier (path parameter).                                        |
| seller\_id    | integer | **Yes**  | The seller's unique identifier (query parameter). Required to authorize the request. |

  

Request:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/marketplace/stock/fulfillment/operations/$OPERATION_ID?seller_id=$SELLER_ID
```

Example:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/marketplace/stock/fulfillment/operations/329663159?seller_id=404584692
```

Response:

``` language-javascript
{
   "id": "329663159",
   "seller_id": 404584692,
   "inventory_id": "FIWU34511",
   "date_created": "2020-06-29T13:45:13Z",
   "type": "SALE_CONFIRMATION",
   "detail": {
       "available_quantity": -1,
       "not_available_detail": []
   },
   "result": {
       "total": 1,
       "available_quantity": 0,
       "not_available_detail": [
           {
               "status": "damaged",
               "quantity": 1
           }
       ]
   },
   "external_references": [
       {
           "type": "shipment_id",
           "value": "28518304587"
       }
   ]
}
```

### Errors example

| Status | Message                                              | Error                                    | Description                                                                                         |
|--------|------------------------------------------------------|------------------------------------------|-----------------------------------------------------------------------------------------------------|
| 400    | The param seller\_id is required                     | bad\_request                             | The seller\_id query parameter is missing. Add the seller\_id query parameter to your request.      |
| 400    | Invalid operation\_id abc34567                       | invalid\_param                           | Invalid parameter. The operation\_id must be a valid numeric identifier.                            |
| 401    | Unauthorized                                         | unauthorized                             | The caller is not authenticated on the platform.                                                    |
| 403    | The caller is not authorized to access this resource | forbidden                                | The caller is not authorized to access the resource.                                                |
| 403    | At least one policy returned UNAUTHORIZED            | PA\_UNAUTHORIZED\_RESULT\_FROM\_POLICIES | The caller is not authorized by PolicyAgent. Verify your access token has the required permissions. |
| 404    | Operation not found                                  | not\_found                               | The requested operation cannot be found.                                                            |
| 500    | Internal server error                                | internal\_error                          | Internal error when obtaining the information.                                                      |

  

<div class="andes-message andes-message--neutral">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--neutral site-carriers__message-title">

Note:

</div>

<div class="andes-message__text--neutral site-carriers__message-text">

<div>

The query date returns until day -1. In this case, it returns operations
from 06/29 to 07/27, that is, it does not include the 28th.

</div>

</div>

</div>

</div>

### Response fields

**Paging**  

-   **limit**: number of records to return per "page" of results. By
    default it will be 1000
-   **scroll**: scroll id from which the search continues. When it
    returns scroll = null means that it has no more records on the next
    page. The scroll rules are:

\- In the result you get a scroll\_id field that expires in 5 minutes.  
- You must add the same scroll\_id to the query of the field obtained
previously.  
- If you don´t use the limit parameter, it will return 1000 operations
of the total by default. You can add a maximum limit of 1000.  
- To continue getting the next pages of results, just do the same GET to
the request until you reach the end of the list.  

  

**results**: list of operations found.

-   **id**: identifier of the stock operation
-   **seller\_id**: identifier of the seller who owns the inventory
-   **inventory\_id**: product identifier in the warehouse
-   **date\_created**: creation date of the operation (type date UTC)
-   **type**: type of operation executed (income, sale, sale canceled,
    etc.)

**result**: stock status

-   **available\_quantity**: quantity of products available for sale.
-   **not\_available\_quantity**: total of products that are not
    available.
-   **not\_available\_detail**: detail of the status of the different
    unavailable units.

**status**: item status not available.  
**quantity**: number of items in the assigned state.  
**external\_references**: references to the entities that generate the
operation.

-   **type**: type of external reference, they can be:
-   **shipment\_id**: identifier of the shipment to the buyer.

  

## Operations types

These types of operations reflect the interactions of the different
flows in the stored units.

  

### Inbound

**inbound\_reception** **Stock entry**: The inbound process makes units
available for sale at the end of the income stream. They can have:  
Entry of units that arrived damaged.  

  

### Outbound

**sale\_confirmation**: confirms the reservation of units for sale.  
**sale\_cancelation**: cancel the reservation of units for sale.  
**sale\_delivery\_cancelation**: it was not possible to deliver to the
buyer and returns to the deposit.  
**sale\_return**: sales return by buyer.

  

### Withdrawal

This is the seller's withdrawal request.

**withdrawal\_reservation**: reserve units for a stock picked.  
**withdrawal\_cancelation**: total or partial cancellation of withdrawal
reservation, the reservation of units for a stock picked is canceled.  
**withdrawal\_delivery**: the seller physically pick up the reserved
units.  
**withdrawal\_removal**: stock removed by abandon withdrawal.

  

### Transfer

It is about the internal management of the stock by Mercado Libre, not
the seller.

**transfer\_reservation**: units are reserved for a multi-warehouse
transfer or pick up.  
**transfer\_ajustment**: after inspecting the units, the quality status
is determined and restocked as available or damaged.  
**transfer\_delivery**: enter the units in transfer.  

  

### Quarantine

It's about internal management over quality control.

**quarantine\_reservation**: They reserve units by the quality area for
inspection.  
**quarantine\_restock**: After inspecting the units, determine the
quality status and restock as available or damaged.  
**lost\_refund**: permanent cancellation of lost units (refunded).  
**damaged\_removal**: removed and reimbursed for units damaged in FULL.

  

### Removal QA

This is an internally driven retreat.

**removal\_reservation**: after inspecting the units, the quality status
is determined and they are retired.  
**removal\_completion**: units with poor quality status are
eliminated.  

  

### Stock adjustments

**adjustment**: internal stock adjustments generated by the operation.

  

**Next**:
[Pictures](https://global-selling.mercadolibre.com/devsite/pictures).

</div>
