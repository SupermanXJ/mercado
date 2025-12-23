<div class="inner-content">

## Co-funded campaigns

<div class="details__message">

Sellers are regularly invited to participate in different website
campaigns.  
The main characteristic of this type of campaign is that Mercado Libre
pays a percentage of the offered discount.  
If you received an invitation and want to join, use the resources below.

</div>

  
  

## Check campaign details

Retrieve the details of a specific co-funded campaign, including dates,
status, and benefit distribution between seller and Mercado Libre.

Request:

``` language-javascript
curl -X GET 'https://api.mercadolibre.com/marketplace/seller-promotions/promotions/$PROMOTION_ID?promotion_type=MARKETPLACE_CAMPAIGN&user_id=$USER_ID' \
  -H 'Authorization: Bearer $ACCESS_TOKEN' \
  -H 'version: v2' \
  -H 'X-Client-Id: $CLIENT_ID' \
  -H 'X-Caller-Id: $CALLER_ID'
```

Example:

``` language-javascript
curl -X GET 'https://api.mercadolibre.com/marketplace/seller-promotions/promotions/P-MLM1806015?promotion_type=MARKETPLACE_CAMPAIGN&user_id=1317418851' \
  -H 'Authorization: Bearer $ACCESS_TOKEN' \
  -H 'version: v2' \
  -H 'X-Client-Id: 1317417907' \
  -H 'X-Caller-Id: 1317417907'
```

Response:

``` language-javascript
{
    "id": "P-MLM1806015",
    "type": "MARKETPLACE_CAMPAIGN",
    "status": "started",
    "start_date": "2023-04-20T02:00:00Z",
    "finish_date": "2023-08-01T02:00:00Z",
    "deadline_date": "2023-08-01T01:00:00Z",
    "name": "Test Campaign v2",
    "benefits": {
        "type": "REBATE",
        "meli_percent": 5,
        "seller_percent": 25
    }
}
```

### Response fields

-   **id**: unique campaign identifier.
-   **type**: campaign type. Value: MARKETPLACE\_CAMPAIGN.
-   **status**: current campaign status. See status table below.
-   **start\_date**: campaign start date in ISO 8601 format.
-   **finish\_date**: campaign end date in ISO 8601 format.
-   **deadline\_date**: last date to add items to the campaign.
-   **name**: campaign display name.
-   **benefits**: object containing discount distribution details.
    -   **type**: benefit type. Value: REBATE.
    -   **meli\_percent**: percentage of discount contributed by Mercado
        Libre.
    -   **seller\_percent**: percentage of discount contributed by the
        seller.

  

### Status

Find below the different co-funded campaign statuses:

| Status                | Description                            |
|-----------------------|----------------------------------------|
| **pending\_approval** | Campaign pending approval.             |
| **pending**           | Campaign approved but not yet started. |
| **started**           | Campaign currently active.             |
| **finished**          | Campaign has ended.                    |

## Check campaign Items

Retrieve the list of candidate items and/or items already included in a
co-funded campaign.

Request:

``` language-javascript
curl -X GET 'https://api.mercadolibre.com/marketplace/seller-promotions/promotions/$PROMOTION_ID/items?user_id=$USER_ID' \
  -H 'Authorization: Bearer $ACCESS_TOKEN' \
  -H 'version: v2' \
  -H 'X-Client-Id: $CLIENT_ID' \
  -H 'X-Caller-Id: $CALLER_ID'
```

Example:

``` language-javascript
curl -X GET 'https://api.mercadolibre.com/marketplace/seller-promotions/promotions/P-MLM1806015/items?user_id=1317418851' \
  -H 'Authorization: Bearer $ACCESS_TOKEN' \
  -H 'version: v2' \
  -H 'X-Client-Id: 1317417907' \
  -H 'X-Caller-Id: 1317417907'
```

Response:

``` language-javascript
{
    "results": [
        {
            "id": "MLM3293401659",
            "status": "started",
            "price": 700,
            "original_price": 1000,
            "offer_id": "OFFER-MLM3293401659-177366",
            "meli_percentage": 5,
            "seller_percentage": 25,
            "start_date": "2023-04-23T23:06:53Z",
            "end_date": "2023-08-01T02:00:00Z",
            "net_proceeds": {
                "amount": 20.68,
                "currency": "USD"
            }
        }
    ],
    "paging": {
        "offset": 0,
        "limit": 50,
        "total": 1
    }
}
```

### Response fields

-   **results**: array of items in the campaign.
    -   **id**: item ID.
    -   **status**: item participation status. See item status table
        below.
    -   **price**: current discounted price.
    -   **original\_price**: original price before discount.
    -   **offer\_id**: unique offer identifier assigned when item is
        added to campaign.
    -   **meli\_percentage**: percentage contributed by Mercado Libre
        for this item.
    -   **seller\_percentage**: percentage contributed by the seller for
        this item.
    -   **start\_date**: date when the item started participating in the
        campaign.
    -   **end\_date**: date when the item's participation ends.
    -   **net\_proceeds**: object containing the seller's net earnings
        information.
        -   **amount**: net amount the seller will receive.
        -   **currency**: currency code (e.g., USD).
