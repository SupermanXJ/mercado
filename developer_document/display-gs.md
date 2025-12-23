<div class="inner-content">

## Display Ads

<div class="andes-message andes-message--highlight">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--highlight site-carriers__message-title">

Important:

</div>

<div class="andes-message__text--highlight site-carriers__message-text">

<div>

Display is a service enabled by Commercial Advisors from Mercado Livre.

</div>

</div>

</div>

</div>

<div class="details__message">

Its goal is to improve advertisers' ability to understand and optimize
the performance of their advertising campaigns. You can access relevant
and updated information automatically, allowing advertisers to
efficiently integrate data for analysis and comparison. Sellers,
agencies, and brands can:

-   Show ads for their products when their potential audience accesses
    one of the platforms in the Mercado Livre ecosystem.
-   Choose the audience to whom to display their ads (targeting).
-   Create ads tailored to various advertising spaces quickly.
-   Show ads to users at different moments in the purchasing phase.
-   Establish variable costs based on campaign goals instead of fixed
    costs per impression.

</div>

![](https://http2.mlstatic.com/storage/developers-site-cms-admin/DevSite/178175888822-extraLarge--1-.png)  

## Consult advertiser

Advertisers (advertiser\_id) are those who invest a budget for the
creation and distribution of ads, with the aim of promoting their
products or services. Check the list of advertisers that have access to
a user, according to the type of product required.

  

**Required parameters**

**product\_id**: product type DISPLAY (Display Ads).

  

**Optional parameters**

**sort\_by**: sorts by attribute (advertiser\_id, site\_id). Default is
advertiser\_id.  

**sort\_order**: order (asc, desc). Default is desc.

  

Request:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' -H 'Content-Type: application/json' -H 'Api-Version: 1' 
https://api.mercadolibre.com/advertising/advertisers?product_id=$PRODUCT_ID
```

Ejemplo:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' -H 'Content-Type: application/json' -H 'Api-Version: 1' 
https://api.mercadolibre.com/advertising/advertisers?product_id=DISPLAY
```

Response:

``` language-javascript
{
    "advertisers": [
        {
            "advertiser_id": 000,
            "site_id": "MLB",
            "advertiser_name": "Advertiser AAA",
            "account_name": "MLB - XZY"
        },
        {
            "advertiser_id": 111,
            "site_id": "MLM",
            "advertiser_name": "Advertiser BBB",
            "account_name": "MLM - XYZ"
        },
        {
            "advertiser_id": 222,
            "site_id": "MLA",
            "advertiser_name": "Advertiser CCC",
            "account_name": "MLA - XYZ"
        },
        {
            "advertiser_id": 333,
            "site_id": "MLC",
            "advertiser_name": "Advertiser DDD",
            "account_name": "MLC - XYZ"
        }
    ]
}
```

### Response fields

**advertiser\_id**: advertiser identifier. You will use it for the rest
of the requests.  
**site\_id**: country identifier. Check the [nomenclature of Mercado
Libre sites and their respective
currencies](https://api.mercadolibre.com/sites).  
**advertiser\_name**: name of the advertiser.  
**account\_name**: name of the account.  

<div class="andes-message andes-message--neutral">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--neutral site-carriers__message-title">

Nota:

</div>

<div class="andes-message__text--neutral site-carriers__message-text">

<div>

If you receive the error 404 - No permissions found for user\_id, it
means that the user has not enabled the product and should contact their
Commercial Advisor to manage access to their advertisers.

</div>

</div>

</div>

</div>

  

## Consult campaigns of an advertiser

### Optional parameters

**sort\_by**: sort by attribute (id, name, start\_date, end\_date).
Default is id.  
**sort\_order**: order (asc, desc). Default is desc.  

  

Request:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' -H "Content-Type: application/json" -H "Api-Version: 1" 
https://api.mercadolibre.com/advertising/advertisers/$ADVERTISER_ID/display/campaigns
```

Example:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' -H "Content-Type: application/json" -H "Api-Version: 1" 
https://api.mercadolibre.com/advertising/advertisers/61/display/campaigns
```

Response:

``` language-javascript
{
 "results": [
    {
      "id": 80,
      "name": "CONVERSION_ENERO2022_MLA",
      "start_date": "2022-01-12T17:00:00",
      "end_date": "2022-01-31T23:59:00",
      "advertiser_id": 61,
      "type": "GUARANTEED",
      "status": "paused",
      "site_id": "MLA",
      "goal": "guaranteed"
    }
  ]
}
```

### Response fields

**id**: campaign id. Use the id to consult campaign metrics.  
**name**: campaign name.  
**start\_date**: campaign start date.  
**end\_date**: campaign end date.  
**advertiser\_id**: advertiser id  
**type**: campaign type: Programmatic or Guaranteed.  
**status**: campaign status.  
**site\_id**: country.  
**goal**: It is the advertising goal you set for your campaign when you
created it.  
  

## Types of campaigns and objectives

There are two modalities to show Display Ads:

-   Programmatic mode: advertisers participate in real-time automated
    auctions with a variable bid value according to the relevance of the
    location to the campaign objectives.

-   Guaranteed mode: the display ads are contracted directly with a
    Mercado Livre agent and the spaces are secured for a fixed cost.

      

    | Campaign Type    | Objective                                                                                     | Key Metrics                                                                                                                                                                  |
    |------------------|-----------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | **Programmatic** | **Awareness**: increases the exposure of a brand or product among the users of your interest. | **Reach and frequency** : allow measuring how many users you reached with your ads and how many times they saw them in a determined period. \*With creative video available. |
    | **Programmatic** | **Consideration**: increases visits and user actions on a brand or product.                   | **Clicks and VPP**: allow measuring how many times your ads were clicked and how many visits they generated on the product page.                                             |
    | **Programmatic** | **Conversion**: increases the sales of your brand's products with advertising.                | **Tickets and sales**: allow quantifying the sales generated after users view or click on your ads.                                                                          |
    | **Guaranteed**   | **Guaranteed**: Are created and managed by the Mercado Livre operations team.                 | Allows planning and buying a certain number of impressions at a fixed CPM.                                                                                                   |

    ## Metrics of a campaign

    <div class="andes-message andes-message--highlight">

    <img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />
    <div class="andes-message__content">

    <div
    class="andes-message__title andes-message__title--highlight site-carriers__message-title">

    Important:

    </div>

    <div
    class="andes-message__text--highlight site-carriers__message-text">

    <div>

    The date range for all metrics endpoints **cannot exceed 90 days**.
    If the range between *date\_from* and *date\_to* exceeds this limit,
    the API will return a *400 Bad Request* error.

    </div>

    </div>

    </div>

    </div>

    The results of this endpoint will be the metrics by day and a
    summary of the campaign period. You can query up to 90 days back,
    considering September 1, 2022, as the start date.

      

    **Required parameters**

    **date\_from**: date from the query in format YYYY-MM-DD.  
    **date\_to**: date until the query in format YYYY-MM-DD.  

      

    **Optional parameters**

    **sort\_by**: sort by attribute: id, name, start\_date, end\_date.
    By default, it is id.  
    **sort\_order**: ascending (asc) or descending (desc) order. By
    default, it is desc.  

      

    Request:

    ``` language-javascript
    curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' -H "Content-Type: application/json" -H "Api-Version: 1" 
    https://api.mercadolibre.com/advertising/advertisers/$ADVERTISER_ID/display/campaigns/$CAMPAIGN_ID/metrics?date_from=YYYY-MM-DD&date_to=YYYY-MM-DD
    ```

    Example:

    ``` language-javascript
    curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' -H "Content-Type: application/json" -H "Api-Version: 1" 
    https://api.mercadolibre.com/advertising/advertisers/11111/display/campaigns/80/metrics?date_from=2024-04-01&date_to=2024-04-15
    ```

    Response:

    ``` language-javascript
    {
      "metrics": [
        {
          "date": "2024-02-01",
          "site_id": "MLM",
          "currency": "MXN",
          "prints": 17961,
          "clicks": 186,
          "active_views": 0,
          "completed_views": 0,
          "reach": 10079,
          "ctr": 0.01,
          "consumed_budget": 57449.13,
          "cpm": 3198.55,
          "cpc": 308.87,
          "average_frequency": 1148.98,
          "event_time": {
            "cpa_order": 1083.95,
            "cpa_ppv": 135.81,
            "roas": 10.03,
            "units_quantity": 75,
            "direct_amount": 576150,
            "direct_item_quantity": 53,
            "attribution_ppv": 423,
            "attribution_add_to_cart": 26,
            "attribution_bookmark": 33,
            "attribution_checkout": 24,
            "attribution_leads": 0,
            "cpl": 0.0
          },
          "touch_point": {
            "cpa_order": 1148.98,
            "cpa_ppv": 125.16,
            "roas": 12.36,
            "units_quantity": 70,
            "direct_amount": 710324,
            "direct_item_quantity": 50,
            "attribution_ppv": 459,
            "attribution_add_to_cart": 26,
            "attribution_bookmark": 35,
            "attribution_checkout": 28,
            "attribution_leads": 0,
            "cpl": 0.0
          }
        }
      ],
      "summary": {
        "site_id": "MLM",
        "currency": "MXN",
        "prints": 170462,
        "clicks": 2033,
        "active_views": 0,
        "completed_views": 0,
        "reach": 48957,
        "ctr": 0.01,
        "consumed_budget": 605406.93,
        "cpm": 3551.57,
        "cpc": 297.79,
        "average_frequency": 1509.74,
        "event_time": {
          "cpa_order": 1513.52,
          "cpa_ppv": 128.59,
          "roas": 9.48,
          "units_quantity": 586,
          "direct_amount": 5741691,
          "direct_item_quantity": 400,
          "attribution_ppv": 4708,
          "attribution_add_to_cart": 263,
          "attribution_bookmark": 375,
          "attribution_checkout": 219,
          "attribution_leads": 0,
          "cpl": 0.0
        },
        "touch_point": {
          "cpa_order": 1509.74,
          "cpa_ppv": 125.66,
          "roas": 9.49,
          "units_quantity": 586,
          "direct_amount": 5746421,
          "direct_item_quantity": 401,
          "attribution_ppv": 4818,
          "attribution_add_to_cart": 270,
          "attribution_bookmark": 352,
          "attribution_checkout": 225,
          "attribution_leads": 0,
          "cpl": 0.0
        }
      }
    }
    ```

    ## Line items of a campaign

    Line items are more specific settings within a campaign that allow
    you to define different instructions or rules for displaying ads.
    The line item defines the ad purchase parameters: the user profile
    you want to reach, their geographic location, the device from which
    they browse, among others. Each line item is associated with a
    single campaign and consumes its budget.

      

    Line items allow including different audiences, budgets, creatives,
    and impression frequency within the same campaign. This gives more
    variety and flexibility to bid on ad display opportunities.

      

    ### Optional parameters

    **sort\_by**: possible values: id, name, start\_date, end\_date.  
    **sort\_order**: possible values: asc, desc.

      

    Request:

    ``` language-javascript
    curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' -H "Content-Type: application/json" -H "Api-Version: 1" 
    https://api.mercadolibre.com/advertising/advertisers/$ADVERTISER_ID/display/campaigns/$CAMPAIGN_ID/line_items?sort_by=start_date&sort_order=asc
    ```

    Example:

    ``` language-javascript
    curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' -H "Content-Type: application/json" -H "Api-Version: 1" 
    https://api.mercadolibre.com/advertising/advertisers/123456/display/campaigns/987654/line_items?sort_by=start_date&sort_order=asc
    ```

    Resposta:

    ``` language-javascript
    {
     "results": [
        {
          "line_item_id": 1,
          "name": "Name_Line_Item_Test",
          "start_date": "2022-01-12T17:00:00",
          "end_date": "2022-01-31T23:59:00",
          "campaing_id": 987654,
          "type": "Social",
          "status": "paused"
        }
      ]
    }
    ```

    ### Response fields

    **line\_item\_id**: id of the line item.  
    **name**: name of the line item.  
    **start\_date**: start date of the line item.  
    **end\_date**: end date of the line item.  
    **type**: type of line item. Varies according to the assigned
    creative.

    -   **Display**: Native banner image and text. Suitable for
        different advertising spaces on Mercado Livre and Mercado Pago.
    -   **Social**: vertical format video with bottom banner. Available
        for Mercado Livre Clips spaces.
    -   **Video**: horizontal format video. Available for streaming
        platforms integrated with Mercado Ads. This type of line item is
        only enabled for campaigns with the Awareness objective.

    **status**: status of the line item.

      

    ## Line Item Metrics

    The results of this endpoint will be the metrics by day and a
    summary of the campaign period. You can query up to 90 days back,
    considering September 1, 2022, as the starting date.

      

    ### Mandatory parameters

    **dimension**: type of metric: line\_items.  
    **date\_from**: date from the query in YYYY-MM-DD format.  
    **date\_to**: date to the query in YYYY-MM-DD format.

      

    ### Optional parameters

    **campaign\_id**: id of the campaign.  
    **ids**: list of ids of the dimension to consult, separated by
    commas..  

      

    Request:

    ``` language-javascript
    curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' -H "Content-Type: application/json" -H "Api-Version: 1" 
    https://api.mercadolibre.com/advertising/advertisers/$ADVERTISER_ID/display/metrics?dimension=line_items&date_from=YYYY-MM-DD&date_to=YYYY-MM-DD&campaign_id=$CAMPAIGN_ID
    ```

    Example:

    ``` language-javascript
    curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' -H "Content-Type: application/json" -H "Api-Version: 1" 
    https://api.mercadolibre.com/advertising/advertisers/0000/display/metrics?dimension=line_items&date_from=2024-09-19&date_to=2024-09-19&campaign_id=1111
    ```

    Response:

    ``` language-javascript
    [
        {
            "campaign_id": 1111,
            "line_item_id": 010101,
            "metrics": [
                {
                    "date": "2024-09-19",
                    "site_id": "MLM",
                    "currency": "MXN",
                    "prints": 2460,
                    "clicks": 20,
                    "active_views": 388,
                    "completed_views": 55,
                    "reach": 2091,
                    "ctr": 0.01,
                    "consumed_budget": 423.01,
                    "cpm": 171.96,
                    "cpc": 21.15,
                    "average_frequency": 0.0,
                    "event_time": {
                        "cpa_order": 0.0,
                        "cpa_ppv": 28.2,
                        "roas": 0.0,
                        "units_quantity": 0,
                        "direct_amount": 0.0,
                        "direct_item_quantity": 0,
                        "attribution_ppv": 15,
                        "attribution_add_to_cart": 0,
                        "attribution_bookmark": 9,
                        "attribution_checkout": 0,
                        "attribution_leads": 0,
                        "cpl": 0.0
                    },
                    "touch_point": {
                        "cpa_order": 0.0,
                        "cpa_ppv": 17.63,
                        "roas": 0.0,
                        "units_quantity": 0,
                        "direct_amount": 0.0,
                        "direct_item_quantity": 0,
                        "attribution_ppv": 24,
                        "attribution_add_to_cart": 2,
                        "attribution_bookmark": 9,
                        "attribution_checkout": 0,
                        "attribution_leads": 0,
                        "cpl": 0.0
                    }
                },
                {
                    "date": "2024-09-20",
                    "site_id": "MLM",
                    "currency": "MXN",
                    "prints": 2907,
                    "clicks": 23,
                    "active_views": 511,
                    "completed_views": 73,
                    "reach": 2475,
                    "ctr": 0.01,
                    "consumed_budget": 494.54,
                    "cpm": 170.12,
                    "cpc": 21.5,
                    "average_frequency": 0.0,
                    "event_time": {
                        "cpa_order": 0.0,
                        "cpa_ppv": 26.03,
                        "roas": 0.0,
                        "units_quantity": 0,
                        "direct_amount": 0.0,
                        "direct_item_quantity": 0,
                        "attribution_ppv": 19,
                        "attribution_add_to_cart": 1,
                        "attribution_bookmark": 4,
                        "attribution_checkout": 0,
                        "attribution_leads": 0,
                        "cpl": 0.0
                    },
                    "touch_point": {
                        "cpa_order": 0.0,
                        "cpa_ppv": 24.73,
                        "roas": 0.0,
                        "units_quantity": 0,
                        "direct_amount": 0.0,
                        "direct_item_quantity": 0,
                        "attribution_ppv": 20,
                        "attribution_add_to_cart": 1,
                        "attribution_bookmark": 6,
                        "attribution_checkout": 0,
                        "attribution_leads": 0,
                        "cpl": 0.0
                    }
                }
            ],
            "summary": {
                "site_id": "MLM",
                "currency": "MXN",
                "prints": 5367,
                "clicks": 43,
                "active_views": 899,
                "completed_views": 128,
                "reach": 4477,
                "ctr": 0.01,
                "consumed_budget": 917.55,
                "cpm": 170.96,
                "cpc": 21.34,
                "average_frequency": 0.0,
                "event_time": {
                    "cpa_order": 0.0,
                    "cpa_ppv": 26.99,
                    "roas": 0.0,
                    "units_quantity": 0,
                    "direct_amount": 0.0,
                    "direct_item_quantity": 0,
                    "attribution_ppv": 34,
                    "attribution_add_to_cart": 1,
                    "attribution_bookmark": 13,
                    "attribution_checkout": 0,
                    "attribution_leads": 0,
                    "cpl": 0.0
                },
                "touch_point": {
                    "cpa_order": 0.0,
                    "cpa_ppv": 20.85,
                    "roas": 0.0,
                    "units_quantity": 0,
                    "direct_amount": 0.0,
                    "direct_item_quantity": 0,
                    "attribution_ppv": 44,
                    "attribution_add_to_cart": 3,
                    "attribution_bookmark": 15,
                    "attribution_checkout": 0,
                    "attribution_leads": 0,
                    "cpl": 0.0
                }
            }
        }
    ]
    ```

      

    ## Line Item Creatives

    Creatives are the visual elements displayed in the available
    advertising spaces. In display ads, advertisers can generate their
    own creatives or select them from a library. A creative can be used
    in more than one item.

      

    ### Optional parameters

    **sort\_by**: possible values: id, name.  
    **sort\_order**: possible values: asc, desc.

      

    Request:

    ``` language-javascript
    curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' -H "Content-Type: application/json" -H "Api-Version: 1" 
    https://api.mercadolibre.com/advertising/advertisers/$ADVERTISER_ID/display/campaigns/$CAMPAIGN_ID/line_items/$LINE_ITEM_ID/creatives?sort_by=start_date&sort_order=asc
    ```

    Example:

    ``` language-javascript
    curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' -H "Content-Type: application/json" -H "Api-Version: 1" 
    https://api.mercadolibre.com/advertising/advertisers/0001/display/campaigns/999999/line_items/0000001/creatives?sort_by=start_date&sort_order=asc
    ```

    Response:

    ``` language-javascript
    {
        "results": [
            {
                "creative_id": 123456,
                "name": "Name_Creative_Test",
                "status": "active",
                "line_item_id": 0000001,
                "campaign_id": 999999
            }
        ]
    }
    ```

    ### Response fields

    **creative\_id**: id of the creative.  
    **name**: name of the creative.  
    **status**: status of the creative. It can be: Under review, active
    or rejected.  

    **line\_item\_id**: id of the line item.  
    **campaign\_id**: id of the campaign.

      

    <div class="andes-message andes-message--neutral">

    <img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />
    <div class="andes-message__content">

    <div
    class="andes-message__title andes-message__title--neutral site-carriers__message-title">

    Note:

    </div>

    <div
    class="andes-message__text--neutral site-carriers__message-text">

    <div>

    When you create a new creative, its status is "Under review". That
    is, before a creative starts to display, Mercado Livre must confirm
    that it meets the guidelines, policies, and that there are no
    errors. When the review is completed, the creative may change its
    status to "Approved" or "Rejected".

    </div>

    </div>

    </div>

    </div>

    ## Metrics of creatives

    The results of this endpoint will be the metrics by day and a
    summary for the line item's date range. You can see up to 90 days
    back, considering September 1, 2022, as the starting date.

      

    ### Mandatory parameters

    **dimension**: type of metric: creatives.  
    **date\_from**: date from the query in YYYY-MM-DD format.  
    **date\_to**: date until the query in YYYY-MM-DD format.  

      

    ### Optional parameters

    **ids**: list of ids of the dimension to consult.

      

    Request:

    ``` language-javascript
    curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' -H "Content-Type: application/json" -H "Api-Version: 1" 
    https://api.mercadolibre.com/advertising/advertisers/$ADVERTISER_ID/display/metrics?dimension=creatives&date_from=YYYY-MM-DD&date_to=YYYY-MM-DD&line_item_id=$LINE_ITEM_ID
    ```

    Example:

    ``` language-javascript
    curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' -H "Content-Type: application/json" -H "Api-Version: 1" 
    https://api.mercadolibre.com/advertising/advertisers/0000/display/metrics?dimension=creatives&date_from=2024-09-19&date_to=2024-09-20&line_item_id=4321
    ```

    Response:

    ``` language-javascript
    [
        {
            "campaign_id": 1111,
            "line_item_id": 4321,
            "creative_id": 3333,
            "metrics": [
                {
                    "date": "2024-09-19",
                    "site_id": "MLM",
                    "currency": "MXN",
                    "prints": 579,
                    "clicks": 3,
                    "active_views": 104,
                    "completed_views": 20,
                    "reach": 527,
                    "ctr": 0.01,
                    "consumed_budget": 99.52,
                    "cpm": 171.89,
                    "cpc": 33.17,
                    "average_frequency": 0.0,
                    "event_time": {
                        "cpa_order": 0.0,
                        "cpa_ppv": 0.0,
                        "roas": 0.0,
                        "units_quantity": 0,
                        "direct_amount": 0.0,
                        "direct_item_quantity": 0,
                        "attribution_ppv": 0,
                        "attribution_add_to_cart": 0,
                        "attribution_bookmark": 0,
                        "attribution_checkout": 0,
                        "attribution_leads": 0,
                        "cpl": 0.0
                    },
                    "touch_point": {
                        "cpa_order": 0.0,
                        "cpa_ppv": 33.17,
                        "roas": 0.0,
                        "units_quantity": 0,
                        "direct_amount": 0.0,
                        "direct_item_quantity": 0,
                        "attribution_ppv": 3,
                        "attribution_add_to_cart": 0,
                        "attribution_bookmark": 0,
                        "attribution_checkout": 0,
                        "attribution_leads": 0,
                        "cpl": 0.0
                    }
                },
                {
                    "date": "2024-09-20",
                    "site_id": "MLM",
                    "currency": "MXN",
                    "prints": 569,
                    "clicks": 0,
                    "active_views": 90,
                    "completed_views": 18,
                    "reach": 517,
                    "ctr": 0.0,
                    "consumed_budget": 96.42,
                    "cpm": 169.46,
                    "cpc": 0.0,
                    "average_frequency": 0.0,
                    "event_time": {
                        "cpa_order": 0.0,
                        "cpa_ppv": 0.0,
                        "roas": 0.0,
                        "units_quantity": 0,
                        "direct_amount": 0.0,
                        "direct_item_quantity": 0,
                        "attribution_ppv": 0,
                        "attribution_add_to_cart": 0,
                        "attribution_bookmark": 0,
                        "attribution_checkout": 0,
                        "attribution_leads": 0,
                        "cpl": 0.0
                    },
                    "touch_point": {
                        "cpa_order": 0.0,
                        "cpa_ppv": 96.42,
                        "roas": 0.0,
                        "units_quantity": 0,
                        "direct_amount": 0.0,
                        "direct_item_quantity": 0,
                        "attribution_ppv": 1,
                        "attribution_add_to_cart": 0,
                        "attribution_bookmark": 0,
                        "attribution_checkout": 0,
                        "attribution_leads": 0,
                        "cpl": 0.0
                    }
                }
            ],
            "summary": {
                "site_id": "MLM",
                "currency": "MXN",
                "prints": 1148,
                "clicks": 3,
                "active_views": 194,
                "completed_views": 38,
                "reach": 1037,
                "ctr": 0.0,
                "consumed_budget": 195.94,
                "cpm": 170.68,
                "cpc": 65.31,
                "average_frequency": 0.0,
                "event_time": {
                    "cpa_order": 0.0,
                    "cpa_ppv": 0.0,
                    "roas": 0.0,
                    "units_quantity": 0,
                    "direct_amount": 0.0,
                    "direct_item_quantity": 0,
                    "attribution_ppv": 0,
                    "attribution_add_to_cart": 0,
                    "attribution_bookmark": 0,
                    "attribution_checkout": 0,
                    "attribution_leads": 0,
                    "cpl": 0.0
                },
                "touch_point": {
                    "cpa_order": 0.0,
                    "cpa_ppv": 48.99,
                    "roas": 0.0,
                    "units_quantity": 0,
                    "direct_amount": 0.0,
                    "direct_item_quantity": 0,
                    "attribution_ppv": 4,
                    "attribution_add_to_cart": 0,
                    "attribution_bookmark": 0,
                    "attribution_checkout": 0,
                    "attribution_leads": 0,
                    "cpl": 0.0
                }
            }
        },
        {
            "campaign_id": 1111,
            "line_item_id": 4321,
            "creative_id": 3333,
            "metrics": [
                {
                    "date": "2024-09-19",
                    "site_id": "MLM",
                    "currency": "MXN",
                    "prints": 550,
                    "clicks": 3,
                    "active_views": 70,
                    "completed_views": 7,
                    "reach": 503,
                    "ctr": 0.01,
                    "consumed_budget": 94.6,
                    "cpm": 172.01,
                    "cpc": 31.53,
                    "average_frequency": 0.0,
                    "event_time": {
                        "cpa_order": 0.0,
                        "cpa_ppv": 94.6,
                        "roas": 0.0,
                        "units_quantity": 0,
                        "direct_amount": 0.0,
                        "direct_item_quantity": 0,
                        "attribution_ppv": 1,
                        "attribution_add_to_cart": 0,
                        "attribution_bookmark": 6,
                        "attribution_checkout": 0,
                        "attribution_leads": 0,
                        "cpl": 0.0
                    },
                    "touch_point": {
                        "cpa_order": 0.0,
                        "cpa_ppv": 94.6,
                        "roas": 0.0,
                        "units_quantity": 0,
                        "direct_amount": 0.0,
                        "direct_item_quantity": 0,
                        "attribution_ppv": 1,
                        "attribution_add_to_cart": 0,
                        "attribution_bookmark": 6,
                        "attribution_checkout": 0,
                        "attribution_leads": 0,
                        "cpl": 0.0
                    }
                },
                {
                    "date": "2024-09-20",
                    "site_id": "MLM",
                    "currency": "MXN",
                    "prints": 544,
                    "clicks": 6,
                    "active_views": 92,
                    "completed_views": 8,
                    "reach": 495,
                    "ctr": 0.01,
                    "consumed_budget": 92.72,
                    "cpm": 170.44,
                    "cpc": 15.45,
                    "average_frequency": 0.0,
                    "event_time": {
                        "cpa_order": 0.0,
                        "cpa_ppv": 15.45,
                        "roas": 0.0,
                        "units_quantity": 0,
                        "direct_amount": 0.0,
                        "direct_item_quantity": 0,
                        "attribution_ppv": 6,
                        "attribution_add_to_cart": 0,
                        "attribution_bookmark": 0,
                        "attribution_checkout": 0,
                        "attribution_leads": 0,
                        "cpl": 0.0
                    },
                    "touch_point": {
                        "cpa_order": 0.0,
                        "cpa_ppv": 13.25,
                        "roas": 0.0,
                        "units_quantity": 0,
                        "direct_amount": 0.0,
                        "direct_item_quantity": 0,
                        "attribution_ppv": 7,
                        "attribution_add_to_cart": 0,
                        "attribution_bookmark": 1,
                        "attribution_checkout": 0,
                        "attribution_leads": 0,
                        "cpl": 0.0
                    }
                }
            ],
            "summary": {
                "site_id": "MLM",
                "currency": "MXN",
                "prints": 1094,
                "clicks": 9,
                "active_views": 162,
                "completed_views": 15,
                "reach": 991,
                "ctr": 0.01,
                "consumed_budget": 187.32,
                "cpm": 171.23,
                "cpc": 20.81,
                "average_frequency": 0.0,
                "event_time": {
                    "cpa_order": 0.0,
                    "cpa_ppv": 26.76,
                    "roas": 0.0,
                    "units_quantity": 0,
                    "direct_amount": 0.0,
                    "direct_item_quantity": 0,
                    "attribution_ppv": 7,
                    "attribution_add_to_cart": 0,
                    "attribution_bookmark": 6,
                    "attribution_checkout": 0,
                    "attribution_leads": 0,
                    "cpl": 0.0
                },
                "touch_point": {
                    "cpa_order": 0.0,
                    "cpa_ppv": 23.42,
                    "roas": 0.0,
                    "units_quantity": 0,
                    "direct_amount": 0.0,
                    "direct_item_quantity": 0,
                    "attribution_ppv": 8,
                    "attribution_add_to_cart": 0,
                    "attribution_bookmark": 7,
                    "attribution_checkout": 0,
                    "attribution_leads": 0,
                    "cpl": 0.0
                }
            }
        },
        {
            "campaign_id": 4321,
            "line_item_id": 3333,
            "creative_id": 4444,
            "metrics": [
                {
                    "date": "2024-09-19",
                    "site_id": "MLM",
                    "currency": "MXN",
                    "prints": 582,
                    "clicks": 9,
                    "active_views": 97,
                    "completed_views": 13,
                    "reach": 545,
                    "ctr": 0.02,
                    "consumed_budget": 100.34,
                    "cpm": 172.4,
                    "cpc": 11.15,
                    "average_frequency": 0.0,
                    "event_time": {
                        "cpa_order": 0.0,
                        "cpa_ppv": 7.72,
                        "roas": 0.0,
                        "units_quantity": 0,
                        "direct_amount": 0.0,
                        "direct_item_quantity": 0,
                        "attribution_ppv": 13,
                        "attribution_add_to_cart": 0,
                        "attribution_bookmark": 0,
                        "attribution_checkout": 0,
                        "attribution_leads": 0,
                        "cpl": 0.0
                    },
                    "touch_point": {
                        "cpa_order": 0.0,
                        "cpa_ppv": 5.9,
                        "roas": 0.0,
                        "units_quantity": 0,
                        "direct_amount": 0.0,
                        "direct_item_quantity": 0,
                        "attribution_ppv": 17,
                        "attribution_add_to_cart": 0,
                        "attribution_bookmark": 0,
                        "attribution_checkout": 0,
                        "attribution_leads": 0,
                        "cpl": 0.0
                    }
                },
                {
                    "date": "2024-09-20",
                    "site_id": "MLM",
                    "currency": "MXN",
                    "prints": 651,
                    "clicks": 8,
                    "active_views": 117,
                    "completed_views": 17,
                    "reach": 590,
                    "ctr": 0.01,
                    "consumed_budget": 111.42,
                    "cpm": 171.15,
                    "cpc": 13.93,
                    "average_frequency": 0.0,
                    "event_time": {
                        "cpa_order": 0.0,
                        "cpa_ppv": 22.28,
                        "roas": 0.0,
                        "units_quantity": 0,
                        "direct_amount": 0.0,
                        "direct_item_quantity": 0,
                        "attribution_ppv": 5,
                        "attribution_add_to_cart": 0,
                        "attribution_bookmark": 1,
                        "attribution_checkout": 0,
                        "attribution_leads": 0,
                        "cpl": 0.0
                    },
                    "touch_point": {
                        "cpa_order": 0.0,
                        "cpa_ppv": 27.85,
                        "roas": 0.0,
                        "units_quantity": 0,
                        "direct_amount": 0.0,
                        "direct_item_quantity": 0,
                        "attribution_ppv": 4,
                        "attribution_add_to_cart": 0,
                        "attribution_bookmark": 2,
                        "attribution_checkout": 0,
                        "attribution_leads": 0,
                        "cpl": 0.0
                    }
                }
            ],
            "summary": {
                "site_id": "MLM",
                "currency": "MXN",
                "prints": 1233,
                "clicks": 17,
                "active_views": 214,
                "completed_views": 30,
                "reach": 1128,
                "ctr": 0.01,
                "consumed_budget": 211.75,
                "cpm": 171.74,
                "cpc": 12.46,
                "average_frequency": 0.0,
                "event_time": {
                    "cpa_order": 0.0,
                    "cpa_ppv": 11.76,
                    "roas": 0.0,
                    "units_quantity": 0,
                    "direct_amount": 0.0,
                    "direct_item_quantity": 0,
                    "attribution_ppv": 18,
                    "attribution_add_to_cart": 0,
                    "attribution_bookmark": 1,
                    "attribution_checkout": 0,
                    "attribution_leads": 0,
                    "cpl": 0.0
                },
                "touch_point": {
                    "cpa_order": 0.0,
                    "cpa_ppv": 10.08,
                    "roas": 0.0,
                    "units_quantity": 0,
                    "direct_amount": 0.0,
                    "direct_item_quantity": 0,
                    "attribution_ppv": 21,
                    "attribution_add_to_cart": 0,
                    "attribution_bookmark": 2,
                    "attribution_checkout": 0,
                    "attribution_leads": 0,
                    "cpl": 0.0
                }
            }
        },
        {
            "campaign_id": 2222,
            "line_item_id": 3333,
            "creative_id": 4444,
            "metrics": [
                {
                    "date": "2024-09-19",
                    "site_id": "MLM",
                    "currency": "MXN",
                    "prints": 350,
                    "clicks": 4,
                    "active_views": 54,
                    "completed_views": 6,
                    "reach": 298,
                    "ctr": 0.01,
                    "consumed_budget": 59.75,
                    "cpm": 170.72,
                    "cpc": 14.94,
                    "average_frequency": 0.0,
                    "event_time": {
                        "cpa_order": 0.0,
                        "cpa_ppv": 0.0,
                        "roas": 0.0,
                        "units_quantity": 0,
                        "direct_amount": 0.0,
                        "direct_item_quantity": 0,
                        "attribution_ppv": 0,
                        "attribution_add_to_cart": 0,
                        "attribution_bookmark": 3,
                        "attribution_checkout": 0,
                        "attribution_leads": 0,
                        "cpl": 0.0
                    },
                    "touch_point": {
                        "cpa_order": 0.0,
                        "cpa_ppv": 59.75,
                        "roas": 0.0,
                        "units_quantity": 0,
                        "direct_amount": 0.0,
                        "direct_item_quantity": 0,
                        "attribution_ppv": 1,
                        "attribution_add_to_cart": 2,
                        "attribution_bookmark": 3,
                        "attribution_checkout": 0,
                        "attribution_leads": 0,
                        "cpl": 0.0
                    }
                },
                {
                    "date": "2024-09-20",
                    "site_id": "MLM",
                    "currency": "MXN",
                    "prints": 613,
                    "clicks": 5,
                    "active_views": 128,
                    "completed_views": 16,
                    "reach": 529,
                    "ctr": 0.01,
                    "consumed_budget": 103.73,
                    "cpm": 169.22,
                    "cpc": 20.75,
                    "average_frequency": 0.0,
                    "event_time": {
                        "cpa_order": 0.0,
                        "cpa_ppv": 51.86,
                        "roas": 0.0,
                        "units_quantity": 0,
                        "direct_amount": 0.0,
                        "direct_item_quantity": 0,
                        "attribution_ppv": 2,
                        "attribution_add_to_cart": 1,
                        "attribution_bookmark": 3,
                        "attribution_checkout": 0,
                        "attribution_leads": 0,
                        "cpl": 0.0
                    },
                    "touch_point": {
                        "cpa_order": 0.0,
                        "cpa_ppv": 51.86,
                        "roas": 0.0,
                        "units_quantity": 0,
                        "direct_amount": 0.0,
                        "direct_item_quantity": 0,
                        "attribution_ppv": 2,
                        "attribution_add_to_cart": 1,
                        "attribution_bookmark": 3,
                        "attribution_checkout": 0,
                        "attribution_leads": 0,
                        "cpl": 0.0
                    }
                }
            ],
            "summary": {
                "site_id": "MLM",
                "currency": "MXN",
                "prints": 963,
                "clicks": 9,
                "active_views": 182,
                "completed_views": 22,
                "reach": 825,
                "ctr": 0.01,
                "consumed_budget": 163.48,
                "cpm": 169.76,
                "cpc": 18.16,
                "average_frequency": 0.0,
                "event_time": {
                    "cpa_order": 0.0,
                    "cpa_ppv": 81.74,
                    "roas": 0.0,
                    "units_quantity": 0,
                    "direct_amount": 0.0,
                    "direct_item_quantity": 0,
                    "attribution_ppv": 2,
                    "attribution_add_to_cart": 1,
                    "attribution_bookmark": 6,
                    "attribution_checkout": 0,
                    "attribution_leads": 0,
                    "cpl": 0.0
                },
                "touch_point": {
                    "cpa_order": 0.0,
                    "cpa_ppv": 54.49,
                    "roas": 0.0,
                    "units_quantity": 0,
                    "direct_amount": 0.0,
                    "direct_item_quantity": 0,
                    "attribution_ppv": 3,
                    "attribution_add_to_cart": 3,
                    "attribution_bookmark": 6,
                    "attribution_checkout": 0,
                    "attribution_leads": 0,
                    "cpl": 0.0
                }
            }
        },
        {
            "campaign_id": 2222,
            "line_item_id": 3333,
            "creative_id": 4444,
            "metrics": [
                {
                    "date": "2024-09-19",
                    "site_id": "MLM",
                    "currency": "MXN",
                    "prints": 399,
                    "clicks": 1,
                    "active_views": 63,
                    "completed_views": 9,
                    "reach": 347,
                    "ctr": 0.0,
                    "consumed_budget": 68.8,
                    "cpm": 172.43,
                    "cpc": 68.8,
                    "average_frequency": 0.0,
                    "event_time": {
                        "cpa_order": 0.0,
                        "cpa_ppv": 68.8,
                        "roas": 0.0,
                        "units_quantity": 0,
                        "direct_amount": 0.0,
                        "direct_item_quantity": 0,
                        "attribution_ppv": 1,
                        "attribution_add_to_cart": 0,
                        "attribution_bookmark": 0,
                        "attribution_checkout": 0,
                        "attribution_leads": 0,
                        "cpl": 0.0
                    },
                    "touch_point": {
                        "cpa_order": 0.0,
                        "cpa_ppv": 34.4,
                        "roas": 0.0,
                        "units_quantity": 0,
                        "direct_amount": 0.0,
                        "direct_item_quantity": 0,
                        "attribution_ppv": 2,
                        "attribution_add_to_cart": 0,
                        "attribution_bookmark": 0,
                        "attribution_checkout": 0,
                        "attribution_leads": 0,
                        "cpl": 0.0
                    }
                },
                {
                    "date": "2024-09-20",
                    "site_id": "MLM",
                    "currency": "MXN",
                    "prints": 530,
                    "clicks": 4,
                    "active_views": 84,
                    "completed_views": 14,
                    "reach": 484,
                    "ctr": 0.01,
                    "consumed_budget": 90.25,
                    "cpm": 170.29,
                    "cpc": 22.56,
                    "average_frequency": 0.0,
                    "event_time": {
                        "cpa_order": 0.0,
                        "cpa_ppv": 15.04,
                        "roas": 0.0,
                        "units_quantity": 0,
                        "direct_amount": 0.0,
                        "direct_item_quantity": 0,
                        "attribution_ppv": 6,
                        "attribution_add_to_cart": 0,
                        "attribution_bookmark": 0,
                        "attribution_checkout": 0,
                        "attribution_leads": 0,
                        "cpl": 0.0
                    },
                    "touch_point": {
                        "cpa_order": 0.0,
                        "cpa_ppv": 15.04,
                        "roas": 0.0,
                        "units_quantity": 0,
                        "direct_amount": 0.0,
                        "direct_item_quantity": 0,
                        "attribution_ppv": 6,
                        "attribution_add_to_cart": 0,
                        "attribution_bookmark": 0,
                        "attribution_checkout": 0,
                        "attribution_leads": 0,
                        "cpl": 0.0
                    }
                }
            ],
            "summary": {
                "site_id": "MLM",
                "currency": "MXN",
                "prints": 929,
                "clicks": 5,
                "active_views": 147,
                "completed_views": 23,
                "reach": 825,
                "ctr": 0.01,
                "consumed_budget": 159.05,
                "cpm": 171.21,
                "cpc": 31.81,
                "average_frequency": 0.0,
                "event_time": {
                    "cpa_order": 0.0,
                    "cpa_ppv": 22.72,
                    "roas": 0.0,
                    "units_quantity": 0,
                    "direct_amount": 0.0,
                    "direct_item_quantity": 0,
                    "attribution_ppv": 7,
                    "attribution_add_to_cart": 0,
                    "attribution_bookmark": 0,
                    "attribution_checkout": 0,
                    "attribution_leads": 0,
                    "cpl": 0.0
                },
                "touch_point": {
                    "cpa_order": 0.0,
                    "cpa_ppv": 19.88,
                    "roas": 0.0,
                    "units_quantity": 0,
                    "direct_amount": 0.0,
                    "direct_item_quantity": 0,
                    "attribution_ppv": 8,
                    "attribution_add_to_cart": 0,
                    "attribution_bookmark": 0,
                    "attribution_checkout": 0,
                    "attribution_leads": 0,
                    "cpl": 0.0
                }
            }
        }
    ]
    ```

      

    ## Glossary

    **date**: campaign date.  
    **site\_id**: country identifier. Consult the [nomenclature of
    Mercado Livre sites and their respective
    currencies](https://api.mercadolibre.com/sites).  
    **currency**: currency identifier.  
    **prints**: impressions. It is the number of times your ads were
    displayed.  
    **clicks**: number of times users clicked on your ads.  
    **active\_views** (active views): number of times users saw the
    first 6 seconds of your Social and Video ad.  
    **completed\_views** (full views): number of times users saw your
    complete Social and Video ad.  
    **reach**: Reach. It is the number of unique users who were shown
    your ads.  
    **ctr**: Click-Through Rate. Rate of clicks obtained from total
    impressions.  
    **consumed\_budget**: Investment: It is the actual money spent to
    display your ads.  
    **cpm**: average cost you pay for every thousand ad impressions.  
    **cpc**: cost per click. It is the average cost you pay for each
    click that the ads receive.  
    **average\_frequency**: Average frequency. Average number of times
    your ads were displayed to the same user.  
      

    The attribution metrics can be presented in two ways:  

      
    **Metrics assigned by Action Date (event\_time)**: the metrics will
    be shown associated with the exact date when the action was
    performed (e.g., Sales).  
    **Metrics assigned by Display Date (touchpoint)**: the metrics will
    be shown associated with the date of click or visible impression to
    which they were attributed.

    -   **cpa\_order**: (sales): average cost for each sale based on the
        investment.
    -   **cpa\_ppv**: average cost of each view of the product page
        based on the investment.
    -   **roas**: return of money that you earn on the investment.
    -   **units\_quantity**: quantity of units of your products sold
        among all purchases attributed to your ads.
    -   **direct\_amount** (revenue): total value of sales attributed to
        your ads.
    -   **direct\_item\_quantity**: number of times users made a
        purchase after seeing or clicking on your ads.
    -   **attribution\_ppv** (product page views): number of times users
        viewed your product page after seeing or clicking on your ads.
    -   **attribution\_add\_to\_cart**: number of times users added your
        promoted products to the cart after seeing or clicking on your
        ads.
    -   **attribution\_bookmark**: number of times people added a
        product to favorites after seeing or clicking on your ads.
    -   **attribution\_checkout**: number of times users started a
        purchase process of your promoted products after seeing or
        clicking on your ads.
    -   **attribution\_leads**: Contacts generated by potential
        customers after they saw or clicked on your ads.
    -   **cpl**: average cost of each lead based on the investment. This
        value is always zero.

</div>
