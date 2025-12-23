<div class="inner-content">

## Manage orders

<div class="details__message">

An order is a request made by a customer on a listed item that intends
to buy under a series of conditions to be selected in the online
checkout flow. These conditions are detailed in the order that will be
replicated for buyer and seller accounts. You will find information
about the product to fill out there. The Global Selling orders
correspond to each local marketplace (México, Brasil and Chile) and
sellers manage these orders in a unified way. Next, we detail the order
management flow.

</div>

  

## Receive notifications

Some events happen on Global Selling's side and notifications are the
only way to become aware of them. Receiving notifications enables you to
have a real-time feed of the changes that occur on the different
resources of our API. Learn more about
[notifications](https://global-selling.mercadolibre.com/devsite/receive-notifications#marketplace-orders).

  

## Summary

This examples will help you manage orders.

<table class="andes-table">
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead class="andes-table__head">
<tr class="header andes-table__row">
<th class="andes-table__header andes-table__header--left">Resource</th>
<th class="andes-table__header andes-table__header--left">Description</th>
<th class="andes-table__header andes-table__header--left">Example</th>
</tr>
</thead>
<tbody class="andes-table__body">
<tr class="odd andes-table__row">
<td class="andes-table__column andes-table__column--left"><strong>/marketplace/orders/search</strong></td>
<td class="andes-table__column andes-table__column--left">Search all orders from a seller.</td>
<td class="andes-table__column andes-table__column--left"><a href="#modal1">GET</a>
<div id="modal1" class="modalmask">
<div class="modalbox movedown">
<a href="#close" class="go-back">Go back</a> <a href="#close" class="close" title="Close">X</a>
<h3 id="search-the-orders-by-seller">Search the orders by seller</h3>
<pre class="language-javascript details__code-terminal-json"><code>curl -X GET -H &#39;Authorization: Bearer $ACCESS_TOKEN&#39; https://api.mercadolibre.com/marketplace/orders/search</code></pre>
<h3 id="response">Response</h3>
<pre class="language-javascript details__code-terminal-json"><code>{
  &quot;query&quot;: &quot;&quot;,
  &quot;results&quot;: [{
    &quot;id&quot;: 2315686468,
    &quot;buyer&quot;: {
      &quot;id&quot;: 441782523
    },
    &quot;config&quot;: {
      &quot;items&quot;: [{
        &quot;id&quot;: &quot;MLM755638064&quot;
      }]
    },
    &quot;orders&quot;: [{
      &quot;id&quot;: 2315686468,
      &quot;items&quot;: null,
      &quot;feedback&quot;: {
        &quot;purchase&quot;: null,
        &quot;sale&quot;: null
      },
      &quot;payments&quot;: [{
        &quot;id&quot;: 5882999015
      }],
      &quot;mediations&quot;: [],
      &quot;seller&quot;: {
        &quot;id&quot;: 523132944
      }
    }],
    &quot;shipment&quot;: {
      &quot;id&quot;: 28242306889,
      &quot;payments&quot;: []
    }
  }],
  &quot;sort&quot;: {
    &quot;id&quot;: &quot;date_asc&quot;,
    &quot;name&quot;: &quot;Date ascending&quot;
  },
  &quot;available_sorts&quot;: [{
    &quot;id&quot;: &quot;date_desc&quot;,
    &quot;name&quot;: &quot;Date descending&quot;
  }],
  &quot;filters&quot;: [],
  &quot;paging&quot;: {
    &quot;total&quot;: 1,
    &quot;limit&quot;: 50,
    &quot;scroll_id&quot;: &quot;YXNzb3J0ZWQtbWVkaXVtLXpldGEtdGVtcA==:ZHMtYXNzb3J0ZWQtbWVkaXVtLXpldGEtMDE=:DXF1ZXJ5QW5kRmV0Y2gBAAAAAHxnEgwWZG1TRzNfNklSaE9VTUZYeGhfc1dFdw==&quot;
  }
}</code></pre>
<a href="https://global-selling.mercadolibre.com/devsite/manage-sales-global-selling">Learn more.</a>
</div>
</div></td>
</tr>
</tbody>
<tbody class="andes-table__body">
<tr class="odd andes-table__row">
<td class="andes-table__column andes-table__column--left"><strong>/marketplace/orders/search?seller=$SELLER_ID</strong></td>
<td class="andes-table__column andes-table__column--left">Search one order from a seller.</td>
<td class="andes-table__column andes-table__column--left"><a href="#modal2">GET</a>
<div id="modal2" class="modalmask">
<div class="modalbox movedown">
<a href="#close" class="go-back">Go back</a> <a href="#close" class="close" title="Close">X</a>
<h3 id="search-order-by-seller">Search order by seller</h3>
<pre class="language-javascript details__code-terminal-json"><code>curl -X GET -H &#39;Authorization: Bearer $ACCESS_TOKEN&#39; http://api.mercadolibre.com/marketplace/orders/search?seller.id=523133081</code></pre>
<h3 id="response-1">Response</h3>
<pre class="language-javascript details__code-terminal-json"><code>        &quot;seller_custom_field&quot;: null,
        &quot;variation_attributes&quot;: [],
        &quot;category_id&quot;: &quot;MLA3530&quot;,

    }]
  }]
}</code></pre>
<a href="https://global-selling.mercadolibre.com/devsite/manage-sales-global-selling">Learn more.</a>
</div>
</div></td>
</tr>
</tbody>
<tbody class="andes-table__body">
<tr class="odd andes-table__row">
<td class="andes-table__column andes-table__column--left"><strong>/sites/$SITE_ID/payment_methods</strong></td>
<td class="andes-table__column andes-table__column--left">Returns the payment methods provided by Mercado Pago.</td>
<td class="andes-table__column andes-table__column--left"><a href="#modal4">GET</a>
<div id="modal4" class="modalmask">
<div class="modalbox movedown">
<a href="#close" class="go-back">Go back</a> <a href="#close" class="close" title="Close">X</a>
<h3 id="returns-data-for-a-payment">Returns data for a payment</h3>
<pre class="language-javascript details__code-terminal-json"><code>curl -X GET -H &#39;Authorization: Bearer $ACCESS_TOKEN&#39; http://api.mercadolibre.com/sites/MLM/payment_methods</code></pre>
<h3 id="response-2">Response</h3>
<pre class="language-javascript details__code-terminal-json"><code>[
    {
        &quot;id&quot;: &quot;visa&quot;,
        &quot;name&quot;: &quot;Visa&quot;,
        &quot;payment_type_id&quot;: &quot;credit_card&quot;,
        &quot;thumbnail&quot;: &quot;http://img.mlstatic.com/org-img/MP3/API/logos/visa.gif&quot;,
        &quot;secure_thumbnail&quot;: &quot;https://www.mercadopago.com/org-img/MP3/API/logos/visa.gif&quot;
    },
    {
        &quot;id&quot;: &quot;amex&quot;,
        &quot;name&quot;: &quot;American Express&quot;,
        &quot;payment_type_id&quot;: &quot;credit_card&quot;,
        &quot;thumbnail&quot;: &quot;http://img.mlstatic.com/org-img/MP3/API/logos/amex.gif&quot;,
        &quot;secure_thumbnail&quot;: &quot;https://www.mercadopago.com/org-img/MP3/API/logos/amex.gif&quot;
    },
    {
        &quot;id&quot;: &quot;master&quot;,
        &quot;name&quot;: &quot;Mastercard&quot;,
        &quot;payment_type_id&quot;: &quot;credit_card&quot;,
        &quot;thumbnail&quot;: &quot;http://img.mlstatic.com/org-img/MP3/API/logos/master.gif&quot;,
        &quot;secure_thumbnail&quot;: &quot;https://www.mercadopago.com/org-img/MP3/API/logos/master.gif&quot;
    },
    {
        &quot;id&quot;: &quot;debmaster&quot;,
        &quot;name&quot;: &quot;Mastercard Débito&quot;,
        &quot;payment_type_id&quot;: &quot;debit_card&quot;,
        &quot;thumbnail&quot;: &quot;http://img.mlstatic.com/org-img/MP3/API/logos/debmaster.gif&quot;,
        &quot;secure_thumbnail&quot;: &quot;https://www.mercadopago.com/org-img/MP3/API/logos/debmaster.gif&quot;
    },
    {
        &quot;id&quot;: &quot;debvisa&quot;,
        &quot;name&quot;: &quot;Visa Débito&quot;,
        &quot;payment_type_id&quot;: &quot;debit_card&quot;,
        &quot;thumbnail&quot;: &quot;http://img.mlstatic.com/org-img/MP3/API/logos/debvisa.gif&quot;,
        &quot;secure_thumbnail&quot;: &quot;https://www.mercadopago.com/org-img/MP3/API/logos/debvisa.gif&quot;
    },
    {
        &quot;id&quot;: &quot;mercadopagocard&quot;,
        &quot;name&quot;: &quot;Tarjeta MercadoPago&quot;,
        &quot;payment_type_id&quot;: &quot;prepaid_card&quot;,
        &quot;thumbnail&quot;: &quot;http://img.mlstatic.com/org-img/MP3/API/logos/mercadopagocard.gif&quot;,
        &quot;secure_thumbnail&quot;: &quot;https://www.mercadopago.com/org-img/MP3/API/logos/mercadopagocard.gif&quot;
    },
    {
        &quot;id&quot;: &quot;serfin&quot;,
        &quot;name&quot;: &quot;Santander&quot;,
        &quot;payment_type_id&quot;: &quot;atm&quot;,
        &quot;thumbnail&quot;: &quot;http://img.mlstatic.com/org-img/MP3/API/logos/2016.gif&quot;,
        &quot;secure_thumbnail&quot;: &quot;https://www.mercadopago.com/org-img/MP3/API/logos/2016.gif&quot;
    },
    {
        &quot;id&quot;: &quot;oxxo&quot;,
        &quot;name&quot;: &quot;OXXO&quot;,
        &quot;payment_type_id&quot;: &quot;ticket&quot;,
        &quot;thumbnail&quot;: &quot;http://img.mlstatic.com/org-img/MP3/API/logos/2017.gif&quot;,
        &quot;secure_thumbnail&quot;: &quot;https://www.mercadopago.com/org-img/MP3/API/logos/2017.gif&quot;
    },
    {
        &quot;id&quot;: &quot;account_money&quot;,
        &quot;name&quot;: &quot;Dinero en mi cuenta de MercadoPago&quot;,
        &quot;payment_type_id&quot;: &quot;account_money&quot;,
        &quot;thumbnail&quot;: &quot;http://img.mlstatic.com/org-img/MP3/API/logos/2018.gif&quot;,
        &quot;secure_thumbnail&quot;: &quot;https://www.mercadopago.com/org-img/MP3/API/logos/2018.gif&quot;
    },
    {
        &quot;id&quot;: &quot;bancomer&quot;,
        &quot;name&quot;: &quot;BBVA Bancomer&quot;,
        &quot;payment_type_id&quot;: &quot;atm&quot;,
        &quot;thumbnail&quot;: &quot;http://img.mlstatic.com/org-img/MP3/API/logos/2014.gif&quot;,
        &quot;secure_thumbnail&quot;: &quot;https://www.mercadopago.com/org-img/MP3/API/logos/2014.gif&quot;
    },
    {
        &quot;id&quot;: &quot;banamex&quot;,
        &quot;name&quot;: &quot;Citibanamex&quot;,
        &quot;payment_type_id&quot;: &quot;atm&quot;,
        &quot;thumbnail&quot;: &quot;http://img.mlstatic.com/org-img/MP3/API/logos/2015.gif&quot;,
        &quot;secure_thumbnail&quot;: &quot;https://www.mercadopago.com/org-img/MP3/API/logos/2015.gif&quot;
    },
    {
        &quot;id&quot;: &quot;consumer_credits&quot;,
        &quot;name&quot;: &quot;Mercado Crédito&quot;,
        &quot;payment_type_id&quot;: &quot;digital_currency&quot;,
        &quot;thumbnail&quot;: &quot;http://img.mlstatic.com/org-img/MP3/API/logos/consumer_credits.gif&quot;,
        &quot;secure_thumbnail&quot;: &quot;http://img.mlstatic.com/org-img/MP3/API/logos/consumer_credits.gif&quot;
    }
]</code></pre>
<a href="https://global-selling.mercadolibre.com/devsite/set-categories-for-your-products-global-selling">Learn more.</a>
</div>
</div></td>
</tr>
</tbody>
<tbody class="andes-table__body">
<tr class="odd andes-table__row">
<td class="andes-table__column andes-table__column--left"><strong>/sites/$SITE_ID/payment_methods/$id</strong></td>
<td class="andes-table__column andes-table__column--left">Returns the detail of the specific payment method.</td>
<td class="andes-table__column andes-table__column--left"><a href="#modal5">GET</a>
<div id="modal5" class="modalmask">
<div class="modalbox movedown">
<a href="#close" class="go-back">Go back</a> <a href="#close" class="close" title="Close">X</a>
<h3 id="get-payment-method">Get payment method</h3>
<pre class="language-javascript details__code-terminal-json"><code>curl -X GET -H &#39;Authorization: Bearer $ACCESS_TOKEN&#39; http://api.mercadolibre.com/sites/MLM/payment_methods/visa</code></pre>
<h3 id="response-3">Response</h3>
<pre class="language-javascript details__code-terminal-json"><code>{
  &quot;name&quot;: &quot;Visa&quot;,
  &quot;id&quot;: &quot;visa&quot;,
  &quot;payment_type_id&quot;: &quot;credit_card&quot;,
  &quot;card_issuer&quot;: {},
  &quot;site_id&quot;: &quot;MLM&quot;,
  &quot;secure_thumbnail&quot;: &quot;https://www.mercadopago.com/org-img/MP3/API/logos/visa.gif&quot;,
  &quot;thumbnail&quot;: &quot;http://img.mlstatic.com/org-img/MP3/API/logos/visa.gif&quot;,
  &quot;labels&quot;: [],
  &quot;total_financial_cost&quot;: null,
  &quot;min_accreditation_days&quot;: 0,
  &quot;max_accreditation_days&quot;: 2,
  &quot;payer_costs&quot;: [],
  &quot;deferred_capture&quot;: &quot;supported&quot;,
  &quot;exceptions_by_card_issuer&quot;: [],
  &quot;card_configuration&quot;: []
}</code></pre>
</div>
</div></td>
</tr>
</tbody>
<tbody class="andes-table__body">
<tr class="odd andes-table__row">
<td class="andes-table__column andes-table__column--left"><strong>/marketplace/orders/$ORDER_ID/invoice</strong></td>
<td class="andes-table__column andes-table__column--left">Get the "proforma" invoice to be used for customs declarations.</td>
<td class="andes-table__column andes-table__column--left"><a href="#modal6">GET</a>
<div id="modal6" class="modalmask">
<div class="modalbox movedown">
<a href="#close" class="go-back">Go back</a> <a href="#close" class="close" title="Close">X</a>
<h3 id="get-an-order-invoice">Get an order invoice</h3>
<pre class="language-javascript details__code-terminal-json"><code>curl -X GET -H &#39;Authorization: Bearer $ACCESS_TOKEN&#39; http://api.mercadolibre.com/marketplace/orders/2315686468/invoice</code></pre>
<h3 id="response-get-the-proforma-invoice-to-be-used-for-customs-declarations.">Response:<br />
Get the "proforma" invoice to be used for customs declarations.</h3>
<a href="https://global-selling.mercadolibre.com/devsite/manage-sales-global-selling">Learn more.</a>
</div>
</div></td>
</tr>
</tbody>
</table>

  

