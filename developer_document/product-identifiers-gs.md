<div class="inner-content">

## Product identifiers

<div class="details__message">

Identifiers are codes used to unequivocally locate a product. For
example, GTIN is mandatory in the listing for all their variations.
Learn more about how to [identify the product universal
code](https://www.mercadolibre.com.ar/ayuda/Codigo_univer_sal_de_producto_3429).

</div>

## GTIN and identifiers types

GTIN (Global Trade Item Number) is the global trade item number used to
unequivocally identify any product or item about which there is a need
to both retrieve specific information and put a price to. The GTIN will
save all the PIs in this field, concatenating values. This is a standard
that includes EAN, UPC, JAN, GTIN14, ISBN, ISBN10 and ISBN13 codes.  
Currently, the attribute has the tag `new_required` and indicates that
it is mandatory if the publication has a new condition.

**GTIN types by region:**

-   **UPC** (North America / GTIN-12): 12-digit number. 8-digit UPC-E
    codes must be converted to 12-digit UPC-A.
-   **EAN** (Europe / GTIN-13): 13-digit number.
-   **JAN** (Japan / GTIN-13): 8 or 13 digit number.
-   **ISBN** (books): 13-digit number. ISBN-10 values must be converted
    to ISBN-13.
-   **ITF-14** (multi-packs / GTIN-14): 14-digit number.
-   **Part Number**: Codes used to unequivocally locate an automotive
    spare part by defining the spare part compatibilities.

  

## Logic for using the GTIN attribute

When the category has the GTIN attribute, check the applicable tags:

-   If it has the `required` tag, you must complete it at all times.
-   If it has the `conditional_required` tag, prioritize using GTIN, but
    if unavailable, you can use `EMPTY_GTIN_REASON` (see section below).
-   If it has the `new_required` tag, it's mandatory only for items in
    "new" condition.

<div class="andes-message andes-message--neutral">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div class="andes-message__title andes-message__title--neutral">

Tip:

</div>

<div class="andes-message__text--neutral">

<div>

Always check `/categories/$CATEGORY_ID/attributes` to identify the
applicable tags for GTIN in your category before publishing.

</div>

</div>

</div>

</div>

  

## Send product identifier information

You can send this information just like you post attributes, regardless
of the category.

<div class="andes-message andes-message--neutral">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div class="andes-message__title andes-message__title--neutral">

Note:

</div>

<div class="andes-message__text--neutral">

<div>

For some categories, the `GTIN` attribute is mandatory, and it is
recognized with the `"conditional_required": true` label which is
specified in the call to `/categories/$CATEGORY_ID/attributes`.  
  
It is important to clarify that, if the item the seller is trying to
publish **belongs to a brand that already has at least 30 GTINs
published**, the attribute changes from **not required status to
required**.  
  
In case it is not sent in the call to /items/ and it is required for the
brand, [it will be
validated](https://global-selling.mercadolibre.com/devsite/validations-cbt#:~:text=the%20validation%20caused.-,Detail,-You%20will%20find)
by sending message 7810 with code:
`item.attribute.missing_conditional_required`, thus requesting the
loading of the attribute.

</div>

</div>

</div>

</div>

Example of item without variations:

``` language-javascript
curl -X POST -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/global/items
  -d '{
    "sites_to_sell": [
        {
            "site_id": "MLM",
            "logistic_type": "remote"
        },
        {
            "site_id": "MLA",
            "logistic_type": "remote"
        }
    ],
    "title": "Test Items Stainless Steel Water Jug with variations",
    "category_id": "CBT74531",
    "price": 65.99,
    "available_quantity": 99,
    "description": {
        "plain_text": "Introducing the Test Items Stainless Steel Water Jug..."
    },
    "pictures": [
        {"id": "701198-CBT79185512197_092024"},
        {"id": "802215-CBT79185512155_092024"}
    ],
    "attributes": [
        {"id": "BRAND", "name": "Brand", "value_id": "35486409", "value_name": "Other"},
        {"id": "MODEL", "value_id": null, "value_name": "cántara", "name": "Model"},
        {"id": "ITEM_CONDITION", "value_id": "2230284", "name": "Item condition", "value_name": "New"},
        {"id": "GTIN", "name": "Universal product code", "value_id": null, "value_name": "764486313435"},
        {"id": "PACKAGE_HEIGHT", "name": "Package height", "value_id": null, "value_name": "12.29 cm"},
        {"id": "PACKAGE_LENGTH", "name": "Package length", "value_id": null, "value_name": "28.9 cm"},
        {"id": "PACKAGE_WEIGHT", "name": "Package weight", "value_id": null, "value_name": "381.01 g"},
        {"id": "PACKAGE_WIDTH", "name": "Package width", "value_id": null, "value_name": "18.48 cm"},
        {"id": "SELLER_SKU", "name": "SKU", "value_id": null, "value_name": "70079449"}
    ],
    "condition": "new",
    "listing_type_id": "gold_pro",
    "sale_terms": [
        {"id": "WARRANTY_TYPE", "name": "Warranty type", "value_id": "6150835", "value_name": "No warranty"}
    ]
}'
```

Response example of item without variations:

``` language-javascript
{
    "item_id": "CBT2300912600",
    "seller_id": 2227281946,
    "site_id": "CBT",
    "site_items": [
        {
            "item_id": "MLM2246336099",
            "seller_id": 2227281948,
            "site_id": "MLM",
            "logistic_type": "remote"
        },
        {
            "item_id": "MLA2021589026",
            "seller_id": 2227795872,
            "site_id": "MLA",
            "logistic_type": "remote"
        }
    ]
}
```

Example of item with variations:

``` language-javascript
curl -X POST -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/global/items
  -d '{
    "sites_to_sell": [
        {"site_id": "MLM", "logistic_type": "remote"},
        {"site_id": "MLA", "logistic_type": "remote"}
    ],
    "title": "Test Items Stainless Steel Water Jug with variations",
    "category_id": "CBT74531",
    "price": 25.95,
    "description": {
        "plain_text": "Introducing the Test Items Stainless Steel Water Jug..."
    },
    "pictures": [
        {"id": "701198-CBT79185512197_092024"},
        {"id": "706052-CBT79185512181_092024"}
    ],
    "attributes": [
        {"id": "BRAND", "name": "Brand", "value_id": "35486409", "value_name": "Other"},
        {"id": "MODEL", "value_id": null, "value_name": "cántara", "name": "Model"},
        {"id": "ITEM_CONDITION", "value_id": "2230284", "name": "Item condition", "value_name": "New"}
    ],
    "variations": [
        {
            "attribute_combinations": [
                {"id": "COLOR", "name": "Color", "value_id": "283165", "value_name": "Gray"}
            ],
            "available_quantity": 36,
            "price": 25.95,
            "picture_ids": ["701198-CBT79185512197_092024"],
            "attributes": [
                {"id": "PACKAGE_HEIGHT", "name": "Package height", "value_name": "12.29 cm"},
                {"id": "PACKAGE_LENGTH", "name": "Package length", "value_name": "28.9 cm"},
                {"id": "PACKAGE_WEIGHT", "name": "Package weight", "value_name": "381.01 g"},
                {"id": "PACKAGE_WIDTH", "name": "Package width", "value_name": "18.48 cm"},
                {"id": "SELLER_SKU", "name": "SKU", "value_name": "70079449"},
                {"id": "GTIN", "name": "Universal product code", "value_name": "764486313435"}
            ]
        },
        {
            "attribute_combinations": [
                {"id": "COLOR", "name": "Color", "value_id": "51994", "value_name": "Pink"}
            ],
            "available_quantity": 13,
            "price": 25.95,
            "picture_ids": ["706052-CBT79185512181_092024"],
            "attributes": [
                {"id": "PACKAGE_HEIGHT", "name": "Package height", "value_name": "11.01 cm"},
                {"id": "PACKAGE_LENGTH", "name": "Package length", "value_name": "29.01 cm"},
                {"id": "PACKAGE_WEIGHT", "name": "Package weight", "value_name": "377.01 g"},
                {"id": "PACKAGE_WIDTH", "name": "Package width", "value_name": "17.01 cm"},
                {"id": "SELLER_SKU", "name": "SKU", "value_name": "70079450"},
                {"id": "GTIN", "name": "Universal product code", "value_name": "764486313466"}
            ]
        }
    ],
    "condition": "new",
    "listing_type_id": "gold_pro",
    "sale_terms": [
        {"id": "WARRANTY_TYPE", "name": "Warranty type", "value_id": "6150835", "value_name": "No warranty"}
    ]
}'
```

Response example of item with variations:

``` language-javascript
{
    "item_id": "CBT2300963366",
    "seller_id": 2227281946,
    "site_id": "CBT",
    "site_items": [
        {
            "item_id": "MLM3576532224",
            "seller_id": 2227281948,
            "site_id": "MLM",
            "logistic_type": "remote"
        },
        {
            "item_id": "MLA2021576308",
            "seller_id": 2227795872,
            "site_id": "MLA",
            "logistic_type": "remote"
        }
    ]
}
```

## Add information to an existing item

### Example of item variation:

Adding the GTIN attribute with the corresponding product code.  
**No variations**

``` language-javascript
curl -X PUT -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/items/CBT2300912600
  -d '{
    "attributes": [
        {
            "id": "GTIN",
            "value_name": "7898937064478"
        }
    ]
}'
```

**Response 200 OK**  

**With variations**  

In the same way that any attribute in a variation is added or modified,
to add or modify them you must indicate the list of variations that you
want to remain in the item (indicating its variation ID), and add the
list of attributes that you want to remain in each of the variations.

``` language-javascript
curl -X PUT -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/items/CBT2300963366
  -d '{
    "variations": [
        {
            "id": 183007318470,
            "attributes": [
                {
                    "id": "GTIN",
                    "value_name": "4004133109216"
                }
            ]
        },
        {
            "id": 183007318472,
            "attributes": [
                {
                    "id": "GTIN",
                    "value_name": "2800001053351"
                }
            ]
        }
    ]
}'
```

**Response 200 OK**  

<div class="andes-message andes-message--highlight">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div class="andes-message__title andes-message__title--highlight">

Important:

</div>

<div class="andes-message__text--highlight">

<div>

If the item has the GTIN attribute at item level, you cannot specify it
again at variation level. In this case, you must remove it from item
level first and then specify it at variation level.  
  
The `variation ID` must be a valid numeric ID obtained from the item's
current variations. Do not leave this field empty or the request will
fail with a JSON parsing error.

</div>

</div>

</div>

</div>

### Removing GTIN from item level

If the item already has the GTIN attribute at item level and you need to
move it to variation level, first delete it by setting `value_name` to
`null`:

``` language-javascript
curl -X PUT -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/items/CBT2300912600
  -d '{
    "attributes": [
        {
            "id": "GTIN",
            "value_name": null
        }
    ]
}'
```

**Response 200 OK**

After removing the GTIN from item level, you can then specify it at
variation level as shown in the examples above.

  

## Query information about product identifiers

To get this information, you should make a GET to the API:  
Request:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/items/$ITEM_ID?include_attributes=all
```

Example:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/items/CBT945341307?include_attributes=all
```

Response:

``` language-javascript
{
   "id": "CBT945341307",
   "site_id": "CBT",
   "title": "Test Item With Gtin Code And Variations",
   "seller_id": 567809758,
   "category_id": "CBT1645",
   "price": 30.11,
   "currency_id": "USD",
   "available_quantity": 2,
   "condition": "new",
   "attributes": [
      {"id": "BRAND", "name": "Brand", "value_name": "Durabrand"},
      {"id": "MODEL", "name": "Model", "value_name": "HSD"},
      {"id": "PACKAGE_HEIGHT", "name": "Package height", "value_name": "100 cm"},
      {"id": "PACKAGE_LENGTH", "name": "Package length", "value_name": "10 cm"},
      {"id": "PACKAGE_WEIGHT", "name": "Package weight", "value_name": "1.7 lb"},
      {"id": "PACKAGE_WIDTH", "name": "Package width", "value_name": "100 cm"}
   ],
   "variations": [
      {
         "id": 61382392580,
         "price": 30.11,
         "attribute_combinations": [
            {"id": "STRUCTURE_COLOR", "name": "Structure color", "value_name": "Brown"}
         ],
         "available_quantity": 1,
         "attributes": [
            {"id": "GTIN", "name": "Universal product code", "value_name": "4006381333931"}
         ]
      },
      {
         "id": 61382392584,
         "price": 30.11,
         "attribute_combinations": [
            {"id": "STRUCTURE_COLOR", "name": "Structure color", "value_name": "Black"}
         ],
         "available_quantity": 1,
         "attributes": [
            {"id": "GTIN", "name": "Universal product code", "value_name": "7015057271221"}
         ]
      }
   ],
   "status": "active",
   "warranty": "Factory warranty: 90 days"
}
```

  

## GTIN validations

The API performs the following validations on GTIN values before
accepting them:

| Validation           | Description                                   | Behavior                                           |
|----------------------|-----------------------------------------------|----------------------------------------------------|
| **Format**           | Must contain only numeric characters          | Rejected if contains letters or special characters |
| **Length**           | Must have exactly 8, 10, 12, 13, or 14 digits | Rejected if length is invalid                      |
| **Checksum**         | Must pass the GS1 check digit algorithm       | Rejected if checksum is invalid                    |
| **Invalid patterns** | Cannot be all zeros or reserved patterns      | Rejected with error 7710                           |

  

**Valid GTIN examples:**

-   EAN-13: `7891234567895`
-   GTIN-14: `10614141000415`
-   EAN-8: `96385074`

**Invalid GTIN examples:**

-   `INVALID_ABC123` → Contains letters
-   `0000000000000` → All zeros
-   `123` → Too short

<div class="andes-message andes-message--neutral">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div class="andes-message__title andes-message__title--neutral">

Tip:

</div>

<div class="andes-message__text--neutral">

<div>

When testing, use real product codes or generate valid test GTINs using
a [GS1 check digit
calculator](https://www.gs1.org/services/check-digit-calculator).

</div>

</div>

</div>

</div>

  

## Reasons for not sending GTIN

In some categories the GTIN attribute is marked as
`conditional_required`. If you cannot send it, you can add the reason
using the `EMPTY_GTIN_REASON` attribute.

To use the `EMPTY_GTIN_REASON` attribute, it is important to follow the
established rules. You can check the allowed values by calling
`/categories/$CATEGORY_ID/attributes`.

**Allowed values:**

-   **Artisanal**: The item is a craft, handmade, or self-made product.
-   **Kit**: The item is a set of items or a kit.
-   **Not registered**: The item is not yet registered with a GTIN.
-   **Other**: Another reason (different from Artisanal, Kit, and Not
    registered) prevents loading the GTIN attribute.

<div class="andes-message andes-message--highlight">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div class="andes-message__title andes-message__title--highlight">

Important:

</div>

<div class="andes-message__text--highlight">

<div>

The `EMPTY_GTIN_REASON` attribute is conditionally required
(`conditional_required: true`) and **will only be allowed** in cases
where no GTIN is loaded for brands in specific domains. **Always
prioritize sending the GTIN** when available.

</div>

</div>

</div>

</div>

**Example request with EMPTY\_GTIN\_REASON:**

``` language-javascript
curl -X POST -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/global/items
  -d '{
    "sites_to_sell": [
        {"site_id": "MLM", "logistic_type": "remote"}
    ],
    "title": "Handmade Artisan Bracelet",
    "category_id": "CBT12345",
    "price": 15.99,
    "available_quantity": 10,
    "attributes": [
        {"id": "BRAND", "name": "Brand", "value_name": "Handmade"},
        {"id": "ITEM_CONDITION", "value_id": "2230284", "value_name": "New"},
        {"id": "EMPTY_GTIN_REASON", "value_name": "Artisanal"}
    ],
    "condition": "new",
    "listing_type_id": "gold_pro"
}'
```

**Validation error when EMPTY\_GTIN\_REASON is required but missing:**

``` language-javascript
{
    "message": "Validation error",
    "error": "validation_error",
    "status": 400,
    "cause": [
        {
            "department": "supply",
            "cause_id": 7810,
            "type": "error",
            "code": "item.attribute.missing_conditional_required",
            "references": ["item.attributes"],
            "message": "The attributes [EMPTY_GTIN_REASON] are required for category [CBT12345]. Check the attribute is present in the attributes list or in all variation's attributes_combination or attributes."
        }
    ]
}
```

  

## Considerations

<div class="andes-message andes-message--highlight">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div class="andes-message__title andes-message__title--highlight">

Important:

</div>

<div class="andes-message__text--highlight">

<div>

Items published without a properly loaded GTIN may be
**moderated/paused**. To view and manage these moderations, use the
[moderations management
resource](https://global-selling.mercadolibre.com/devsite/moderations-gs).

</div>

</div>

</div>

</div>

-   They are not internal SKUs. Use the `SELLER_SKU` attribute for your
    internal product codes.
-   You can send more than one identifier code for the same listing. In
    that case, send all identifiers in the GTIN attribute **separated by
    comma**. The GTIN will save all the PIs in this field, concatenating
    values.
-   Check if the attribute has the tag `new_required` and the condition
    of the item is new, since the attribute is mandatory to publish.
-   The number of characters varies by code type: they can have 8, 10,
    12, 13 or 14 characters. You can even rewrite the same code with
    left zero padding and it will still be valid.
-   GTINs sent are validated against the **GS1 checksum algorithm**.
    Invalid checksums will be rejected even if the format appears
    correct.
-   It is advisable to include the Brand and, at least, one additional
    identifier. These are the conditions required to participate in
    third-party product listings, such as Google Shopping.
-   For categories where the `MODEL` attribute has the
    `catalog_required` tag, you must include it in the request. Check
    `/categories/{category_id}/attributes` to identify required fields.
-   When publishing to multiple sites using `sites_to_sell`, ensure your
    user account is configured for each site and logistic type
    combination.
-   Remember to check `/categories/$CATEGORY_ID/attributes` to verify if
    attributes are marked with: `required` (always mandatory),
    `new_required` (mandatory if item is new), or `conditional_required`
    (mandatory under certain conditions).

  

## Message code reference

| Error\_code | Error type | Error message                                                                                    | Description                                                                           | Possible solution                                                                                                                 |
|-------------|------------|--------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------|
| **7710**    | ERROR      | Product Identifier \[GTIN\] has invalid values: \[00000000\]                                     | The Product Identifier inserted isn't valid.                                          | Introduce a valid Product Identifier. Use real GTINs or generate valid test codes with proper checksums.                          |
| **7711**    | WARNING    | Product Identifier \[GTIN\] has invalid format values: \[abc12345\]                              | The Product Identifier inserted isn't valid.                                          | Introduce a valid Product Identifier using only numeric characters with correct length (8, 10, 12, 13, or 14 digits).             |
| **3704**    | WARNING    | The "{attribute}" field is mandatory and was not added.                                          | A required catalog attribute is missing from the request.                             | Add the required attribute specified in the message. Check `/categories/{category_id}/attributes` for required fields like MODEL. |
| **5119**    | ERROR      | Current user {user\_id} is not configured to list in site {site} using {logistic\_type} logistic | The user account is not enabled for the specified site and logistic type combination. | Contact support to enable your account for the desired site and logistic type combination.                                        |
| **7810**    | ERROR      | The attributes \[GTIN\] are required for category \[category\_id\]                               | A conditionally required attribute (GTIN or EMPTY\_GTIN\_REASON) is missing.          | Add the GTIN attribute with a valid code, or if unavailable, add EMPTY\_GTIN\_REASON with a valid reason.                         |

  

## Resource identifier description

**BRAND:** Brand name of the product.  
**MPN:** Manufacturer Part Number.  
**GTIN:** Global Trade Item Number (includes EAN, UPC, JAN, ISBN
codes).  

  

## Part Number

<div class="details__message">

The codes used to unequivocally locate an automotive spare part by
defining the spare part compatibilities, among others, are referred to
as Part Numbers. Based on a specific part number we can learn the car
for which it is used.

</div>

  

**Next**:
[Variations](https://global-selling.mercadolibre.com/devsite/variations-global-selling).

</div>
