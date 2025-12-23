<div class="inner-content">

## Price discount

Sellers who want to apply a specific discount to their items can use the
following resources to create, remove, and query discounts.

  

### Requirements

To offer this discount, the following conditions must be met:

-   Seller must have a green reputation.
-   Seller must have at least 1 product sale.
-   Item status must be **active**.
-   Item condition must be **new**.
-   Item listing type cannot be **free**.

  

## Offer discount for an item

Use this resource to apply a price discount to a specific item.

<div class="andes-message andes-message--neutral">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--neutral site-carriers__message-title">

Note:

</div>

<div class="andes-message__text--neutral site-carriers__message-text">

<div>

To offer a discount, you must send **prices** in the request body, not
percentages. Use **deal\_price** instead of **discount\_percent** and
**top\_deal\_price** instead of **top\_discount\_percent**.

</div>

</div>

</div>

</div>

Request:

``` language-javascript
curl -X POST -H 'Authorization: Bearer $ACCESS_TOKEN' \
-d '{
    "deal_price": $DEAL_PRICE,
    "top_deal_price": $TOP_DEAL_PRICE,
    "start_date": "$START_DATE",
    "finish_date": "$FINISH_DATE",
    "promotion_type": "PRICE_DISCOUNT"
}' \
'https://api.mercadolibre.com/marketplace/seller-promotions/items/$ITEM_ID?user_id=$USER_ID' \
--header 'version: v2' \
--header 'X-Client-Id: $CLIENT_ID' \
--header 'X-Caller-Id: $CALLER_ID'
```

Example:

``` language-javascript
curl -X POST -H 'Authorization: Bearer $ACCESS_TOKEN' \
-d '{
    "deal_price": 20,
    "top_deal_price": 15,
    "start_date": "2025-12-09T00:00:00",
    "finish_date": "2025-12-16T23:59:59",
    "promotion_type": "PRICE_DISCOUNT"
}' \
'https://api.mercadolibre.com/marketplace/seller-promotions/items/MLM3782207298?user_id=2487485082' \
--header 'version: v2' \
--header 'X-Client-Id: 1317417907' \
--header 'X-Caller-Id: 1317417907'
```

Response:

``` language-javascript
{
    "price": 20,
    "original_price": 39.29,
    "currency_id": "USD",
    "offer_id": "OFFER-MLM3782207298-11795706698"
}
```

### Parameters

-   **deal\_price:** discounted price for all buyers.
-   **top\_deal\_price:** discounted price for loyalty program members
    (Mercado Puntos level 3 to 6). *(optional)*
-   **start\_date:** discount start date in local format.
-   **finish\_date:** discount end date in local format.
-   **promotion\_type:** must be `PRICE_DISCOUNT`.

### Response fields

-   **price:** the discounted price applied to the item.
-   **original\_price:** the original price of the item before the
    discount.
-   **currency\_id:** currency code (e.g., USD, MXN).
-   **offer\_id:** unique identifier for the created offer.

### Considerations

-   Discounts can be segmented by setting a general price for all buyers
    and a special price for loyalty members (Mercado Puntos level 3 to
    6).
-   For discounts up to 35%, the general discount must be at least 5%
    higher than the loyalty member discount. For discounts above 35%,
    the difference must be at least 10%.
-   The maximum discount allowed is 80%, and the minimum discount must
    be at least 5%.
-   If the item price increases, all discounts will be automatically
    removed.
-   The maximum duration for a PRICE\_DISCOUNT promotion is 14 days.
-   If the item is already participating in a DEAL when the discount
    starts, the PRICE\_DISCOUNT will not be applied until the DEAL ends.
-   The **start\_date** and **finish\_date** parameters only consider
    the date, not the time. By default, discounts start at 00:00:00 on
    the start date and end at 23:59:59 on the finish date.

  

<div class="andes-message andes-message--neutral">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--neutral site-carriers__message-title">

Note:

</div>

<div class="andes-message__text--neutral site-carriers__message-text">

<div>

For testing purposes, the test user must have a green reputation and the
item must have at least 1 sale at the current price.

</div>

</div>

</div>

</div>

  

### Item status

The table below shows the possible item statuses when applying a price
discount:

| Status                 | Description                         |
|------------------------|-------------------------------------|
| **pending**            | Scheduled discount, not yet active. |
| **started**            | Item with active discount.          |
| **finished**           | Discount has ended.                 |
| **sync\_requested**    | Discount activation in progress.    |
| **restore\_requested** | Discount removal in progress.       |

  
  

## Delete a price discount

Use this resource to remove a price discount from an item.

Request:

``` language-javascript
curl -X DELETE -H 'Authorization: Bearer $ACCESS_TOKEN' \
'https://api.mercadolibre.com/marketplace/seller-promotions/items/$ITEM_ID?promotion_type=PRICE_DISCOUNT&user_id=$USER_ID' \
--header 'version: v2' \
--header 'X-Client-Id: $CLIENT_ID' \
--header 'X-Caller-Id: $CALLER_ID'
```

Example:

``` language-javascript
curl -X DELETE -H 'Authorization: Bearer $ACCESS_TOKEN' \
'https://api.mercadolibre.com/marketplace/seller-promotions/items/MLM3782207298?promotion_type=PRICE_DISCOUNT&user_id=2487485082' \
--header 'version: v2' \
--header 'X-Client-Id: 1317417907' \
--header 'X-Caller-Id: 1317417907'
```

Response: **HTTP 200 OK** (empty body)

  

<div class="andes-message andes-message--neutral">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--neutral site-carriers__message-title">

Note:

</div>

<div class="andes-message__text--neutral site-carriers__message-text">

<div>

When removing a PRICE\_DISCOUNT, all discount tiers will be removed. You
cannot remove discounts by buyer level individually.

</div>

</div>

</div>

</div>

  
  

## Errors

The following errors may occur when offering discounts:

### Discount percentage out of range

``` language-javascript
{
    "key": "buyer_discount_not_in_range",
    "message": "buyers_discount_percentage parameter must be in range (5, 80)"
}
```

``` language-javascript
{
    "key": "best_buyer_discount_not_in_range",
    "message": "buyers_discount_percentage parameter must be in range (5, 80)"
}
```

**Cause:** The discount percentage is outside the allowed range (5% to
80%).

  

### Insufficient discount difference between tiers

``` language-javascript
{
    "key": "discount_below_10_percent_difference",
    "message": "The best buyer discount difference cannot be below 10% when buyers discount is above 35%"
}
```

``` language-javascript
{
    "key": "discount_below_5_percent_difference",
    "message": "The discount difference cannot be below 5%"
}
```

**Cause:** The difference between general and loyalty member discounts
does not meet the minimum requirements.

  

### Price credibility error

``` language-javascript
{
    "key": "error_credibility_price",
    "message": "The price is not credible."
}
```

**Cause:** The discount results in a price that the system considers not
credible. A higher original price or smaller discount may be required.

  

**Next:** [Deal of the
Day](https://global-selling.mercadolibre.com/devsite/deal-of-day-gs)

</div>