## Order status

Order statuses are the following:

| Status                   | Description                                                          |
|--------------------------|----------------------------------------------------------------------|
| **payment\_required**    | Order payment should be confirmed to display user information.       |
| **payment\_in\_process** | There is an order-related payment, but it has not been credited yet. |
| **partially\_paid**      | The order have a credited associated payment, but it is not enough.  |
| **paid**                 | The order-related payment is credited.                               |
| **cancelled**            | For some reason, the order was not fulfilled.\*                      |
| **invalid**              | The order was invalidated as it came from a malicious buyer.         |

<div class="andes-message andes-message--neutral">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--neutral site-carriers__message-title">

Note:

</div>

<div class="andes-message__text--neutral site-carriers__message-text">

<div>

An order may be canceled due to the following reasons:  
- Payment approval was required to subtract stock, but, during the
approval process period, the item was paused/terminated due to stockout;
so, the payment is returned to the buyer.  
- Payment was required, but, as it was not paid within a specific
period, it was automatically canceled.  
- After making a transaction, for some reason the seller is banned from
the site.

</div>

</div>

</div>

</div>

  

## Search orders

You can use the /search functionality of the /orders resource to make
searches with filters. Note that /search does not perform any action if
it is not followed by a filter.

  

To consume this resource, make a call with GET method as shown in the
following curl:

