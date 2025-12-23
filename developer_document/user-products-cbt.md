<div class="inner-content">

## User Products

<div class="details__message">

User Product (UP) is a new concept implemented in Mercado Libre that
allows sellers to select different sale conditions for each variant of
the same product. In the context of Cross-Border Trade (CBT), the
adoption of the UP structure implies a transformation of the item
listing flow, simplifying the process by eliminating variations in the
product body.

</div>

<div class="andes-message andes-message--highlight">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div class="andes-message__title andes-message__title--highlight">

Important:

</div>

<div class="andes-message__text andes-message__text--highlight">

-   This documentation applies to sellers with the
    **user\_product\_seller** tag enabled.
-   The User Product model is being progressively implemented for all
    Global Selling sellers.
-   You can perform tests by requesting the environment setup for your
    TEST users with the following
    [form](https://docs.google.com/forms/d/1QBOHmzKdggHJPuDgOjKsYbtmodiWZmvZ-MuGtrhtvDQ/preview).
-   This feature will initially only be available for sellers with the
    Fulfillment China shipping mode.

</div>

</div>

</div>

During a coexistence period, backward compatibility is maintained to
facilitate the transition to the new architecture. The adoption of User
Product (UP) generates a centralized catalog, which decreases
redundancies and optimizes management. This flow organizes the creation
of User Product Global (siteless), User Product per site, Stock
locations, and Items.

-   Backward compatibility is ensured by maintaining current
    **endpoints** during the coexistence phase.
-   Future evolution contemplates the elimination of UP CBT and Item
    CBT, simplifying the process to UPSiteless directly to UP per site.
-   The solution is based on a Global UP (UPG) and a Local UP (UPL)
    associated with the same seller.
-   There will be a global UP (without a site) and a local UP for each
    site.
-   The **seller\_id's** of the UPs (global and local) will be identical
    (the **merchant\_id**).
-   However, the **seller\_id's** of the items for each site, linked to
    the local UPs, will be different, as each site will have its
    exclusive sellers.

## General Description

This flow organizes the creation of:

-   **User Product Global (UPG)**: A product without a site that serves
    as a parent for all specific products of each marketplace.
-   **User Product Local (UPL)**: Site-specific products linked to the
    Global UP, one per marketplace.
-   **Stock Locations**: Inventory management entities associated with
    the Global UP.
-   **Items**: Sale conditions (price, listing type, shipping) linked to
    the Local UPs.

  

## Global UP Siteless Structure

<div class="update-image"
style="background-color:#ffffff;padding:8px;margin:10px 0;border-radius:4px;max-width:100%;overflow:hidden">

![Logistic-Fulfillment](https://http2.mlstatic.com/storage/developers-site-cms-admin/141087526182-Logistic-Fulfilment.png)

</div>

  

## Key Concepts

-   The **seller\_id** for both Global and Local UPs will be the same
    (merchant\_id).
-   The stock/inventory is associated only with the Global UP.
-   All items in the tree will have the same **inventory\_id**.

## Differences with Traditional Variations

| Aspect           | Traditional Variations        | User Products Model                  |
|:-----------------|:------------------------------|:-------------------------------------|
| Structure        | 1 item with variations array  | Multiple UPs, each with its item     |
| Price            | Same price for all variations | Different price per variation        |
| Listing type     | Same for all variations       | Can differ per variation             |
| Stock management | By variation in the item      | At Global UP level (Stock Locations) |
| Product info     | At item level                 | At UP level                          |
| Grouping         | By item\_id                   | By family\_id                        |

## Model Changes

## Titles

-   New field: **family\_name**.
-   The **title** field is received temporarily for backward
    compatibility; it is internally mapped to family\_name.
-   If both are sent, **family\_name** has priority.

## Pictures

-   Pictures must be sent only by **id**, as the **source** field is no
    longer supported. Check **[working with
    pictures](https://global-selling.mercadolibre.com/devsite/pictures)**
    section out for more details on how to upload pictures.

``` language-javascript
{
  "pictures": [
    {
      "id": "701198-CBT79185512197_092024"
    }
  ]
}
```

## Variations

-   Do not send **variations** in the body. If it contains values, the
    API will return **400 Bad Request**.

## Item Condition

The item condition is defined by the **ITEM\_CONDITION** attribute.
Currently, only items with "New" status are allowed:

``` language-javascript
{
  "id": "ITEM_CONDITION",
  "values": [
    {
      "id": "2230284",
      "name": "New"
    }
  ]
}
```

## Frequently Asked Questions

-   **How can I identify sellers under the new User Product model?**
-   Through the **"user\_product\_seller"** tag in the /users API.
-   **How can I identify items under the User Product model?**
-   Validating if the item has **family\_name** different from null and
    if it has the **"user\_product\_listing"** tag.
-   **Can I continue sending the variations array?**
-   No, each variation will be a different User Product.
-   **How can I obtain all items belonging to the same family?**
-   GET /items to obtain the **user\_product\_id**
-   GET /user-products/$USER\_PRODUCT\_ID to obtain the **family\_id**
-   GET /user-products/$UPG\_ID/locals to obtain all Local UPs
-   GET
    /users/$SELLER\_ID/items/search?user\_product\_id=$USER\_PRODUCT\_ID
    to obtain all items of a UP

**Next**: [Price per
Variation](https://global-selling.mercadolibre.com/devsite/price-per-variation-cbt?nocache=true).

</div>
