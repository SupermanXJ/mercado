<div class="inner-content">

## Manage Automations

Price automations on MercadoLibre are essential tools for sellers who
want to keep their products competitive and maximize their profit
margins. These tools allow product prices to be adjusted dynamically and
strategically in response to different market variables. Below are the
functionalities available to manage automations.

  

<div class="andes-message andes-message--highlight">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--highlight site-carriers__message-title">

**Important:**

</div>

<div class="andes-message__text--highlight site-carriers__message-text">

<div>

If the listing has price changes made outside of price automation, this
will immediately cause the automation to stop functioning, in order to
avoid inconsistencies and outdated prices.  

</div>

</div>

</div>

</div>

  

## Get Available Rules for an Item

For a specific item, you can retrieve the list of available rules that
can be used for price automation by making a GET request to the resource
**/marketplace/items/{itemId}/prices/automate/rules**.****

  

### Rules

| rule\_id   | Title                                       | Description                                                                                                     |
|------------|---------------------------------------------|-----------------------------------------------------------------------------------------------------------------|
| “INT\_EXT” | Best price inside and outside Mercado Libre | Your price will adjust to the lowest price among similar listings on Mercado Libre and others outside the site. |
| “INT”      | Price to win on Mercado Libre               | Your price will adjust to the lowest price among similar listings on Mercado Libre.                             |

### Preconditions to obtain the available rules for an item

-   It must be queried on an existing item
-   The item must be eligible for automation

**Request:**

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/marketplace/items/$ITEM_ID/prices/automate/rules
```

**Example:**

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/marketplace/items/MLM2245313004/prices/automate/rules
```

**Response:**

``` language-javascript
{
    "item_id": "MLM2245313004",
    "rules": [
        {
            "rule_id": "INT",
            "title": "Price to win on Mercado Libre",
            "description": "Your price will be adjusted by comparing the price and selling conditions of same listings on Mercado Libre and other marketplaces."
        },
        {
            "rule_id": "INT_EXT",
            "title": "Best price on Mercado Libre and off the site",
            "description": "Your price will be adjusted by comparing the price and selling conditions of same listings on Mercado Libre and other marketplaces."
        }
    ]
}
```

### Response fields

The response of a GET to the resource
**/marketplace/items/$ITEM\_ID/prices/automate/rules** will provide the
following parameters:

-   **item\_id**: Item identifier
-   **rules**: List of rules available for an item. Currently it can
    only be **INT\_EXT** and **INT**
    -   **rule\_id**: Automation rule.

  

### Possible errors when obtaining the available rules

When obtaining the available rules for an item, you may encounter the
following errors. It is crucial that you understand the cause of each
one and know how to correct them in order to efficiently manage the
situation. Here is the information you need to identify and resolve
these issues.

  

**Item not found:**

``` language-javascript
{
    "error": "item_not_found",
    "message" : "Item with id [MLA123456] not found",
    "status": 404,
    "cause": []
}
```

**User not authorized:**

``` language-javascript
{
    "error": "user_not_authorized",
    "message": "User is not allowed to automate items",
    "status": 412,
    "cause": []
}
```

**Item cannot be automated:**

``` language-javascript
{
    "error": "item_not_automatizable",
    "message" : "Item with id [MLA123456] has no rules available",
    "status": 412,
    "cause": []
}
```

**The established strategy cannot be processed:**

``` language-javascript
{
    "error": "unprocessable_get_strategies",
    "message" : "Error calling retrieve item strategies service",
    "status": 422,
    "cause": []
}
```

**Unauthorized:**

``` language-javascript
{
    "code": "unauthorized",
    "message": "invalid access token"
}
```

  

## Assign a new price automation

To assign a new price automation, you need to perform a POST request to
the resource **/marketplace/items/$ITEM\_ID/prices/automate**.

<div class="andes-message andes-message--highlight">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--highlight site-carriers__message-title">

**Important:**

</div>

<div class="andes-message__text--highlight site-carriers__message-text">

<div>