``` language-javascript
curl -H 'Authorization: Bearer $ACCESS_TOKEN' -X GET https://api.mercadolibre.com/marketplace/orders/search
```

<div class="andes-message andes-message--neutral">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--neutral site-carriers__message-title">

Note:

</div>

<div class="andes-message__text--neutral site-carriers__message-text">

<div>

This request has a limit 100 request per minute.

</div>

</div>

</div>

</div>

Example:

``` language-javascript
curl -H 'Authorization: Bearer $ACCESS_TOKEN' -X GET https://api.mercadolibre.com/marketplace/orders/search
```

Cart order response:

``` language-javascript
{
            "id": 2000000580342535, -> Don't use it. Use the orders node id.
            "buyer": {
                "id": 116038996
            },
            "config": {
                "items": [
                    {
                        "id": "MLM759344664"
                    }
                ]
            },
            "orders": [
                {
                    "id": 2497671750, -> This is the order id you have to use.
                    "items": null,
                    "feedback": {
                        "purchase": null,
                        "sale": null
                    },
                    "payments": [
                        {
                            "id": 7032122688
                        }
                    ],
                    "mediations": [],
                    "seller": {
                        "id": 514048142
                    }
                }
            ],
            "shipment": {
                "id": 28504764933,
                "payments": []
            }
        }
```

