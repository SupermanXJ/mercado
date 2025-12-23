<div class="inner-content">

## Manage cart orders

With the shopping cart feature, buyers can combine multiple items into a
single purchase. As they browse your listings, we'll suggest additional
products from your store for them to add to their cart.

For this reason, when you receive a notification from the
**marketplace\_orders** topic, it's essential to check the **pack\_id**
field in the response. If the **pack\_id** field returns a value other
than null, you should query the **pack\_id** in the
/marketplace/orders/pack/$PACK\_ID resource. This way, you'll obtain all
the orders associated with that **pack\_id**. Additionally, it's
necessary to validate the shipping id of the orders, as multiple orders
may share the same shipping id. Below, we provide a flowchart explaining
the correct procedure.

  
![Orders and Packs
flowchart](https://http2.mlstatic.com/storage/developers-site-cms-admin/182721577046-Ordes---Packs.jpg)  

## View cart sales

With this resource, you can consult all sales of the same pack
(**pack\_id**).

Request:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/marketplace/orders/pack/$PACK_ID
```

Example:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/marketplace/orders/pack/2000003508553677
```

Response:

``` language-javascript
{
 "id": 2000003508553677,
 "status": "released",
 "status_detail": null,
 "date_created": "2022-04-08T17:00:48.000-0400",
 "last_updated": "2022-04-08T17:02:07.000-0400",
 "family_pack_id": null,
 "buyer": {
     "id": 266272126
 },
 "shipment": {
     "id": 41297142475
 },
 "orders": [
     {
         "id": 2000003508897196
     },
     {
         "id": 2000003508911076
     }
 ]
}
```

### Response fields

-   **id**: Package identifier (integer).
-   **status**: Package status. Possible values:

<!-- -->

-   **filling**: The sale is paid and the pack is created, orders and
    shipments are being created.
-   **filled**: The orders and shipments of the pack are created and the
    distribution of the payment to each entity begins.
-   **released**: All orders and shipments are paid. This is the most
    commonly viewed status.

<!-- -->

-   **status\_detail**: Status detail. Shows the reason for a
    cancellation when applicable. Returns null if no detail is
    available.
-   **date\_created**: Date and time when the pack was created (ISO 8601
    format).
-   **last\_updated**: Date and time of the last update to the pack (ISO
    8601 format).
-   **family\_pack\_id**: When a pack is split, new packs are generated.
    A **child pack** stores in this field the ID of the parent pack.
    Returns null if the pack has not been split.
-   **buyer**: Object containing buyer information.

<!-- -->

-   **id**: Buyer's unique identifier.

<!-- -->

-   **shipment**: Object containing shipment information.

<!-- -->

-   **id**: Shipment's unique identifier.

<!-- -->

-   **orders**: Array of order objects associated with this pack.

<!-- -->

-   **id**: Order's unique identifier.

  

## Errors

The following table lists the specific errors that may be returned when
querying the pack resource:

| HTTP Code | Error             | Message                               | Solution                                                                                                          |
|-----------|-------------------|---------------------------------------|-------------------------------------------------------------------------------------------------------------------|
| 400       | Bad Request       | Invalid Parameter                     | Ensure the pack ID is a valid positive integer. Avoid negative numbers, decimals, strings, or special characters. |
| 403       | forbidden         | No orders found.                      | The pack ID may be zero or invalid. Verify the pack exists and belongs to your seller account.                    |
| 403       | not\_owned\_order | The user has not access to the order. | You can only access packs that belong to your seller account. Verify the pack ID is correct.                      |
| 404       | not\_found        | Resource not found                    | The specified pack ID does not exist. Verify the pack ID is correct.                                              |

  

**Next:**
[Shipments](https://global-selling.mercadolibre.com/devsite/manage-shipments).

</div>
