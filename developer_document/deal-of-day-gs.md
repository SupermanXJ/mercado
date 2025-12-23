<div class="inner-content">

## Deals of the day

Sellers are regularly invited to participate in different website
promotions. If you received an invitation to participate in a daily deal
and want to join, use the following resources.

  
![](https://http2.mlstatic.com/storage/developers-site-cms-admin/DevSite/283675808089-deal-of-day-mexico.png)  
  

## Check items in a deal of the day

To retrieve the items included in a Deal of the Day, perform the
following request:

Request:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' \
'https://api.mercadolibre.com/marketplace/seller-promotions/promotions/$DOD_ID/items?promotion_type=DOD&user_id=$USER_ID' \
--header 'version: v2' \
--header 'X-Caller-Id: $CALLER_ID' \
--header 'X-Client-Id: $CLIENT_ID'
```

Example:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' \
'https://api.mercadolibre.com/marketplace/seller-promotions/promotions/DOD-MLM1000/items?promotion_type=DOD&user_id=2487485082' \
--header 'version: v2' \
--header 'X-Caller-Id: 1317417907' \
--header 'X-Client-Id: 1317417907'
```

Response:

``` language-javascript
{
    "results": [
        {
            "id": "MLM3782167908",
            "status": "candidate",
            "price": 825.55,
            "original_price": 835.55,
            "currency_id": "USD",
            "start_date": "2024-02-16T21:00:00",
            "finish_date": "2024-02-17T20:59:59",
            "stock": {
                "min": 1,
                "max": 2
            },
            "max_discounted_price": 700.72,
            "min_discounted_price": 13.7,
            "net_proceeds": {
                "amount": 657.48,
                "currency": "USD"
            }
        }
    ],
    "paging": {
        "offset": 0,
        "limit": 50,
        "total": 1,
        "searchAfter": ""
    }
}
```

### Response fields

-   **id:** item identifier.
-   **status:** promotion item status (see table below).
-   **price:** promotion item price. For `candidate` items, it refers to
    the suggested price.
-   **original\_price:** current item price (before discount).
-   **currency\_id:** currency code (e.g., USD, MXN).
-   **start\_date:** deal start date for this item.
-   **finish\_date:** deal end date for this item.
-   **stock:** stock requirements for the promotion.
    -   **min:** minimum stock required to participate.
    -   **max:** maximum stock allowed for the promotion.
-   **max\_discounted\_price:** maximum allowed discounted price for
    this item.
-   **min\_discounted\_price:** minimum allowed discounted price for
    this item.
-   **net\_proceeds:** net proceeds information.
    -   **amount:** net amount the seller will receive.
    -   **currency:** currency of the net proceeds.

  

### Item status

The table below shows the possible item status in this type of
promotion:

| Status        | Description                                     |
|---------------|-------------------------------------------------|
| **candidate** | Candidate item to participate in the promotion. |
| **pending**   | Scheduled promotion item.                       |
| **started**   | Active promotion item.                          |
| **finished**  | Item removed from deal.                         |

  
  

## Specify items for a deal of the day

Once you are invited to participate in a **deal of the day**, you can
specify the candidate items to be included.

Request:

``` language-javascript
curl -X POST -H 'Authorization: Bearer $ACCESS_TOKEN' \
-d '{
    "deal_id": "$DEAL_ID",
    "deal_price": $DEAL_PRICE,
    "original_price": $ORIGINAL_PRICE,
    "promotion_type": "DOD"
}' \
'https://api.mercadolibre.com/marketplace/seller-promotions/items/$ITEM_ID?user_id=$USER_ID' \
--header 'version: v2'
```

Example:

``` language-javascript
curl -X POST -H 'Authorization: Bearer $ACCESS_TOKEN' \
-d '{
    "deal_id": "DOD-MLM1000",
    "original_price": 825.55,
    "deal_price": 500,
    "promotion_type": "DOD"
}' \
'https://api.mercadolibre.com/marketplace/seller-promotions/items/MLM3782167908?user_id=2487485082' \
--header 'version: v2'
```

Response:

``` language-javascript
{
    "price": 500,
    "original_price": 835.55,
    "currency_id": "USD",
    "offer_id": "OFFER-MLM3782167908-11796614713"
}
```

### Parameters

-   **deal\_id:** deal of the day identifier (e.g., DOD-MLM1000).
-   **deal\_price:** promotional price for the item in the deal.
-   **original\_price:** item price before being included in the
    promotion.
-   **promotion\_type:** type of promotion, must be `DOD` (Deal of the
    Day).

### Response fields

-   **price:** the promotional price applied to the item.
-   **original\_price:** the original price of the item.
-   **currency\_id:** currency code (e.g., USD, MXN).
-   **offer\_id:** unique identifier for the created offer.

  
  

## Delete items from a deal

Use this resource to remove an item offer from a deal of the day.

Request:

``` language-javascript
curl -X DELETE -H 'Authorization: Bearer $ACCESS_TOKEN' \
'https://api.mercadolibre.com/marketplace/seller-promotions/items/$ITEM_ID?user_id=$USER_ID&promotion_type=DOD&promotion_id=$DEAL_ID' \
--header 'version: v2'
```

Example:

``` language-javascript
curl -X DELETE -H 'Authorization: Bearer $ACCESS_TOKEN' \
'https://api.mercadolibre.com/marketplace/seller-promotions/items/MLM3782167908?user_id=2487485082&promotion_type=DOD&promotion_id=DOD-MLM1000' \
--header 'version: v2'
```

Response: **Status 200 OK** (empty body)

  

**Next:** [Lightning
Deal](https://global-selling.mercadolibre.com/devsite/lightning-deal)

</div>