Individual order response:

``` language-javascript
{
            "id": 2483140131,
            "buyer": {
                "id": 441782523
            },
            "config": {
                "items": [
                    {
                        "id": "MLM781272686"
                    }
                ]
            },
            "orders": [
                {
                    "id": 2483140131, -> this is the order id.
                    "items": null,
                    "feedback": {
                        "purchase": null,
                        "sale": null
                    },
                    "payments": [
                        {
                            "id": 6903805442
                        }
                    ],
                    "mediations": [
                        {
                            "id": 5022947125
                        }
                    ],
                    "seller": {
                        "id": 523132944
                    }
                }
            ],
            "shipment": {
                "id": 30041416576,
                "payments": []
            }
        }
```

<div class="andes-message andes-message--neutral">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--neutral site-carriers__message-title">

Note:

</div>

<div class="andes-message__text--neutral site-carriers__message-text">

<div>

Use the order ID´s from the orders node.

</div>

</div>

</div>

</div>

### Parameters

| Parameter  | Description                                                                   |
|------------|-------------------------------------------------------------------------------|
| **sort**   | Shows field you can use to sort results.                                      |
| **order**  | Shows order direction you need to organize results with.                      |
| **limit**  | The limit of results requested, it has a maximum of 1000.                     |
| **offset** | Using the offset attribute, you can move the lower limit of the result block. |

  

