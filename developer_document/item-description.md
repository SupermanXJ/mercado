<div class="inner-content">

## Item description

<div class="details__message">

The item description has information about the product and serves to
complement what is detailed in the datasheet. It should include the
technical characteristics and the differentiators against competition.
Remember that this will allow the buyer to quickly find all the
specifications that characterize the products. See more why [Datasheet
is the best way to
sell](https://sellers.mercadolibre.com/news/datasheets-the-best-way-to-show-what-you-sell/)
or [more about
Datasheets](https://sellers.mercadolibre.com/tag/datasheets/).

</div>

## Tips for describing a post

-   First load the important data in the data sheet, that is to say all
    the specifications without forgetting the universal product code.
-   Verify that the data that you are going to write in the description
    are the details that are not in the data sheet.
-   Nests the information so that it is well organized. Use uppercase,
    hyphens, spacing, etc.
-   Be brief and read your own description to check its length.

## Get item description

Retrieves the description of a global selling item for a specific site
and logistic type.

### Parameters

| Parameter       | Type   | Required | Description                                                |
|:----------------|:-------|:---------|:-----------------------------------------------------------|
| `site_id`       | String | Yes      | The target marketplace site ID (e.g., `MLM`, `MLA`, `MLB`) |
| `logistic_type` | String | Yes      | The logistic type. Use `remote` for cross-border items     |

Request:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/marketplace/items/$ITEM_ID/description?site_id=$SITE_ID&logistic_type=$LOGISTIC_TYPE
```

Example:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/marketplace/items/CBT123456/description?site_id=MLM&logistic_type=remote
```

Response:

``` language-javascript
{
  "text": "",
  "plain_text": "Esta descripción está en su idioma local",
  "translated_plain_text": "This description is in your local language",
  "last_updated": "2021-12-10T14:48:05Z",
  "date_created": "2021-04-08T16:29:47Z"
}
```

### Response fields

| Field                   | Description                                             |
|:------------------------|:--------------------------------------------------------|
| `text`                  | Description text (legacy field, may be empty)           |
| `plain_text`            | Description text in local language                      |
| `translated_plain_text` | Description text translated to the target site language |
| `last_updated`          | Date and time of the last description update            |
| `date_created`          | Date and time when the description was created          |

### Errors

| Status | Error         | Message                                      | Solution                                                             |
|:-------|:--------------|:---------------------------------------------|:---------------------------------------------------------------------|
| 400    | `Bad Request` | Invalid or empty site\_id                    | Provide a valid `site_id` parameter                                  |
| 400    | `Bad Request` | Invalid or empty logistic\_type              | Provide a valid `logistic_type` parameter                            |
| 400    | `bad_request` | Invalid or empty parent item id              | Verify the item ID format (e.g., `CBT123456`)                        |
| 400    | `bad_request` | you dont have user in this site and logistic | Verify you have permissions for the specified site and logistic type |
| 403    | `forbidden`   | Invalid caller.id                            | Provide a valid access token in the Authorization header             |
| 404    | `not_found`   | Item with id {id} not found                  | Verify the item ID exists                                            |
| 404    | `not_found`   | Description of item with id {id} not found   | The item exists but has no description yet                           |

<div class="andes-message andes-message--neutral">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div class="andes-message__title andes-message__title--neutral">

Note:

</div>

<div class="andes-message__text--neutral">

The description is translated automatically. Once the item is generated
for new sites, the description must be updated within 2 days
automatically by the site.  
- This is based on our update list, which is why it is not updated
within 2 days.

</div>

</div>

</div>

## Upload item description

Once the global item is created, you can load its description with the
following POST. Remember that they must contain plain text and you will
not be able to change the fonts, sizes or mark texts in bold. You can
only perform line breaks as follows: `\n`.

<div class="andes-message andes-message--highlight">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div class="andes-message__title andes-message__title--highlight">

Important:

</div>

<div class="andes-message__text--highlight">

If the item already has a description, you must use the PUT method to
[replace an existing description](#replacing) instead.

</div>

</div>

</div>

### Parameters (Body)

| Parameter       | Type   | Required | Description                                   |
|:----------------|:-------|:---------|:----------------------------------------------|
| `site_id`       | String | Yes      | The target marketplace site ID                |
| `logistic_type` | String | Yes      | The logistic type (`remote` for cross-border) |
| `plain_text`    | String | Yes      | The description content in plain text         |

Request:

``` language-javascript
curl -X POST -H 'Authorization: Bearer $ACCESS_TOKEN' -H "Content-Type: application/json" -d
{
  "site_id": "$SITE_ID",
  "logistic_type": "$LOGISTIC_TYPE",
  "plain_text": "plain text description \n"
}
https://api.mercadolibre.com/marketplace/items/$ITEM_ID/description
```

Example:

``` language-javascript
curl -X POST -H 'Authorization: Bearer $ACCESS_TOKEN' -H "Content-Type: application/json" -d
{
  "site_id": "MLM",
  "logistic_type": "remote",
  "plain_text": "Product description text.\nNew line here."
}
https://api.mercadolibre.com/marketplace/items/CBT123456/description
```

Response (201 Created):

``` language-javascript
{
  "message": "",
  "error": "Created",
  "status": 201,
  "cause": null
}
```

### Errors

| Status | Error                           | Message                                         | Solution                                                                |
|:-------|:--------------------------------|:------------------------------------------------|:------------------------------------------------------------------------|
| 400    | `item.description.invalid`      | Item already has a description, use PUT instead | Use the PUT method to [update existing descriptions](#replacing)        |
| 400    | `bad_request`                   | you dont have user in this site and logistic    | Verify `site_id` and `logistic_type` are valid and you have permissions |
| 400    | `item.description.type.invalid` | The description must be in plain text           | Remove HTML tags, emojis, or special characters from `plain_text`       |

## Benefits of using plain text

-   They will have better results in searches.
-   Descriptions can be downloaded 5 times faster.
-   They will be properly displayed in all devices (mobile, tablets,
    computer).
-   Besides, you will be able to upload up to 10 item pictures and/or a
    link with a YouTube video.

<div class="andes-message andes-message--neutral">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div class="andes-message__title andes-message__title--neutral">

Note:

</div>

<div class="andes-message__text--neutral">

\- Bear in mind that you can add any payment and shipping method that
you wish to the VIP.  
- If you want your listing to show all item variations, even
differential stock for each of them, we encourage you to [use customized
variations](https://developers.mercadolibre.com.ar/en_us/variations#Customized-variation).

</div>

</div>

</div>

## Replace an existing description

To make modifications to an existing description, use the following PUT
request.

### Parameters (Body)

| Parameter                | Type   | Required | Description                                   |
|:-------------------------|:-------|:---------|:----------------------------------------------|
| `site_id`                | String | Yes      | The target marketplace site ID                |
| `logistic_type`          | String | Yes      | The logistic type (`remote` for cross-border) |
| `description.plain_text` | String | Yes      | The new description content in plain text     |

Request:

``` language-javascript
curl -X PUT -H 'Authorization: Bearer $ACCESS_TOKEN' -H "Content-Type: application/json" -d
{
  "site_id": "$SITE_ID",
  "logistic_type": "$LOGISTIC_TYPE",
  "description": {
    "plain_text": "$PLAIN_TEXT"
  }
}
https://api.mercadolibre.com/global/items/$ITEM_ID
```

Example:

``` language-javascript
curl -X PUT -H 'Authorization: Bearer $ACCESS_TOKEN' -H "Content-Type: application/json" -d
{
  "site_id": "MLM",
  "logistic_type": "remote",
  "description": {
    "plain_text": "Updated description text."
  }
}
https://api.mercadolibre.com/global/items/CBT123456
```

Response (200 OK):

``` language-javascript
{}
```

<div class="andes-message andes-message--neutral">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div class="andes-message__title andes-message__title--neutral">

Note:

</div>

<div class="andes-message__text--neutral">

A successful update returns an empty object `{}`.

</div>

</div>

</div>

### Errors

| Status | Error              | Message                                             | Solution                                                                                             |
|:-------|:-------------------|:----------------------------------------------------|:-----------------------------------------------------------------------------------------------------|
| 400    | `missing_body`     | Required request body is missing. Please try again. | Include a valid JSON body in the request                                                             |
| 400    | `validation_error` | The description must be in plain text               | Remove invalid characters from `plain_text`. Check the `references` field for the character position |
| 404    | `not_found`        | Item with id {id} not found                         | Verify the item ID exists                                                                            |

## Character validation errors

If you POST or PUT a description that contains unacceptable characters
(such as HTML tags or emojis), the response will contain information
about the error, including the position of the invalid character.

Example request with invalid characters:

``` language-javascript
curl -X POST -H 'Authorization: Bearer $ACCESS_TOKEN' -H "Content-Type: application/json" -d
{
  "site_id": "MLM",
  "logistic_type": "remote",
  "plain_text": "Texto < br > "
}
https://api.mercadolibre.com/marketplace/items/$ITEM_ID/description
```

Error response:

``` language-javascript
{
  "message": "Validation error",
  "error": "validation_error",
  "status": 400,
  "cause": [
    {
      "department": "items",
      "cause_id": 398,
      "type": "error",
      "code": "item.description.type.invalid",
      "references": [
        "plain_text[12]"
      ],
      "message": "The description must be in plain text"
    }
  ]
}
```

In the `references` field you can find the exact position of the
character that generates the error. In this example, position 12.

**Next**: [Specific
Regulations](https://global-selling.mercadolibre.com/devsite/specific-regulations).

</div>
