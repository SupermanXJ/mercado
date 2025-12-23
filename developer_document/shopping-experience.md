<div class="inner-content">

## Shopping experience

<div class="andes-message andes-message--highlight">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--highlight site-carriers__message-title">

Important:

</div>

<div class="andes-message__text--highlight site-carriers__message-text">

<div>

This feature is available in Argentina, Brazil, Uruguay, Mexico,
Colombia and Chile.

</div>

</div>

</div>

</div>

<div class="details__message">

Shopping experience is an algorithm that applies rules to position each
item according to its performance based on customer service indicators.
This feature helps sellers detect problems with their items so they can
improve customer service quality based on complaints and
cancellations.  

The resource allows sellers to display the shopping experience they
offer in their listings, understand how each item is performing
regarding complaints and cancellations, identify the type of problems
generated, learn how to improve, and understand the consequences of poor
performance.  

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

In addition to the existing
[/health](https://global-selling.mercadolibre.com/devsite/listings-quality-gs)
resource (listings quality), the shopping experience provides different
levels and solutions for item performance evaluation.

</div>

</div>

</div>

</div>

  

The resource **/purchase\_experience/** allows you to identify the
status of your listings, with the level reached and their corresponding
actionable items in case they need to be improved with respect to the
shopping experience offered.

  

Request:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/marketplace/items/$ITEM_ID/purchase_experience
```

Example:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/marketplace/items/CBT939406528/purchase_experience
```

Response:

``` language-javascript
[
    {
        "item_id": "MLC1755787034",
        "freeze": {
         "text": ""
        },
        "title": {
            "text": "Your shopping experience cannot be measured yet"
        },
        "subtitles": [
            {
                "order": 0,
                "text": "We did not calculate it yet because your listing did not have any orders in the last 180 days."
            }
        ],
        "actions": [],
        "reputation": {
            "color": "gray",
            "value": -1
        },
        "status": {},
        "metrics_details": {
            "empty_state_title": "You had no orders with problems in the last 180 days.",
            "problems": null,
            "distribution": {
                "level_one": null
            }
        }
    },
    {
        "item_id": "MLM1884643783",
        "freeze": {},
        "title": {
            "text": "Your shopping experience cannot be measured yet"
        },
        "subtitles": [
            {
                "order": 0,
                "text": "We did not calculate it yet because your listing did not have any orders in the last 180 days."
            }
        ],
        "actions": [],
        "reputation": {
            "color": "gray",
            "value": -1
        },
        "status": {
            "id": "moderated"
        },
        "metrics_details": {
            "empty_state_title": "You had no orders with problems in the last 180 days.",
            "problems": null,
            "distribution": {
                "from": "2023-04-20T23:41:45Z",
                "to": "2023-10-17T23:41:45Z",
                "level_one": []
            }
        }
    },
    {
        "item_id": "MCO1288981083",
        "freeze": {},
        "title": {
            "text": "Shopping experience"
        },
        "subtitles": [
            {
                "order": 0,
                "text": "There is an issue with this product. Check the tips on how to improve the shopping experience."
            },
            {
                "order": 1,
                "text": "You are providing a good shopping experience."
            }
        ],
        "actions": [
            {
                "order": 0,
                "text": "Edit listing"
            },
            {
                "order": 1,
                "text": "Pause from the list"
            }
        ],
        "reputation": {
            "color": "green",
            "text": "Good",
            "value": 100
        },
        "status": {
            "id": "active"
        },
        "metrics_details": {
            "empty_state_title": "",
            "problems": [
                {
                    "order": 0,
                    "key": "PRODUCT",
                    "color": "#7267E4",
                    "quantity": "1 issue",
                    "cancellations": 0,
                    "claims": 1,
                    "tag": "MAIN ISSUE",
                    "level_two": {
                        "key": "DIFFERENT_FROM_REQUESTED",
                        "title": {
                            "text": "Product didn't match the order"
                        }
                    },
                    "level_three": {
                        "key": "QUALITY_ISSUES",
                        "title": {
                            "text": "The quality of the product was not what the buyer expected"
                        },
                        "remedy": {
                            "text": "Make sure to include the material of the products in the description to avoid complaints related to quality. Try selling products of the best quality in general."
                        }
                    }
                }
            ],
            "distribution": {
                "from": "2023-06-22T02:56:04Z",
                "to": "2023-12-19T02:56:04Z",
                "level_one": [
                    {
                        "key": "PRODUCT",
                        "title": {
                            "text": "With the delivered product"
                        },
                        "color": "#7267E4",
                        "percentage": 100,
                        "quantities_level_two": [
                            {
                                "key": "DIFFERENT_FROM_REQUESTED",
                                "title": {
                                    "text": "Product didn't match the order"
                                },
                                "quantity": 1
                            }
                        ]
                    }
                ]
            }
        }
    }
 ]
```

  

### Response fields

| Field                                    | Type    | Description                                                                     |
|------------------------------------------|---------|---------------------------------------------------------------------------------|
| **item\_id**                             | String  | Identification of the item being checked.                                       |
| **freeze**                               | Object  | Experience freeze notice. When present, no actions are generated over the item. |
| **freeze.text**                          | String  | Freeze message explaining why the item is protected from penalties.             |
| **title**                                | Object  | Main reason why the item is in the current status.                              |
| **title.text**                           | String  | Title text content.                                                             |
| **subtitles**                            | Array   | Details explaining why the item is in the current status.                       |
| **subtitles\[\].order**                  | Integer | Display order of the subtitle.                                                  |
| **subtitles\[\].text**                   | String  | Subtitle text content.                                                          |
| **subtitles\[\].placeholders**           | Array   | Values to replace {0}, {1} placeholders in the text.                            |
| **actions**                              | Array   | Possible actionable items to edit the current situation.                        |
| **actions\[\].order**                    | Integer | Display order of the action.                                                    |
| **actions\[\].text**                     | String  | Action button text.                                                             |
| **reputation**                           | Object  | Current reputation status according to shopping experience.                     |
| **reputation.color**                     | String  | Reputation color (gray, green, yellow, orange, red).                            |
| **reputation.text**                      | String  | Reputation label (e.g., "Good").                                                |
| **reputation.value**                     | Integer | Reputation score. -1 indicates not enough data to calculate.                    |
| **status**                               | Object  | Status information of the listing.                                              |
| **status.id**                            | Enum    | Listing status: active, paused, or moderated.                                   |
| **status.assigned\_by**                  | Enum    | Who assigned the status: reputation or other.                                   |
| **metrics\_details**                     | Object  | Details of problems, levels, solutions, and distribution.                       |
| **metrics\_details.empty\_state\_title** | String  | Message shown when there are no problems.                                       |
| **metrics\_details.problems**            | Array   | List of problems affecting the shopping experience.                             |
| **metrics\_details.distribution**        | Object  | Distribution of problems over time.                                             |

  

-   Status -&gt; **paused**

![](https://http2.mlstatic.com/storage/developers-site-cms-admin/207649856963-Captura-de-Pantalla-2023-11-07-a-la-s--12.58.03.png)  

-   Status -&gt; **active**

![](https://http2.mlstatic.com/storage/developers-site-cms-admin/207648357157-Captura-de-Pantalla-2023-11-08-a-la-s--12.53.53.png)  

## Fields and Response components

**Text**

``` language-javascript
{
    "order": uint,
    "text": string,
    "placeholders": []string
}
```

Example: text {0} text {1}. \[0\]

-   The {} should be replaced by the placeholders.
-   The \[\] should be replaced by the actions.

``` language-javascript
{
    "text": "For now, {0}this listing will not lose exposure nor be paused or cancelled for providing a bad or medium experience.{1} It is important to solve its problems to improve the experience you provide.",
    "placeholders": [
        "<b>",
        "</b>"
    ]
}
```

**Freeze**

The first part of the freeze wording changes according to the type of
freeze applied.

  

-   Req\_commercial

``` language-javascript
"freeze": {
    "text": "Due to a Commercial Agreement, {0}this listing will not lose exposure, nor be paused or cancelled for having a bad or medium shopping experience.{1} Keep in mind that it is important to solve the problems to improve the experience you provide.",
    "placeholders": [
        "<b>",
        "</b>"
    ]
}
```

-   Internal\_recovery\_grntee

``` language-javascript
"freeze": {
    "text": "Due to the Reputation Benefit, {0}this listing will not lose exposure, nor be paused or cancelled for having a bad or medium shopping experience.{1} Keep in mind that it is important to solve the problems to improve the experience you provide.",
    "placeholders": [
        "<b>",
        "</b>"
    ]
}
```

-   Internal\_recovery

``` language-javascript
"freeze": {
    "text": "Due to the Light Green Benefit, {0}this listing will not lose exposure, nor be paused or cancelled for having a bad or medium shopping experience.{1} Keep in mind that it is important to solve the problems to improve the experience you provide.",
    "placeholders": [
        "<b>",
        "</b>"
    ]
}
```

-   Internal\_newbie\_grntee

``` language-javascript
"freeze": {
    "text": "Due to the Reputation Benefit, {0}this listing will not lose exposure, nor be paused or cancelled for having a bad or medium shopping experience.{1} Keep in mind that it is important to solve the problems to improve the experience you provide.",
    "placeholders": [
        "<b>",
        "</b>"
    ]
}
```

-   Rest of freezed

The other freeze types are: **grace\_time, internal\_reputation,
req\_legal, frozen**.

``` language-javascript
"freeze": {
    "text": "For now, {0}this listing will not lose exposure nor be paused or cancelled for providing a bad or medium experience.{1} It is important to solve its problems to improve the experience you provide.",
    "placeholders": [
        "<b>",
        "</b>"
    ]
}
```

**Status**

``` language-javascript
{
    "id": enum (active | paused | moderated),
    "assigned_by": enum (reputation | other),
    "text": string
}
```

**Subtitle**

A change was added to obtain the amount of sales of an item in the last
180 days and show it in the fronts.

<div class="andes-message andes-message--neutral">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--neutral site-carriers__message-title">

Note:

</div>

<div class="andes-message__text--neutral site-carriers__message-text">

<div>

This change is gradual, so you should be able to recognize the current
answer (without placeholders) and the new answer (with placeholders).

</div>

</div>

</div>

</div>

![](https://http2.mlstatic.com/storage/developers-site-cms-admin/200485208402-Captura-de-Tela-2024-01-30-a-s-10.30.10.png)  
![](https://http2.mlstatic.com/storage/developers-site-cms-admin/200485142907-Captura-de-Tela-2024-01-30-a-s-10.30.24.png)  

Current response

``` language-javascript
"subtitles": [
    {
        "order": 0,
        "text": "You have 9 issues with this product. Check the tips on how to improve."
    },
    {
        "order": 1,
        "text": "The experience your listing provides affects your exposure and we could cancel it."
    }
]
```

New response

``` language-javascript
"subtitles": [
    {
        "order": 0,
        "text": "In the last 180 days you made {0}12 sales{1} and had {0}9 issues.{1} Check the tips on how to improve.",
        "placeholders": [
            "<b>",
            "</b>"
        ]
    },
    {
        "order": 1,
        "text": "The experience your listing provides affects your exposure and we could cancel it."
    }
]
```

**Action**

``` language-javascript
{
    "order": uint,
    "text": string
}
```

According to the conditions shown in the items, the possible actions are
the following.

  

**Active items**

-   If the item has score 100 and has no problems: See publication.
-   If the item has score 100 with problems or a lower score (excluding
    score -1, which is when the item has no sales): Modify publication
    and Pause from the list.

**Paused items**

-   Paused by the seller: Modify publication and View publication.
-   Paused by Buying Experience: Modify publication and Reactivate from
    the list.

**Cancelled item**

-   Overridden by shopping experience: How to provide a good experience.
-   Overridden by other moderation: View post.

**Reputation**

``` language-javascript
{
    "color": string,
    "text": string,
    "value": int
}
```

**Metrics details**

``` language-javascript
{
    "empty_state_title": string,
    "problems": []problem,
    "distribution": distribution
}
```

**Problem**

| Field             | Type    | Description                                             |
|-------------------|---------|---------------------------------------------------------|
| **order**         | Integer | Display order of the problem.                           |
| **key**           | String  | Level 1 problem category key (e.g., PRODUCT, SHIPPING). |
| **color**         | String  | Color code for the problem category.                    |
| **quantity**      | String  | Text describing the number of issues.                   |
| **cancellations** | Integer | Number of cancellations related to this problem.        |
| **claims**        | Integer | Number of claims related to this problem.               |
| **tag**           | String  | Problem tag (e.g., MAIN ISSUE).                         |
| **level\_two**    | Object  | Level 2 problem details.                                |
| **level\_three**  | Object  | Level 3 problem details with remedy.                    |

  

**Level 2**

``` language-javascript
{
    "key": string,
    "title": {
        "text": string
    }
}
```

| Field          | Type   | Description                                             |
|----------------|--------|---------------------------------------------------------|
| **key**        | String | Level 2 problem key (e.g., DIFFERENT\_FROM\_REQUESTED). |
| **title.text** | String | Level 2 problem description.                            |

  

**Level 3**

``` language-javascript
{
    "key": string,
    "title": {
        "text": string
    },
    "remedy": {
        "text": string
    }
}
```

| Field           | Type   | Description                            |
|-----------------|--------|----------------------------------------|
| **key**         | String | Level 3 problem key.                   |
| **title.text**  | String | Level 3 problem description.           |
| **remedy.text** | String | Suggested solution to fix the problem. |

  

**Distribution**

``` language-javascript
{
    "from": date,
    "to": date,
    "level_one": []level_one
}
```

**Date format**

``` language-javascript
{
    "from": "2023-07-04T19:08:56Z",
    "to": "2023-11-04T19:08:56Z"
}
```

**Level 1**

| Field                                     | Type    | Description                                    |
|-------------------------------------------|---------|------------------------------------------------|
| **key**                                   | String  | Level 1 category key.                          |
| **title.text**                            | String  | Level 1 category description.                  |
| **color**                                 | String  | Color code for the category.                   |
| **percentage**                            | Float   | Percentage of total problems in this category. |
| **quantities\_level\_two**                | Array   | Breakdown by Level 2 subcategories.            |
| **quantities\_level\_two\[\].key**        | String  | Level 2 key.                                   |
| **quantities\_level\_two\[\].title.text** | String  | Level 2 description.                           |
| **quantities\_level\_two\[\].quantity**   | Integer | Number of problems in this subcategory.        |

  

### Errors

| HTTP Status | Error       | Message                                   | Description                                                                  |
|-------------|-------------|-------------------------------------------|------------------------------------------------------------------------------|
| **400**     | Bad Request | CBT item CBT1763076395 has no site items. | The queried parent item has no site items.                                   |
| **403**     | forbidden   | Can not identify the user.                | The user cannot be identified. A Seller\_ID/Merchant\_ID parent is expected. |
| **404**     | not\_found  | Item with id CBT12345678 not found.       | The queried parent item does not exist. A CBT item parent is expected.       |

  

</div>
