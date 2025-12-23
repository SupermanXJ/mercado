<div class="inner-content">

## Items & Searches

<div class="andes-message andes-message--highlight">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--highlight site-carriers__message-title">

Important:

</div>

<div class="andes-message__text--highlight site-carriers__message-text">

<div>

The `/sites/$SITE_ID/search` endpoints now return **403 Forbidden** for
Cross-Border Trade (CBT) integrations. Use
`/users/{USER_ID}/items/search` to search items from your seller
account. See the [Summary of available
resources](#Summary-of-available-resources) table for migration details.

</div>

</div>

</div>

</div>

  

The Items & Searches API allows you to retrieve item information and
search for items within your seller account. For Global Selling (CBT)
integrations, use the authenticated endpoints to access your listings
across all marketplaces.

  

## Summary of available resources

| Resource                                                                        | Description                                                                      | Replace by                                                                            |
|---------------------------------------------------------------------------------|----------------------------------------------------------------------------------|---------------------------------------------------------------------------------------|
| /sites/$SITE\_ID/search?q=$TEXT\_TO\_SEARCH                                     | Get items by a search query. **(Deprecated for CBT - returns 403)**              | https://api.mercadolibre.com/users/{User\_id}/items/search                            |
| /sites/$SITE\_ID/search?category=$CATEGORY\_ID                                  | Get items listed in a category. **(Deprecated for CBT - returns 403)**           | https://api.mercadolibre.com/users/{User\_id}/items/search?category\_id=$CATEGORY\_ID |
| /sites/$SITE\_ID/search?nickname=$NICKNAME                                      | Get items from the listings by nickname. **(Deprecated for CBT - returns 403)**  | There isn't replacement.                                                              |
| /sites/$SITE\_ID/search?seller\_id=$SELLER\_ID                                  | Can list items by seller. **(Deprecated for CBT - returns 403)**                 | https://api.mercadolibre.com/users/{User\_id}/items/search                            |
| /users/$USER\_ID/items/search                                                   | Can list all a seller account's items.                                           | Remains the same.                                                                     |
| /items?ids=$ITEM\_ID1,$ITEM\_ID2                                                | Multiget with multiple numbers of items.                                         | Remains the same.                                                                     |
| /users?ids=$USER\_ID1,$USER\_ID2                                                | Multiget with multiple numbers of users.                                         | Our recommendation is using the individual access token.                              |
| /items?ids=$ITEM\_ID1,$ITEM\_ID2&attributes=$ATTRIBUTE1,$ATTRIBUTE2,$ATTRIBUTE3 | Multiget with multiple numbers of items selecting only the fields of interest.   | Remains the same.                                                                     |
| /users/$USER\_ID/items/search?search\_type=scan                                 | To get more than 1000 records.                                                   | Remains the same.                                                                     |
| /items/$ITEM\_ID/marketplace\_items                                             | To get the mapping between an item on the global site and the marketplace items. | Remains the same.                                                                     |

  
  

## Values in sold\_quantity and available\_quantity fields

In the public resources of Items and Searches, the information of the
"sold\_quantity" and "available\_quantity" fields will be referential
with the following values:

  

<div class="content-table"
style="vertical-align:top;margin:0 30px 10px 0;display:inline-block">

### sold\_quantity

| Real data            | Reference |
|----------------------|-----------|
| 1                    | 1         |
| 2                    | 2         |
| 3                    | 3         |
| 4                    | 4         |
| 5                    | 5         |
| RANGO\_6\_25         | 5         |
| RANGO\_26\_50        | 25        |
| RANGO\_51\_100       | 50        |
| RANGO\_101\_150      | 100       |
| RANGO\_151\_200      | 150       |
| RANGO\_201\_250      | 200       |
| RANGO\_251\_500      | 250       |
| RANGO\_501\_5000     | 500       |
| RANGO\_5001\_50000   | 5000      |
| RANGO\_50001\_500000 | 50000     |

</div>

<div class="content-table"
style="vertical-align:top;margin:0 30px;display:inline-block">

### available\_quantity

| Real data           | Reference |
|---------------------|-----------|
| RANGO\_1\_50        | 1         |
| RANGO\_51\_100      | 50        |
| RANGO\_101\_150     | 100       |
| RANGO\_151\_200     | 150       |
| RANGO\_201\_250     | 200       |
| RANGO\_251\_500     | 250       |
| RANGO\_501\_5000    | 500       |
| RANGO\_5001\_50000  | 5000      |
| RANGO\_50001\_99999 | 50000     |

</div>

  

## Get user items

Retrieve all items from your seller account. This is the recommended
method for CBT integrations.

### Call

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/users/$USER_ID/items/search
```

### Example

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/users/2560656533/items/search
```

### Response

``` language-javascript
{
  "seller_id": "2560656533",
  "results": ["CBT2518294370", "CBT2777715207"],
  "paging": {
    "limit": 50,
    "offset": 0,
    "total": 2
  },
  "query": null,
  "orders": [
    {
      "id": "stop_time_asc",
      "name": "Order by stop time ascending"
    }
  ],
  "available_orders": [
    {"id": "stop_time_asc", "name": "Order by stop time ascending"},
    {"id": "stop_time_desc", "name": "Order by stop time descending"},
    {"id": "start_time_asc", "name": "Order by start time ascending"},
    {"id": "start_time_desc", "name": "Order by start time descending"},
    {"id": "available_quantity_asc", "name": "Order by available quantity ascending"}
  ]
}
```

### Response fields

| Field             | Type        | Description                                        |
|-------------------|-------------|----------------------------------------------------|
| seller\_id        | String      | The seller's user ID.                              |
| results           | Array       | List of item IDs belonging to the seller.          |
| paging            | Object      | Pagination information.                            |
| paging.limit      | Integer     | Maximum number of results per page. Default: 50.   |
| paging.offset     | Integer     | Current offset position in the results.            |
| paging.total      | Integer     | Total number of items in the seller's account.     |
| query             | String/Null | Search query if provided, null otherwise.          |
| orders            | Array       | Current sort order applied to the results.         |
| available\_orders | Array       | List of available sorting options for the results. |

  

### Parameters

| Parameter   | Type    | Description                                                   |
|-------------|---------|---------------------------------------------------------------|
| limit       | Integer | Maximum number of items to return. Default: 50, Maximum: 100. |
| offset      | Integer | Position to start returning results from. Maximum: 1000.      |
| status      | String  | Filter by item status (active, paused, closed).               |
| sku         | String  | Filter by seller\_custom\_field value.                        |
| seller\_sku | String  | Filter by SELLER\_SKU attribute value.                        |

  

### Get user items with pagination

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/users/$USER_ID/items/search?limit=5
```

### By status

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/users/$USER_ID/items/search?status=active
```

### By SKU

-   Seller\_custom\_field: if the item contains a SKU in the
    "seller\_custom\_field" field, you can try as follows:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/users/$USER_ID/items/search?sku=$SELLER_CUSTOM_FIELD
```

-   Seller\_sku: If the item contains a SKU in the "SELLER\_SKU"
    field/attribute, you can try like this:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/users/$USER_ID/items/search?seller_sku=$SELLER_SKU
```

### With/without product identifier

Using the parameters:  
- **missing\_product\_identifiers=true** get items that do not have a
Product Identifier loaded or submitted. Thus, you identify which
listings you can improve by complying with one of the most important
quality requirements.  
- **missing\_product\_identifiers=false** you get the list of listings
with PIs uploaded or sending.

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/users/$USER_ID/items/search?missing_product_identifiers=true
```

  

## Filter and sort the results of the seller's items

Inside the resource /users/{user\_id}/items/search? there are the
"available\_orders" and "available\_filters" fields.

**How to order?** In this case you must add "orders" with the available
ID of the order you want to apply, for example: "start\_time\_desc".

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/users/$USER_ID/items/search?orders=start_time_desc
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

By default it already comes with a stop\_time\_asc order applied.

</div>

</div>

</div>

</div>

**How to filter?** For example, to filter items with listing\_type
"gold\_pro" you will find the "listing\_type\_id" available among the
"available\_filters" and within it the value with "gold\_pro" ID.

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/users/$USER_ID/items/search?listing_type_id=gold_pro
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

The use of our item search resource from a seller does not replace the
use of item notifications. This is always to have the most consistent
and up-to-date integration about the publication data of the vendors
that work with your application.

</div>

</div>

</div>

</div>

  

## Multiget

Use the Multiget function to improve the interaction with the resources
of items and users, and thus be able to access with a single request to
a maximum of 20 results.

Keep in mind that the response using multiget will be returned in verb
format, which means that in addition to the JSON with the information,
we will respond with a code that will indicate if the query was
successful or not for each of the searches.

<div class="andes-message andes-message--neutral">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--neutral site-carriers__message-title">

Note:

</div>

<div class="andes-message__text--neutral site-carriers__message-text">

<div>

When using multiget, always check the `code` field for each item in the
response array. Items not found will have `code: 404` while successful
items have `code: 200`.

</div>

</div>

</div>

</div>

  

Request to /items:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/items?ids=$ITEM_ID1,$ITEM_ID2
```

Example:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/items?ids=CBT2518294370,MLMU3366891824
```

Response:

``` language-javascript
[
  {
    "code": 200,
    "body": {
      "id": "CBT2518294370",
      "site_id": "CBT",
      "title": "Game Test Play Toy",
      "seller_id": 2560656533,
      "category_id": "CBT11625",
      "price": 83,
      "base_price": 83,
      "currency_id": "USD",
      "initial_quantity": 2,
      "available_quantity": 2,
      "sold_quantity": 0
    }
  },
  {
    "code": 404,
    "body": {
      "id": "MLMU3366891824",
      "error": "resource not found",
      "message": "Si quieres conocer los recursos de la API..."
    }
  }
]
```

  

Request to /users:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/users?ids=$USER_ID1,$USER_ID2
```

Example:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/users?ids=2560656533
```

Response:

``` language-javascript
[
  {
    "code": 200,
    "body": {
      "id": 2560656533,
      "nickname": "TESTUSER667696975",
      "registration_date": "2025-07-16T14:35:12.982-04:00",
      "country_id": "US",
      "site_id": "CBT",
      "seller_reputation": {
        "level_id": null,
        "power_seller_status": null,
        "transactions": {
          "canceled": 0,
          "completed": 0,
          "period": "historic",
          "total": 0
        }
      },
      "status": {
        "site_status": "active"
      }
    }
  }
]
```

  

## Fields selection

Another alternative that you can implement in the GET to items is the
selection of fields to receive only those that are necessary.

In order to define the fields you want to receive, you must add the
attributes parameter as shown in the example. Learn more about how to
work with Attributes in the
[documentation](https://global-selling.mercadolibre.com/devsite/atributtes-global-selling).

  

Request:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/items?ids=$ITEM_ID1,$ITEM_ID2&attributes=$ATTRIBUTE1,$ATTRIBUTE2,$ATTRIBUTE3
```

Example:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/items?ids=CBT2518294370&attributes=id,title,price,category_id
```

Response:

``` language-javascript
[
  {
    "code": 200,
    "body": {
      "title": "Game Test Play Toy",
      "category_id": "CBT11625",
      "price": 83,
      "id": "CBT2518294370"
    }
  }
]
```

  

## Search mode above 1000 records

### Work with Scan + Hash

All searches performed in **the Items, Questions and Answers** API of
the form users/{user\_id}/items/search or /questions/search greater than
1000 must have the new search\_type=scan parameter without using the
offset parameter.

<div class="andes-message andes-message--neutral">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--neutral site-carriers__message-title">

Note:

</div>

<div class="andes-message__text--neutral site-carriers__message-text">

<div>

If you want to query data less than 1000, you can continue doing it as
before (with offset).

</div>

</div>

</div>

</div>

The steps to query more than 1000 results are as follows:

-   Add search\_type=scan to query and remove the offset.
-   In the result, you will get a scroll\_id field that expires after 5
    minutes.
-   You must add to the query scroll\_id equal to the field obtained
    previously.
-   You will get the results from position 1000 onwards.
-   If the limit parameter is not used, 50 items of the total will be
    returned by default. You can add a maximum limit of 100.
-   To continue to obtain the next pages of results, just make the same
    GET to the request until you reach the end of the list.

<div class="andes-message andes-message--neutral">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--neutral site-carriers__message-title">

Note:

</div>

<div class="andes-message__text--neutral site-carriers__message-text">

<div>

When the `scroll_id` returns empty (`""`), it means you have reached the
end of the results.

</div>

</div>

</div>

</div>

You can learn how to do it:

-   Add search\_type=scan  
    To get the scroll\_id:

Items:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/users/$USER_ID/items/search?search_type=scan
```

Response:

``` language-javascript
{
  "scroll_id": "eyJpZCI6IkNCVDI3Nzc3MTUyMDciLCJudW1lcmljX2lkIjoyNzc3NzE1MjA3LCJzdG9wX3RpbWUiOiIyMDQ1LTExLTI4VDA0OjAwOjAwLjAwMFoifQ==",
  "seller_id": "2560656533",
  "results": ["CBT2518294370", "CBT2777715207"],
  "paging": {
    "limit": 50,
    "total": 2
  }
}
```

-   We add the scroll\_id= obtained in the previous step:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/users/$USER_ID/items/search?search_type=scan&scroll_id=eyJpZCI6IkNCVDI3Nzc3MTUyMDciLCJudW1lcmljX2lkIjoyNzc3NzE1MjA3LCJzdG9wX3RpbWUiOiIyMDQ1LTExLTI4VDA0OjAwOjAwLjAwMFoifQ==
```

End of results response:

``` language-javascript
{
  "scroll_id": "",
  "seller_id": "2560656533",
  "results": [],
  "paging": {
    "limit": 50,
    "total": 2
  }
}
```

  

## Get the items mappings

This service allows you to obtain all the marketplace items of a Global
(CBT) item.

Request:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/items/$ITEM_ID/marketplace_items
```

Example:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/items/CBT2518294370/marketplace_items
```

Response:

``` language-javascript
{
  "item_id": "CBT2518294370",
  "user_id": 2560656533,
  "site_id": "CBT",
  "date_created": "2025-07-16T18:43:36Z",
  "marketplace_items": [
    {
      "item_id": "MLM2374731499",
      "user_id": 2560656535,
      "site_id": "MLM",
      "date_created": "2025-07-16T18:43:36Z",
      "parent_id": "CBT2518294370"
    },
    {
      "item_id": "MLC2975544398",
      "user_id": 2565546852,
      "site_id": "MLC",
      "date_created": "2025-07-16T18:43:36Z",
      "parent_id": "CBT2518294370"
    },
    {
      "item_id": "MCO2954679252",
      "user_id": 2565546854,
      "site_id": "MCO",
      "date_created": "2025-07-16T18:43:36Z",
      "parent_id": "CBT2518294370"
    }
  ],
  "parent_id": ""
}
```

### Response fields

| Field                                | Type    | Description                                                       |
|--------------------------------------|---------|-------------------------------------------------------------------|
| item\_id                             | String  | The global (CBT) item ID.                                         |
| user\_id                             | Integer | The seller's user ID on the global site.                          |
| site\_id                             | String  | The site ID ("CBT" for global items).                             |
| date\_created                        | String  | Date and time when the item was created (ISO 8601).               |
| marketplace\_items                   | Array   | List of marketplace-specific items created from this global item. |
| marketplace\_items\[\].item\_id      | String  | The item ID in the specific marketplace (e.g., MLM, MLC, MCO).    |
| marketplace\_items\[\].user\_id      | Integer | The seller's user ID in the specific marketplace.                 |
| marketplace\_items\[\].site\_id      | String  | The marketplace site ID.                                          |
| marketplace\_items\[\].date\_created | String  | Date when the marketplace item was created.                       |
| marketplace\_items\[\].parent\_id    | String  | Reference to the parent global (CBT) item ID.                     |
| parent\_id                           | String  | Empty for global items, contains parent ID for marketplace items. |

  

## Errors

The following table lists the specific errors you may encounter when
using the Items & Searches API:

| Code | Type               | Message                                           | Solution                                                                                                                            |
|------|--------------------|---------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------|
| 400  | bad\_request       | handler error, bad request no site\_id provided   | Verify the site\_id is a valid marketplace ID (MLM, MLB, MLA, etc.). CBT is not valid for search endpoints.                         |
| 400  | invalid.scroll.id  | Invalid Scroll Id: Error decode reading Scroll ID | The scroll\_id parameter is malformed or expired. Request a new scroll\_id by calling the endpoint without the parameter.           |
| 403  | forbidden          | forbidden                                         | The endpoint requires special permissions or is restricted. Use /users/{USER\_ID}/items/search instead of /sites/{SITE\_ID}/search. |
| 403  | forbidden          | Searching another user items is restricted.       | You can only search items from your own account. Use the authenticated user's ID.                                                   |
| 404  | not\_found         | Item with id {ITEM\_ID} not found                 | The item does not exist or has been deleted. Verify the item ID format and existence.                                               |
| 404  | resource not found | Si quieres conocer los recursos de la API...      | The resource path is invalid or the item/user does not exist. Check the endpoint URL structure.                                     |

  

## Next

Learn how to work with
[Location](https://global-selling.mercadolibre.com/devsite/location-global-selling)
to configure shipping origins.

</div>
