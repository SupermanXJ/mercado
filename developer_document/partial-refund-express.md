<div class="inner-content">

## Partial Refund Express

<div class="details__message">

Partial Refund Express is a feature that allows sellers to automate
partial refunds, facilitating the resolution of issues without reaching
the point of a claim. This feature relieves you from the task of
individually responding to complaints related to your product, allowing
you to experience benefits such as:

-   **Saving time**: Allows you to stay focused on your business goals.
-   **Reduce complaints**: Lower your queue of complaints and effort in
    resolving them.
-   **Protect reputation**: Keep your account's reputation intact.

See more [how automatic refunds work in Global
Selling](https://global-selling.mercadolibre.com/help/31456).

</div>

## Create a rule

Sellers can create refund rules depending on the logistics with
predefined configurations that automate the evaluation of claims. Each
rule establishes specific parameters that are compared against the
claim's information to determine the refund amount offered to the buyer
to avoid the buyer opening a claim.

  

### Mandatory parameters

-   **active** (boolean): Indicates whether the rule is active or
    paused. Values: `true` or `false`.
-   **price\_range** (object): Defines the price range to be evaluated.
    -   **from**: Minimum price of the range (integer).
    -   **to**: Maximum price of the range (integer).
    -   **all\_prices**: If set to `true`, it will apply to all prices,
        regardless of the range (boolean).
-   **refund\_offer** (integer): Percentage of automatic refund offered
    to the buyer. Available values: `90`, `80`, `70`, `60`, `50`, `40`,
    `30`, `20`, `10`.
-   **logistic** (array): List of logistics options applicable to the
    rule. Available values:
    -   **global\_seller**: Allows sellers to manage shipments on a
        global scale.
    -   **cbt\_fulfillment**: Fulfillment managed by Mercado Libre,
        storing and shipping products from their centers.
    -   **cbt\_fulfillment\_us**: US fulfillment managed by Mercado
        Libre, storing and shipping products from their centers.
    -   **cbt\_on\_site**: Shipping and management of products by CBT on
        Site Business Model.
-   **reason** (array): List of claim reasons considered within the
    rule. Available values:
    -   **all\_reasons**: All reasons are admitted.
    -   **product\_is\_damaged**: The product is damaged.
    -   **product\_is\_different**: The item received is different from
        the purchased product.
    -   **product\_does\_not\_work**: The product did not work.
    -   **buyer\_regretted\_purchase**: The buyer regretted the
        purchase.

<div class="andes-message andes-message--neutral">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--neutral site-carriers__message-title">

Note:

</div>

<div class="andes-message__text--neutral site-carriers__message-text">

<div>

There are no time settings available through the front end or API; you
can only activate, pause, or delete rules.

</div>

</div>

</div>

</div>

**Request:**

``` language-javascript
curl -X POST -H 'Authorization: Bearer $ACCESS_TOKEN' \
-H 'Content-Type: application/json' \
https://api.mercadolibre.com/marketplace/automatic/rules/refund \
-d '[
    {
        "active": true,
        "price_range": {
            "from": $FROM_PRICE,
            "to": $TO_PRICE,
            "all_prices": false
        },
        "refund_offer": $REFUND_PERCENTAGE,
        "logistic": ["$LOGISTIC_TYPE"],
        "reason": ["$REASON_CODE"]
    }
]'
```

**Example:**

``` language-javascript
curl -X POST -H 'Authorization: Bearer $ACCESS_TOKEN' \
-H 'Content-Type: application/json' \
https://api.mercadolibre.com/marketplace/automatic/rules/refund \
-d '[
    {
        "active": true,
        "price_range": {
            "from": 390,
            "to": 399,
            "all_prices": false
        },
        "refund_offer": 70,
        "logistic": ["global_seller"],
        "reason": ["product_is_damaged", "product_is_different"]
    }
]'
```

**Response:**

``` language-javascript
[
    {
        "id": "DecisionRule_0ba83bb4-f775-47f0-ac31-b3dae716b78a",
        "active": true,
        "price_range": {
            "from": 390,
            "to": 399,
            "all_prices": false
        },
        "refund_offer": 70,
        "logistic": ["global_seller"],
        "reason": ["product_is_damaged", "product_is_different"]
    }
]
```

### Response fields

-   **id**: Unique identifier for the rule. Format: `DecisionRule_UUID`.
-   **active**: Current status of the rule (`true` or `false`).
-   **price\_range**: The configured price range for the rule.
-   **refund\_offer**: The percentage of refund configured.
-   **logistic**: Array of logistics types the rule applies to.
-   **reason**: Array of claim reasons the rule covers.

## Get all available rules created

Retrieve all refund rules configured for your seller account.

**Request:**

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' \
https://api.mercadolibre.com/marketplace/automatic/rules/refund
```

**Response:**

``` language-javascript
[
    {
        "id": "DecisionRule_0ba83bb4-f775-47f0-ac31-b3dae716b78a",
        "active": true,
        "price_range": {
            "from": 220,
            "to": 300,
            "all_prices": false
        },
        "refund_offer": 20,
        "logistic": ["global_seller"],
        "reason": ["product_is_damaged"]
    },
    {
        "id": "DecisionRule_1ca94cc5-g886-58g1-bd42-c4ebf827c89b",
        "active": false,
        "price_range": {
            "from": 0,
            "to": 0,
            "all_prices": true
        },
        "refund_offer": 50,
        "logistic": ["cbt_fulfillment"],
        "reason": ["all_reasons"]
    }
]
```

## Modify an existing rule

You can modify all existing attributes of a rule using the rule ID. For
example, disable a rule by setting the value of `active` to `false`.

**Request:**

``` language-javascript
curl -X PUT -H 'Authorization: Bearer $ACCESS_TOKEN' \
-H 'Content-Type: application/json' \
https://api.mercadolibre.com/marketplace/automatic/rules/refund \
-d '[
    {
        "id": "$RULE_ID",
        "active": $ACTIVE_STATUS,
        "price_range": {
            "from": $FROM_PRICE,
            "to": $TO_PRICE,
            "all_prices": false
        },
        "refund_offer": $REFUND_PERCENTAGE,
        "logistic": ["$LOGISTIC_TYPE"],
        "reason": ["$REASON_CODE"]
    }
]'
```

**Example:**

``` language-javascript
curl -X PUT -H 'Authorization: Bearer $ACCESS_TOKEN' \
-H 'Content-Type: application/json' \
https://api.mercadolibre.com/marketplace/automatic/rules/refund \
-d '[
    {
        "id": "DecisionRule_0ba83bb4-f775-47f0-ac31-b3dae716b78a",
        "active": false,
        "price_range": {
            "from": 390,
            "to": 399,
            "all_prices": false
        },
        "refund_offer": 70,
        "logistic": ["global_seller"],
        "reason": ["product_is_damaged", "product_is_different"]
    }
]'
```

**Response:**

``` language-javascript
[
    {
        "id": "DecisionRule_0ba83bb4-f775-47f0-ac31-b3dae716b78a",
        "active": false,
        "price_range": {
            "from": 390,
            "to": 399,
            "all_prices": false
        },
        "refund_offer": 70,
        "logistic": ["global_seller"],
        "reason": ["product_is_damaged", "product_is_different"]
    }
]
```

## Delete a rule

Delete a rule or multiple rules at the same time by providing the IDs in
an array.

**Request:**

``` language-javascript
curl -X DELETE -H 'Authorization: Bearer $ACCESS_TOKEN' \
-H 'Content-Type: application/json' \
https://api.mercadolibre.com/marketplace/automatic/rules/refund \
-d '{
    "id": ["$RULE_ID_1", "$RULE_ID_2"]
}'
```

**Example:**

``` language-javascript
curl -X DELETE -H 'Authorization: Bearer $ACCESS_TOKEN' \
-H 'Content-Type: application/json' \
https://api.mercadolibre.com/marketplace/automatic/rules/refund \
-d '{
    "id": [
        "DecisionRule_0ba83bb4-f775-47f0-ac31-b3dae716b78a",
        "DecisionRule_0ba83bb4-f775-47f0-ac31-b3dae716bn69a"
    ]
}'
```

**Response:** `200 OK`

## Errors

The following table describes the possible error responses when using
the Partial Refund Express API:

| HTTP Code | Error                 | Message                                                                   | Description                                                                                       | Solution                                                                                                                                       |
|-----------|-----------------------|---------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------|
| **401**   | unauthorized\_scopes  | Unauthorized scopes                                                       | The application does not have the required scopes to access this API.                             | Contact Mercado Libre developer support to enable the `partial_refund_express` scope for your application.                                     |
| **400**   | invalid\_price\_range | The provided price range is invalid                                       | Incorrect format for price ranges, such as negative numbers or `from` greater than `to`.          | Ensure `from` is less than or equal to `to`, and both values are positive integers.                                                            |
| **400**   | max\_rules\_exceeded  | Customize up to 6 rules to improve the efficiency of complaint resolution | There are already 6 configured rules and additional rules are attempted to be added.              | Delete an existing rule before creating a new one, or modify an existing rule instead.                                                         |
| **400**   | invalid\_logistic     | The logistic 'X' is not configured. Your available logistics are Y        | A logistic type that the seller does not have configured is used.                                 | Use only the logistics types available for your seller account as indicated in the error message.                                              |
| **400**   | invalid\_percentage   | Percentage not allowed                                                    | An unavailable percentage value is provided.                                                      | Use only allowed values: 10, 20, 30, 40, 50, 60, 70, 80, or 90.                                                                                |
| **400**   | invalid\_reason       | The reason 'X' is not configured                                          | A reason not available in the allowed list is used.                                               | Use only valid reason codes: `all_reasons`, `product_is_damaged`, `product_is_different`, `product_does_not_work`, `buyer_regretted_purchase`. |
| **400**   | rule\_overlap         | The rule 'X' overlaps with another existing rule id 'Y'                   | The rule being created or updated has parameters and price ranges that overlap with another rule. | Ensure each rule has distinct price ranges or parameters compared to other rules.                                                              |
| **404**   | not\_found            | ID X not found                                                            | The specified rule ID does not exist.                                                             | Verify the rule ID by first calling GET to retrieve all existing rules.                                                                        |

## Reason values reference

The following table provides a quick reference for all valid `reason`
values:

| Reason Code                | Description                                            |
|----------------------------|--------------------------------------------------------|
| `all_reasons`              | Applies to all claim reasons                           |
| `product_is_damaged`       | The product arrived damaged or broken                  |
| `product_is_different`     | The item received is different from what was purchased |
| `product_does_not_work`    | The product does not function as expected              |
| `buyer_regretted_purchase` | The buyer changed their mind about the purchase        |

## Logistic values reference

The following table provides a quick reference for all valid `logistic`
values:

| Logistic Code        | Description                                        |
|----------------------|----------------------------------------------------|
| `global_seller`      | Seller manages shipments globally (self-fulfilled) |
| `cbt_fulfillment`    | Mercado Libre fulfillment from LATAM centers       |
| `cbt_fulfillment_us` | Mercado Libre fulfillment from US centers          |
| `cbt_on_site`        | CBT on Site business model                         |

## Related topics

-   [Returns](https://global-selling.mercadolibre.com/devsite/manage-returns) -
    Manage product returns and shipping labels
-   [Manage
    claims](https://global-selling.mercadolibre.com/devsite/manage-claims) -
    Handle buyer claims and disputes
-   [Claims
    messages](https://global-selling.mercadolibre.com/devsite/manage-claims-messages) -
    Send and receive messages within claims
-   [Claim
    resolutions](https://global-selling.mercadolibre.com/devsite/manage-claim-resolutions) -
    Resolve claims with refunds, returns, or disputes

**Next:**
[Returns](https://global-selling.mercadolibre.com/devsite/manage-returns)

</div>
