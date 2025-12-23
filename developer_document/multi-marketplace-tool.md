<div class="inner-content">

## Multi-marketplace tool

<div class="andes-message andes-message--highlight">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--highlight site-carriers__message-title">

Important:

</div>

<div class="andes-message__text--highlight site-carriers__message-text">

<div>

This API is only available for logistic type remote.

</div>

</div>

</div>

</div>

<div class="details__message">

Introducing our latest tool, designed to simplify the selling experience
of your sellers across different marketplaces. Our tool analyzes the
performance of your seller´s listing on a particular marketplace and
then generates recommendations for publishing the same listing on other
sites where it is not yet listed. This allows you to expand your
exposure and increase your chances of making a sale. Additionally, you
can customize your preferences according to your needs. [See more about
Multi-marketplace
tool](https://global-selling.mercadolibre.com/help/25055).

</div>

## Benefits

-   There is no need to look for products in each marketplace of
    operation. Our system automatically refreshes a list with eligible
    products for you to review.
-   The tool will indicate a suggested price per country based on the
    current listing price, shipping fee, and selling fee.
-   You'll be able to review where your products are listed, their
    current price, and how many you've sold.
-   Once the listing request is submitted, soon you'll be able to find
    your items in the listings section of the marketplace that you
    chose.
-   The suggested price on the destination sites [will keep your net
    profits](https://global-selling.mercadolibre.com/help/27264).

  

## Restrictions for suggesting item

-   Reputation is orange or red.
-   Items exceed the price allowed on the destination site.
-   Items belong to a category not allowed on this site.

  
![](https://http2.mlstatic.com/storage/developers-site-cms-admin/220355584608-Captura-de-Tela-2023-06-14-a-s-11.06.11.png)  

## Get suggestions

Get suggestions from a seller previously analyzed by Mercado Libre.
Learn more about [how do we calculate the net price of your
top-performing items on other
sites](https://global-selling.mercadolibre.com/help/27279).

  

## Optional parameters

-   **origin**: site\_id from which the suggestion is generated. one or
    all the following values, separated by comma (,): MLM (México), MLB
    (Brazil), MLC (Chile), MCO (Colombia).
-   **destination**: site\_id where you want to publish the item. One or
    all the following values, separated by comma (,): MLM (México), MLB
    (Brazil), MLC (Chile), MCO (Colombia).
-   **limit**: Maximum number of results per request. Accepts greater
    than or equal to 25.
-   **offset**: Change the lower limit of the results block. For
    example, if you are interested in recovering the 50 elements that
    follow the predetermined response.

Request:

``` language-javascript
curl -H 'Authorization: Bearer $ACCESS_TOKEN' -X GET https://api.mercadolibre.com/multi-marketplace-tool/suggestions?origin=$SITE_ID&destination=$SITE_ID&limit=LIMIT&offset=OFFSET
```

Example:  
Basic request

``` language-javascript
curl -H 'Authorization: Bearer $ACCESS_TOKEN' -X GET https://api.mercadolibre.com/multi-marketplace-tool/suggestions
```

Full filters request:

``` language-javascript
curl -H 'Authorization: Bearer $ACCESS_TOKEN' -X GET https://api.mercadolibre.com/multi-marketplace-tool/suggestions?origin=MLM,MLB,MLC&destination=MLM,MLB,MLC&limit=25&offset=0
```

Response:

``` language-javascript
[
  {
    "id": "CBT1534535475",
    "title": "Test item Do Not Buy It, Virtual Assistants Charcoal",
    "suggestions": [
      {
      
        "site_id": "MCO",
        "price": 11.00,
        "logistic_type": "remote"
      },
      {
       
        "site_id": "MLC",
        "price": 12.00,
        "logistic": "remote"
      }
    ],
  },
  {
    "id": "CBT324526635",
    "title": "Test item awesome green dress",
    "suggestions": [
      {
        "site_id": "MLB",
        "price": 14.00,
        "logistic": "remote"
      },
      {
        "site_id": "MLM",
        "price": 12.00,
        "logistic": "remote"
      }
    ],
  }
]
```

### Response fields

For each item in the response list:

-   **ID**: global item id.
-   **Title**: global item title.
-   **Suggestions**: active suggestions based on which new marketplace
    items associated with a CBT item can be created.

For each suggestion in the list of suggestions:

-   **suggestions.site\_id**: suggested site to publish the new item.
-   **suggestions.price**: suggested price in dollars. On the
    destination sites will keep your net profits. You can change it if
    you want.
-   **suggestions.logistic\_type**: logistics of the item to be
    published. You cannot change it.

## Create suggested items

From the publication suggestions, massively execute your publications
taking the received suggestions. Unlike the [API to publish marketplace
items](https://global-selling.mercadolibre.com/devsite/marketplace-items#Marketplace-items),
with the following endpoint you can only publish from active
suggestions, this resource return and processID, it will be used to get
status of publish process. This request is exactly the same as from get
suggestions resource, you can send a complete get suggestions response
as body, including the title it will be ignored.

  

Example:

``` language-javascript
curl -H 'Authorization: Bearer $ACCESS_TOKEN' -X POST https://api.mercadolibre.com/multi-marketplace-tool/suggestions
[
    {
      "id": "CBT1534535475",
      "suggestions": [
        {
          "site_id": "MCO",
          "price": 11.00,
          "logistic_type": "remote"
        },
        {
          "site_id": "MLC",
          "price": 12.00,
          "logistic_type": "remote"
        }
      ]
    },
    {
      "id": "CBT14741241",
      "suggestions": [
        {
          "site_id": "MLC",
          "price": 14.00,
          "logistic_type": "remote"
        },
        {
          "site_id": "MLC",
          "price": 15.00,
          "logistic_type": "remote"
        }
      ]
    }
  ]
```

Response:

``` language-javascript
{
    "id":"112ebe6d-13cc-496a-a22b-e28607aff1d8"
  }
```

Next, you can know more details about the status of the process.

  

## Errors

<table class="andes-table">
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead class="andes-table__head">
<tr class="header andes-table__row">
<th class="andes-table__header andes-table__header--left">Http code</th>
<th class="andes-table__header andes-table__header--left">Error</th>
<th class="andes-table__header andes-table__header--left">Message</th>
<th class="andes-table__header andes-table__header--left">Description</th>
</tr>
</thead>
<tbody class="andes-table__body">
<tr class="odd andes-table__row">
<th></th>
<th></th>
<th></th>
<th></th>
</tr>

<tr class="odd andes-table__row">
<td class="andes-table__column andes-table__column--left">400</td>
<td class="andes-table__column andes-table__column--left">ID</td>
<td class="andes-table__column andes-table__column--left">xlaunch config ids [Global item id] not found</td>
<td class="andes-table__column andes-table__column--left">The global item id is not available for multi-marketplace tools.</td>
</tr>
<tr class="even andes-table__row">
<td class="andes-table__column andes-table__column--left">400</td>
<td class="andes-table__column andes-table__column--left">suggestions.site_id<br />
suggestions.logistic</td>
<td class="andes-table__column andes-table__column--left">there is not active suggestions for [Global item id]</td>
<td class="andes-table__column andes-table__column--left">The suggestions data includes site or logistic where there is not an active suggestion.</td>
</tr>
<tr class="odd andes-table__row">
<td class="andes-table__column andes-table__column--left">400</td>
<td class="andes-table__column andes-table__column--left">array body</td>
<td class="andes-table__column andes-table__column--left">global items quantity exceed max allowed per request</td>
<td class="andes-table__column andes-table__column--left">The global items with active suggestions exceed max allowed, max allow may vary, refer to the documentation.</td>
</tr>
<tr class="even andes-table__row">
<td class="andes-table__column andes-table__column--left">400</td>
<td class="andes-table__column andes-table__column--left">array body<br />
suggestions.price<br />
suggestions.site_id<br />
suggestions.logistic<br />
</td>
<td class="andes-table__column andes-table__column--left">check request body for [Global item ID]</td>
<td class="andes-table__column andes-table__column--left">Some suggestions present in the request do not have a valid price or a valid site id or a valid logistic type.</td>
</tr>
<tr class="odd andes-table__row">
<td class="andes-table__column andes-table__column--left">400</td>
<td class="andes-table__column andes-table__column--left">array body</td>
<td class="andes-table__column andes-table__column--left">request is empty</td>
<td class="andes-table__column andes-table__column--left">Request body must have valid suggestion elements.</td>
</tr>
</tbody>
</table>

  

## Listing process status

You will get as a response the publication processes in progress and the
information available on the publication processes is temporary, it will
be available only for 7 days.

  

Request:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/multi-marketplace-tool/suggestions/status/
```

Response:

``` language-javascript
{
  "processes": [
    {
      "id": "50da0d6a-8687-4964-be6d-9f97dd1839c0",
      "status": "in_progress",
      "process_date": "2003-04-17T12:33:37.294287-05:00"
    },
    {
      "id": "db4338bb-3859-497d-a447-2dde5c5b51f7",
      "status": "done",
      "process_date": "1981-04-20T12:33:37.294287-05:00"
    }
  ]
}
```

### Response fields

-   **processes.id**: identifier of a specific process, after one
    request of marketplace items creation you received this id.
-   **processes.status**: the status of the one specific process, if at
    least one marketplace creation is in status "in\_progress" the
    process will have set status as "in\_progress"
-   **processes.process\_date**: the date when the process was launched.

## Error

| Http code | Error   | Message                                   | Description                                   |
|-----------|---------|-------------------------------------------|-----------------------------------------------|
|           |         |                                           |                                               |
| 404       | process | there are no publishing processes running | The user has not publishing processes running |

  

## Listing process status detail

You will get as a response the publication processes in progress for a
specific process id.

  

Request:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/multi-marketplace-tool/suggestions/status/{processID}
```

Response:

``` language-javascript
{
     "id": "112ebe6d-13cc-496a-a22b-e28607aff1d8",
     "status": "done",
     "process_date": "2023-04-20T18:28:16.274864607-04:00",
     "global_items": [
          {
               "id": "CBT1598143049",
               "marketplace_items": [
                    {
                         "item_id": "MLC239845623",
                         "site_id": "MLC",
                         "logistic_type": "remote",
                         "status": "successful",
                         "price": 666
                    }
               ]
          }
     ]
}
```

### Response fields

-   **id**: identifier of a specific process, after one request of
    marketplace items creation you received this id.
-   **status**: the status of the one specific process, if at least one
    marketplace creation is in status "in\_progress" the process will
    have set status as "in\_progress".
-   **process\_date**: the date when the process was launched.
-   **global\_items**: array that contains data about global items with
    marketplace items being created.
-   **global\_items.id**: global item identifier.
-   **global\_items.marketplace\_items**: array that contains data about
    marketplace items that are being created.
-   **global\_items.marketplace\_items.item\_id**: Item id of new
    marketplace item after a successful creation, if creation was not
    possible will be not present in the response.
-   **global\_items.marketplace\_items.site\_id**: local site where
    marketplace item is being created.
-   **global\_items.marketplace\_items.status** creation status, the
    possible values are:

<!-- -->

-   in\_progress the creation is running.
-   successful when the marketplace creation finishes ok.
-   error when marketplace creation was not possible.

  

**global\_items.marketplace\_items.price**: the price with marketplace
item was created, if cretation finishes in error this field will not be
present.

**global\_items.marketplace\_items.reasons**: Is an Array that contains
reasons (strings) because marketplace items cannot be created, if the
creation ends successful this field will not be present in the response.

### Error

| Http code | Error   | Message                                   | Description                                   |
|-----------|---------|-------------------------------------------|-----------------------------------------------|
|           |         |                                           |                                               |
| 404       | process | there are no publishing processes running | The user has not publishing processes running |

  

## Automatic listing

Know the current configuration of the automatic listing process. If you
want, you can activate and deactivate it.

  

Request:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/multi-marketplace-tool/config/automatic
```

Response:

``` language-javascript
[
    {
        "site_id": "MLM",
        "logistic_type": "remote",
        "enabled": true
    },
    {
        "site_id": "MLC",
        "logistic_type": "remote",
        "enabled": true
    },
    {
        "site_id": "MLB",
        "logistic_type": "remote",
        "enabled": true
    },
    {
        "site_id": "MCO",
        "logistic_type": "remote",
        "enabled": false
    },
    {
        "site_id": "MLA",
        "logistic_type": "remote",
        "enabled": true
    }
]
```

### Response fields

-   **site\_id**: marketplace site.
-   **logistic\_type**: logistics that applies the configuration.
-   **enabled**: indicates whether the automatic listing is active or
    not.

**Note:** The sites returned depend on the marketplaces enabled for each
seller.

  

## Activate and deactivate automatic multi-marketplace tool

If you want, [you can activate it in Global
Selling](https://global-selling.mercadolibre.com/listings/multi-marketplace-tool/settings).

  

**Important:** You must send all sites in the request body. Any site not
included will keep its current configuration.

  

Request:

``` language-javascript
curl -X PUT -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/multi-marketplace-tool/config/automatic/
[
    {
        "site_id": "MLM",
        "logistic_type": "remote",
        "enabled": true
    },
    {
        "site_id": "MLC",
        "logistic_type": "remote",
        "enabled": true
    },
    {
        "site_id": "MLB",
        "logistic_type": "remote",
        "enabled": true
    },
    {
        "site_id": "MCO",
        "logistic_type": "remote",
        "enabled": true  // updated
    },
    {
        "site_id": "MLA",
        "logistic_type": "remote",
        "enabled": false  // updated
    }
]
```

### Error

| Http code | Error   | Message                   | Description                             |
|-----------|---------|---------------------------|-----------------------------------------|
|           |         |                           |                                         |
| 400       | site.id | \[Site id\] is not active | The site id is not active for this user |

  

## Validate unrealized suggestions

You will know the different reasons why a suggestion could not be
carried out. In this way, you know the reason why an item cannot be
published in multi-marketplaces, for example by rules of origin or
destination.

  

Request:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/multi-marketplace-tool/suggestions/validate
```

Response:

``` language-javascript
[
  {
    "id": "CBT1534535475",
    "title": "Test item Do Not Buy It, Virtual Assistants Charcoal",
    "to_validate": [
      {
        "site_id": "MCO",
        "logistic_type": "remote",
        "reasons": [
          "Listing cap no valid.",
          "Listing category not valid"
        ]
      },
      {
        "site_id": "MLC",
        "logistic_type": "remote",
        "reasons": [
          "Listing cap no valid."
        ]
      }
    ]
  },
  {
    "id": "CBT324526635",
    "title": "Test item awesome green dress",
    "to_validate": [
      {
        "site_id": "MLB",
        "logistic_type": "remote",
        "reasons": [
          "Listing price not valid"
        ]
      },
      {
        "site_id": "MLM",
        "logistic_type": "remote",
        "reasons": [
          "Listing price not valid"
        ]
      }
    ]
  }
]
```

### Response fields

-   **id**: global item ID.
-   **title**: global item title.
-   **to\_validate**: array with report of unrealized suggestions on
    different marketplace items.
-   **to\_validate.reasons**: reasons why the rules of origin,
    destination or price validation have not been overcome.
-   **to\_validate.site\_id**: site\_id where the rules of origin,
    destination or validation are not overcome.
-   **to\_validate.logistic\_type**: logistics where validation rules
    are not approved.

  

</div>
