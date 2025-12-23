<div class="inner-content">

## Price per Variation

<div class="details__message">

The Price per Variation (PxV) initiative aims to provide the seller with
the ability to offer different sales conditions for the variants of the
same product, allowing them to apply their sales strategies in a more
flexible and scalable way.

</div>

<div class="andes-message andes-message--highlight">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj4KPC9jaXJjbGU+PC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div class="andes-message__title andes-message__title--highlight">

Important:

</div>

<div class="andes-message__text andes-message__text--highlight">

-   Under the User Product model, each variation becomes a separate User
    Product with its own sales conditions (item\_id).
-   This allows having different prices per variation. For now, we will
    only activate User Product for sellers who have stock in
    meli\_facility.
-   Due to this, it will not be possible to modify the stock manually,
    as management is handled by the fulfillment flow.
-   You can perform tests by requesting the environment for your TEST
    users with the following
    [form](https://docs.google.com/forms/d/1QBOHmzKdggHJPuDgOjKsYbtmodiWZmvZ-MuGtrhtvDQ/preview).
-   This feature will initially only be available for sellers with the
    Fulfillment China shipping mode.

</div>

</div>

</div>

With the adoption of User Products for Global Selling, the concept of
variations changes fundamentally. Instead of having a single item with
multiple variations, each variation becomes an independent User Product
with its own item (sales condition). This architecture allows setting
different prices for each variation.

  

## How it works

In the new model:

-   Each variation of color, size, or attribute is a **separate User
    Product**.
-   All variations of the same product share the same **family\_id**.
-   Each User Product has its own item with independent **price**,
    **listing\_type**, and **shipping** configuration.
-   Product information (attributes, images, title) is managed at the UP
    level.
-   Sales conditions (price, stock, shipping) are managed at the item
    level.

  

## Architecture

<div class="update-image"
style="background-color:#ffffff;padding:8px;margin:10px 0;border-radius:4px;max-width:100%;overflow:hidden">

![UP](https://http2.mlstatic.com/storage/developers-site-cms-admin/141087623635-UP.png)

</div>

  

## UP Sellers Validation

The enablement of sellers to the new User Products model will be carried
out progressively. While the 100% enablement is completed, there will be
two types of sellers: those not yet active using the previous model, and
those active who must publish using the User Products model.

Enabled sellers will have the **"user\_product\_seller"** tag, which you
can identify by making a call to the users API.

You can get the details of a User Product through the following call:

``` language-javascript
curl -X GET 'https://api.mercadolibre.com/users/user_id' \
--header 'Authorization: Bearer TOKEN'
```

Example:

``` language-javascript
curl -X GET 'https://api.mercadolibre.com/users/2929727114' \
--header 'Authorization: Bearer $TOKEN'
```

Response: Validation of user\_product\_seller tag (200 OK):

``` language-javascript
{
  "user_type": "normal",
  "tags": [
    "user_product_seller",
    "normal"
  ]
}
```

## Creating variations as User Products

Below are considerations to keep in mind when publishing an item under
the new UP model.

The new **family\_name** field is a required field that the seller must
complete; this field will be a generic description of the item. For
example:

-   Family name: "Apple iPhone 256GB"
-   Item\_1: "Apple iPhone 256GB Red"
-   Item\_2: "Apple iPhone 256GB Blue"

<div class="andes-message andes-message--neutral">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj4KPC9jaXJjbGU+PC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div class="andes-message__title andes-message__title--neutral">

Note:

</div>

<div class="andes-message__text--neutral">

-   The price and sales conditions can change in each item that is
    published.
-   Currently, each UserProduct admits a maximum of 30 sales conditions
    (items).
-   Attempting to associate more than 30 sales conditions to the same UP
    will generate an error.

</div>

</div>

</div>

Additionally, the **title** field should not be sent by the seller as
Mercado Libre will complete it automatically with information from the
specific item or product. This is done to achieve more standardized
items.

  

## Create Global UP

Request for the creation of a Global User Product
(siteless\_user\_product\_id), Local UP (user\_product\_id), and the
sales condition.

Request for the Red variation:

``` language-javascript
curl -X POST 'https://api.mercadolibre.com/global/user-products' \
--header 'Authorization: Bearer $TOKEN'
```

Example:

``` language-javascript
curl -X POST 'https://api.mercadolibre.com/global/user-products' \
--header 'Authorization: Bearer APP_USR-xxxxxxxxxxxxxxx' \
--header 'Content-Type: application/json' \
--data '{
  "sites_to_sell": [
    {
      "site_id": "MCO",
      "logistic_type": "remote",
      "user_id": 1305628788
    },
    {
      "site_id": "MLC",
      "logistic_type": "remote",
      "user_id": 1305628788
    },
    {
      "site_id": "MLB",
      "logistic_type": "remote",
      "user_id": 1305628788
    }
  ],
  "family_name": "Red T-shirt M logo",
  "title": "T-shirt M logo",
  "category_id": "CBT416197",
  "price": 25,
  "available_quantity": 100,
  "description": {
    "plain_text": "Sample item for E2E flow in MLM."
  },
  "pictures": [
    {
      "id": "655219-CBT82943741035_032025"
    }
  ],
  "attributes": [
    {
      "id": "ITEM_CONDITION",
      "values": [
        {
          "id": "2230284",
          "name": "New"
        }
      ]
    },
    {
      "id": "BRAND",
      "value_name": "FlowBrand"
    },
    {
      "id": "MODEL",
      "value_name": "FlowModel"
    },
    {
      "id": "PACKAGE_HEIGHT",
      "value_name": "10 cm"
    },
    {
      "id": "PACKAGE_LENGTH",
      "value_name": "20 cm"
    },
    {
      "id": "PACKAGE_WIDTH",
      "value_name": "15 cm"
    },
    {
      "id": "PACKAGE_WEIGHT",
      "value_name": "500 g"
    }
  ],
  "sale_terms": [
    {
      "id": "WARRANTY_TYPE",
      "value_id": "6150835",
      "value_name": "No warranty"
    }
  ]
}'
```

Response:

``` language-javascript
{
  "item_id": "CBT2826958659",
  "seller_id": 1305628788,
  "site_id": "CBT",
  "parent_user_product_id": "CBTU3687816070",
  "siteless_user_product_id": "U3687816070",
  "siteless_family_id": 4919667263731854,
  "site_items": [
    {
      "item_id": "MCO3419064200",
      "seller_id": 1305630918,
      "site_id": "MCO",
      "user_product_id": "MCOU3687816070",
      "logistic_type": "remote"
    },
    {
      "item_id": "MLB6068255422",
      "seller_id": 1305627900,
      "site_id": "MLB",
      "user_product_id": "MLBU3687816070",
      "logistic_type": "remote"
    },
    {
      "item_id": "MLC3437222586",
      "seller_id": 1305631715,
      "site_id": "MLC",
      "user_product_id": "MLCU3687816070",
      "logistic_type": "remote"
    }
  ]
}
```

Repeat for Blue and Green variations with their respective attributes.

  

## Create Local UP

If a global UP is already created, new local UP can be created, similar
to [activating and item in another
marketplace](https://global-selling.mercadolibre.com/devsite/global-listing#:~:text=validates%20consistencies.-,Activate%20in%20another%20marketplace,-Recommendation%3A).  
Request for the creation of User products (user\_product\_id) per site:

Request:

``` language-javascript
curl -X POST -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/global/user-products/{siteless_user_product_id}
```

Example:

``` language-javascript
curl -X POST 'https://api.mercadolibre.com/global/user-products/U3687816070' \
--header 'Authorization: Bearer APP_USR-xxxxxxxxxxxxxxxxxxxx' \
--header 'Content-Type: application/json' \
--data '{
  "sites_to_sell": [
    {
      "site_id": "MLM",
      "logistic_type": "remote",
      "listing_type_id": "gold_pro",
      "price": 200
    }
  ]
}'
```

Response: 200 OK

``` language-javascript
{
  "item_id": "CBT2827162121",
  "seller_id": 1305628788,
  "site_id": "CBT",
  "parent_user_product_id": "CBTU3689227954",
  "siteless_user_product_id": "U3689227954",
  "site_items": [
    {
      "item_id": "MLM4537463738",
      "seller_id": 1305634202,
      "site_id": "MLM",
      "user_product_id": "MLMU3689227954",
      "logistic_type": "remote"
    }
  ]
}
```

## Identifying user products of the same family

All User Products that represent variations of the same product share
the same **family\_id**.

## Obtain all User products of a family

For local UPs:

``` language-javascript
GET /sites/<site_id>/user-products-families/<family_id>
```

Example:

``` language-javascript
curl --location 'https://api.mercadolibre.com/sites/{site_id}/user-products-families/{family_id}' \
--header 'Authorization: Bearer $TOKEN' \
--header 'X-API-Version: 2'
```

Response:

``` language-javascript
{
  "user_products_ids": [
    "U3688865954"
  ],
  "family_id": 2439906451747239,
  "user_id": 2929727114
}
```

Request:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' -H 'X-API-Version: 2' https://api.mercadolibre.com/internal/user-products-families/$FAMILY_ID
```

Response:

``` language-javascript
{
  "user_products_ids": [
    "U1234",
    "U1235",
    "U1236"
  ],
  "family_id": 111111111,
  "user_id": 12345
}
```

## Obtain User Product

Retrieves information about a Global User Product.

Request:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' -H 'X-API-Version: 2' https://api.mercadolibre.com/user-products/{siteless_user_product_id}
```

<div class="andes-message andes-message--neutral">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj4KPC9jaXJjbGU+PC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div class="andes-message__title andes-message__title--neutral">

Important:

</div>

<div class="andes-message__text--neutral">

Use the header **X-API-Version: 2** to get the locale field and support
for Global UPs.

</div>

</div>

</div>

Retrieves information about a Local User Product.

Request:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' -H 'X-API-Version: 2' https://api.mercadolibre.com/user-products/{local-user_product_id}
```

## Obtain Global UP from Local UP

Given a local UP ID, retrieves the global UP ID.

Request:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/user-products/{local-user_product_id}/global
```

Response:

``` language-javascript
{
  "global_id": "U3241085954"
}
```

If the UP has no global\_id:

``` language-javascript
{
  "error": "not_found",
  "message": "user-product not found",
  "status": 404
}
```

## Obtain Local UPs from Global UP

Given a global UP ID, retrieves all associated local UP IDs.

Request:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/user-products/{siteless_user_product_id}/locals
```

Response:

``` language-javascript
{
  "locals": [
    "MCOU3687816070",
    "MLCU3687816070",
    "MLBU3687816070",
    "CBTU3687816070"
  ]
}
```

## Updating prices

To update the price of a specific variation, update its item:

``` language-javascript
curl -X PUT -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/global/user-products/{siteless_user_product_id}
```

``` language-javascript
curl -X PUT -H 'https://api.mercadolibre.com/global/user-products/U3687816074' \
--header 'Authorization: Bearer APP_USR-xxxxxxxxxxxxxxxxxxxx' \
--header 'Content-Type: application/json' \
--data '{
  "listing_sites": [
    {
      "listing_id": "MLM4529604428",
      "price": 55.50
    }
  ]
}'
```

Response: 200 OK

``` language-javascript
{
  "id": "U3685216136",
  "errors": null,
  "listing_sites": [
    {
      "id": "MLM4529604428",
      "success": true,
      "errors": null
    }
  ]
}
```

## Updating images

Updates a User Product (Global). When updating images, the thumbnail
will be recalculated.

Request:

``` language-javascript
curl -X PUT -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/user-products/{siteless_user_product_id}
```

``` language-javascript
{
  "pictures": [
    {
      "id": "790745-CBT77271594694_072024"
    }
  ]
}
```

Response:

``` language-javascript
{
  "id": "U3685216136",
  "success": true,
  "errors": null
}
```

<div class="andes-message andes-message--neutral">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj4KPC9jaXJjbGU+PC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div class="andes-message__title andes-message__title--neutral">

Note:

</div>

<div class="andes-message__text--neutral">

-   To update images, you must send ALL images.
-   To add a new one, send all existing ones plus the new one.
-   To delete one, send all images except the one you want to delete.

</div>

</div>

</div>

## Attribute Operations

#### Add attribute

Request:

``` language-javascript
curl -X PUT 'https://api.mercadolibre.com/global/user-products/U3687816070' \
--header 'Authorization: Bearer $TOKEN' \
--header 'Content-Type: application/json' \
--data '{
  "attributes": [
    {
      "id": "PACKAGE_LENGTH",
      "values": [
        {
          "name": "25 cm"
        }
      ]
    }
  ]
}'
```

Response: 200 OK

``` language-javascript
{
  "id": "U3687816070",
  "success": true,
  "errors": null
}
```

#### Modify attribute

Request:

``` language-javascript
curl -X PUT 'https://api.mercadolibre.com/global/user-products/{siteless_user_product_id}' \
--header 'Authorization: Bearer $TOKEN' \
--header 'Content-Type: application/json' \
--data '{
  "attributes": [
    {
      "id": "PACKAGE_LENGTH",
      "values": [
        {
          "name": "25 cm"
        }
      ]
    },
    {
      "id": "PACKAGE_HEIGHT",
      "values": [
        {
          "name": "12 cm"
        }
      ]
    },
    {
      "id": "PACKAGE_WEIGHT",
      "values": [
        {
          "name": "550 g"
        }
      ]
    },
    {
      "id": "PACKAGE_WIDTH",
      "values": [
        {
          "name": "18 cm"
        }
      ]
    }
  ]
}'
```

Response: 200 OK

``` language-javascript
{
  "id": "U3687816070",
  "success": true,
  "errors": null
}
```

#### Delete attribute

Request:

``` language-javascript
curl -X PUT 'https://api.mercadolibre.com/global/user-products/U3687816070' \
--header 'Authorization: Bearer $TOKEN' \
--header 'Content-Type: application/json' \
--data '{
  "attributes": [
    {
      "id": "PACKAGE_LENGTH",
      "values": null
    }
  ]
}'
```

Response: 200 OK

``` language-javascript
{
  "id": "U3687816070",
  "success": true,
  "errors": null
}
```

## Considerations

-   Once a seller is enabled for User Products (tag
    **"user\_product\_seller"**), new items must be created under this
    model.
-   The **variations** array cannot be sent after enabling User
    Products - it will return an error.

</div>