## Search orders with filters

Search orders using limit filter resource allows to restrict results.
You should make a call using GET method like this:

  

Request:

``` language-javascript
curl -H 'Authorization: Bearer $ACCESS_TOKEN' -X GET  https://api.mercadolibre.com/marketplace/orders/search?buyer=$BUYER_ID&limit=$LIMIT
```

Example:

``` language-javascript
curl -H 'Authorization: Bearer $ACCESS_TOKEN' -X GET https://api.mercadolibre.com/marketplace/orders/search?buyer=441782523&limit=50
```

Response:

``` language-javascript
{
   "query":"",
   "results":[
      {
         "id":2194210960,
         "buyer":{
            "id":441782523
         },
         "config":{
            "items":[
               {
                  "id":"MLM733232983"
               }
            ]
         },
         "orders":[
            {
               "id":2194210960,
               "items":null,
               "feedback":{
                  "purchase":null,
                  "sale":null
               },
               "payments":[
                  {
                     "id":5384783409
                  }
               ],
               "mediations":[
                  {
                     "id":1041550651
                  }
               ]
            }
         ],
         "shipment":{
            "id":28140042692,
            "payments":[

            ]
         }
      },
      {
         "id":2194336280,
         "buyer":{
            "id":441782523
         },
         "config":{
            "items":[
               {
                  "id":"MLM733232983"
               }
            ]
         },
         "orders":[
            {
               "id":2194336280,
               "items":null,
               "feedback":{
                  "purchase":null,
                  "sale":null
               },
               "payments":[
                  {
                     "id":5384748271
                  }
               ],
               "mediations":[
                  {
                     "id":5007508763
                  }
               ]
            }
         ],
         "shipment":{
            "id":28139907607,
            "payments":[

            ]
         }
      }
   ],
   "sort":{
      "id":"date_asc",
      "name":"Date ascending"
   },
   "available_sorts":[
      {
         "id":"date_desc",
         "name":"Date descending"
      }
   ],
   "filters":[],
   "paging":{
      "total":2,
      "limit":50
   }
}
```

### Parameters

