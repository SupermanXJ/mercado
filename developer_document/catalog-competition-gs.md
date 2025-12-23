<div class="inner-content">

## Catalog competition

<div class="details__message">

In catalog, publications compete for the sales of the product page and
an algorithm determines who will be the winner of those sales based on
characteristics of the publication and the seller itself, such as
**Price**, **interest-free fees**, **Full shipping**, **Free shipping**
or **in the day**. In addition, we will speak of "the winner" in a
unique way, although eventually the seller could be winning in general
but not in particular for certain users (for example, if they live very
far and they would not get a shipment in the day).

</div>

## Publications competing notification

With the **Item competition** topic you can subscribe and start [receive
notifications](https://global-selling.mercadolibre.com/devsite/receive-notifications)
of the change of status of catalog items, and will allow you to
recognize the item that modifies its competition status to winner or
vice versa. To view the competitor information and review the conditions
under which the seller is competing to win the product page, **use the
/price\_to\_win resource** to find out what actions to take.

  
  

## Conditions and price of the winning item

<div class="andes-message andes-message--highlight">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--highlight site-carriers__message-title">

Important:

</div>

<div class="andes-message__text--highlight site-carriers__message-text">

<div>

Sellers who share conditions of sale in their products similar to those
of the catalog winner, have a visibility part on the product page and
their status is **"sharing\_first\_place"**.

</div>

</div>

</div>

</div>

With the resource **/price\_to\_win?siteId=$SITE\_ID&version=v2** you
recognize the status of the catalog publication: it may be winning,
sharing first, losing or listed. The latter means that you have reasons
why the post is not competing.  
You can also **build a competition table** to compare the conditions of
the items and improve them based on the competition. With this
functionality in your development, sellers will know what conditions to
improve to win the product page.

  

**Item missing example**

Request:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/items/$ITEM_ID/price_to_win?siteId=$SITE_ID&version=v2
```

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/items/MLA123456789/price_to_win?siteId=MLA&version=v2
```

Response:

``` language-javascript
{
   "item_id": "MLA901414479",
   "current_price": 12999,
   "currency_id": "ARS",
   "price_to_win": 11500,
   "boosts": [
       {
           "id": "same_day_shipping",
           "status": "boosted",
           "description": "Envíos en el día por Mercado Envíos"
       },
       {
           "id": "fulfillment",
           "status": "opportunity",
           "description": "Mercado Envíos Full"
       },
       {
           "id": "free_installments",
           "status": "opportunity",
           "description": "Cuotas sin interés"
       },
       {
           "id": "free_shipping",
           "status": "not_apply",
           "description": "Envíos gratis por Mercado Envíos"
       },
       {
           "id": "shipping_collect",
           "status": "boosted",
           "description": "Mercado Envíos Colecta"
       }
   ],
   "status": "competing",
   "competitors_sharing_first_place": "null",
   "visit_share": "minimum",
   "consistent": true,
   "reason": [],
   "catalog_product_id": "MLA16107499",
   "winner": {
       "item_id": "MLA884484295",
       "price": 13499,
       "currency_id": "ARS",
       "boosts": [
           {
               "id": "same_day_shipping",
               "status": "boosted",
               "description": "Envíos en el día por Mercado Envíos"
           },
           {
               "id": "fulfillment",
               "status": "opportunity",
               "description": "Mercado Envíos Full"
           },
           {
               "id": "free_installments",
               "status": "boosted",
               "description": "Cuotas sin interés"
           },
           {
               "id": "free_shipping",
               "status": "not_apply",
               "description": "Envíos gratis por Mercado Envíos"
           },
           {
               "id": "shipping_collect",
               "status": "boosted",
               "description": "Mercado Envíos Colecta"
           }
       ]
   }
}
```

**Item winning example**

Request:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/items/$ITEM_ID/price_to_win?siteId=$SITE_ID&version=v2
```

Example:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/items/MLA123456789/price_to_win?siteId=MLA&version=v2
```

Response:

``` language-javascript
{
   "item_id": "MLA884484295",
   "current_price": 13499,
   "currency_id": "ARS",
   "price_to_win": 13499,
   "boosts": [
       {
           "id": "same_day_shipping",
           "status": "boosted",
           "description": "Envíos en el día por Mercado Envíos"
       },
       {
           "id": "fulfillment",
           "status": "opportunity",
           "description": "Mercado Envíos Full"
       },
       {
           "id": "free_installments",
           "status": "boosted",
           "description": "Cuotas sin interés"
       },
       {
           "id": "free_shipping",
           "status": "not_apply",
           "description": "Envíos gratis por Mercado Envíos"
       },
       {
           "id": "shipping_collect",
           "status": "boosted",
           "description": "Mercado Envíos Colecta"
       }
   ],
   "status": "winning",
   "competitors_sharing_first_place": "0",
   "visit_share": "maximum",
    "consistent": true,
   "reason": [],
   "catalog_product_id": "MLA16107499",
   "winner": {
       "item_id": "MLA884484295",
       "price": 13499,
       "currency_id": "ARS",
       "boosts": [
           {
               "id": "same_day_shipping",
               "status": "boosted",
               "description": "Envíos en el día por Mercado Envíos"
           },
           {
               "id": "fulfillment",
               "status": "opportunity",
               "description": "Mercado Envíos Full"
           },
           {
               "id": "free_installments",
               "status": "boosted",
               "description": "Cuotas sin interés"
           },
           {
               "id": "free_shipping",
               "status": "not_apply",
               "description": "Envíos gratis por Mercado Envíos"
           },
           {
               "id": "shipping_collect",
               "status": "boosted",
               "description": "Mercado Envíos Colecta"
           }
       ]
   }
}
```

**Item sharing first place example**

<div class="andes-message andes-message--neutral">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--neutral site-carriers__message-title">

Note:

</div>

<div class="andes-message__text--neutral site-carriers__message-text">

<div>

The **sharing\_first\_place status** identifies all sellers with the
best offer and a level of shared exposure in Catalog.

</div>

</div>

</div>

</div>

Example:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/items/MLA123456710/price_to_win?siteId=MLA&version=v2
```

Response:

``` language-javascript
{
   "item_id": "MLA901414479",
   "current_price": 12999,
   "currency_id": "ARS",
   "price_to_win": 11500,
   "boosts": [
       {
           "id": "same_day_shipping",
           "status": "boosted",
           "description": "Envíos en el día por Mercado Envíos"
       },
       {
           "id": "fulfillment",
           "status": "opportunity",
           "description": "Mercado Envíos Full"
       },
       {
           "id": "free_installments",
           "status": "opportunity",
           "description": "Cuotas sin interés"
       },
       {
           "id": "free_shipping",
           "status": "not_apply",
           "description": "Envíos gratis por Mercado Envíos"
       },
       {
           "id": "shipping_collect",
           "status": "boosted",
           "description": "Mercado Envíos Colecta"
       }
   ],
   "status": "sharing_first_place",
   "competitors_sharing_first_place": "2",
   "visit_share": "medium",
   "consistent": true,
   "reason": [],
   "catalog_product_id": "MLA16107499",
   "winner": {
       "item_id": "MLA884484295",
       "price": 13499,
       "currency_id": "ARS",
       "boosts": [
           {
               "id": "same_day_shipping",
               "status": "boosted",
               "description": "Envíos en el día por Mercado Envíos"
           },
           {
               "id": "fulfillment",
               "status": "opportunity",
               "description": "Mercado Envíos Full"
           },
           {
               "id": "free_installments",
               "status": "boosted",
               "description": "Cuotas sin interés"
           },
           {
               "id": "free_shipping",
               "status": "not_apply",
               "description": "Envíos gratis por Mercado Envíos"
           },
           {
               "id": "shipping_collect",
               "status": "boosted",
               "description": "Mercado Envíos Colecta"
           }
       ]
   }
}
```

**Item not competing example**

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/items/MLA123456710/price_to_win?siteId=MLA&version=v2
```

Response:

``` language-javascript
{
   "item_id":"MLA123456710",
   "current_price":68000,
   "currency_id":"ARS",
   "price_to_win":null,
   "boosts":{
      "same_day_shipping":false,
      "fulfillment":false,
      "free_installments":false,
      "free_shipping":true,
      "cross_docking":false,
      "drop_off":true,
      "shipping_quarantine":false
   },
   "status":"listed",
   "competitors_sharing_first_place": null,
   "visit_share": "minimum",
   "reason":[
      "item_paused"
   ]
}
```

  

### Response fields

**price\_to\_win**: price in the current currency of the publication to
be the winner, that is, request PUT to the /items resource with the
suggested price, the publication will win the product page.  
**boosts**: characteristics of the publication that provide chances of
winning, such as:

**same\_day\_shipping**: shipping on day with Mercado Envios.

**fulfillment**: Mercado Envios Full.

**free\_installments**: interest-free fees.

**free\_shipping**: free Shipping with Mercado Envios.

**shipping\_quarantine**: shipping normally.

**shipping\_collect**: Mercado Envios Colecta.

Now, you can recognize within the boost the state of these and draw a
comparison table accordingly.

| Boost status | Detail                                                                                       |
|--------------|----------------------------------------------------------------------------------------------|
| boosted      | It has the condition of sale and currently applies the boost.                                |
| not\_boosted | It has the condition of sale but it is not a boost that improves the chances of winning.     |
| opportunity  | It does not have the condition of sale. If applied, it would improve the chances of winning. |
| not\_apply   | The sales condition does not apply as a boost to the product where the item competes.        |

<div class="andes-message andes-message--neutral">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--neutral site-carriers__message-title">

Note:

</div>

<div class="andes-message__text--neutral site-carriers__message-text">

<div>

This information allows you to quickly compare with the second listing
on the publication of the item that is winning the product page.

</div>

</div>

</div>

</div>

**status**: indicates whether the product is winning for the public or
for minority segments such as those who do not take advantage of day
shipping. When it is winning, the value is winning, otherwise it will be
competing for the one who is losing and a new value is added
**sharing\_first\_place** for when the first place is shared and they
are divided among all those who share the first place according to your
conditions the levels of visibility on the product page.  
**competitors\_sharing\_first\_place** sellers quantity who share the
first place. It will also depend on the states:

-   **Winning**: will be 0, so being the winner takes all the sales and
    visibility in the catalog.
-   **Competing**: will be null, so when losing it has to improve the
    conditions to share the first place or to win.
-   **Listed**: will be null, so when losing it has to improve the
    conditions to share the first place or to win.
-   **Sharing\_first\_place**: number of sellers competing for first
    place.

**visit\_share**: visibility level on the catalog publication. The
values may vary depending on the states:

-   **Winning**: will always be maximum.
-   **Competing**: will always be minimum.
-   **Sharing\_first\_place**: always will be medium.

**reason**: It will display information only when the publication is not
competing, allowing you to identify the reason why it is not competing
and thus take improvement actions.

In this request you will have to use an item\_id of a catalog
publication. If not, you will receive an 4XX error code. Moreover, there
are variables such as the reputation that are used to determine the
winner. However, for a good seller, the variables used to determine the
winner will be the previous ones.

## Reasons

There are different reasons why a publication is not competing within
the catalog, below we list all the possible reasons that the [endpoint
de
price\_to\_win](https://global-selling.mercadolibre.com/devsite/catalog-competition-gs)
endpoint will answer in the **reason** attribute, which will allow you
to perform the different actions to improve your publication and enter
it to the competition.

| Reason                                              | Description                                                                                                                                                                                 |
|-----------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| non\_trusted\_seller                                | The seller is not in the whitelist of fraud. It cannot compete. It appears at the end in the listings.                                                                                      |
| reputation\_below\_threshold                        | The seller does not reach the minimum reputation to win. It cannot compete. It only appears in the listings.                                                                                |
| item\_reputation\_below\_threshold                  | The publication cannot compete, as it does not reach the reputation required to win. It appears in the listings.                                                                            |
| winner\_has\_better\_reputation                     | The seller has a reputation that could compete but there is a winner with a better reputation. At the moment, it only appears in the listings (yellow case with green winner).              |
| manufacturing\_time                                 | The item has manufacturing time, only appears in the listings and cannot win because the winner has immediate stock.                                                                        |
| temporarily\_winning\_manufacturing\_time           | The item has manufacturing time, it is temporarily winning because there are no competitors in the same reputation level without MF.                                                        |
| temporarily\_competing\_manufacturing\_time         | The item has manufacturing time, it is competing temporarily because there are no competitors at the same reputation level without MF, the winner also has MF.                              |
| temporarily\_winning\_best\_reputation\_available   | The seller is not green but has a reputation that can win and is the best offer available. He is winning temporarily. If a better offer appears, stop winning.                              |
| temporarily\_competing\_best\_reputation\_available | The seller is not green but it is the best reputation available, it is competing temporarily. The winner is also of the same reputation. If a best seller appears, it is only listed again. |
| item\_paused                                        | The item is paused, it cannot be listed.                                                                                                                                                    |
| item\_not\_opted\_in                                | The item has not opted in, cannot be listed or is a test item.                                                                                                                              |
| shipping mmode                                      | Only available for MLB. Seller is not competing because their shipping method is inferior to the winner. ME2 &gt; ME1 &gt; Custom Shipping &gt; Not Specified.                              |

  

## Winning publication

Using [the /products/$PRODUCT\_ID
resource](https://global-selling.mercadolibre.com/devsite/products-search-gs#Product-by-ID),
in addition to knowing the characteristics and status of the product,
you can recognize the publication that is winning the product page using
the **buy\_box\_winner** field.

  

## Consult the list of publications for a product

If you need to know which seller´s products are the ones that compete
for the sales of a particular product, make this request:

Request:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/products/$PRODUCT_ID/items
```

Example:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/products/MLB6309815/items
```

Short response:

``` language-javascript
{
  "paging": {
    "total": 7,
    "offset": 0,
    "limit": 100
  },
  "results": [
    {
      "item_id": "MLA824759321",
      "category_id": "MLA1055",
      "seller_id": 90205574,
      "price": 13999,
      "currency_id": "ARS",
      "sold_quantity": 0,
      "available_quantity": 1,
      "shipping": {
        "mode": "me2",
        "tags": [
          "mandatory_free_shipping"
        ],
        "free_shipping": true,
        "logistic_type": "fulfillment",
        "store_pick_up": false
      },
      "warranty": "Garantía de fábrica: 1 años",
      "condition": "new",
      "sale_terms": [
        {
          "id": "INVOICE",
          "name": "Facturación",
          "value_id": "6891885",
          "value_name": "Factura A",
          "value_struct": null
        },
        {
          "id": "WARRANTY_TYPE",
          "name": "Tipo de garantía",
          "value_id": "2230279",
          "value_name": "Garantía de fábrica",
          "value_struct": null
        },
        {
          "id": "WARRANTY_TIME",
          "name": "Tiempo de garantía",
          "value_id": null,
          "value_name": "1 años",
          "value_struct": {
            "number": 1,
            "unit": "años"
          }
        }
      ],
      "official_store_id": null,
      "original_price": null,
      "listing_type_id": "gold_special",
      "accepts_mercadopago": true,
      "seller_address": {
        "city": {
          "id": "TUxBQ0xBWmI3M2Q3",
          "name": "Santa Fe"
        },
        "state": {
          "id": "TUxBUFNBTmU5Nzk2",
          "name": "Santa Fe"
        },
        "neighborhood": {
          "id": "TUxBQk9UUjQyMjJa",
          "name": "Otros Barrios"
        }
      },
      "international_delivery_mode": "none",
      "tags": [
        "extended_warranty_eligible",
        "good_quality_picture",
        "good_quality_thumbnail",
        "immediate_payment",
        "cart_eligible"
      ],
      "tier": ""
    },
    {},
    {},
    {},
    {},
    {},
    {}
  ]
}
```

Take into account that “results” will give the items that are competing
to win this product.

## Filtering

This filtering will work in exactly the same way as in the resource of
Search (/sites/{site}/search) where it is possible to use the values of
<span style="font-family:monospace">available\_filters</span> as a
parameter in the URL:

  

You currently have the following filtering options:

<table class="andes-table">
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead class="andes-table__head">
<tr class="header andes-table__row">
<th class="andes-table__header andes-table__header--left">Parameters</th>
<th class="andes-table__header andes-table__header--left">Value</th>
<th class="andes-table__header andes-table__header--left">Description</th>
</tr>
</thead>
<tbody class="andes-table__body">
<tr class="odd andes-table__row">
<td class="andes-table__column andes-table__column--left">official_store</td>
<td class="andes-table__column andes-table__column--left">all</td>
<td class="andes-table__column andes-table__column--left">To show only products with winner of Official Stores.</td>
</tr>
<tr class="even andes-table__row">
<td class="andes-table__column andes-table__column--left">official_store_id</td>
<td class="andes-table__column andes-table__column--left">id</td>
<td class="andes-table__column andes-table__column--left">To show the winner products of an Official Store.</td>
</tr>
<tr class="odd andes-table__row">
<td class="andes-table__column andes-table__column--left">discount</td>
<td class="andes-table__column andes-table__column--left">10-100</td>
<td class="andes-table__column andes-table__column--left">To show products with a winner with a discount greater than or equal to 10%.</td>
</tr>
<tr class="even andes-table__row">
<td class="andes-table__column andes-table__column--left">price</td>
<td class="andes-table__column andes-table__column--left">100-200</td>
<td class="andes-table__column andes-table__column--left">For products with winner priced between 100 and 200.<br />
*100 for products with winner with a price greater than or equal to 100.<br />
*200 for products with winner with a price less than or equal to 200.</td>
</tr>
<tr class="odd andes-table__row">
<td class="andes-table__column andes-table__column--left">shipping</td>
<td class="andes-table__column andes-table__column--left">fulfillment</td>
<td class="andes-table__column andes-table__column--left">For products with winner with FBM.</td>
</tr>
<tr class="even andes-table__row">
<td class="andes-table__column andes-table__column--left">shipping</td>
<td class="andes-table__column andes-table__column--left">mercadoenvios</td>
<td class="andes-table__column andes-table__column--left">For products with winner without FBM.</td>
</tr>
<tr class="odd andes-table__row">
<td class="andes-table__column andes-table__column--left">shipping_cost</td>
<td class="andes-table__column andes-table__column--left">free</td>
<td class="andes-table__column andes-table__column--left">For products with winner with free shipping.</td>
</tr>
<tr class="even andes-table__row">
<td class="andes-table__column andes-table__column--left">shipping_time</td>
<td class="andes-table__column andes-table__column--left">sameday/ nextday</td>
<td class="andes-table__column andes-table__column--left">It must be used together with the query param b.buyer_zones which indicates in which areas the buyer is located.</td>
</tr>
<tr class="odd andes-table__row">
<td class="andes-table__column andes-table__column--left">seller_id</td>
<td class="andes-table__column andes-table__column--left">id</td>
<td class="andes-table__column andes-table__column--left">Get the winner user_id</td>
</tr>
</tbody>
</table>

Example:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/products/MLB6309815/items?shipping_cost=free
```

</div>
