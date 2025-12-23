<div class="inner-content">

## Seller campaigns

Sellers can create their own campaigns through their Mercado Libre
account and manage them through the integration. If the seller has
created a campaign and wants to manage the candidate items, they can do
so with the following resources.

  

## Create a campaign

To create a seller campaign, follow these steps:

<div class="andes-message andes-message--highlight">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--highlight site-carriers__message-title">

Important:

</div>

<div class="andes-message__text--highlight site-carriers__message-text">

<div>

The maximum period for this type of campaign is **14 days**.

</div>

</div>

</div>

</div>

### Request

``` language-javascript
curl -X POST 'https://api.mercadolibre.com/marketplace/seller-promotions/seller-campaign/$USER_ID' \
--header 'Authorization: Bearer $ACCESS_TOKEN' \
--header 'Content-Type: application/json' \
--header 'version: v2'

{
   "promotion_type": "SELLER_CAMPAIGN",
   "name": "test campaign seller",
   "sub_type": "FLEXIBLE_PERCENTAGE",
   "start_date": "2025-07-17T00:00:00",
   "finish_date": "2025-07-30T00:00:00"
}
```

Example:

``` language-javascript
curl -X POST 'https://api.mercadolibre.com/marketplace/seller-promotions/seller-campaign/2487485082' \
--header 'Authorization: Bearer $ACCESS_TOKEN' \
--header 'Content-Type: application/json' \
--header 'version: v2'

{
   "promotion_type": "SELLER_CAMPAIGN",
   "name": "My Flexible Percentage Campaign",
   "sub_type": "FLEXIBLE_PERCENTAGE",
   "start_date": "2025-12-05T00:00:00",
   "finish_date": "2025-12-18T00:00:00"
}
```

Response:

``` language-javascript
{
    "id": "C-MLM703970",
    "type": "SELLER_CAMPAIGN",
    "name": "My Flexible Percentage Campaign",
    "sub_type": "FLEXIBLE_PERCENTAGE",
    "status": "started",
    "start_date": "2025-12-05T00:00:00",
    "finish_date": "2025-12-18T23:59:59",
    "allow_combination": false
}
```

### Response fields

-   **id:** unique identifier of the campaign (format:
    C-{SITE\_ID}{NUMBER}).
-   **type:** campaign type. Always returns **SELLER\_CAMPAIGN**.
-   **name:** campaign name.
-   **sub\_type:** campaign subtype: **FLEXIBLE\_PERCENTAGE**.
-   **status:** campaign status. Possible values: `pending`, `started`,
    `finished`.
-   **start\_date:** campaign start date.
-   **finish\_date:** campaign end date.
-   **allow\_combination:** indicates whether the campaign can be
    combined with other promotions. Default: `false`.

  

### Request fields

-   **promotion\_type:** type of campaign to create, at the moment only
    **SELLER\_CAMPAIGN** is allowed.
-   **name:** campaign name.
-   **sub\_type:** campaign subtype. Use **FLEXIBLE\_PERCENTAGE**.
-   **start\_date:** campaign start date in local format
    (YYYY-MM-DDTHH:mm:ss). The beginning of the day will always be taken
    as the start time.
-   **finish\_date:** campaign end date **in local format**
    (YYYY-MM-DDTHH:mm:ss). The end of the day will always be taken as
    the end time. Maximum 14 days from start\_date.

  

## Update a campaign

All fields can be modified, **but only the fields that you wish to
modify should be submitted**. The only mandatory field is
**promotion\_type**, which must always be present.

  

Request:

``` language-javascript
curl -X PUT 'https://api.mercadolibre.com/marketplace/seller-promotions/seller-campaign/$CAMPAIGN_ID?user_id=$USER_ID' \
--header 'Authorization: Bearer $ACCESS_TOKEN' \
--header 'Content-Type: application/json' \
--header 'version: v2'

{
   "promotion_type": "SELLER_CAMPAIGN",
   "name": "test campaign seller updated"
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

In this example we only send the "name" field because it is the only
change we want to apply. You cannot change the **start\_date** of a
promotion that is already in **started** status.

</div>

</div>

</div>

</div>

Example:

``` language-javascript
curl -X PUT 'https://api.mercadolibre.com/marketplace/seller-promotions/seller-campaign/C-MLM703970?user_id=2487485082' \
--header 'Authorization: Bearer $ACCESS_TOKEN' \
--header 'Content-Type: application/json' \
--header 'version: v2'