-   **paging**: pagination information.
    -   **offset**: current offset position.
    -   **limit**: maximum items per page.
    -   **total**: total number of items.

  

<div class="andes-message andes-message--neutral">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--neutral site-carriers__message-title">

Note:

</div>

<div class="andes-message__text--neutral site-carriers__message-text">

<div>

When a new campaign is created, all applicable items are selected with
status **candidate** and no assigned offer ID. When the seller adds an
item to the campaign, the status changes and a unique **offer\_id** is
assigned.

</div>

</div>

</div>

</div>

  

### Item status

| Status        | Description                                   |
|---------------|-----------------------------------------------|
| **candidate** | Item eligible to participate in the campaign. |
| **pending**   | Item approved and scheduled for the campaign. |
| **started**   | Item actively participating in the campaign.  |
| **finished**  | Item removed from the campaign.               |

## Submit an item to a campaign

<div class="andes-message andes-message--neutral">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--neutral site-carriers__message-title">

Note:

</div>

<div class="andes-message__text--neutral site-carriers__message-text">

<div>

Use **promotion\_id** (not deal\_id) to add and remove items from this
campaign type.

</div>

</div>

</div>

</div>

Once you are invited to participate in a co-funded campaign, you can
specify the products to be included.

Request:

``` language-javascript
curl -X POST 'https://api.mercadolibre.com/marketplace/seller-promotions/items/$ITEM_ID?user_id=$USER_ID' \
  -H 'Authorization: Bearer $ACCESS_TOKEN' \
  -H 'version: v2' \
  -H 'X-Client-Id: $CLIENT_ID' \
  -H 'X-Caller-Id: $CALLER_ID' \
  -H 'Content-Type: application/json' \
  -d '{
    "promotion_id": "$PROMOTION_ID",
    "promotion_type": "MARKETPLACE_CAMPAIGN"
  }'
```

Example:

``` language-javascript
curl -X POST 'https://api.mercadolibre.com/marketplace/seller-promotions/items/MLM3293401659?user_id=1317418851' \
  -H 'Authorization: Bearer $ACCESS_TOKEN' \
  -H 'version: v2' \
  -H 'X-Client-Id: 1317417907' \
  -H 'X-Caller-Id: 1317417907' \
  -H 'Content-Type: application/json' \
  -d '{
    "promotion_id": "P-MLM1806015",
    "promotion_type": "MARKETPLACE_CAMPAIGN"
  }'
```

Response:

``` language-javascript
{
    "offer_id": "OFFER-MLM3293401659-177366",
    "price": 700,
    "original_price": 1000
}
```

### Response fields

-   **offer\_id**: unique offer identifier for the item in the campaign.
-   **price**: discounted price applied to the item.
-   **original\_price**: original item price before discount.

  

### Request body parameters

-   **promotion\_id**: campaign identifier.
-   **promotion\_type**: must be MARKETPLACE\_CAMPAIGN.

## Modify items

Since prices cannot be changed directly, follow the steps below to
change the price of an item included in a co-funded campaign.

Steps:

-   Delete the item from the campaign.
-   Change item price just like regular price synchronization.
-   Add the item back to the campaign.

  

<div class="andes-message andes-message--neutral">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--neutral site-carriers__message-title">

Note:

</div>

<div class="andes-message__text--neutral site-carriers__message-text">

<div>

Items in co-funded campaigns have price restrictions. If the price of an
included item increases, the item will be automatically removed from the
campaign and cannot be re-added.

</div>

</div>

</div>

</div>

## Delete items

Remove an item from a co-funded campaign.

Request:

``` language-javascript
curl -X DELETE 'https://api.mercadolibre.com/marketplace/seller-promotions/items/$ITEM_ID?promotion_type=MARKETPLACE_CAMPAIGN&promotion_id=$PROMOTION_ID&offer_id=$OFFER_ID&user_id=$USER_ID' \
  -H 'Authorization: Bearer $ACCESS_TOKEN' \
  -H 'version: v2' \
  -H 'X-Client-Id: $CLIENT_ID' \
  -H 'X-Caller-Id: $CALLER_ID'
```

Example:

``` language-javascript
curl -X DELETE 'https://api.mercadolibre.com/marketplace/seller-promotions/items/MLM3293401659?promotion_type=MARKETPLACE_CAMPAIGN&promotion_id=P-MLM1806015&offer_id=OFFER-MLM3293401659-177366&user_id=1317418851' \
  -H 'Authorization: Bearer $ACCESS_TOKEN' \
  -H 'version: v2' \
  -H 'X-Client-Id: 1317417907' \
  -H 'X-Caller-Id: 1317417907'
```

Response: **HTTP 200 OK**

  

**Next**: [Pre-negotiated Discount per
Item](https://global-selling.mercadolibre.com/devsite/pre-negotiated-discount-per-item-gs)

</div>
