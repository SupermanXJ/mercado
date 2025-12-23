<div class="inner-content">

## Pricing Reference

<div class="details__message">

Price references on Mercado Livre are recommendations to help sellers
set competitive prices. Based on an analysis of current prices of
similar products, both on the Mercado Livre platform and elsewhere, on
sales history, and on demand, these references aim to guide the seller
in establishing a price that is attractive to buyers. This increases the
chances of sale and improves positioning in search results.

</div>

## Get items with price references by seller

 

Returns a list of **items\_id** that have price references for a
specific **seller\_id**.

  

### Preconditions for getting price references by seller

-   Must query an existing user

Request:

``` language-javascript
curl -H 'Authorization: Bearer $ACCESS_TOKEN' -X GET https://api.mercadolibre.com/marketplace/benchmarks/user/$USER_ID/items
```

Example:

``` language-javascript
curl -H 'Authorization: Bearer $ACCESS_TOKEN' -X GET https://api.mercadolibre.com/marketplace/benchmarks/user/1305627900/items
```

Response:

``` language-javascript
{
    "total": 3,
    "items": [
        "MLB3770847075",
        "MLB3746732952",
        "MLB3690598506"
    ]
}
```

**Response fields:**

  

The response of a GET to the
**/marketplace/benchmarks/user/$USER\_ID/items** resource will provide
the following parameters

  

**total**: total number of items.  

**items**: list of items represented by a string value.

  

## Get price reference details by item\_id

 

To query the referred price to assign to a specific item, you need to
perform a GET on the resource
**/marketplace/benchmarks/items/$ITEM\_ID/details**

  

### Preconditions for obtaining price references

-   Must query an existing item

Request:

``` language-javascript
curl -H 'Authorization: Bearer $ACCESS_TOKEN' -X GET https://api.mercadolibre.com/marketplace/benchmarks/items/$ITEM_ID/details
```

Example:

``` language-javascript
curl -H 'Authorization: Bearer $ACCESS_TOKEN' -X GET https://api.mercadolibre.com/marketplace/benchmarks/items/MLB5324094348/details?
```

Response:

``` language-javascript
{
    "item_id": "MLB5324094348",
    "status": "no_benchmark_ok",
    "currency_id": "BRL",
    "ratio": 5.51,
    "strategy_type": "similar_price",
    "current_price": {
        "amount": 2755,
        "usd_amount": 500
    },
    "suggested_price": {
        "amount": 2755,
        "usd_amount": 500
    },
    "estimated_taxes": {
        "amount": 2459.57,
        "usd_amount": 446.75
    },
    "lowest_price": {
        "amount": 0,
        "usd_amount": 0
    },
    "internal_price": {
        "amount": 2755,
        "usd_amount": 500
    },
    "external_price": {
        "amount": 0,
        "usd_amount": 0
    },
    "percent_difference": 0,
    "costs": {
        "selling_fees": 82.5,
        "shipping_fees": 7.53
    },
    "applicable_suggestion": false,
    "metadata": {
        "type": "",
        "graph": [
            {
                "item_id": "",
                "price": {
                    "amount": 8540.5,
                    "usd_amount": 1550
                },
                "info": {
                    "thumbnail": "",
                    "title": "Teste E Teste Ads 2",
                    "url": "",
                    "sold_quantity": 0
                },
                "quantity": 0,
                "current": false,
                "suggested": false
            }
        ],
        "compared_values": 1
    },
    "external_metadata": {
        "rival_info": null,
        "compared_values": 0
    },
    "last_updated": "09-12-2025 14:33:36"
}
```

### Response fields

**item\_id**: ID of the item.  
**status**: Status of the price reference in relation to the competition
benchmark. The possible price references are:  

-   **no\_benchmark\_lowest**: item price is lower than the reference
    price.
-   **no\_benchmark\_ok**: item price equals the reference price.
-   **with\_benchmark\_high**: item price is greater than the reference
    price.
-   **with\_benchmark\_highest**: item price is higher than both the
    reference price and the maximum price of its competitors.

**currency\_id**: currency used, in this case, "MXN" (Mexican Peso).  
**ratio**: Relationship between the current price and the reference
price.  
**current\_price**: current price of the item, including the "amount"
(20170 MXN) and the equivalent "usd\_amount" (1000 USD).  

-   **amount**: price expressed in local currency.
-   **usd\_amount**: price expressed in dollars.

**suggested\_price**: reference price for the item, including the
"amount" (15127.5 MXN) and the equivalent "usd\_amount" (750 USD).  
**lowest\_price**:  
**estimated\_taxes**: estimated taxes for the item, including the
"amount" and the equivalent "usd\_amount".  
**internal\_price**: reference price compared internally at Mercado
Libre.  
**applicable\_suggestion**: whether the price reference is applicable to
this item or not.  
**percent\_difference**: percentage difference between the current price
and the reference price (27%).  
**costs**: costs associated with the item, including "selling\_fees"
(150 MXN) and "shipping\_fees" (31.25 MXN).  

**last\_updated**: last price reference date.  
**metadata**: metadata about the item.  

**type**: type of metadata. Available values: similar\_price and
adjusted\_price.  

**graph**: additional information about a related item.  

-   **item\_id**: no information provided.
-   **price**: provides the price details for the related item,
    including the **amount** (3047.39 MXN) and the equivalent
    **usd\_amount** (177.38 USD).
-   **info**: only title information is shared.
-   **quantity**: no information provided.
-   **current**: specifies whether the related item is the current item
    (false in this case).
-   **suggested**: specifies whether the related item is referenced
    (false in this case).
-   **compared\_values**: indicates the number of compared values (1 in
    this case).

<div class="andes-message andes-message--neutral">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--neutral site-carriers__message-title">

Note:

</div>

<div class="andes-message__text--neutral site-carriers__message-text">

<div>

If your item is from the catalog, the reference value "internal\_price"
will be the same as the reference price to win in price\_to\_win.

</div>

</div>

</div>

</div>

## Possible errors when querying an item's price references

 

When querying an item's price reference, you may encounter the following
errors. It is crucial that you understand the cause of each one and know
how to correct them, to efficiently handle the situation. Here you have
the necessary information to identify and resolve these problems.

  

| Status\_code | Error code | Error message                                                                       | Description                                                                      |
|--------------|------------|-------------------------------------------------------------------------------------|----------------------------------------------------------------------------------|
| 403          | forbidden  | Can not identify the user                                                           | When the user in the parameter does not correspond to a site user of the caller. |
| 404          | not found  | User has no items with price suggestion                                             | When user has no suggestions for item´s price.                                   |
| 404          | forbidden  | Item MLX1234 is not a CBT item                                                      | When the item being queried is not from CBT.                                     |
| 404          | forbidden  | Item price reference not found, item id: \[MLX1234\], error: \[kvs: key not found\] | When the CBT item does not have price references.                                |

**Next**: [Manage
automations](https://global-selling.mercadolibre.com/devsite/manage-automations).

  

</div>
