<div class="inner-content">

## Communications

With the **/communications/notices** resource you can access all
**current and specific** communications sent by Mercado Libre to each
seller and integrator, including:

-   **News**: improvements, new features, and policy updates.
-   **Alerts**: urgent notifications about regularization needs,
    potential flow blocks (such as listing, selling), operational
    changes, and service interruptions.
-   **Releases**: communications about new tools and features.
-   **Training and Events**: announcements of educational opportunities,
    training sessions, and webinars.
-   **Advertising**: promotions and commercial campaigns of interest.

  

<div class="andes-message andes-message--highlight">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--highlight site-carriers__message-title">

Important:

</div>

<div class="andes-message__text--highlight site-carriers__message-text">

<div>

All types of communications can generate an action and direct users to
log into their Mercado Libre account. It is essential to highlight these
news in a visible space so that both sellers and integrators can easily
access the information.

</div>

</div>

</div>

</div>

  
<img src="https://http2.mlstatic.com/storage/developers-site-cms-admin/DevSite/280788298615-novedades.png" width="885" height="450" alt="Seller News Screenshot" />  
  

## Get news

Communications are specific to each user. Therefore:

-   To receive communications directed to sellers, use each seller's
    access token.
-   To access communications, updates, or alerts related to your
    integration, you must make the query with the access token of the
    application owner user. That is, you must self-grant permission to
    your own application and obtain a valid access token.

  

<div class="andes-message andes-message--neutral">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--neutral site-carriers__message-title">

Note:

</div>

<div class="andes-message__text--neutral site-carriers__message-text">

<div>

The news are ordered by creation date, in descending order and you will
only see those in force at the time of consultation.

</div>

</div>

</div>

</div>

  

### Optional parameters

-   **limit**: Maximum number of communications to be received.
    Default: 20.
-   **offset**: If the total is greater than the limit, the offset is
    used for paging. Default: 0.

  

Request:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/communications/notices?limit=$LIMIT&offset=$OFFSET
```

Example:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/communications/notices?limit=20&offset=0
```

Response for seller communications:

``` language-javascript
{
  "paging": {
      "total": 2,
      "offset": 0,
      "limit": 20
  },
  "results": [
      {
          "actions": [
              {
                  "text": "More information",
                  "link": "https://global-selling.mercadolibre.com/devsite/seller-news"
              },
              {
                  "text": "Give feedback",
                  "link": "https://www.mercadolivre.com.br/novidades"
              }
          ],
          "id": "3691",
          "label": "Welcome integrators to the news center! test 2",
          "description": "<p><strong>We are making CDN information available to all integrators since June.</strong> Get ready to be more informed than ever of the latest MeLi news.</p>\n",
          "highlighted": true,
          "from_date": "2021-07-12T15:00:00.000Z",
          "tags": [
              {
                  "tag": "BLACK_FRIDAY",
                  "type": "EVENTS"
              },
              {
                  "tag": "BILLING",
                  "type": "BILLING"
              },
              {
                  "tag": "SHIPPING_GENERIC",
                  "type": "SHIPPING"
              }
          ]
      },
      {
          "actions": [
              {
                  "text": "More information",
                  "link": "https://global-selling.mercadolibre.com/devsite/seller-news"
              },
              {
                  "text": "Give feedback",
                  "link": "https://www.mercadolivre.com.br/novidades"
              }
          ],
          "id": "3446",
          "label": "Welcome integrators to the news center!",
          "description": "<p>We are making CDN information available to all integrators since June. Get ready to be more informed than ever of the latest MeLi news.</p>\n",
          "highlighted": true,
          "from_date": "2021-07-15T15:00:00.000Z",
          "tags": [
              {
                  "tag": "COVID",
                  "type": "EVENTS"
              },
              {
                  "tag": "SHIPPING_GENERIC",
                  "type": "SHIPPING"
              }
          ]
      }
  ]
}
```

  

Response for integrator communications:

