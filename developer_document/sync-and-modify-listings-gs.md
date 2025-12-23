<div class="inner-content">

## Update items

<div class="details__message">

To update any item from your listings, you need to specify the item\_id
and the [seller's
access\_token](https://global-selling.mercadolibre.com/devsite/authentication-and-authorization-global-selling).
Keep in mind that not every field can be updated and this will vary
whether the item had sales or not, and also remember your item must be
active in order to be modified.

</div>

<div class="andes-message andes-message--neutral">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--neutral site-carriers__message-title">

Note:

</div>

<div class="andes-message__text--neutral site-carriers__message-text">

<div>

Successful PUT requests to update items return an empty JSON object `{}`
with HTTP Status Code 200. To verify the changes, perform a GET request
to the item endpoint.

</div>

</div>

</div>

</div>

  

**When the item has sales**, you cannot change title, condition, buying
mode. Also remember that **listing\_type** can be modified only once.

  

**When updating your listing variations**, you can change the values
from an existing variation by sending the id and the fields you want to
update. Remember to send the id of the other variations or they will be
deleted.

  

**If you want to add a new variation**, specify all the existing
variation's id and add the required fields for the new variation without
the id field.

  

**In case you want to remove an existing variation**, don't include its
id in the body of the request.

  

Example:

``` language-javascript
curl -X PUT -H 'Authorization: Bearer $ACCESS_TOKEN' -d
{
  "variations": [
          {
              "id": 123,
               "available_quantity": 100
          },
          {
            "available_quantity": 200,
            "attribute_combinations": [
                     {
                         "color": "Blue"
                     } 
                 ]
          }      
      ]
}
https://api.mercadolibre.com/global/items/CBT123
```

In the previous example we updated the available quantity from an
existing variation and added a new variation with the color blue.

  

## Update marketplace item

In this case, the changes sent in the request will only impact the
marketplace item that you indicated. Therefore, the values **must be
written in the local language per site**:

-   Spanish for Mercado Libre México, Colombia and Chile.
-   Portuguese for Mercado Livre Brazil.

You can update a specific marketplace item in two different ways:

-   Specifying the marketplace **item\_id** in the URI.

``` language-javascript
curl -X PUT -H 'Authorization: Bearer $ACCESS_TOKEN' -d
{
  "title": "Nuevo título"
}
https://api.mercadolibre.com/global/items/MLC123
```

-   Sending the global item\_id in the URI and specifying the site\_id
    and logistic\_type in the body.

``` language-javascript
curl -X PUT -H 'Authorization: Bearer $ACCESS_TOKEN' -d
{
   "site_id": "MLC",
   "logistic_type": "remote",
   "title": "Nuevo título"
}
https://api.mercadolibre.com/global/items/CBT123
```

In this case, the listing MLC123 corresponds with the global item CBT123
in the site MLC with the remote logistic, so both of these requests are
equivalent.

<div class="andes-message andes-message--neutral">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--neutral site-carriers__message-title">

Notes:

</div>

<div class="andes-message__text--neutral site-carriers__message-text">

<div>

\- You can modify the logistic type only with **fulfillment or remote**
value.  
- If you want to change the
[price](https://global-selling.mercadolibre.com/devsite/sync-and-modify-listings-gs#Update-prices)
and
[stock](https://global-selling.mercadolibre.com/devsite/sync-and-modify-listings-gs#Update-stock)
of an item, it must be taken into account if the publication has
variations.  
- Allow changes in the titles of the items with **sales achieved
(sold\_quantity = 0)**.

</div>

</div>

</div>

</div>

  

### Pictures

You can always add or replace item pictures. Learn more our [working
with pictures
guide](https://global-selling.mercadolibre.com/devsite/pictures) to know
the best way to get through it.

  

## Product status

The available status to global and marketplace items are active or
paused. You can see how to change the status:

<table class="andes-table">
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead class="andes-table__head">
<tr class="header andes-table__row">
<th class="andes-table__header andes-table__header--center">Global item (CBTXXX)</th>
<th class="andes-table__header andes-table__header--center">Marketplace item</th>
</tr>
</thead>
<tbody class="andes-table__body">
<tr class="odd andes-table__row">
<td class="andes-table__column andes-table__column--center">- active<br />
- paused</td>
<td class="andes-table__column andes-table__column--center">- active<br />
- paused<br />
- deleted</td>
</tr>
</tbody>
</table>

  

Example to pause a CBT item:

``` language-javascript
curl -X PUT -H 'Authorization: Bearer $ACCESS_TOKEN' -d
{
    "status": "paused"
}
https://api.mercadolibre.com/global/items/CBT2796239245
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

Request the /global/items resource with the parent id (CBT item id), and
put the status to modify the status.

</div>

</div>

</div>

</div>

Response: Status Code 200

  

Example to reactivate a CBT item:

``` language-javascript
curl -X PUT -H 'Authorization: Bearer $ACCESS_TOKEN' -d
{
    "status": "active"
}
https://api.mercadolibre.com/global/items/CBT2796239245
```

Response: Status Code 200

  

Example to pause a marketplace item only:

``` language-javascript
curl -X PUT -H 'Authorization: Bearer $ACCESS_TOKEN' -d
{
    "site_id": "MLC",
    "logistic_type": "remote",
    "status": "paused"
}
https://api.mercadolibre.com/global/items/CBT2796239245
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

Request the /global/items resource with the global id (CBT item id), and
include the site\_id and logistic\_type to modify the specific
marketplace item status.

</div>

</div>

</div>

</div>

Response: Status Code 200

  

Example to reactivate a marketplace item only:

``` language-javascript
curl -X PUT -H 'Authorization: Bearer $ACCESS_TOKEN' -d
{
    "site_id": "MLC",
    "logistic_type": "remote",
    "status": "active"
}
https://api.mercadolibre.com/global/items/CBT2796239245
```

Response: Status Code 200

  

## Status descriptions

**Active**: Listing is active and bids and questions can be received.
You can change the listing display (upgrade listing type).  
**Paused**: Listing is paused and bids and questions cant be received.
It may be automatically (out of stock) or at the user's discretion.  
**Inactive**: Listing is closed and you can't make any other action.  
**Under review**: Listing has moderated due a problem and needs to be
fixed.  

  

## Update stock

To update a marketplace item stock you have to make a PUT and add the
quantity value in the "available\_quantity" field taking the following
into account. Remember you **can update items with variations** and
**items without variations** as following examples.

  

So, if the seller has 10 (ten) units in stock, they must be detailed in
the Global item and this amount will be in all sites where the item is
listed, as well as when a sale is made, the subtraction will be
reflected in the Global Selling site.

  

## Update stock with variations

Request:

``` language-javascript
curl -X PUT -H 'Authorization: Bearer $ACCESS_TOKEN' -d
{
    "variations": [
       {
           "id": number,
           "available_quantity": number
       },
       {
            "id": number,
           "available_quantity": number
       }
   ]
}
https://api.mercadolibre.com/global/items/$ITEM_ID
```

Example:

``` language-javascript
curl -X PUT -H 'Authorization: Bearer $ACCESS_TOKEN' -d
{
    "variations": [
       {
           "id": 60819719795,
           "available_quantity": 100
       },
       {
            "id": 60819719802,
           "available_quantity": 150
       }
   ]
}
https://api.mercadolibre.com/global/items/CBT944238398
```

Response: Status Code 200

  

## Update stock without variations

Request:

``` language-javascript
curl -X PUT -H 'Authorization: Bearer $ACCESS_TOKEN' -d
{
   "available_quantity": number
}
https://api.mercadolibre.com/global/items/$ITEM_ID
```

Example:

``` language-javascript
curl -X PUT -H 'Authorization: Bearer $ACCESS_TOKEN' -d
{
   "available_quantity": 55
}
https://api.mercadolibre.com/global/items/CBT2796239245
```

Response: Status Code 200

  
  

### Considerations

-   When making a PUT to an available\_quantity with 0, the status will
    change to "paused" with out\_of\_stock sub status.
-   When making a PUT to an available\_quantity high 0 and
    out\_of\_stock status, the status will change to active without
    out\_of\_stock sub status.

  

## Update global item price

To update the price of a global item, send a PUT request with the new
price value. This will update the price across all marketplaces where no
specific price has been set.

Request:

``` language-javascript
curl -X PUT -H 'Authorization: Bearer $ACCESS_TOKEN' -d
{
  "price": 72.99
}
https://api.mercadolibre.com/global/items/CBT2796239245
```

Response: Status Code 200

  

## Update prices

<div class="andes-message andes-message--highlight">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--highlight site-carriers__message-title">

**Important:**

</div>

<div class="andes-message__text--highlight site-carriers__message-text">

<div>

Before modifying the price of an item using a **PUT** request to
**/items**,
<a href="https://global-selling.mercadolibre.com/devsite/manage-automations#:~:text=and%20outdated%20prices.-,Get%20Available%20Rules%20for%20an%20Item,-For%20a%20specific" class="andes-link">check if the listing has an active price automation</a>
. If the price is updated manually, the automation will be immediately
disabled to prevent inconsistencies and outdated information.  

</div>

</div>

</div>

</div>

In relation to the price of the product, the seller can put a specific
price for each marketplace item and if it's not defined, the price of
the Global item will be replicated on marketplace items. Look at the
next PUT example to modify a specific marketplace item price.

Request:

``` language-javascript
curl -X PUT -H 'Authorization: Bearer $ACCESS_TOKEN' -d
{
    "site_id": string,
    "logistic_type": string,
    "price": number
}
https://api.mercadolibre.com/global/items/$ITEM_ID
```

Example:

``` language-javascript
curl -X PUT -H 'Authorization: Bearer $ACCESS_TOKEN' -d
{
    "site_id": "MLC",
    "logistic_type": "remote", 
    "price": 68.50
}
https://api.mercadolibre.com/global/items/CBT2796239245
```

Response: Status Code 200

  

## Update prices with Net Proceeds

<div class="andes-message andes-message--highlight">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--highlight site-carriers__message-title">

Important:

</div>

<div class="andes-message__text--highlight site-carriers__message-text">

<div>

As of **January 5, 2026**, the **listing\_price field will be
deprecated** for item publication. All POST/PUT requests to the
**/global/items** endpoint must use the **net\_proceeds** field to
indicate the net amount received. We recommend making the necessary
adjustments as soon as possible to ensure the continued correct
functioning of the features.

</div>

</div>

</div>

</div>

You can update the Net Proceeds value of a listing using both the global
item ID and the local item ID. Both options are valid and can be chosen
according to your needs.

  

<div class="andes-message andes-message--neutral">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--neutral site-carriers__message-title">

Note:

</div>

<div class="andes-message__text--neutral site-carriers__message-text">

<div>

The global item ID always starts with the "CBT" prefix, while the local
item ID starts with the corresponding site code, for example, "MLB" for
Brazil or "MLC" for Chile.

</div>

</div>

</div>

</div>

  

### Update with local item

To update Net Proceeds directly through a local item, provide only the
"net\_proceeds" field.

**Request:**

``` language-javascript
curl -X PUT -H 'Authorization: Bearer $ACCESS_TOKEN' -d
{
    "net_proceeds": 45
}
https://api.mercadolibre.com/global/items/MLC1780459445
```

**Response:** Status Code 200

  

### Update with global item

To update the Net Proceeds value in multiple local items belonging to
the same global item, use the global item update endpoint. Simply
include the information of each local item in the "site\_listings"
array, informing the corresponding "listing\_item\_id", logistics type,
and the new "net\_proceeds" value.

**Request:**

``` language-javascript
curl -X PUT -H 'Authorization: Bearer $ACCESS_TOKEN' -d
{
   "site_listings": [
        {
            "logistic_type": "remote",
            "listing_item_id": "MLC2994461456",
            "net_proceeds": 45
        },
        {
            "logistic_type": "remote",
            "listing_item_id": "MLB5523633278",
            "net_proceeds": 50
        }
   ]
}
https://api.mercadolibre.com/global/items/CBT2546610318
```

**Response:** Status Code 200

<div class="andes-message andes-message--highlight" style="color:white">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div class="andes-message__title andes-message__title--highlight">

**Important:**

</div>

<div class="andes-message__text--highlight">

Make sure that the **"listing\_item\_id"** informed belong to the
indicated global item. This approach allows updating multiple
marketplaces in a centralized way, ensuring consistency and efficiency
in price management.

</div>

</div>

</div>

  

### Update of a single local item from the Global item

To update the Net Proceeds of only one local item belonging to a global
item, it is possible to do this without the need to inform the
"listing\_item\_id". Simply indicate the corresponding "site\_id", along
with the "logistic\_type" and the new "net\_proceeds" value.

**Request:**

``` language-javascript
curl -X PUT -H 'Authorization: Bearer $ACCESS_TOKEN' -d
{
    "site_id": "MLC",
    "logistic_type": "remote",
    "net_proceeds": 48
}
https://api.mercadolibre.com/global/items/CBT2796239245
```

**Response:** Status Code 200

<div class="andes-message andes-message--neutral">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--neutral site-carriers__message-title">

Note:

</div>

<div class="andes-message__text--neutral site-carriers__message-text">

<div>

This update is useful for specific updates in a single marketplace,
maintaining the global structure of the item and avoiding direct
manipulation of local IDs.

</div>

</div>

</div>

</div>

  
  

## Delete marketplace items

In order to **delete marketplace items**, the item to delete must be in
a paused or closed state and then delete it.

  
  

## Fulfillment restrictions

When updating a global item with at least one of its marketplace
listings using the Fulfillment logistic, and with current stock or a
valid inbound, the following validations are done.

If the marketplace listing has at least one variation:

-   The edition of **attribute\_combinations** values is not allowed,
    this means:
-   The elimination of an existing variation is not allowed.
-   The change of status to "closed" is not allowed.

If the marketplace listing doesn't have variations:

-   The **addition** of a new variation is not allowed.
-   The **change** of status to "closed" is not allowed.

## Package validations

The packages attributes of an listing must follow the requirements
below:

-   The width, height and length must be greater or equal than 3
    centimeters.
-   The weight must be greater or equal than 50 grams.
-   The volume calculated with the following formula must be bigger than
    0.02

Width \* Height \* Length/5000  
  

## Rate limit locking restriction

We implemented a rate limit restriction in order to control the requests
sended to the API. The rate limit is configured to 1500 requests per
minute per seller, if you exceed this limit, you will receive an empty
response with a 429 status code.

  

## Errors

| Error                   | Message                                                                                                                                                                                                                            | Solution                                                                                                                                                                                                              |
|-------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 404 - Not Found         | Item with id CBTXXX not found                                                                                                                                                                                                      | Verify the item\_id exists and belongs to the authenticated user.                                                                                                                                                     |
| 403 - Forbidden         | At least one policy returned UNAUTHORIZED.                                                                                                                                                                                         | Verify the access\_token belongs to the item owner and has proper permissions.                                                                                                                                        |
| 400 - Validation error  | The body sent is not valid, make sure you write the fields and values correctly                                                                                                                                                    | Check that status value is "active" or "paused" only.                                                                                                                                                                 |
| 400 - Invalid price     | Cannot update item price because it is an invalid value                                                                                                                                                                            | Price must be a positive number greater than 0.                                                                                                                                                                       |
| 400 - Invalid stock     | invalid property type: \[available\_quantity\] expected Number greater than 0                                                                                                                                                      | available\_quantity must be a positive integer (0 or greater).                                                                                                                                                        |
| 400 - Invalid site      | User not found by site: INVALID                                                                                                                                                                                                    | Verify site\_id is valid (MLB, MLC, MLM, MCO).                                                                                                                                                                        |
| 400 - Validation error  | Cannot modify CBT item from this resource.                                                                                                                                                                                         | To edit global items: send the URL https://api.mercadolibre.com/global/items. To edit marketplace items: send the https://api.mercadolibre.com/global/items/CBTXXX with the marketplace item information.             |
| 400 - Validation error  | The item could not be updated because the item or variation you are trying to modify has inventory.                                                                                                                                | The request sended doesn't pass Fulfillment validations. Please, [check Fulfillment restrictions](https://global-selling.mercadolibre.com/devsite/sync-and-modify-listings-gs#Restrictions).                          |
| 400 - Bad request       | Error processing dimensions for item                                                                                                                                                                                               | The request sent doesn't contain all the packages attributes mentioned. For information about shipment dimensions and cost, visit our [shipping cost calculator](https://global-selling.mercadolibre.com/help/22213). |
| 400 - Validation error  | Shipping configuration is not valid for item.                                                                                                                                                                                      | The listing contains the IS\_FLAMMABLE attribute. The package dimensions exceed the limits by carrier. The user does not have the me2 logistic type Digital products cannot be sent in me2.                           |
| 422 - Bad request       | The submitted dimensions and/or weights do not correspond to real measurements of the package. You must use the correct dimensions of the package that you'll use to dispatch your product, as well as the net weight of the item. | Check more information about How to calculate the shipping cost of your products.                                                                                                                                     |
| 429 - Too Many Requests | Rate limit exceeded                                                                                                                                                                                                                | Wait and retry. Rate limit is 1500 requests per minute per seller.                                                                                                                                                    |

**Next**: [Multi-marketplace
tool](https://global-selling.mercadolibre.com/devsite/multi-marketplace-tool)
.

  

</div>
