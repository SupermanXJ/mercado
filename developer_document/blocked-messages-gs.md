<div class="inner-content">

## Blocked messages

Remember that we moderate the shortened links with the following tools

-   Bitly
-   Bl.ink
-   Polr
-   Rebrandly
-   T2M
-   TinyURL
-   URL Shortener by Zapier
-   Yourls

  

## Check blocked messages

Request:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/messages/packs/$PACK_ID/sellers/$SELLER_ID?limit=$LIMIT&offset=$OFFSET&tag=post_sale
```

Example:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/messages/packs/22175467/sellers/32086568493?limit=2&offset=1&tag=post_sale
```

Response:

``` language-javascript
{
    "paging": {
        "limit": 10,
        "offset": 0,
        "total": 4
    },
    "conversation_status": {
        "path": "/packs/22175467/sellers/32086568493",
        "status": "blocked",
        "substatus": "blocked_by_buyer",
        "status_date": "2020-01-10T19:58:04.317Z",
        "status_update_allowed": false,
        "claim_ids": null,
        "shipping_id": null
    },
    "messages": [...]
}
```

Learn more **the response fields** and reasons (**substatus**) for which
we block certain after-sales messages to improve the buyer experience:

  

**status**: this field admits two values:

-   **active**: the conversation is open to send/receive messages.
-   **blocked**: the conversation is closed to send/receive messages.

**substatus**

-   **blocked\_by\_time**: the seller may respond in all cases as long
    as 30 days have not elapsed since the last message that was sent.
    The period to receive messages has expired and will only be reopened
    if the buyer so decides.
-   **blocked\_by\_buyer**: the buyer decides to block the reception of
    messages.
-   **bloqued\_by\_mediation**: there is an ongoing mediation between
    the buyer and the seller.
-   **blocked\_by\_fulfillment**: being a sale with Fulfillment, the
    messages will be available when the package is delivered (shipping
    status: `delivered`).
-   **blocked\_by\_payment**: the payment has not yet been made (by the
    buyer) or has not yet been impacted.  
    An order is not paid when it has any of the status
    **payment\_required**, **payment\_in\_process**, or
    **partially\_paid**. This block is temporary until the payment is
    made and has impacted on the order. The update is not instantaneous,
    so we recommend waiting 60 seconds for it to have an impact.
-   **blocked\_by\_conversation\_initiated\_by\_seller**: the purchase
    in its entirety is of Supermarket products, and the seller initiates
    the conversation. This block applies in Argentina, Mexico and
    Brazil. When the buyer starts the conversation, the seller's
    messaging will not be blocked.
-   **blocked\_by\_conversation\_use\_message\_api**: the seller
    attempts to communicate via action-guide when the buyer has already
    started the conversation.
-   **blocked\_by\_conversation\_initiated\_by\_seller\_limited**: this
    block applies to Mercado Envíos 2 sales in Brazil, Chile, Argentina,
    Mexico and Colombia. You must use the Reasons to communicate
    resource. When the buyer starts the conversation, the seller's
    messaging will not be blocked.
-   **blocked\_by\_cancelled\_order**: cannot communicate because the
    sale is cancelled.
-   **blocked\_by\_cancelled\_order\_by\_fraud**: cannot communicate
    because the sale was cancelled due to irregular behavior of the
    seller or buyer. If messages exist and this block occurs, they will
    not be available as they represent a risk point.
-   **blocked\_by\_mediation\_fbm**: the seller cannot communicate
    because there is an ongoing mediation in a Fulfillment sale.
-   **blocked\_by\_guest\_shops**: messaging is blocked because the
    purchase was made by a guest user in MShops.
-   **blocked\_by\_conversation\_expired**: messaging is blocked and
    messages are not returned for seller and buyer when Mercado Libre
    detects that 18 months have passed since the purchase date.
-   **blocked\_by\_refund**: the seller cannot communicate with the
    buyer because a partial or full refund of the order has been made.
    It will only be reopened if the buyer sends a new message.
-   **blocked\_by\_claim\_change\_closed**: claim messaging is blocked
    because there is a closed product change associated with the order.
-   **blocked\_by\_deactivated\_account**: messaging is blocked because
    the buyer or seller deleted their account.
-   **blocked\_by\_restrictions**: messaging is blocked because there is
    a restriction on the seller or buyer.
-   **blocked\_by\_cancelled\_order\_hidden**: cannot communicate
    because the purchase/sale could not be processed and has been
    cancelled. The order will only be visible to the buyer.
-   **blocked\_by\_claim\_change\_open**: messaging is blocked because
    there is an ongoing product change associated with the order.
-   **blocked\_by\_message\_pending\_review**: the seller cannot
    communicate with the buyer because the conversation is under review.
    Communication will be possible after message review.
-   **blocked\_by\_return\_to\_buyer\_fulfillment**: messaging is
    blocked for cases where, after triage review in Fulfillment, it is
    decided to return the product to the buyer due to non-compliance
    with return policies.
-   **blocked\_by\_ai\_assistant**: messaging is disabled for being a
    Fulfillment sale.

**status\_date**: is the date when the conversation status was updated.

</div>