**Automations in Publications:**  
By applying automation to your publications, you **increase** the
likelihood that they will stand out. For example, they may receive the
“Recommended” label in search results and the VIP distinction. If your
prices **drop due to an automatic adjustment** , your buyers will see
**discounted prices** , increasing your chances of making a sale.

**Opt-In to Catalog:**  
Similarly, if automation is applied to a traditional item and then the
opt-in to catalog is performed, the automation settings will be
transferred to the catalog item.

</div>

</div>

</div>

</div>

  

### Preconditions to assign an automation

-   The rule must be applied to an existing item
-   It must necessarily have a minimum price
-   Prices cannot be absurd (Maximum and Minimum)
-   It must meet the [creation
    conditions](https://global-selling.mercadolibre.com/devsite/manage-automations#:~:text=automate/rules.-,Rules,-rule_id)

**Request:**

``` language-javascript
curl -X POST -H 'Authorization: Bearer $ACCESS_TOKEN'
{
  "rule_id" : "INT_EXT", 
  "min_price": 100,
  "max_price": 1000
}

https://api.mercadolibre.com/marketplace/items/$ITEM_ID/prices/automate
```

**Example:**

``` language-javascript
curl -X POST -H 'Authorization: Bearer $ACCESS_TOKEN'
{
  "rule_id" : "INT_EXT", 
  "min_price": 100,
  "max_price": 1000
}
https://api.mercadolibre.com/marketplace/items/MLM2245313004/prices/automate
```

**Response:**

``` language-javascript
{
    "status": "ACTIVE",
    "item_id": "MLM2245313004",
    "item_rule": {
        "rule_id": "INT_EXT",
        "title": "Best price on Mercado Libre and off the site",
        "description": "Your price will be adjusted by comparing the price and selling conditions of same listings on Mercado Libre and other marketplaces."
    },
    "min_price": 100,
    "max_price": 1000
}
```

### Response fields

The response of a POST to the resource pricing-automation
**/marketplace/items/$ITEM\_ID/prices/automate** will provide the
following parameters

**item\_id**: Item identifier

**status**: Automation status, possible statuses:

-   ACTIVE
-   PAUSED

**item\_rule**: Automation rule, currently the only rules available are:

**rule\_id**: Automation rule.

**“INT\_EXT”** (Internal and external competition simultaneously).

**“INT”** (Internal competition only; if it is a catalog item, only that
type of listing will be considered).

-   
-   **title:** Name of the selected rule. The only one available is
    “Price to win sales”.
-   
-   **description:** Description of the selected rule.

**min\_price**: Minimum price set for the automation.

**max\_price**: Maximum price set for the automation.

  

### Possible errors when assigning an automation

When assigning a new automation, you may encounter the following errors.
It is crucial that you understand the cause of each one and know how to
correct them in order to efficiently manage the situation. Here is the
information you need to identify and resolve these issues.

  

**Field rule\_id without value:**

``` language-javascript
{
    "error": "argument_not_valid",
    "message": "rule_id must not be null",
    "status": 400,
    "cause": [
        {
            "code": "rule_id_not_null",
            "message": "Rule identifier is required"
        }
    ]
}
```

**Item not found:**

``` language-javascript
{
    "error": "item_not_found",
    "message" : "Item with id [MLA123456] not found",
    "status": 404
}
```

**User not authorized:**

``` language-javascript
{
    "error": "user_not_authorized",
    "message": "User is not allowed to automate items",
    "status": 412
}
```

**Automation already created:**

``` language-javascript
{
    "error": "automation_already_created",
    "message" : "Automation already created",
    "status": 412
}
```

**Automation not allowed:**

``` language-javascript
{
   "error": "automation_operation_not_allowed",
   "message" : "Cannot perform [assign automation] for item with id [MLA123456]",
   "status": 412
}
```

**Unable to process the established rule:**

``` language-javascript
{
     "error": "unprocessable_set_rule",
     "message" : "Error calling rule assignment service",
     "status": 422
}
```

**Unauthorized**

``` language-javascript
{
    "code": "unauthorized",
    "message": "invalid access token"
}
```

  

## Retrieve Existing Price Automation of a particular item

To obtain the price automation for an item, you need to query the
resource **/marketplace/items/$ITEM\_ID/prices/automate**.

  

### Preconditions to obtain an automation

-   It must correspond to an existing item
-   It must be an already assigned automation
-   It must meet the [retrieval
    conditions](https://global-selling.mercadolibre.com/devsite/manage-automations#:~:text=automate/rules.-,Rules,-rule_id)

**Request:**

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' 
https://api.mercadolibre.com/marketplace/items/$ITEM_ID/prices/automate
```

**Example:**

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' 
https://api.mercadolibre.com/marketplace/items/MLM2245313004/prices/automate
```

**Response:**

``` language-javascript
{
   "status": "ACTIVE",
   "item_id": "MLM2245313004",
   "item_rule": {
       "rule_id": "INT_EXT",
       "title": "Best price on Mercado Libre and off the site",
       "description": "Your price will be adjusted by comparing the price and selling conditions of same listings on Mercado Libre and other marketplaces."
   },
   "min_price": 100,
   "max_price": 1000
}
```

### Response fields

The response of a GET to the resource
**/marketplace/items/$ITEM\_ID/prices/automate** will provide the
following parameters:

-   **item\_id**: Item identifier
-   **status**: Automation status, possible statuses:
    -   ACTIVE
    -   PAUSED
-   **item\_rule**:
    -   **rule\_id**: Automation rule.
-   **min\_price**: Minimum price set for the automation.
-   **max\_price**: Maximum price set for the automation.

  

### Possible errors when obtaining an automation

When consulting an automation, you may encounter the following errors.
It is crucial that you understand the cause of each one and know how to
correct them in order to efficiently manage the situation. Here is the
information you need to identify and resolve these issues.

  

**Item not found:**

``` language-javascript
{
    "error": "item_not_found",
    "message" :"Item with id [MLA123456] not found",
    "status": 404,
    "cause": []
}
```

**Automation not found:**

``` language-javascript
{
    "error": "automation_not_found",
    "message" : "Automation not found for item with id [MLA123456]",
    "status": 404,
    "cause": []
}
```

**User not authorized:**

``` language-javascript
{
    "error": "user_not_authorized",
    "message": "User is not allowed to automate items",
    "status": 412,
    "cause": []
}
```

**Automation not allowed:**

``` language-javascript
{
   "error": "automation_operation_not_allowed",
   "message" : "Cannot perform [get automation] for item with id [MLA123456]",
   "status": 412,
   "cause": []
}
```

**Unable to process the established rule:**

``` language-javascript
{
     "error": "unprocessable_get_rule",
     "message" : "Error calling rule assignment service",
     "status": 422
}
```

**Unauthorized:**

``` language-javascript
{
    "code": "unauthorized",
    "message": "invalid access token"
}
```

  

## Update Price Automation

To update a price automation rule for an item that is already assigned,
you need to perform a PUT request to the resource
**/marketplace/items/{itemId}/prices/automate**.

  

### Preconditions to update an automation

-   The rule must be applied to an existing item.
-   It is mandatory that it has a minimum price.
-   Prices cannot be absurd (Maximum and Minimum).

**Request:**

``` language-javascript
curl -X PUT -H 'Authorization: Bearer $ACCESS_TOKEN' 
{
  "rule_id" : "INT_EXT",
  "min_price": 111,
  "max_price": 999
}
https://api.mercadolibre.com/marketplace/items/{itemId}/prices/automate
```

**Example:**

``` language-javascript
curl -X PUT -H 'Authorization: Bearer $ACCESS_TOKEN' 
{
  "rule_id" : "INT_EXT",
  "min_price": 111,
  "max_price": 999
}

https://api.mercadolibre.com/marketplace/items/MLM2245313004/prices/automate
```

**Response:**

``` language-javascript
{
    "status": "ACTIVE",
    "item_id": "MLM2245313004",
    "item_rule": {
        "rule_id": "INT_EXT",
        "title": "Best price on Mercado Libre and off the site",
        "description": "Your price will be adjusted by comparing the price and selling conditions of same listings on Mercado Libre and other marketplaces."
    },
    "min_price": 111,
    "max_price": 999
}
```

### Response fields

The response of a PUT to the resource
**/marketplace/items/{itemId}/prices/automate** will provide the
following parameters:

-   **item\_id**: Item identifier
-   **status**: Automation status, possible statuses:
    -   ACTIVE
    -   PAUSED
-   **item\_rule**:
    -   **rule\_id**: Automation rule.
    -   **title**: The title of the automation rule.
    -   **description**: A detailed description of the automation rule.
-   **min\_price**: Minimum price set for the automation.
-   **max\_price**: Maximum price set for the automation.

  

### Possible errors when updating an automation

When updating an automation, you may encounter the following errors. It
is crucial that you understand the cause of each one and know how to
correct them in order to efficiently manage the situation. Here is the
information you need to identify and resolve these issues.

  

**Field rule\_id without value:**

``` language-javascript
{
    "error": "argument_not_valid",
    "message": "rule_id must not be null",
    "status": 400,
    "cause": [
        {
            "code": "rule_id_not_null",
            "message": "Rule identifier is required"
        }
    ]
}
```

**Item not found:**

``` language-javascript
{
    "error": "item_not_found",
    "message" : "Item with id [MLA123456] not found",
    "status": 404,
    "cause": []
}
```

**User not authorized:**

``` language-javascript
{
    "error": "user_not_authorized",
    "message": "User is not allowed to automate items",
    "status": 412,
    "cause": []
}
```

**Automation not allowed:**

``` language-javascript
{
   "error": "automation_operation_not_allowed",
   "message" : "Cannot perform [assign automation] for item with id [MLA123456]",
   "status": 412,
   "cause": []
}
```

**Unable to process the established rule:**

``` language-javascript
{
    "error": "unprocessable_set_rule",
    "message" : "Error calling rule retrieve service",
    "status": 422,
    "cause": []
}
```

**Unauthorized:**

``` language-javascript
{
    "code": "unauthorized",
    "message": "invalid access token"
}
```

## Delete a Price Automation

To delete a price automation rule from an item that is currently
assigned, a DELETE request must be made to the resource
**/marketplace/items/{itemId}/prices/automate**.

  

### Preconditions to delete an automation

-   The rule must be deleted from an existing item
-   An existing rule must be deleted

**Request:**

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' 
https://api.mercadolibre.com/marketplace/items/{itemId}/prices/automate
```

**Example:**

``` language-javascript
ccurl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' 
https://api.mercadolibre.com/marketplace/items/MLM2245313004/prices/automate
```

**The successful response will be only a "200 - OK" with an empty
return.**

``` language-javascript
{}
```

  

### Possible errors when deleting an automation

When deleting an automation, you may encounter the following errors. It
is crucial that you understand the cause of each one and know how to
correct them in order to efficiently manage the situation. Here is the
information you need to identify and resolve these issues.

  

**Item not found:**

``` language-javascript
{
    "error": "item_not_found",
    "message" : "Item with id [MLA123456] not found",
    "status": 404,
    "cause": []
}
```

**Automation not found:**

``` language-javascript
{
    "error": "automation_not_found",
    "message" : "Automation not found for item with id [MLA123456]",
    "status": 404,
    "cause": []
}
```

**User not authorized:**

``` language-javascript
{
    "error": "user_not_authorized",
    "message": "User is not allowed to automate items",
    "status": 412,
    "cause": []
}
```

**Automation not allowed:**

``` language-javascript
{
   "error": "automation_operation_not_allowed",
   "message" : "Cannot perform [delete automation] for item with id [MLA123456]",
   "status": 412,
   "cause": []
}
```

**Unable to process the established rule:**

``` language-javascript
{
    "error": "unprocessable_delete_rule",
    "message" : "Error calling rule retrieve service",
    "status": 422,
    "cause": []
}
```

**Unauthorized:**

``` language-javascript
{
    "code": "unauthorized",
    "message": "invalid access token"
}
```

</div>