| Parameter              | Description                                                                                                                            |
|------------------------|----------------------------------------------------------------------------------------------------------------------------------------|
| **buyer**              | To search orders by certain buyer.                                                                                                     |
| **seller.id**          | To search orders by certain seller.                                                                                                    |
| **order.status**       | To search orders by certain status (paid, cancelled, payment\_required, paid).                                                         |
| **site**               | To search orders of country shown in site (MLM, MLB, MLC).                                                                             |
| **limit**              | To reduce page size changing number of results to show in each page. If not stated, 50 results will be brought -maximum allowed value. |
| **offset**             | Using the offset attribute, you can move the lower limit of the result block.                                                          |
| **date\_created.from** | To search from a certain order creation date.                                                                                          |
| **date\_created.to**   | To search for orders created up to a certain date.                                                                                     |
| **last\_updated.from** | To search from a certain order update date.                                                                                            |
| **last\_updated.to**   | To search for orders updated up to a certain date.                                                                                     |
| **date\_closed.from**  | To search from a certain closing date.                                                                                                 |
| **date\_closed.to**    | To search for orders closed until a certain date.                                                                                      |
| **mediations.stage**   | It can be some status separated by ','.                                                                                                |

  

### Available date formats

-   yyyy-MM (eg 1997-07)
-   yyyy-MM-dd (eg 1997-07-16)
-   yyyy-MM-ddThh (eg 1997-07-16T19)
-   yyyy-MM-ddThh:mm (eg 1997-07-16T19:20)
-   yyyy-MM-ddThh:mm:ss (eg 1997-07-16T19:20:30)
-   yyyy-MM-ddThh:mm:ss.ms (eg 1997-07-16T19:20:30.45)
-   yyyy-MM-ddThh:mm:ss.ms-TZD (eg 1997-07-16T19:20:30.45-01:00)

### Available sorts

Search orders can receive parameters with which you can sort the search
results by dates. The available sorts parameters are:

| Sort              | Description             |
|-------------------|-------------------------|
| **date\_asc**     | Date ascending          |
| **date\_desc**    | Date descending         |
| **updated\_asc**  | Last updated ascending  |
| **updated\_desc** | Last updated descending |
| **closed\_asc**   | Date close ascending    |
| **closed\_desc**  | Date close descending   |

  

### Errors

| HTTP Code | Error                         | Message                                                  |
|-----------|-------------------------------|----------------------------------------------------------|
| **403**   | forbidden                     | Invalid caller.id                                        |
| **403**   | forbidden                     | Can not identify the user                                |
| **404**   | not\_found                    | Resource not found                                       |
| **500**   | internal\_server\_error       | Oops! Something went wrong...                            |
| **401**   | not\_found                    | invalid\_token                                           |
| **400**   | bad\_request                  | Malformed access\_token: TOKEN\_NOT\_VALID               |
| **400**   | bad\_request                  | Param not valid                                          |
| **451**   | unavailable.for.legal.reasons | The requested user is not available due to legal reasons |

  

## Get an order

<div class="andes-message andes-message--highlight">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--highlight site-carriers__message-title">

Important:

</div>

<div class="andes-message__text--highlight site-carriers__message-text">

<div>

