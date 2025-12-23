<div class="inner-content">

## Volume discount

<div class="details__message">

The Volume Discounts (DxV) feature allows sellers to offer discounts
based on the quantity of products purchased. This endpoint lets you
manage promotions linked to the system.

</div>

## Create campaign

Sellers can create a volume discount campaign, defining specific
parameters to apply discounts according to quantity purchased.

### Example:

``` language-javascript
curl --location \
'https://api.mercadolibre.com/marketplace/seller-promotions/seller-campaign/$USERID' \
--header 'Version: v2' \
--header 'Authorization: $ACCESS_TOKEN' \
--header 'Content-Type: application/json' \
--data '{ 
 "promotion_type": "VOLUME", 
 "sub_type": "BNGM", 
 "buy_quantity": 2, 
 "pay_quantity": 1, 
 "allow_combination": true, 
 "name": "Mi descuento de volumen", 
 "start_date": "2025-10-07T00:00:00", 
 "finish_date": "2025-10-20T00:00:00" 
} '
```

### Response:

``` language-javascript
{
 "id": "C-MLB360923", 
 "type": "VOLUME", 
 "sub_type": "BNGM|BNSP|SPONTH", 
 "(*)"buy_quantity": 9, 
 "(*)"pay_quantity": 3, 
 "(*)"discount_percentage": 30, 
 "allow_combination": true, 
 "status": "pending", 
 "start_date": "2023-07-17T00:00:00", 
 "finish_date": "2023-07-20T23:59:59", 
 "name": "test campaña bngm" 
}
```

### Fields:

-   promotion\_type: VOLUME
-   name: Unique name to identify the campaign
-   start\_date and finish date: campaign validity period.
-   allow\_combination: Determines if different items can be combined to
    apply a promotion. It is not possible to combine a volume promo with
    another discount.
-   sub\_type: can be one of the following.
    -   BNGM (Buy N get M): pay 3 and take 9.
    -   BNSP (Buy N save P%): 50% OFF buying 2.
    -   SPONTH (Save P% on the Nth): 50% OFF on the 2nd unit.
-   (\*) Based on the subtype, you must send 2 of the following fields:
    buy\_quantity, pay\_quantity, discount\_percentage.
-   BNGM: send buy\_quantity indicating the amount to buy (e.g. 9) and
    pay\_quantity indicating the amount to pay (e.g. 3).
-   BNSP: send buy\_quantity indicating the amount to buy (e.g. 2) and
    discount\_percentage indicating the discount percent (e.g. 50).
-   SPONTH: buy\_quantity indicating the amount to buy (e.g. 2) and
    discount\_percentage indicating the discount percent on that unit
    (e.g. 50).

## Update campaign

For editing volume campaigns consider the following:

-   You cannot modify the start or finish dates.
-   For active campaigns, only the name can be modified.
-   For scheduled campaigns, only send fields you want to change. If you
    want to modify campaign attributes (buy\_quantity, pay\_quantity,
    discount\_percentage) or change its subtype, you must include all
    corresponding attributes according to the subtype, even if they are
    not being changed.

### Example:

``` language-javascript
curl --location --request PUT 
'https://api.mercadolibre.com/marketplace/seller-promotions/seller-campaign/:promotionId?user_id=$USERID&callers=$USERID' \
--header 'Version: v2' \
--header 'Authorization: Bearer $ACCESS_TOKEN' \
--header 'Content-Type: application/json' \
--data '{ 
 "promotion_type": "VOLUME", 
 "sub_type": "BNGM|BNSP|SPONTH", 
 "(*)buy_quantity": 3, 
 "(*)pay_quantity": 1, 
 (*)"discount_percentage": 30, 
 "allow_combination": true, 
 "name": "Mi descuento de volumen" 
} '
```

### Response:

``` language-javascript
{ 
  "id": "C-MLA5689", 
  "type": "VOLUME", 
  "sub_type": "BNSP", 
  "status": "pending", 
  "start_date": "2024-08-22T17:20:00", 
  "finish_date": "2024-08-28T00:00:00", 
  "name": "Nombre cambiado", 
  "buy_quantity": 3, 
  "discount_percentage": 60, 
  "allow_combination": true, 
}
```