{
   "promotion_type": "SELLER_CAMPAIGN",
   "name": "Updated Campaign Name"
}
```

Response:

``` language-javascript
{
    "id": "C-MLM703970",
    "type": "SELLER_CAMPAIGN",
    "name": "Updated Campaign Name",
    "sub_type": "FLEXIBLE_PERCENTAGE",
    "status": "started",
    "start_date": "2025-12-09T00:00:00",
    "finish_date": "2025-12-22T23:59:59",
    "allow_combination": false
}
```

## Delete a campaign

To remove a seller campaign, perform the following request:

``` language-javascript
curl -X DELETE 'https://api.mercadolibre.com/marketplace/seller-promotions/seller-campaign/$CAMPAIGN_ID?promotion_type=SELLER_CAMPAIGN&user_id=$USER_ID' \
--header 'Authorization: Bearer $ACCESS_TOKEN' \
--header 'version: v2'
```

Example:

``` language-javascript
curl -X DELETE 'https://api.mercadolibre.com/marketplace/seller-promotions/seller-campaign/C-MLM703970?promotion_type=SELLER_CAMPAIGN&user_id=2487485082' \
--header 'Authorization: Bearer $ACCESS_TOKEN' \
--header 'version: v2'
```

Response: **Status 200 OK**

<div class="andes-message andes-message--neutral">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--neutral site-carriers__message-title">

Note:

</div>

<div class="andes-message__text--neutral site-carriers__message-text">

<div>

The response body is empty on successful deletion.

</div>

</div>

</div>

</div>

  

## View campaign details

View the details of a seller campaign:

Request:

``` language-javascript
curl -X GET 'https://api.mercadolibre.com/marketplace/seller-promotions/promotions/$PROMOTION_ID?promotion_type=SELLER_CAMPAIGN&user_id=$USER_ID' \
--header 'Authorization: Bearer $ACCESS_TOKEN' \
--header 'version: v2'
```

Example:

``` language-javascript
curl -X GET 'https://api.mercadolibre.com/marketplace/seller-promotions/promotions/C-MLM703970?promotion_type=SELLER_CAMPAIGN&user_id=2487485082' \
--header 'Authorization: Bearer $ACCESS_TOKEN' \
--header 'version: v2'
```

Response:

``` language-javascript
{
    "id": "C-MLM703970",
    "type": "SELLER_CAMPAIGN",
    "status": "started",
    "start_date": "2025-12-09T06:00:00Z",
    "finish_date": "2025-12-22T05:59:59Z",
    "name": "Updated Campaign Name",
    "sub_type": "FLEXIBLE_PERCENTAGE",
    "allow_combination": false
}
```

### Response fields

-   **id:** campaign identifier.
-   **type:** campaign type (SELLER\_CAMPAIGN).
-   **sub\_type:** campaign subtype (FLEXIBLE\_PERCENTAGE).
-   **status:** campaign status.
-   **start\_date:** date when the campaign starts (UTC format).
-   **finish\_date:** date when the campaign ends (UTC format).
-   **name:** name of the campaign.
-   **allow\_combination:** indicates whether the campaign can be
    combined with other promotions.

  
  

## Seller campaign status

These are the different states that a seller's campaign can go through:

| Status       | Description                              |
|--------------|------------------------------------------|
| **pending**  | Promotion approved, but not yet started. |
| **started**  | Active promotion.                        |
| **finished** | Finished promotion.                      |

  
  

## View items in a campaign

To see the items that are part of a seller campaign, make the following
query:

Request:

``` language-javascript
curl -X GET 'https://api.mercadolibre.com/marketplace/seller-promotions/promotions/$PROMOTION_ID/items?promotion_type=SELLER_CAMPAIGN&user_id=$USER_ID' \
--header 'Authorization: Bearer $ACCESS_TOKEN' \
--header 'version: v2'
```

Example:

``` language-javascript
curl -X GET 'https://api.mercadolibre.com/marketplace/seller-promotions/promotions/C-MLM703970/items?promotion_type=SELLER_CAMPAIGN&user_id=2487485082' \
--header 'Authorization: Bearer $ACCESS_TOKEN' \
--header 'version: v2'
```

Response example (started item):

``` language-javascript
{
    "results": [
        {
            "id": "MLM4007773188",
            "status": "started",
            "price": 19,
            "original_price": 20,
            "currency_id": "USD",
            "start_date": "2025-12-09T00:00:00",
            "end_date": "2025-12-22T23:59:59",
            "net_proceeds": {
                "amount": 10.61,
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

Response example (candidate item with price suggestions):

``` language-javascript
{
    "results": [
        {
            "id": "MLM3782207406",
            "status": "candidate",
            "price": 0,
            "original_price": 270.34,
            "currency_id": "USD",
            "start_date": "2025-12-09T00:00:00",
            "end_date": "2025-12-22T23:59:59",
            "max_discounted_price": 256.82,
            "min_discounted_price": 162.21,
            "suggested_discounted_price": 240.50,
            "net_proceeds": {
                "suggested_discounted_price": {
                    "amount": 180.25,
                    "currency": "USD"
                },
                "max_discounted_price": {
                    "amount": 78.47,
                    "currency": "USD"
                },
                "min_discounted_price": {
                    "amount": 50.00,
                    "currency": "USD"
                }
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

-   **id:** item ID.
-   **status:** item status in the campaign. See **Items status** table
    below.
-   **price:** current promotional price. Returns `0` for candidate
    items.
-   **original\_price:** original item price before discount.
-   **currency\_id:** currency code (e.g., USD, MXN).
-   **start\_date:** promotion start date for this item.
-   **end\_date:** promotion end date for this item.
-   **max\_discounted\_price:** maximum allowed discounted price.
-   **min\_discounted\_price:** minimum allowed discounted price.
-   **suggested\_discounted\_price:** system-suggested promotional
    price.
-   **net\_proceeds:** estimated net amount that the seller will receive
    for an item within a specific promotion.
    -   **amount:** net amount the seller will receive (for started
        items).
    -   **currency:** currency of the net proceeds.
    -   **suggested\_discounted\_price:** object with net proceeds at
        the suggested price (for candidate items).
    -   **max\_discounted\_price:** object with net proceeds at the
        maximum discounted price.
    -   **min\_discounted\_price:** object with net proceeds at the
        minimum discounted price.

  

## Items status

In the following table you will find the possible status that items in a
seller campaign can have:

| Status        | Description                                       |
|---------------|---------------------------------------------------|
| **candidate** | Item is eligible to participate in the promotion. |
| **pending**   | Approved item with scheduled promotion.           |
| **started**   | Item is currently active in the campaign.         |
| **finished**  | Item has been removed from the campaign.          |

  
  

## Indicate items for a campaign

Once you have created a campaign and identified eligible items, you can
indicate which products you want to include in the campaign.

Request:

``` language-javascript
curl -X POST 'https://api.mercadolibre.com/marketplace/seller-promotions/items/$ITEM_ID?user_id=$USER_ID' \
--header 'Authorization: Bearer $ACCESS_TOKEN' \
--header 'Content-Type: application/json' \
--header 'version: v2'

{
   "promotion_id": "$CAMPAIGN_ID",
   "promotion_type": "SELLER_CAMPAIGN",
   "deal_price": $DEAL_PRICE,
   "top_deal_price": $TOP_DEAL_PRICE
}
```

Example:

``` language-javascript
curl -X POST 'https://api.mercadolibre.com/marketplace/seller-promotions/items/MLM4007773188?user_id=2487485082' \
--header 'Authorization: Bearer $ACCESS_TOKEN' \
--header 'Content-Type: application/json' \
--header 'version: v2'

{
    "promotion_id": "C-MLM703970",
    "promotion_type": "SELLER_CAMPAIGN",
    "deal_price": 19,
    "top_deal_price": 6
}
```

Response:

``` language-javascript
{
    "price": 19,
    "original_price": 20,
    "currency_id": "USD"
}
```

### Parameters

-   **promotion\_id:** campaign ID (e.g., C-MLM703970). Required.
-   **promotion\_type:** promotion type. Must be **SELLER\_CAMPAIGN**.
    Required.
-   **deal\_price:** item price during the promotion. Must be between
    **min\_discounted\_price** and **max\_discounted\_price**. Required.
-   **top\_deal\_price:** special price for Mercado Puntos members
    (levels 3-6). Optional.

### Response fields

-   **price:** the promotional price applied to the item.
-   **original\_price:** the original item price.
-   **currency\_id:** currency code.

  

## Remove items from a campaign

By performing this action you can indicate which products you want to
exclude from a campaign.

Request:

``` language-javascript
curl -X DELETE 'https://api.mercadolibre.com/marketplace/seller-promotions/items/$ITEM_ID?promotion_type=SELLER_CAMPAIGN&promotion_id=$CAMPAIGN_ID&user_id=$USER_ID&offer_id=$USER_ID' \
--header 'Authorization: Bearer $ACCESS_TOKEN' \
--header 'version: v2'
```

Example:

``` language-javascript
curl -X DELETE 'https://api.mercadolibre.com/marketplace/seller-promotions/items/MLM4007773188?promotion_type=SELLER_CAMPAIGN&promotion_id=C-MLM703970&user_id=2487485082&offer_id=2487485082' \
--header 'Authorization: Bearer $ACCESS_TOKEN' \
--header 'version: v2'
```

Response: **Status 200 OK**

<div class="andes-message andes-message--neutral">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--neutral site-carriers__message-title">

Note:

</div>

<div class="andes-message__text--neutral site-carriers__message-text">

<div>

The response body is empty on successful removal.

</div>

</div>

</div>

</div>

  
  

## Validation errors: 400 bad request

| Error message                                                                                               | Description                                                                                                                                                                                                                                                   |
|-------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| The name already exists                                                                                     | A seller campaign with the same name already exists.                                                                                                                                                                                                          |
| Invalid sub\_type                                                                                           | When the sub\_type of a SELLER\_CAMPAIGN is not FLEXIBLE\_PERCENTAGE .                                                                                                                                                                                        |
| The percentage is greater than allowed. the maximum percentage allowed is 70.000000                         | The maximum percentage allowed is 70%. If it is sent, for example 71, it will return this error.                                                                                                                                                              |
| The percentage is less than allowed. the minimum percentage allowed is 10.000000                            | The percentage is below the allowed.                                                                                                                                                                                                                          |
| Invalid promotion type                                                                                      | When the promotion\_type is invalid.                                                                                                                                                                                                                          |
| Start and finish dates must be in local format                                                              | When the dates sent are not in local format (like the example) or are not sent at all.                                                                                                                                                                        |
| Start\_date cannot be earlier than today                                                                    | Start\_date cannot be earlier than today.                                                                                                                                                                                                                     |
| Finish\_date cannot be earlier than startdate                                                               | Finish\_date cannot be earlier than start\_date.                                                                                                                                                                                                              |
| Maximum period cannot exceed the allowed                                                                    | When the distance between the start and finish date is greater than the allowed one.                                                                                                                                                                          |
| The percentage difference between sellerpercentage and loyaltypercentage does not meet the minimum required | The difference between the seller\_percentage and loyalty\_percentage must be greater than or equal to 5%.                                                                                                                                                    |
| Maximum period cannot exceed the allowed                                                                    | When you want to update some date (or both), and the new period between them exceeds the allowed one.                                                                                                                                                         |
| Percentages of a FLEXIBLE PERCENTAGE promotion must be updated per offer                                    | An attempt is made to modify a percentage or loyalty percentage to a campaign that is of the flexible\_percentage type. Percentages can only be set generally in fixed\_percentages. For flexible promotions, the prices of particular offers must be edited. |
| The start\_date field cannot be modified for the current promotion status                                   | You cannot change the start date of a promotion in the started state.                                                                                                                                                                                         |

Next: [Automated co-participation and competitive pricing
campaign](https://global-selling.mercadolibre.com/devsite/automated-co-participation-and-competitive-pricing-campaign).

</div>