``` language-javascript
{
  "paging": {
      "total": 1,
      "offset": 0,
      "limit": 20
  },
  "results": [
      {
          "actions": [
              {
                  "text": "View documentation",
                  "link": "https://global-selling.mercadolibre.com/devsite/authentication-and-authorization"
              }
          ],
          "id": "18168",
          "label": "Review request",
          "description": "<p>We have identified that your integration currently sends the access token through query parameters, a practice considered vulnerable according to WebSec recommendations. For this reason, we will soon begin rejecting requests that do not send the token via header, responding with a 301 error. To avoid issues with your integration, we ask you to update the sending method as soon as possible.</p>",
          "highlighted": false,
          "from_date": "2025-02-12T03:00:00.000Z",
          "tags": [],
          "dismiss_key": "public-dismiss_1410022527_18168",
          "title": "Review request"
      }
  ]
}
```

  

## Response fields

**paging**: results paging format.

-   **total**: The total results found.
-   **offset**: Index of the result from which you want to obtain. Ex:
    With 100 news in total, using a limit of 20. If you want to see the
    second page, send offset = 20 and it will show results from 20
    to 39.
-   **limit**: The maximum number of results to display on a single
    page.

**results**: list of news.

-   **actions** (optional): list with actions.
    -   **text**: text of the action.
    -   **link**: link of the action.
-   **id**: communication identification.
-   **label**: title of the communication.
-   **description**: communication description.
-   **highlighted**: indicates if the news is highlighted in Mercado
    Libre or not.
-   **from\_date**: date in ISO format, indicates the creation of the
    novelty.
-   **tags**: with the following tag you identify the types of
    communications.
-   **category** and **sub\_category**: allow organizing and grouping
    news, facilitating identification, analysis, and timely
    decision-making.
    -   **ALERT** (Alert)
        -   Blocking
        -   Requirement
        -   Restriction
        -   Warning
    -   **NEW** (News)
        -   Operational contingency
        -   Pre-moderation notice
        -   Business rule change
        -   Other type
    -   **RELEASE** (Release)
        -   New product or feature
        -   Existing product improvement
        -   Other type
    -   **PUBLICITY** (Advertising)
    -   **MODAL** (Modal)
    -   **OPPORTUNITY** (Training or event)

You can also group them by sites, publications, shipping, attention,
billing, and events.

The **type** and their corresponding **Tag**.

**Attention**

-   METRICS: Metrics
-   CANCELLATIONS: Cancellations
-   RETURNS: Returns

**Shipping**

-   SHIPPING\_GENERIC: Shipping
-   SHIPPING: Mercado Envíos
-   SHIPPING\_XD: Mercado Envíos colecta
-   FLEX: Flex
-   FULL: Full
-   SHIPPING\_CARRIER: Mercado Envíos Partnered Carrier

**Events**

-   CHRISTMAS: Christmas
-   BLACK\_FRIDAY: Black Friday
-   HOT\_SALE: Hot Sale
-   CYBER\_MONDAY: Cyber Monday
-   COVID: COVID-19

**Billing**

-   COSTS: Costs
-   BILLING: Billing
-   TRANSMITTER: Invoice (NF-e) issuer

**Sites**

-   MCO: Colombia
-   MLC\_FULFILLMENT: Chile - Full
-   MLC\_REMOTE: Chile
-   MLB: Brasil
-   MLM\_REMOTE: México
-   MLM\_FULFILLMENT: México - Full

**Publications**

-   PUBLICATIONS: Publications
-   PROMOTIONS\_CENTRAL: Promotions central
-   CATALOG: Catalog

  

## Errors

The following table describes the possible errors when using invalid
parameters:

| Status Code | Code         | Message                 | Solution                                                   |
|-------------|--------------|-------------------------|------------------------------------------------------------|
| 400         | bad\_request | limit must be numeric.  | Ensure the `limit` parameter is a positive integer value.  |
| 400         | bad\_request | offset must be numeric. | Ensure the `offset` parameter is a positive integer value. |

  

## Next

Learn more about seller metrics and reputation:

-   [Seller reputation](seller-reputation-global-selling)

</div>