## Delete campaign

Allows deleting a specific campaign by its ID.

### Example:

``` language-javascript
curl --location --request DELETE 
'https://api.mercadolibre.com/marketplace/seller-promotions/seller-campaign/$PROMOTIONId?user_id=$USERID&callers=$USERID&promotion_type=VOLUME' \
--header 'Version: v2' \
--header 'Authorization: Bearer $ACCESS_TOKEN' \
--header 'Content-Type: application/json'
```

## Get campaign items

You can obtain the candidates and offers of a seller's items for a
volume campaign.

### Example:

``` language-javascript
curl --location 
'https://api.mercadolibre.com/marketplace/seller-promotions/promotions/$PROMOTION_ID?user_id=$USERID&callers=$USERID&promotion_type=VOLUME' \
--header 'version: v2' \
--header 'Authorization: Bearer $ACCESS_TOKEN'
```

### Response:

``` language-javascript
{ 
  "results": [ 
      { 
          "id": "MLM4007773188", 
          "status": "candidate", 
          "original_price": 20, 
          "buy_quantity": 3, 
          "discount_percentage": 20, 
          "allow_combination": true, 
          "start_date": "2025-09-25T06:00:00Z", 
          "end_date": "2025-10-26T05:59:59Z", 
          "sub_type": "BNSP" 
      }
  ]
}
```

### Response fields

-   id: Item id, String
-   status: Promotion status, String
-   original\_price: Original price of the item, int
-   (1)(2) buy\_quantity: Number of items obtained, int
-   \(2\) pay\_quantity: Number of items paid, int
-   \(1\) discount\_percentage: Discount % for the number of items
    bought (buy\_quantity), int (0-100)
-   allow\_combination: Boolean, True = Combinable, False = Not
    Combinable
-   start\_date: Promotion start date
-   end\_date: Promotion end date
-   sub\_type: Promotion subtype, String

## Assign items to a campaign

Link a specific item to a DxV campaign so that discount rules apply to
that item.

### Example:

``` language-javascript
curl --location 
'https://api.mercadolibre.com/marketplace/seller-promotions/items/$ITEM_ID?user_id=$USERID&callers=$USERID' \
--header 'version: v2' \
--header 'Authorization: Bearer $ACCESS_TOKEN' \
--header 'Content-Type: application/json' \
--data '{ 
"promotion_id": "C-MLM614177", 
"promotion_type": "VOLUME" 
} '
```

### Response:

``` language-javascript
{ 
"price": 11000, 
"original_price": 13000, 
"offer_id": "OFFER-MLA123-1111" 
}
```

### Parameters

-   price: discounted price applied.
-   original\_price: base price.
-   offer\_id: identifier of the created offer.

## Response fields (assign items)

-   price: Discounted price for the item, int
-   original\_price: Original price of the item, int
-   currency\_id: Currency id, String
-   offer\_id: Offer id, String

### Errors

-   400 Bad Request:
    -   Invalid promotion type (promotion\_type not VOLUME or not
        enabled).
    -   Offer with same range start date / end date already exists in
        offers (conflicting ranges).
    -   Offers\_Maximum\_Quantity\_Reached (maximum 5 quantity discounts
        per item).
-   404 Not Found: Promotion Not Found (invalid promotion\_id).
-   403 Forbidden: "Invalid caller.id" (caller is not owner of the
    campaign).

## Remove items

Removes an item previously linked to a DxV campaign, preventing
discounts from applying to that item.

``` language-javascript
curl -X DELETE -H 'Authorization: Bearer $ACCESS_TOKEN' 
https://api.mercadolibre.com/marketplace/seller-promotions/items/$ITEM_ID&promotion_type=VOLUME&promotion_id=$PROMOTIONS_ID \
--header 'version: v2' \
--header 'X-Client-Id: ' \
--header 'X-Caller-Id: '
```

### Errors (Remove items)

-   400 Bad Request: No offers found for item, Invalid promotion type.
-   403 Forbidden: "Invalid caller.id".

</div>