We will no longer provide personal seller and buyer data in the GET
response of Orders with Mercado Envíos 2, as it is possible [check the
/users
endpoint](https://global-selling.mercadolibre.com/devsite/manage-users-global-selling#user-private-information).

</div>

</div>

</div>

</div>

For implementation, make a request with GET method as shown below:

  

Request:

``` language-javascript
curl -H 'Authorization: Bearer $ACCESS_TOKEN' -X GET https://api.mercadolibre.com/marketplace/orders/$ORDER_ID
```

Example:

``` language-javascript
curl -H 'Authorization: Bearer $ACCESS_TOKEN' -X GET https://api.mercadolibre.com/marketplace/orders/2000003508419013
```

Response:

``` language-javascript
{
    "id": 2000003508419013,
    "date_created": "2020-01-31T18:03:35.000-04:00",
    "date_closed": "2020-01-31T18:03:36.000-04:00",
    "last_updated": "2020-01-31T18:03:36.000-04:00",
    "manufacturing_ending_date": null,
    "feedback": {
        "sale": null,
        "purchase": null
    },
    "mediations": [],
    "comments": null,
    "pack_id": null,
    "pickup_id": null,
    "order_request": {
        "return": null,
        "change": null
    },
    "fulfilled": null,
    "paid_amount": 15.1,
    "coupon": {
        "id": null,
        "amount": 0
    },
    "expiration_date": "2020-05-10T18:03:36.000-04:00",
    "order_items": [
        {
            "item": {
                "id": "MLM754639529",
                "title": "Elemento De Prueba - Para Pruebas De Carga",
                "category_id": "MLM71792",
                "variation_id": null,
                "seller_custom_field": null,
                "variation_attributes": [],
                "condition": "new",
                "seller_sku": null,
                "parent_item_id": "CBT910504819"
            },
            "quantity": 1,
            "unit_price": 15.1,
            "full_unit_price": 15.1,
            "currency_id": "USD",
            "manufacturing_days": null,
            "sale_fee": 2.64,
            "base_exchange_rate": 19.25
        }
    ],
    "currency_id": "USD",
    "payments": [
        {
            "id": 5855860136,
            "order_id": 2000003508419013,
            "payer_id": 441782523,
            "collector": {
                "id": 481240836
            },
            "card_id": 8738685222,
            "site_id": "MLM",
            "reason": "Elemento De Prueba - Para Pruebas De Carga",
            "payment_method_id": "amex",
            "currency_id": "USD",
            "installments": 1,
            "issuer_id": "157",
            "atm_transfer_reference": {
                "company_id": null,
                "transaction_id": "1234567"
            },
            "coupon_id": null,
            "activation_uri": null,
            "operation_type": "regular_payment",
            "payment_type": "credit_card",
            "available_actions": [
                "refund"
            ],
            "status": "approved",
            "status_code": null,
            "status_detail": "accredited",
            "transaction_amount": 15.1,
            "taxes_amount": 0,
            "shipping_cost": 0,
            "coupon_amount": 0,
            "overpaid_amount": 0,
            "total_paid_amount": 15.1,
            "installment_amount": 15.1,
            "deferred_period": null,
            "date_approved": "2020-01-31T18:03:36.000-04:00",
            "authorization_code": "1234567",
            "transaction_order_id": null,
            "date_created": "2020-01-31T18:03:36.000-04:00",
            "date_last_modified": "2020-01-31T18:03:36.000-04:00"
        }
    ],
    "shipping": {
        "id": 28237306862
    },
    "status": "paid",
    "status_detail": {
        "code": "",
        "description": null
    },
    "buyer": {
        "id": 441782523,
        "nickname": "TESTY0DT2NRL",
        "last_name": "Test",
        "first_name": "Test"
    },
    "seller": {
        "id": 481240836
    },
    "taxes": {
        "amount": 0,
        "currency_id": "USD"
    },
    "context": {
       "channel": "marketplace",
       "site": "MLM",
       "flows": [
           "cbt"
       ],
       "application": "purchases-api"
   }
}
```

We remove the data of buyer's billing info from the order. Please, check
this data by doing a [GET to
/orders/order\_id/billing\_info](https://global-selling.mercadolibre.com/devsite/gs-billing-data).

Orders have a lot of attributes. Below you will see a description of the
most important fields:

### Response fields

| Field                | Description                                                                                                                                                 |
|----------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **id**               | Unique order identifier.                                                                                                                                    |
| **date\_created**    | Order creation date.                                                                                                                                        |
| **date\_closed**     | Order confirmation date. It is set when an order status changes for the first time to confirmed / paid and the item is subtracted from the stock.           |
| **expiration\_date** | This is the deadline for the user to qualify since, after that date, the feedback is made visible, payments are released (if any), and charges are created. |
| **status**           | Order status. See [possible values](#Order-status).                                                                                                         |
| **currency\_id**     | You need to define a currency. You need to use USD. This one is also a mandatory attribute.                                                                 |
| **status\_detail**   | Status detail.                                                                                                                                              |
| **code**             | Status code.                                                                                                                                                |
| **description**      | Status description.                                                                                                                                         |
| **buyer**            | Buyer's information.                                                                                                                                        |
| **seller**           | Seller's information.                                                                                                                                       |
| **order\_items**     | Order item listings.                                                                                                                                        |
| **payments**         | Order-related payments.                                                                                                                                     |
| **feedback**         | Order-related feedback information.                                                                                                                         |
| **shipping**         | Shipping configuration for this order.                                                                                                                      |
| **total\_amount**    | Total invoice amount.                                                                                                                                       |
| **tags**             | List of seller selected tags, such as delivered, paid.                                                                                                      |
| **taxes**            | Amount with the sum of taxes to be paid from the order.                                                                                                     |

  

### Parameters

| Parameter     | Description              |
|---------------|--------------------------|
| **ORDER\_ID** | Unique order identifier. |

  

### Errors

| HTTP Code | Error                         | Message                                                  |
|-----------|-------------------------------|----------------------------------------------------------|
| **403**   | forbidden                     | Invalid caller.id                                        |
| **403**   | forbidden                     | Can not identify the user.                               |
| **404**   | not\_found                    | Resource not found.                                      |
| **500**   | internal\_server\_error       | Oops! Something went wrong...                            |
| **401**   | not\_found                    | invalid\_token                                           |
| **400**   | bad\_request                  | Malformed access\_token: TOKEN\_NOT\_VALID               |
| **400**   | bad\_request                  | Param not valid                                          |
| **451**   | unavailable.for.legal.reasons | The requested user is not available due to legal reasons |

  

As soon as you [receive an orders
notification](https://global-selling.mercadolibre.com/devsite/receive-notifications#orders),
with the order ID you get the information making a request to the
/marketplace/orders resource ([get an order](#Get-an-order-detail)).
Then, with the shipping ID you can identify the logistics
(logistic\_type and mode) by consulting the /marketplace/shipments
resource ([get shippment
details](https://global-selling.mercadolibre.com/devsite/manage-shipments#Receive-a-shipment)).
With this information, you will know what steps you should take next
depending on each [shipping
method](https://global-selling.mercadolibre.com/devsite/manage-shipments?nocache=true#Shipping-methods).

\*The error 404 can occur when trying to query a pack\_id with the
orders resource. Please [review how to Manage Cart
Orders](https://global-selling.mercadolibre.com/devsite/packs).

  

## Fraud alerts (stop shipping)

After the payment approval, and due to the relationship with banks and
cards, we may receive an alert that the order is a fraud and to avoid a
financial expense, you shouldn´t send the merchandise to the buyer.  
In this case, **or order is marked with the tag
"fraud\_risk\_detected"** and we send a notification with the topic
"orders\_v2" with the ID of this order.  
Once identified, the order must be canceled. Case the seller has already
been sent products, it will be necessary to check or send it through the
Mercado Libre or Mercado Pago sites.

  

## Invoice

Get the "proforma" invoice to be used for customs declarations.

  

Request:

``` language-javascript
curl -H 'Authorization: Bearer $ACCESS_TOKEN' -X GET https://api.mercadolibre.com/marketplace/orders/$ORDER_ID/invoice
```

Example:

  
<img src="https://http2.mlstatic.com/storage/developers-site-cms-admin/DevSite/324278889017-invoice-global-selling-example.png" class="content__image" />  

## Add product information

<div class="andes-message andes-message--highlight">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--highlight site-carriers__message-title">

Important:

</div>

<div class="andes-message__text--highlight site-carriers__message-text">

<div>

Providing the IMEI number is now mandatory for cell phone purchases in
the Colombian market. Please update your application accordingly.

</div>

</div>

</div>

</div>

Due to regulations in the Colombian market, it will be mandatory to
include the IMEI number (IMEI stands for International Mobile Equipment
Identity. It is a unique 15-digit number assigned to every mobile phone
and smartphone.) on the label when buyers from this market purchase
mobile phones. For this purpose, items associated with the category ID
MCO1055 are considered cell phone purchases. To comply with this
requirement, we have made available a writing resource on the label that
allows for the inclusion of the IMEI number of the mobile phone being
shipped in the package. For implementation, make a request with POST
method as shown below:

  

Request:

``` language-javascript
curl -X POST -H 'Authorization: Bearer $ACCESS_TOKEN' \
-d '{
   "name": "IMEI",
 "value": "1234567890ABCDE"
 }'
https://api.mercadolibre.com/marketplace/orders/$ORDER_ID/attributes
```

Example:

``` language-javascript
curl -X POST -H 'Authorization: Bearer $ACCESS_TOKEN' \
-d '{
   "name": "IMEI",
 "value": "1H24HD121H24HD1"
 }'
https://api.mercadolibre.com/marketplace/orders/2000003508419223/attributes
```

Response: Status Code 201

``` language-javascript
{
   "status": "success"
 }
```

### Errors

| HTTP Code | Error           | Message                                              |
|-----------|-----------------|------------------------------------------------------|
| **400**   | Invalid order   | We can only update product from category \[MCO1055\] |
| **400**   | Invalid request | IMEI must be 15 digits long.                         |
| **400**   | Invalid request | Must specify valid attribute name.                   |

  

**Next**:
[Shipments](https://global-selling.mercadolibre.com/devsite/manage-shipments).

  

</div>
