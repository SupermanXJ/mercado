<div class="inner-content">

## Product Ads

<div class="details__message">

With the following Product Ads endpoints, you can monitor campaigns, ads
and metrics. There are two modes of ad management in Product Ads.

-   **Automatic**: Product Ads selects listings with a good level of
    sales on Mercado Libre and displays them in the top positions of
    search results. You can manually add or remove listings from your
    campaign. When you start using Product Ads, you will use the
    automatic mode by default.
-   **Customized**: You'll be able to create multiple campaigns to group
    your ads, assign and set the budget and goal for each one. This is
    the ideal way to manage your ads because it allows you to have more
    control over your campaigns and make adjustments based on their
    performance.

</div>

![](https://http2.mlstatic.com/storage/developers-site-cms-admin/DevSite/164531543160-s01-cbt-d.png)

## Check advertiser

<div class="andes-message andes-message--highlight">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--highlight site-carriers__message-title">

**Important:**

</div>

<div class="andes-message__text--highlight site-carriers__message-text">

<div>

To use Product Ads, a user must:  
- Have a yellow reputation or higher..  
- Have been registered on Mercado Libre for at least 15 days.  
- Have a minimum number of sales on Mercado Libre (1 for companies, 10
for individuals).  
- Have no overdue invoices on Mercado Libre.

</div>

</div>

</div>

</div>

Advertisers (advertiser\_id) are those who invest a budget for the
creation and distribution of advertising, with the aim of promoting
their products or services. Check the list of advertisers that a user
has access to, according to the type of product required.

  

### Required parameters

**product\_id**: product type PADS (Product Ads).

  

Request:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' -H 'Content-Type: application/json' -H 'Api-Version: 1'
https://api.mercadolibre.com/advertising/advertisers?product_id=PADS
```

Response:

``` language-javascript
{
    "advertisers": [
        {
            "advertiser_id": 123456,
            "site_id": "MLM",
            "advertiser_name": "TEST_ADVERTISER_NAME",
            "account_name": "TEST_ACCOUNT_NAME - ID"
        }
    ]
}
```

### Response fields

**advertiser\_id**: advertiser identifier. You will use this for the
rest of the requests.  
**site\_id**: country identifier. You will use this for the rest of the
requests. Check the [nomenclature of Mercado Libre sites and their
respective currencies](https://api.mercadolibre.com/sites).  
**advertiser\_name**: advertiser name.  
**account\_name**: account name.  

<div class="andes-message andes-message--neutral">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--neutral site-carriers__message-title">

Note:

</div>

<div class="andes-message__text--neutral site-carriers__message-text">

<div>

In case you receive error 404 - No permissions found for user\_id means
that the user does not have the Product enabled.  
The user must access [Mercado
Libre](https://global-selling.mercadolibre.com/sales-summary) &gt;
Listings management &gt; Advertising campaign to activate Product Ads.

</div>

</div>

</div>

</div>

  

## Search campaigns

Get all campaigns of an advertiser.

<div class="andes-message andes-message--highlight">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--highlight site-carriers__message-title">

Important:

</div>

<div class="andes-message__text--highlight site-carriers__message-text">

<div>

From now, the request to
/marketplace/advertising/$ADVERTISER\_SITE\_ID/advertisers/$ADVERTISER\_ID/product\_ads/campaigns
must include **/search** at the end of the endpoint. Please update your
integration to continue using the resource properly.

</div>

</div>

</div>

</div>

Request:

``` language-javascript
curl -X  GET -H 'Authorization: Bearer $ACCESS_TOKEN' -H 'api-version: 2' 
https://api.mercadolibre.com/marketplace/advertising/$ADVERTISER_SITE_ID/advertisers/$ADVERTISER_ID/product_ads/campaigns/search
```

Response:

``` language-javascript
{
    "paging": {
        "offset": 0,
        "total": 19,
        "limit": 50
    },
    "results": [
        {
            "id": 353259452,
            "name": "2025-07-03-campaign-jennifer-MLB-02",
            "status": "active",
            "last_updated": "2025-12-05T01:43:35.000Z",
            "date_created": "2025-07-03T08:50:40.000Z",
            "strategy": "PROFITABILITY",
            "acos_target": 6.5,
            "acos_top_search_target": 0.0,
            "roas_target": 15.38,
            "channel": "marketplace",
            "advertiser_id": 694824,
            "salesforce_event_id": 14,
            "budget": 65.0,
            "automatic_budget": false
        },
        {
            "id": 353295046,
            "name": "666",
            "status": "active",
            "last_updated": "2025-12-05T01:43:35.000Z",
            "date_created": "2025-07-08T09:07:29.000Z",
            "strategy": "INCREASE",
            "acos_target": 33.0,
            "acos_top_search_target": 0.0,
            "roas_target": 3.03,
            "channel": "marketplace",
            "advertiser_id": 694824,
            "salesforce_event_id": 14,
            "budget": 33.0,
            "automatic_budget": false
        },
        {
            "id": 353295528,
            "name": "test0707-C1",
            "status": "paused",
            "last_updated": "2025-12-05T01:43:35.000Z",
            "date_created": "2025-07-07T06:32:27.000Z",
            "strategy": "INCREASE",
            "acos_target": 212.0,
            "acos_top_search_target": 0.0,
            "roas_target": 0.47,
            "channel": "marketplace",
            "advertiser_id": 694824,
            "salesforce_event_id": 14,
            "budget": 1.0,
            "automatic_budget": false
        },
        {
            "id": 353291559,
            "name": "test0707-C8",
            "status": "active",
            "last_updated": "2025-12-05T01:43:35.000Z",
            "date_created": "2025-07-07T09:18:23.000Z",
            "strategy": "INCREASE",
            "acos_target": 21.0,
            "acos_top_search_target": 0.0,
            "roas_target": 4.76,
            "channel": "marketplace",
            "advertiser_id": 694824,
            "salesforce_event_id": 14,
            "budget": 1.0,
            "automatic_budget": false
        },
        {
            "id": 353339103,
            "name": "test0711-C1",
            "status": "active",
            "last_updated": "2025-12-05T01:43:35.000Z",
            "date_created": "2025-07-11T01:46:00.000Z",
            "strategy": "INCREASE",
            "acos_target": 12.0,
            "acos_top_search_target": 0.0,
            "roas_target": 8.33,
            "channel": "marketplace",
            "advertiser_id": 694824,
            "salesforce_event_id": 14,
            "budget": 22.0,
            "automatic_budget": false
        },
        {
            "id": 353326347,
            "name": "710testcampaign001",
            "status": "paused",
            "last_updated": "2025-12-05T01:43:35.000Z",
            "date_created": "2025-07-10T06:38:16.000Z",
            "strategy": "INCREASE",
            "acos_target": 9.99,
            "acos_top_search_target": 0.0,
            "roas_target": 10.01,
            "channel": "marketplace",
            "advertiser_id": 694824,
            "salesforce_event_id": 14,
            "budget": 4.0,
            "automatic_budget": false
        },
        {
            "id": 355032469,
            "name": "Main Campaign 2",
            "status": "active",
            "last_updated": "2025-12-05T01:43:35.000Z",
            "date_created": "2025-11-11T14:55:29.000Z",
            "strategy": "PROFITABILITY",
            "acos_target": 15.0,
            "acos_top_search_target": 0.0,
            "roas_target": 6.67,
            "channel": "marketplace",
            "advertiser_id": 694824,
            "salesforce_event_id": 14,
            "budget": 30.0,
            "automatic_budget": false
        },
        {
            "id": 355327362,
            "name": "Test Campaign 2",
            "status": "active",
            "last_updated": "2025-12-05T11:52:34.000Z",
            "date_created": "2025-12-05T11:52:34.000Z",
            "strategy": "PROFITABILITY",
            "acos_target": 4.0,
            "acos_top_search_target": 0.0,
            "roas_target": 25.0,
            "channel": "marketplace",
            "advertiser_id": 694824,
            "salesforce_event_id": 14,
            "budget": 1000.0,
            "automatic_budget": false
        },
        {
            "id": 353541347,
            "name": "333",
            "status": "active",
            "last_updated": "2025-12-05T01:43:35.000Z",
            "date_created": "2025-07-31T01:57:59.000Z",
            "strategy": "PROFITABILITY",
            "acos_target": 33.0,
            "acos_top_search_target": 0.0,
            "roas_target": 3.03,
            "channel": "marketplace",
            "advertiser_id": 694824,
            "salesforce_event_id": 14,
            "budget": 33.0,
            "automatic_budget": false
        },
        {
            "id": 355327184,
            "name": "Main Campaign",
            "status": "active",
            "last_updated": "2025-12-05T10:39:40.000Z",
            "date_created": "2025-12-05T10:37:41.000Z",
            "strategy": "PROFITABILITY",
            "acos_target": 4.0,
            "acos_top_search_target": 0.0,
            "roas_target": 25.0,
            "channel": "marketplace",
            "advertiser_id": 694824,
            "salesforce_event_id": 14,
            "budget": 950.0,
            "automatic_budget": false
        },
        {
            "id": 355318086,
            "name": "Test Campaign Happy Path",
            "status": "active",
            "last_updated": "2025-12-05T11:23:12.000Z",
            "date_created": "2025-12-05T11:23:12.000Z",
            "strategy": "PROFITABILITY",
            "acos_target": 15.0,
            "acos_top_search_target": 0.0,
            "roas_target": 6.67,
            "channel": "marketplace",
            "advertiser_id": 694824,
            "salesforce_event_id": 14,
            "budget": 1000.0,
            "automatic_budget": false
        },
        {
            "id": 352749583,
            "name": "Test Campaign May 2025 Marce",
            "status": "paused",
            "last_updated": "2025-10-09T19:23:11.000Z",
            "date_created": "2025-05-08T14:51:58.000Z",
            "strategy": "PROFITABILITY",
            "acos_target": 150.0,
            "acos_top_search_target": 0.0,
            "roas_target": 0.67,
            "channel": "marketplace",
            "advertiser_id": 694824,
            "salesforce_event_id": 14,
            "budget": 245.0,
            "automatic_budget": false
        },
        {
            "id": 353265513,
            "name": "2025-07-03-campaign-jennifer-active-MLB",
            "status": "active",
            "last_updated": "2025-12-05T01:43:34.000Z",
            "date_created": "2025-07-03T08:49:29.000Z",
            "strategy": "PROFITABILITY",
            "acos_target": 50.0,
            "acos_top_search_target": 0.0,
            "roas_target": 2.0,
            "channel": "marketplace",
            "advertiser_id": 694824,
            "salesforce_event_id": 14,
            "budget": 20.0,
            "automatic_budget": false
        },
        {
            "id": 355327315,
            "name": "Test Campaign Updated",
            "status": "active",
            "last_updated": "2025-12-05T11:33:48.000Z",
            "date_created": "2025-12-05T11:28:23.000Z",
            "strategy": "PROFITABILITY",
            "acos_target": 4.0,
            "acos_top_search_target": 0.0,
            "roas_target": 25.0,
            "channel": "marketplace",
            "advertiser_id": 694824,
            "salesforce_event_id": 14,
            "budget": 1000.0,
            "automatic_budget": false
        },
        {
            "id": 352741099,
            "name": "Test Campaign May 2025",
            "status": "paused",
            "last_updated": "2025-10-09T17:48:33.000Z",
            "date_created": "2025-05-08T14:37:36.000Z",
            "strategy": "PROFITABILITY",
            "acos_target": 150.0,
            "acos_top_search_target": 0.0,
            "roas_target": 0.67,
            "channel": "marketplace",
            "advertiser_id": 694824,
            "salesforce_event_id": 14,
            "budget": 260.02,
            "automatic_budget": false
        },
        {
            "id": 355327899,
            "name": "Test Campaign Happy Path",
            "status": "active",
            "last_updated": "2025-12-05T13:21:05.000Z",
            "date_created": "2025-12-05T13:21:05.000Z",
            "strategy": "PROFITABILITY",
            "acos_target": 15.0,
            "acos_top_search_target": 0.0,
            "roas_target": 6.67,
            "channel": "marketplace",
            "advertiser_id": 694824,
            "salesforce_event_id": 14,
            "budget": 1000.0,
            "automatic_budget": false
        },
        {
            "id": 352757766,
            "name": "Main Campaign",
            "status": "paused",
            "last_updated": "2025-10-09T17:57:47.000Z",
            "date_created": "2025-05-08T14:11:10.000Z",
            "strategy": "PROFITABILITY",
            "acos_target": 13.0,
            "acos_top_search_target": 0.0,
            "roas_target": 7.69,
            "channel": "marketplace",
            "advertiser_id": 694824,
            "salesforce_event_id": 14,
            "budget": 1.24,
            "automatic_budget": false
        },
        {
            "id": 355328313,
            "name": "Main Campaign",
            "status": "active",
            "last_updated": "2025-12-05T14:32:20.000Z",
            "date_created": "2025-12-05T14:14:18.000Z",
            "strategy": "PROFITABILITY",
            "acos_target": 4.0,
            "acos_top_search_target": 0.0,
            "roas_target": 25.0,
            "channel": "marketplace",
            "advertiser_id": 694824,
            "salesforce_event_id": 14,
            "budget": 990.0,
            "automatic_budget": false
        },
        {
            "id": 353291496,
            "name": "test0707-C5",
            "status": "active",
            "last_updated": "2025-12-05T01:43:35.000Z",
            "date_created": "2025-07-07T08:53:46.000Z",
            "strategy": "PROFITABILITY",
            "acos_target": 50.0,
            "acos_top_search_target": 0.0,
            "roas_target": 2.0,
            "channel": "marketplace",
            "advertiser_id": 694824,
            "salesforce_event_id": 14,
            "budget": 50.0,
            "automatic_budget": false
        }
    ]
}
```

## Create campaign

<div class="andes-message andes-message--highlight">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--highlight site-carriers__message-title">

**Important:**

</div>

<div class="andes-message__text--highlight site-carriers__message-text">

As of **December 8, 2025**, adjust your development so that when
creating or updating a campaign, instead of sending the ACOS value
(acos\_target), **start sending the ROAS value (roas\_target)**.

This change aims to improve sellers’ understanding of campaign
performance, since ROAS focuses on return on investment (how much the
seller earns for each monetary unit invested in advertising).

Existing campaigns will be automatically migrated by the system. We will
calculate the Target ROAS equivalent to the Target ACOS that the seller
had configured in order to maintain their results. ACOS will remain
visible as an optional metric for campaign performance management and
analysis.

The **acos\_target** field will remain available for submission during
your development’s adaptation period. The deprecation date of this field
will be communicated in due course.

</div>

</div>

</div>

When creating the campaign you must send all the campaign parameters:

**name**: Campaign name. It allows you to identify grouped ads more
quickly.

**status**: Campaign status. It can be: active or paused.

**budget**: The campaign's average daily budget will have daily
variation. This will increase sales opportunities and make the
investment more efficient. This is the maximum amount charged per day
for clicks on ads.

**What is the daily limit my campaign can consume?** It can be up to
twice (100%) its original estimate, using the balance you did not spend
in previous days. If your daily estimate is US$ 1,000, we will invest up
to US$ 2,000 if you have US$ 1,000 left over from previous days. This
optimizes the investment and in the end you will never pay more than the
limit of your estimated budget.

<div>

  

</div>

**What happens if I change my estimate during the month?** We restart
the calculation and consider the new amount. On your invoice we will
take into account the estimates that last throughout the campaign for 30
days. Example: at the beginning of the month you set an estimate of R$
1,000 and on the 21st you changed it to R$ 500. At the end of the month
you will pay a maximum of $25,000 ($1,000 × 20 days + $500 × the
remaining days of the month).

<div>

  

</div>

**What happens if I pause my campaign for the entire month?** You will
not consume the estimate defined for the campaign. On your monthly
billing you will only see the consumption of the days the campaign was
active.

-   **strategy**: Type of campaign strategy. It can be:
    -   **profitability**: With the Profitability strategy, the platform
        will show fewer ads but to users who are more likely to buy the
        advertised product. Recommended for products that already have
        many sales on Mercado Libre.
    -   **increase**: The Growth strategy seeks a balance between
        profitability and visibility. Recommended for products with a
        good level of sales but that are not the best sellers.
    -   **visibility**: With the Visibility strategy you aim to invest
        more in advertising to show ads to as many users as possible.
        Recommended for new listings.
-   **channel**: Campaign channel. It can be marketplace (default) or
    mshops.
-   **roas\_target**: Return on advertising spend (Target ROAS). It is
    the revenue generated by the campaign/ad for each monetary unit
    invested in advertising (attributable revenue / advertising spend).
    It must be greater than or equal to 1x and less than or equal to
    35x.

**How do I interpret the relationship between the ROAS I set and my
results?**

  

**Low Target ROAS:** Aims to generate more sales and have greater reach,
although the profitability per sale is lower.

  

**High Target ROAS:** Aims for higher profitability per sale, although
this means your ads will be less competitive and generate a lower volume
of total sales and revenue.

  

**Example:** (as of December 8, 2025)

``` language-javascript
curl -X POST -H 'Authorization: Bearer $ACCESS_TOKEN' -H 'api-version: 2' 
https://api.mercadolibre.com/marketplace/advertising/$ADVERTISER_SITE_ID/advertisers/$ADVERTISER_ID/product_ads/campaigns 
{
    "name": "Main Campaign",
    "status": "active",
    "budget": 950,
    "strategy": "profitability",
    "channel": "marketplace",
    "roas_target": 19
}
```

Response:

``` language-javascript
{
    "id": 355328313,
    "name": "Main Campaign",
    "status": "active",
    "currency_id": "USD",
    "last_updated": "2025-12-05T14:14:18.156Z",
    "date_created": "2025-12-05T14:14:18.156Z",
    "strategy": "PROFITABILITY",
    "acos_target": 5.26,
    "channel": "marketplace",
    "advertiser_id": 694824,
    "budget": 950.0,
    "roas_target": 19.0
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

The **acos\_target** field will remain temporarily visible as an
optional metric to facilitate adaptation and comparison. It will be
calculated automatically based on the ROAS sent using the following
formula: ACOS = (1/ROAS) × 100.

</div>

</div>

</div>

</div>

  

## Modify campaign

<div class="andes-message andes-message--highlight">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--highlight site-carriers__message-title">

**Important:**

</div>

<div class="andes-message__text--highlight site-carriers__message-text">

As of **December 8, 2025**, adjust your development so that when
creating or updating a campaign, instead of sending the ACOS value
(acos\_target), **start sending the ROAS value (roas\_target)**.  
The **acos\_target** field will remain available for submission during
your development’s adaptation period. The deprecation date of this field
will be communicated in due course.

</div>

</div>

</div>

When updating the campaign, you must send at least one of the parameters
you want to modify.

  

**Example:** (as of December 8, 2025)

``` language-javascript
curl -X PUT -H 'Authorization: Bearer $ACCESS_TOKEN' -H 'api-version: 2' 
https://api.mercadolibre.com/marketplace/advertising/$ADVERTISER_SITE_ID/product_ads/campaigns/$CAMPAIGN_ID
{
    "name": "Main Campaign",
    "status": "active",
    "budget": 990,
    "strategy": "profitability",
    "channel": "marketplace",
    "roas_target": 25
}
```

Response:

``` language-javascript
{
    "id": 355328313,
    "name": "Main Campaign",
    "status": "active",
    "currency_id": "USD",
    "last_updated": "2025-12-05T14:32:20.882Z",
    "date_created": "2025-12-05T14:14:18.000Z",
    "strategy": "PROFITABILITY",
    "acos_target": 4.0,
    "channel": "marketplace",
    "advertiser_id": 694824,
    "budget": 990.0,
    "roas_target": 25.0
}
```

**Response parameters:**

-   **id**: Campaign ID.
-   **name**: Campaign name.
-   **status**: Campaign status.
-   **budget**: Daily campaign budget. If the platform uses the entire
    allocated daily budget, the campaign might be able to consume more
    budget and continue displaying ads, but it does not because the
    budget is not sufficient.
-   **currency\_id**: Currency of the campaign’s daily budget. By
    default, it is calculated according to the site.
-   **acos\_target**: Advertising cost of sales (Target ACOS).
    Percentage of the campaign/ad cost in relation to the revenue
    obtained. Must be greater than 3 and less than 500.
-   **strategy**: Type of campaign strategy. Can be profitability,
    increase, or visibility.
-   **channel**: Campaign channel. Can be marketplace or mshops. By
    default, it is marketplace.
-   **roas\_target**: Return on advertising spend (Target ROAS). It is
    the revenue generated by the campaign/ad for each monetary unit
    invested in advertising (attributable revenue ÷ advertising spend).
    Must be greater than or equal to 1x and less than or equal to 35x.
-   **last\_updated**: Date of the last campaign update.
-   **date\_created**: Campaign creation date.

  

<div class="andes-message andes-message--neutral">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--neutral site-carriers__message-title">

Note:

</div>

<div class="andes-message__text--neutral site-carriers__message-text">

<div>

The **acos\_target** field will remain temporarily visible as an
optional metric to facilitate adaptation and comparison. It will be
calculated automatically based on the ROAS sent using the following
formula: ACOS = (1/ROAS) × 100.

</div>

</div>

</div>

</div>

  
  

## Search ads

Request:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' -H 'api-version: 2' 
https://api.mercadolibre.com/marketplace/advertising/$ADVERTISER_SITE_ID/advertisers/$ADVERTISER_ID/product_ads/ads/search
```

Example:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' -H 'api-version: 2' 
https://api.mercadolibre.com/marketplace/advertising/MLM/advertisers/609975/product_ads/ads/search
```

Response:

``` language-javascript
{
    "paging": {
        "offset": 0,
        "total": 3,
        "limit": 50
    },
    "results": [
        {
            "item_id": "MLM2008505002",
            "campaign_id": 352240074,
            "price": 18081.0,
            "price_usd": 900.0,
            "title": "Artículo De Prueba",
            "status": "active",
            "has_discount": false,
            "catalog_listing": false,
            "logistic_type": "drop_off",
            "listing_type_id": "gold_pro",
            "domain_id": "MLM-GAME_CONSOLES_VIDEO_GAMES_AND_ARCADE_MACHINES",
            "date_created": "2023-04-03T20:13:47Z",
            "buy_box_winner": false,
            "channel": "marketplace",
            "advertiser_id": 609975,
            "condition": "new",
            "current_level": "unknown",
            "deferred_stock": false,
            "thumbnail": "http://http2.mlstatic.com/D_704419-CBT54817524535_042023-I.jpg",
            "permalink": "https://articulo.mercadolibre.com.mx/MLM-2008505002-articulo-de-prueba-por-favor-no-pujar-kc-desactivado-_JM",
            "recommended": false,
            "image_quality": "unknown",
            "metrics": {}
        },
        {
            "item_id": "MLM2008102032",
            "campaign_id": 352144891,
            "price": 18081.0,
            "price_usd": 892.89,
            "title": "Artículo De Prueba test",
            "status": "active",
            "has_discount": false,
            "catalog_listing": false,
            "logistic_type": "drop_off",
            "listing_type_id": "gold_pro",
            "domain_id": "MLM-GAME_CONSOLES_VIDEO_GAMES_AND_ARCADE_MACHINES",
            "date_created": "2023-04-03T20:13:47Z",
            "buy_box_winner": false,
            "channel": "marketplace",
            "advertiser_id": 609975,
            "condition": "new",
            "current_level": "unknown",
            "deferred_stock": false,
            "thumbnail": "http://http2.mlstatic.com/D_892360-CBT54821641548_042023-I.jpg",
            "permalink": "https://articulo.mercadolibre.com.mx/MLM-2008102032-articulo-de-prueba-por-favor-no-pujar-kc-desactivado-_JM",
            "recommended": false,
            "image_quality": "unknown",
            "metrics": {}
        },
        {
            "item_id": "MLM2007439322",
            "campaign_id": 352165050,
            "price": 18198.0,
            "price_usd": 900.0,
            "title": "Artículo De Prueba, Por Favor No Pujar Kc: Off",
            "status": "paused",
            "has_discount": false,
            "catalog_listing": false,
            "logistic_type": "drop_off",
            "listing_type_id": "gold_pro",
            "domain_id": "MLM-GAME_CONSOLES_VIDEO_GAMES_AND_ARCADE_MACHINES",
            "date_created": "2023-04-03T20:13:47Z",
            "buy_box_winner": false,
            "channel": "marketplace",
            "advertiser_id": 609975,
            "condition": "new",
            "current_level": "unknown",
            "deferred_stock": false,
            "thumbnail": "http://http2.mlstatic.com/D_988787-CBT68829317273_042023-I.jpg",
            "permalink": "https://articulo.mercadolibre.com.mx/MLM-2007439322-articulo-de-prueba-por-favor-no-pujar-kc-desactivado-_JM",
            "recommended": false,
            "image_quality": "unknown",
            "metrics": {}
        }
    ]
}
```

  

## Ad details

Request:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' -H 'api-version: 2' 
https://api.mercadolibre.com/marketplace/advertising/$ADVERTISER_SITE_ID/product_ads/ads/$ITEM_ID
```

Response:

``` language-javascript
{
  "item_id": "MLM12345678", 
  "campaign_id": 0,
   "price": 16999.0,
   "title": "Pantalla Samsung Led Smart Tv De 65 Pulgadas 4k/uhd",
   "status": "X",
   "has_discount": false,
   "catalog_listing": true,
   "logistic_type": "default",
   "listing_type_id": "gold_pro",
   "domain_id": "MLM-TELEVISIONS",
   "date_created": "2024-03-15T14:41:47Z",
   "buy_box_winner": false,
   "tags": [],
   "channel": "marketplace",
   "official_store_id": 111,
   "brand_value_id": "223",
   "brand_value_name": "Marca",
   "condition": "new",
   "current_level": "unknown",
   "deferred_stock": false,
   "picture_id": "ABCD_12345_XS",
   "thumbnail": "http://http2.mlstatic.com/D_870627-1111.jpg",
   "permalink": "https://articulo.mercadolibre.com.mx/MLM111111-2222-3333-4kuhd-_JM",
   "recommended": false,  
   "metrics_summary": {
       "clicks": 0,
       "prints": 0,
       "cost": 0.01,
       "cpc": 0.01,
       "acos": 0.01,
       "organic_units_quantity": 0,
       "organic_items_quantity": 0,
       "direct_items_quantity": 0,
       "indirect_items_quantity": 0,
       "advertising_items_quantity": 0,
       "direct_units_quantity": 0,
       "indirect_units_quantity": 0,
       "units_quantity": 0,
       "direct_amount": 0.01,
       "indirect_amount": 0.01,
       "total_amount": 0.01
   }
}
```

## Modify Ad

To modify an ad, you can send one or both parameters within the update:

-   **status**: update only the status of the ad (between active and
    paused) or
-   **campaign\_id**: update only the campaign it belongs to. If the ad
    does not have campaigns and is added to a campaign, it will be
    active by default. If the ad is removed from a campaign, it will be
    in idle status (the item is available for advertising but not in any
    advertising campaign).

<div class="andes-message andes-message--neutral">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--neutral site-carriers__message-title">

Notes:

</div>

<div class="andes-message__text--neutral site-carriers__message-text">

<div>

\- To **move ads from a campaign** and have the ad without campaigns,
send campaign\_id: 0. You cannot send status in the same request if you
send campaign\_id: 0 since items are automatically in idle status.  
- When an **ad is without a campaign** and is moved to a campaign, if no
status is sent, it will be active by default.  
- **You cannot move disabled ads** (status **hold**) between campaigns.

</div>

</div>

</div>

</div>

### Mandatory parameters

**channel**: channel where the item is published (marketplace or
mshops). Default: marketplace.

Example:

``` language-javascript
curl -X PUT -H 'Authorization: Bearer $ACCESS_TOKEN'-H 'api-version: 2' 
https://api.mercadolibre.com/marketplace/advertising/$ADVERTISER_SITE_ID/product_ads/ads/$ITEM_ID?channel=marketplace
{
    "status": "active",
    "campaign_id": 1234567
}
```

Response:

``` language-javascript
{
    "item_id": "MLB123",
    "status": "active",
    "campaign_id": 1234567,
    "title": "Item title",
    "permalink": "https://articulo.mercadolibre.com.ar/test.jpg",
    "thumbnail": "http://mla-s2-p.mlstatic.com/test.jpg",
    "picture_id": "ABCD_12345_ZYX",
    "date_created": "2024-02-26T20:07:07.002Z",
    "last_updated": "2024-02-26T20:07:07.002Z",
    "channel": "string",
    "advertiser_id": 0
}
```

## Modify up to 10.000 ads

To modify up to 10,000 items, the first 50 items sent will be updated
synchronously and the impacted items will be returned. The remaining
items, i.e., from 51 to 10,000, will be processed asynchronously and
will respond with http 200. This does not mean that the item will have
been moved at that time, but that it will be processed in the background
with eventual consistency.

<div class="andes-message andes-message--neutral">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--neutral site-carriers__message-title">

Note:

</div>

<div class="andes-message__text--neutral site-carriers__message-text">

<div>

As with single ad updates, you can send one or both parameters within
the update, and the same rules apply.

</div>

</div>

</div>

</div>

Example:

``` language-javascript
curl -X PUT -H 'Authorization: Bearer $ACCESS_TOKEN' -H 'api-version: 2' 
https://api.mercadolibre.com/marketplace/advertising/$ADVERTISER_SITE_ID/advertisers/$ADVERTISER_ID/product_ads/ads?channel=marketplace
{
    "target": [
        "MLM2007439322",
        "MLM2008102032",
        "MLM2008505002"
    ],
    "payload": {
        "status": "active",
        "campaign_id": 352274800
    }
}
}
```

Response:

``` language-javascript
{
    "results": [
        {
            "item_id": "MLM2008102032",
            "status": "active",
            "campaign_id": 352274800,
            "date_created": "2025-03-21T15:40:44.391Z",
            "last_updated": "2025-03-21T15:40:44.391Z",
            "channel": "marketplace",
            "advertiser_id": 609975
        },
        {
            "item_id": "MLM2008505002",
            "status": "paused",
            "campaign_id": 352274800,
            "date_created": "2025-03-21T15:40:44.451Z",
            "last_updated": "2025-03-21T15:40:44.451Z",
            "channel": "marketplace",
            "advertiser_id": 609975
        },
        {
            "item_id": "MLM2007439322",
            "status": "paused",
            "campaign_id": 352274800,
            "date_created": "2025-03-21T15:40:44.498Z",
            "last_updated": "2025-03-21T15:40:44.498Z",
            "channel": "marketplace",
            "advertiser_id": 609975
        }
    ]
}
```

**item\_id**: id of the item at Mercado Libre level.

**status**: status of the item within Product Ads.

**campaign\_id**: id of the campaign to which the item belongs.

**title**: title of the item.

**thumbnail**: thumbnail of the item.

**permalink**: permalink of the item.

**picture\_id**: picture id of the item.

**channel**: sales channel to which the item belongs within Product Ads.

**advertiser\_id**: advertiser to which the item belongs within Product
Ads.

**last\_updated**: date of last update of the item within Product Ads.

**date\_created**: date of creation of the item within Product Ads.

  

## Campaigns metrics

Get all campaigns of an advertiser along with their corresponding
metrics.

  

### Optional parameters

**limit**: limit of items to display

**offset**: pagination attribute of the results, allows navigating
through the pages of the list from 0 to the multiple of the total
elements with the page limit

**date\_from**: start date (YYYY-MM-DD). It is validated that it is
present if metrics are requested

**date\_to**: end date (YYYY-MM-DD). It is validated that it is present
if metrics are requested

**metrics**: comma-separated list (e.g., clicks, prints). Indicates the
fields that will be returned in the response. Possible values:

-   clicks, prints, ctr, cost, cost\_usd, cpc, acos,
    organic\_units\_quantity, organic\_units\_amount,
    organic\_items\_quantity, direct\_items\_quantity,
    indirect\_items\_quantity, advertising\_items\_quantity, cvr, roas,
    sov, direct\_units\_quantity, indirect\_units\_quantity,
    units\_quantity, direct\_amount, indirect\_amount, total\_amount

**aggregation**: aggregation by which the results will be presented.
Default: sum

**aggregation\_type**: type of aggregation in which the results will be
presented. Default: campaign

**metrics\_summary**: Request summarized metrics. Must be used in
conjunction with metrics. Default: false.

  

<div class="andes-message andes-message--neutral">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--neutral site-carriers__message-title">

Note:

</div>

<div class="andes-message__text--neutral site-carriers__message-text">

<div>

\- For all metrics endpoints, you can apply a date range of 90 days
backward.  
- The information for validating metrics is updated at 10:00 AM GMT-3.  
- Only one aggregation\_type can be requested at a time.

</div>

</div>

</div>

</div>

### Available filters

To use the filters, you must follow the structure **?filters\[filter
name\]= value**.

  

**campaign\_ids**: filter by campaign IDs separated by commas.

**campaign\_id**: filter by campaign ID, get all items that have been in
the campaign for the specified date range.

**status**: Campaign status, separated by commas. Available values:
active, paused, deleted.

**channel**: Campaign channel. Can be marketplace or mshops.

  

<div class="andes-message andes-message--highlight">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--highlight site-carriers__message-title">

Important:

</div>

<div class="andes-message__text--highlight site-carriers__message-text">

<div>

From now, the request to
/marketplace/advertising/$ADVERTISER\_SITE\_ID/advertisers/$ADVERTISER\_ID/product\_ads/campaigns
must include **/search** at the end of the endpoint. Please update your
integration to continue using the resource properly.

</div>

</div>

</div>

</div>

Example:

``` language-javascript
curl -X  GET -H 'Authorization: Bearer $ACCESS_TOKEN' -H 'api-version: 2' 
https://api.mercadolibre.com/marketplace/advertising/$ADVERTISER_SITE_ID/advertisers/$ADVERTISER_ID/product_ads/campaigns/search?limit=1&offset=0&date_from=2025-11-01&date_to=2025-11-04;metrics=clicks,prints,ctr,cost,cpc,acos,organic_units_quantity,organic_units_amount,organic_items_quantity,direct_items_quantity,indirect_items_quantity,advertising_items_quantity,cvr,roas,sov,direct_units_quantity,indirect_units_quantity,units_quantity,direct_amount,indirect_amount,total_amount
```

Response:

``` language-javascript
{
    "paging": {
        "offset": 0,
        "total": 19,
        "limit": 1
    },
    "results": [
        {
            "id": 353265513,
            "name": "2025-07-03-campaign-jennifer-active-MLB",
            "status": "active",
            "last_updated": "2025-12-05T01:43:34.000Z",
            "date_created": "2025-07-03T08:49:29.000Z",
            "strategy": "PROFITABILITY",
            "acos_target": 50.0,
            "acos_top_search_target": 0.0,
            "roas_target": 2.0,
            "channel": "marketplace",
            "advertiser_id": 694824,
            "salesforce_event_id": 14,
            "budget": 20.0,
            "automatic_budget": false,
            "metrics": {
                "clicks": 0,
                "prints": 0,
                "cost": 0.0,
                "cpc": 0.0,
                "ctr": 0.0,
                "direct_amount": 0.0,
                "indirect_amount": 0.0,
                "total_amount": 0.0,
                "direct_units_quantity": 0,
                "indirect_units_quantity": 0,
                "units_quantity": 0,
                "direct_items_quantity": 0,
                "indirect_items_quantity": 0,
                "advertising_items_quantity": 0,
                "organic_units_quantity": 0,
                "organic_units_amount": 0.0,
                "organic_items_quantity": 0,
                "acos": 0.0,
                "cvr": 0.0,
                "roas": 0.0,
                "sov": 0.0
            }
        }
    ]
}
```

## Daily campaign metrics

<div class="andes-message andes-message--highlight">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--highlight site-carriers__message-title">

Important:

</div>

<div class="andes-message__text--highlight site-carriers__message-text">

<div>

From now, the request to
/marketplace/advertising/$ADVERTISER\_SITE\_ID/advertisers/$ADVERTISER\_ID/product\_ads/campaigns
must include **/search** at the end of the endpoint. Please update your
integration to continue using the resource properly.

</div>

</div>

</div>

</div>

Example:

``` language-javascript
curl -X  GET -H 'Authorization: Bearer $ACCESS_TOKEN' -H 'api-version: 2' 
https://api.mercadolibre.com/marketplace/advertising/$ADVERTISER_SITE_ID/advertisers/$ADVERTISER_ID/product_ads/campaigns/search?limit=2&offset=0&date_from=2024-01-01&date_to=2024-02-28&metrics=clicks,prints,ctr,cost,cpc,acos,organic_units_quantity,organic_units_amount,organic_items_quantity,direct_items_quantity,indirect_items_quantity,advertising_items_quantity,cvr,roas,sov,direct_units_quantity,indirect_units_quantity,units_quantity,direct_amount,indirect_amount,total_amount&aggregation_type=DAILY
```

Response:

``` language-javascript
{
   "results": [
       {
           "clicks": 43,
           "prints": 5676,
           "cost": 35.0,
           "cpc": 0.81,
           "direct_amount": 149.05,
           "indirect_amount": 149.05,
           "total_amount": 298.1,
           "direct_units_quantity": 1,
           "indirect_units_quantity": 1,
           "units_quantity": 2,
           "direct_items_quantity": 1,
           "indirect_items_quantity": 1,
           "advertising_items_quantity": 2,
           "organic_units_quantity": 12,
           "organic_items_quantity": 9,
           "acos": 11.74,
           "organic_units_amount": 1260.0,
           "sov": 18.18,
           "ctr": 0.76,
           "cvr": 4.65,
           "roas": 851.71,
           "date": "2024-08-01"
       },
       {
           "clicks": 54,
           "prints": 7484,
           "cost": 33.36,
           "cpc": 0.62,
           "direct_amount": 310.88,
           "indirect_amount": 175.47,
           "total_amount": 486.35,
           "direct_units_quantity": 2,
           "indirect_units_quantity": 1,
           "units_quantity": 3,
           "direct_items_quantity": 2,
           "indirect_items_quantity": 1,
           "advertising_items_quantity": 3,
           "organic_units_quantity": 12,
           "organic_items_quantity": 9,
           "acos": 6.86,
           "organic_units_amount": 963.0,
           "sov": 25.0,
           "ctr": 0.72,
           "cvr": 5.56,
           "roas": 1457.88,
           "date": "2024-08-02"
       },
...
}
```

## Summarized campaign metrics

Use the same endpoint to query campaign metrics by adding the parameter
metrics\_summary=true.

<div class="andes-message andes-message--highlight">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--highlight site-carriers__message-title">

Important:

</div>

<div class="andes-message__text--highlight site-carriers__message-text">

<div>

From now, the request to
/marketplace/advertising/$ADVERTISER\_SITE\_ID/advertisers/$ADVERTISER\_ID/product\_ads/campaigns
must include **/search** at the end of the endpoint. Please update your
integration to continue using the resource properly.

</div>

</div>

</div>

</div>

Example:

``` language-javascript
curl -X  GET -H 'Authorization: Bearer $ACCESS_TOKEN' -H 'api-version: 2' 
https://api.mercadolibre.com/marketplace/advertising/$ADVERTISER_SITE_ID/advertisers/$ADVERTISER_ID/product_ads/campaigns/search?limit=1&offset=0&date_from=2025-11-01&date_to=2025-11-04,metrics=clicks,prints,ctr,cost,cpc,acos,organic_units_quantity,organic_units_amount,organic_items_quantity,direct_items_quantity,indirect_items_quantity,advertising_items_quantity,cvr,roas,sov,direct_units_quantity,indirect_units_quantity,units_quantity,direct_amount,indirect_amount,total_amount&metrics_summary=true
```

Response:

``` language-javascript
{
    "paging": {
        "offset": 0,
        "total": 19,
        "limit": 1
    },
    "results": [
        {
            "id": 353265513,
            "name": "2025-07-03-campaign-jennifer-active-MLB",
            "status": "active",
            "last_updated": "2025-12-05T14:45:51.000Z",
            "date_created": "2025-07-03T08:49:29.000Z",
            "strategy": "PROFITABILITY",
            "acos_target": 50.0,
            "acos_top_search_target": 0.0,
            "roas_target": 2.0,
            "channel": "marketplace",
            "advertiser_id": 694824,
            "salesforce_event_id": 14,
            "budget": 20.0,
            "automatic_budget": false,
            "metrics": {
                "clicks": 0,
                "prints": 0,
                "cost": 0.0,
                "cpc": 0.0,
                "ctr": 0.0,
                "direct_amount": 0.0,
                "indirect_amount": 0.0,
                "total_amount": 0.0,
                "direct_units_quantity": 0,
                "indirect_units_quantity": 0,
                "units_quantity": 0,
                "direct_items_quantity": 0,
                "indirect_items_quantity": 0,
                "advertising_items_quantity": 0,
                "organic_units_quantity": 0,
                "organic_units_amount": 0.0,
                "organic_items_quantity": 0,
                "acos": 0.0,
                "cvr": 0.0,
                "roas": 0.0,
                "sov": 0.0
            }
        }
    ],
    "metrics_summary": {
        "clicks": 0,
        "prints": 0,
        "cost": 0.0,
        "cpc": 0.0,
        "ctr": 0.0,
        "direct_amount": 0.0,
        "indirect_amount": 0.0,
        "total_amount": 0.0,
        "direct_units_quantity": 0,
        "indirect_units_quantity": 0,
        "units_quantity": 0,
        "direct_items_quantity": 0,
        "indirect_items_quantity": 0,
        "advertising_items_quantity": 0,
        "organic_units_quantity": 0,
        "organic_units_amount": 0.0,
        "organic_items_quantity": 0,
        "acos": 0.0,
        "cvr": 0.0,
        "roas": 0.0,
        "sov": 0.0
    }
}
```

## Campaign metrics

### Optional parameters

**date\_from**: Start date (YYYY-MM-DD). Validation required if metrics
are requested.

**date\_to**: End date (YYYY-MM-DD). Validation required if metrics are
requested.

**metrics**: Comma-separated list (e.g., clicks, prints) indicates the
fields to be returned in the response. Available values:

-   clicks, prints, ctr, cost, cpc, acos, organic\_units\_quantity,
    organic\_units\_amount, organic\_items\_quantity,
    direct\_items\_quantity, indirect\_items\_quantity,
    advertising\_items\_quantity, cvr, roas, sov,
    direct\_units\_quantity, indirect\_units\_quantity, units\_quantity,
    direct\_amount, indirect\_amount, total\_amount, impression\_share,
    top\_impression\_share, lost\_impression\_share\_by\_budget,
    lost\_impression\_share\_by\_ad\_rank, acos\_benchmark.

**aggregation**: Aggregation for presenting the results. Default: sum.

**aggregation\_type**: Aggregation type for presenting the results.
Default: campaign.

  

### Available filters

**channel**: Campaign channel. Can be marketplace or mshops.

  

Example:

``` language-javascript
curl GET -H 'api-version: 2' -H 'Authorization: Bearer $ACCESS_TOKEN' 
https://api.mercadolibre.com/marketplace/advertising/$ADVERTISER_SITE_ID/product_ads/campaigns/$CAMPAIGN_ID?date_from=2024-01-01&date_to=2024-02-28&metrics=clicks,prints,ctr,cost,cpc,acos,organic_units_quantity,organic_units_amount,organic_items_quantity,direct_items_quantity,indirect_items_quantity,advertising_items_quantity,cvr,roas,sov,direct_units_quantity,indirect_units_quantity,units_quantity,direct_amount,indirect_amount,total_amount,impression_share,top_impression_share,lost_impression_share_by_budget,lost_impression_share_by_ad_rank,acos_benchmark
```

Response:

``` language-javascript
{
   "id": 0,
   "name": "Crecimiento A",
   "status": "active",
   "budget": 0.00,
   "currency_id": "ARS",
   "last_updated": "2024-04-08T16:09:13.000Z",
   "date_created": "2024-04-08T16:09:13.000Z",
   "acos_target": 99.10,
   "strategy": "profitability",
   "channel": "marketplace"
   "metrics": {
       "clicks": 0,
       "prints": 0,
       "ctr": 0.01,
       "cost": 0.01,
       "cpc": 0.01,
       "acos": 0.01,
       "organic_units_quantity": 0,
       "organic_units_amount": 0,
       "organic_items_quantity": 0,
       "direct_items_quantity": 0,
       "indirect_items_quantity": 0,
       "advertising_items_quantity": 0,
       "cvr": 0,
       "roas": 0,
       "sov": 0,
       "direct_units_quantity": 0,
       "indirect_units_quantity": 0,
       "units_quantity": 0,
       "direct_amount": 0.01,
       "indirect_amount": 0.01,
       "total_amount": 0.01,
       "impression_share": 0,
       "top_impression_share": 0,
       "lost_impression_share_by_budget": 0.01,
       "lost_impression_share_by_ad_rank": 0.01,
       "acos_benchmark": 123
   }
}
```

## Daily campaign metrics

Example:

``` language-javascript
curl -X  GET -H 'Authorization: Bearer $ACCESS_TOKEN' -H 'api-version: 2'
https://api.mercadolibre.com/marketplace/advertising/$ADVERTISER_SITE_ID/product_ads/campaigns/$CAMPAIGN_ID?date_from=2024-01-01&date_to=2024-02-28&metrics=clicks,prints,ctr,cost,cpc,acos,organic_units_quantity,organic_units_amount,organic_items_quantity,direct_items_quantity,indirect_items_quantity,advertising_items_quantity,cvr,roas,sov,direct_units_quantity,indirect_units_quantity,units_quantity,direct_amount,indirect_amount,total_amount,impression_share,top_impression_share,lost_impression_share_by_budget,lost_impression_share_by_ad_rank,acos_benchmark&aggregation_type=DAILY
```

Response:

``` language-javascript
{
   [
       {
           "date": "2024-01-01",
           "clicks": 0,
           "prints": 0,
           "ctr": 0.01,
           "cost": 0.01,
           "cpc": 0.01,
           "acos": 0.01,
           "organic_units_quantity": 0,
           "organic_units_amount": 0,
           "organic_items_quantity": 0,
           "direct_items_quantity": 0,
           "indirect_items_quantity": 0,
           "advertising_items_quantity": 0,
           "cvr": 0,
           "roas": 0,
           "sov": 0,
           "direct_units_quantity": 0,
           "indirect_units_quantity": 0,
           "units_quantity": 0,
           "direct_amount": 0.01,
           "indirect_amount": 0.01,
           "total_amount": 0.01,
           "impression_share": 0,
           "top_impression_share": 0,
           "lost_impression_share_by_budget": 0.01,
           "lost_impression_share_by_ad_rank": 0.01,
           "acos_benchmark": 123      
       }
   ]
}
```

## Ads metrics

Get all ads metrics.

### Optional parameters

**limit**: Limit of elements to display.

  

**offset**: Pagination attribute of the results, allows navigating
through the pages of the list from 0 to the multiple of the total
elements with the page limit.

**date\_from**: Start date (YYYY-MM-DD). Validation required if metrics
are requested.

**date\_to**: End date (YYYY-MM-DD). Validation required if metrics are
requested.

**metrics**: Comma-separated list (e.g., clicks, prints) indicates the
fields to be returned in the response. Possible values:

-   clicks, prints, cost, cpc, acos, organic\_units\_quantity,
    organic\_units\_amount, organic\_items\_quantity,
    direct\_items\_quantity, indirect\_items\_quantity,
    advertising\_items\_quantity, direct\_units\_quantity,
    indirect\_units\_quantity, units\_quantity, direct\_amount,
    indirect\_amount, total\_amount.

**sort**: Sorting of the query, asc and desc.

**sort\_by**: Name of the attribute by which the sorting will be
performed.

**aggregation**: Aggregation for presenting the results. Default: sum.

**aggregation\_type**: Aggregation type for presenting the results:
DAILY, item. Default: item.

**metrics\_summary**: Summarizes the metrics and should be used in
combination with metrics. Default false.

  

### Available filters

To use the filters, you must follow the structure **?filters\[filter
name\]= value**.

  

**item\_id**: Ad ID. One or more, separated by comma.

**statuses**: Ad status. Available values: active, paused, hold, idle,
delegated, revoked; typically filtered by active, paused, and idle.

-   **hold**: The item is disabled in advertising, usually because the
    item at the marketplace level is paused or out of stock.
-   **idle**: The item is available for advertising but is not in any
    advertising campaign.
-   **delegated**: Means that from the owner's perspective, the item is
    delegated to another advertiser. This means that although the owner
    (seller) may own the item, they no longer have authority to operate
    on it because it is "loaned out" to another advertiser.
-   **revoked**: Means that from the perspective of the advertiser to
    whom the items were loaned, this advertiser returned them to the
    owner, so they no longer have authority to operate on those items.

**channel**: Sales channel 'marketplace' (Mercado Libre) or 'mshops'
(Mercado Shops).

**price**: Price.

**buy\_box\_winner**: The associated item is the Buy Box winner.
Available values: true or false. Learn more about [Catalog
competition](/en_us/catalog-competition).

**condition**: Condition of the associated item.

**current\_level**: Reputation of the associated item.

**deferred\_stock**: Stock of the associated item.

**domains**: Domain of the associated item.

**logistic\_types**: Logistic type of the associated item.

**listing\_types**: Listing type of the associated item.

**official\_stores**: Official store of the associated item.

**recommended**: The ad is recommended by Product Ads. According to our
models, it performs well, and activating advertising for it will boost
sales.

**campaign\_id**: Get all ads that have been part of a campaign within a
time period.

**campaigns**: List of campaigns separated by comma.

**brand\_value\_id**: Brand identifier.

**brand\_value\_name**: Brand name.

  

Example:

``` language-javascript
curl -X  GET -H 'Authorization: Bearer $ACCESS_TOKEN' -H 'api-version: 2' 
https://api.mercadolibre.com/marketplace/advertising/$ADVERTISER_SITE_ID/advertisers/$ADVERTISER_ID/product_ads/ads/search?limit=1&offset=0&date_from=2024-01-01&date_to=2024-02-28&metrics=clicks,prints,ctr,cost,cpc,acos,organic_units_quantity,organic_units_amount,organic_items_quantity,direct_items_quantity,indirect_items_quantity,advertising_items_quantity,cvr,roas,sov,direct_units_quantity,indirect_units_quantity,units_quantity,direct_amount,indirect_amount,total_amount
```

Response:

``` language-javascript
{
   "paging": {
       "offset": 0,
       "last_item_id": null,
       "total": 387,
       "limit": 1
   },
   "results": [
       {
           "item_id": "MLM12345678",
           "campaign_id": 0,
           "price": 16999.0,
           "title": "Pantalla Samsung Led Smart Tv De 65 Pulgadas 4k/uhd",
           "status": "active",
           "has_discount": false,
           "catalog_listing": true,
           "logistic_type": "default",
           "listing_type_id": "gold_pro",
           "domain_id": "MLM-TELEVISIONS",
           "date_created": "2024-03-15T14:41:47Z",
           "buy_box_winner": false,
           "tags": [],
           "channel": "marketplace",
           "official_store_id": 111,
           "brand_value_id": "222",
           "brand_value_name": "Marca",
           "condition": "new",
           "current_level": "unknown",
           "deferred_stock": false,
           "picture_id": "ABCD_12345_XS",
           "thumbnail": "http://http2.mlstatic.com/D_870627-MLA111111_022024-I.jpg",
           "permalink": "https://articulo.mercadolibre.com.mx/MLM-12345678-pulgadas-4kuhd-_JM",
           "recommended": false,
           "metrics": {
               "clicks": 0,
               "prints": 0,
               "cost": 0.01,
               "cpc": 0.01,
               "acos": 0.01,
               "organic_units_quantity": 0,
               "organic_items_quantity": 0,
               "direct_items_quantity": 0,
               "indirect_items_quantity": 0,
               "advertising_items_quantity": 0,
               "direct_units_quantity": 0,
               "indirect_units_quantity": 0,
               "units_quantity": 0,
               "direct_amount": 0.01,
               "indirect_amount": 0.01,
               "total_amount": 0.01
           }      
       }
   ]
}
```

## Daily ads metrics

Example:

``` language-javascript
curl -X  GET -H 'Authorization: Bearer $ACCESS_TOKEN' -H 'api-version: 2' 
https://api.mercadolibre.com/marketplace/advertising/$ADVERTISER_SITE_ID/advertisers/$ADVERTISER_ID/product_ads/ads/search?limit=1&offset=0&date_from=2024-01-01&date_to=2024-02-28&metrics=clicks,prints,ctr,cost,cpc,acos,organic_units_quantity,organic_units_amount,organic_items_quantity,direct_items_quantity,indirect_items_quantity,advertising_items_quantity,cvr,roas,sov,direct_units_quantity,indirect_units_quantity,units_quantity,direct_amount,indirect_amount,total_amount&aggregation_type=DAILY
```

Response:

``` language-javascript
{
   "paging": {
       "offset": 0,
       "last_item_id": null,
       "total": 387,
       "limit": 1
   },
   "results": [
       {
           "date": "2023-01-01",
           "clicks": 0,
           "prints": 0,
           "cost": 0.01,
           "cpc": 0.01,
           "acos": 0.01,
           "organic_units_quantity": 0,
           "organic_items_quantity": 0,
           "direct_items_quantity": 0,
           "indirect_items_quantity": 0,
           "advertising_items_quantity": 0,
           "direct_units_quantity": 0,
           "indirect_units_quantity": 0,
           "units_quantity": 0,
           "direct_amount": 0.01,
           "indirect_amount": 0.01,
           "total_amount": 0.01
       }
   ]
}
```

## Summarized ads metrics

Example:

``` language-javascript
curl -X  GET -H 'Authorization: Bearer $ACCESS_TOKEN' -H 'api-version: 2' 
https://api.mercadolibre.com/marketplace/advertising/$ADVERTISER_SITE_ID/advertisers/$ADVERTISER_ID/product_ads/ads/search?limit=1&offset=0&date_from=2024-01-01&date_to=2024-02-28&metrics=clicks,prints,ctr,cost,cpc,acos,organic_units_quantity,organic_units_amount,organic_items_quantity,direct_items_quantity,indirect_items_quantity,advertising_items_quantity,cvr,roas,sov,direct_units_quantity,indirect_units_quantity,units_quantity,direct_amount,indirect_amount,total_amount&metrics_summary=true
```

Response:

``` language-javascript
{
   "paging": {
       "offset": 0,
       "last_item_id": null,
       "total": 387,
       "limit": 1
   },
   "results": [
       {
           "item_id": "MLM2945612374",
           "campaign_id": 0,
           "price": 16999.0,
           "title": "Pantalla Samsung Led Smart Tv De 65 Pulgadas 4k/uhd",
           "status": "delegated",
           "has_discount": false,
           "catalog_listing": true,
           "logistic_type": "default",
           "listing_type_id": "gold_pro",
           "domain_id": "MLM-TELEVISIONS",
           "date_created": "2024-03-15T14:41:47Z",
           "buy_box_winner": false,
           "tags": [],
           "channel": "marketplace",
           "official_store_id": 111,
           "brand_value_id": "222",
           "brand_value_name": "Marca",
           "condition": "new",
           "current_level": "unknown",
           "deferred_stock": false,
           "picture_id": "ABCD_12345_XS",
           "thumbnail": "http://http2.mlstatic.com/D_870627-MLA74798069591_022024-I.jpg",
           "permalink": "https://articulo.mercadolibre.com.mx/MLM-2945696974-pantalla-samsung-led-smart-tv-de-65-pulgadas-4kuhd-_JM",
           "recommended": false,
           "metrics": {
               "clicks": 0,
               "prints": 0,
               "cost": 0.01,
               "cpc": 0.01,
               "acos": 0.01,
               "organic_units_quantity": 0,
               "organic_items_quantity": 0,
               "direct_items_quantity": 0,
               "indirect_items_quantity": 0,
               "advertising_items_quantity": 0,
               "direct_units_quantity": 0,
               "indirect_units_quantity": 0,
               "units_quantity": 0,
               "direct_amount": 0.01,
               "indirect_amount": 0.01,
               "total_amount": 0.01
             }      
       }
   ],
   "metrics_summary": {
       "clicks": 0,
       "prints": 0,
       "ctr": 0.01,
       "cost": 0.01,
       "cpc": 0.01,
       "acos": 0.01,
       "organic_units_quantity": 0,
       "organic_units_amount": 0,
       "organic_items_quantity": 0,
       "direct_items_quantity": 0,
       "indirect_items_quantity": 0,
       "advertising_items_quantity": 0,
       "cvr": 0,
       "roas": 0,
       "sov": 0,
       "direct_units_quantity": 0,
       "indirect_units_quantity": 0,
       "units_quantity": 0,
       "direct_amount": 0.01,
       "indirect_amount": 0.01,
       "total_amount": 0.01
   }
}
```

## Ad metrics

### Optional parameters

**date\_from**: Start date (YYYY-MM-DD). Validation required if metrics
are requested.

**date\_to**: End date (YYYY-MM-DD). Validation required if metrics are
requested.

**metrics**: Comma-separated list (e.g., clicks, prints). Indicates the
fields to be returned in the response. Possible values:

-   clicks, prints, ctr, cost, cpc, acos, organic\_units\_quantity,
    organic\_units\_amount, organic\_items\_quantity,
    direct\_items\_quantity, indirect\_items\_quantity,
    advertising\_items\_quantity, cvr, roas, sov,
    direct\_units\_quantity, indirect\_units\_quantity, units\_quantity,
    direct\_amount, indirect\_amount, total\_amount.

**aggregation**: Aggregation for presenting the results. Default: sum.

**aggregation\_type**: Aggregation type for presenting the results:
DAILY, item. Default: item.

**channel**: Item channel, mshops or marketplace. Default value:
marketplace.

  

Request:

``` language-javascript
curl -X  GET -H 'Authorization: Bearer $ACCESS_TOKEN' -H 'api-version: 2' 
https://api.mercadolibre.com/marketplace/advertising/$ADVERTISER_SITE_ID/product_ads/ads/$ITEM_ID?date_from=2024-01-01&date_to=2024-02-28&metrics=clicks,prints,ctr,cost,cpc,acos,organic_units_quantity,organic_units_amount,organic_items_quantity,direct_items_quantity,indirect_items_quantity,advertising_items_quantity,cvr,roas,sov,direct_units_quantity,indirect_units_quantity,units_quantity,direct_amount,indirect_amount,total_amount
```

Response:

``` language-javascript
{
    "item_id": "MLB19901111111",
    "campaign_id": 34858222,
    "price": 160.9,
    "price_usd": 0.0,
    "title": "Kit 20 Pares Futebol",
    "status": "active",
    "has_discount": false,
    "catalog_listing": false,
    "logistic_type": "fulfillment",
    "listing_type_id": "gold_pro",
    "domain_id": "MLB-FOOTBALL_SOCKS",
    "date_created": "2021-08-25T12:17:33Z",
    "buy_box_winner": false,
    "tags": [
        "sll"
    ],
    "channel": "marketplace",
    "brand_value_id": "4220111",
    "brand_value_name": "Sports",
    "condition": "new",
    "current_level": "green",
    "deferred_stock": false,
    "thumbnail": "http://http2.mlstatic.com/D_726420-MLB7411165_022024-I.jpg",
    "permalink": "https://produto.mercadolivre.com.br/MLB-111-kit-20-pares-meio-preto-futebol-adulto-atacado-37-44-_JM",
    "recommended": true,
    "image_quality": "good_quality_thumbnail",
    "metrics": {
        "clicks": 282,
        "prints": 38255,
        "cost": 310.77,
        "cpc": 1.1,
        "direct_amount": 2787.73,
        "indirect_amount": 134.88,
        "total_amount": 2922.61,
        "direct_units_quantity": 19,
        "indirect_units_quantity": 1,
        "units_quantity": 20,
        "direct_items_quantity": 19,
        "indirect_items_quantity": 1,
        "advertising_items_quantity": 20,
        "organic_units_quantity": 21,
        "organic_items_quantity": 21,
        "acos": 10.63,
        "organic_units_amount": 3001.0,
        "sov": 48.78,
        "ctr": 0.74,
        "cvr": 7.09,
        "roas": 940.44
    }
}
```

## Daily Ad Metrics

Example:

``` language-javascript
curl -X  GET -H 'Authorization: Bearer $ACCESS_TOKEN' -H 'api-version: 2' 
https://api.mercadolibre.com/marketplace/advertising/$ADVERTISER_SITE_ID/product_ads/ads/$ITEM_ID?date_from=2024-01-01&date_to=2024-02-28&metrics=clicks,prints,ctr,cost,cpc,acos,organic_units_quantity,organic_units_amount,organic_items_quantity,direct_items_quantity,indirect_items_quantity,advertising_items_quantity,cvr,roas,sov,direct_units_quantity,indirect_units_quantity,units_quantity,direct_amount,indirect_amount,total_amount&aggregation_type=DAILY
```

Response:

``` language-javascript
{
   "results": [
       {
           "clicks": 7,
           "prints": 307,
           "cost": 8.26,
           "cpc": 1.18,
           "direct_amount": 0.0,
           "indirect_amount": 0.0,
           "total_amount": 0.0,
           "direct_units_quantity": 0,
           "indirect_units_quantity": 0,
           "units_quantity": 0,
           "direct_items_quantity": 0,
           "indirect_items_quantity": 0,
           "advertising_items_quantity": 0,
           "organic_units_quantity": 1,
           "organic_items_quantity": 1,
           "acos": 0.0,
           "organic_units_amount": 137.0,
           "sov": 0.0,
           "ctr": 2.28,
           "cvr": 0.0,
           "roas": 0.0,
           "date": "2024-01-01"
       },
…
 ]
}
```

## Glossary

**total**: total number of records obtained.

**offset**: default value: 0.

**limit**: limit of elements in the campaign list. Default: 50.

**results**: results obtained.

**id**: identifier of the ad or campaign.

**budget**: daily average of the campaign's (monthly) budget, that is,
if the budget is not consumed during the day, the remaining budget will
be used in the following days until the end of the month.

**last\_updated**: date of last campaign modification.

**date\_created**: campaign creation date.

**price**: price of the associated item.

**title**: name of the publication.

**has\_discount**: whether it has a discount. This value is identified
based on the difference between the regular amount and the amount
provided by [Prices API](/en_us/price-apl#Get-current-sales-price).

**catalog\_listing**: catalog publication.

**logistic\_type**: logistics type for item shipping.

**listing\_type\_id**: identifier of the publication type.

**domain\_id**: domain.

**date\_created**: date of ad creation.

**official\_store\_id**: identifier of the official store.

**buy\_box\_winner**: buy box winner.

**channel**: campaign channel (marketplace or mshops).

**campaign\_id**: campaign identifier.

**condition**: Item condition.

**current\_level**: reputation.

**deferred\_stock**: available product stock. An [item with
manufacturing\_time](/en_us/products-sync-listings#Availability-time)
(availability time) causes the ad not to be displayed; ads with
immediate stock are prioritized.

**thumbnail**: link to the thumbnail image.

**permalink**: link to the publication.

**brand\_value\_id**: identifier of the brand associated with the item.

**brand\_value\_name**: name of the brand associated with the item.

**status**: status of the ad or campaign.

**recommended**: the ad is recommended.

**metrics**: Item or campaign metrics.

**clicks**: Campaign clicks.

**prints**: Number of impressions (times the ad is displayed).

**sov**: Sales by advertising percentage over total sales.

**clicks**: Campaign clicks.

**ctr**: Click-through rate.

**cost**: Campaign investment.

**cpc**: Cost per click.

**acos**: Advertising cost of sales percentage over revenue.

  

**Sales without advertising**

-   **organic\_units\_quantity**: number of units sold without
    advertising.
-   **organic\_units\_amount**: organic order sales amount.
-   **organic\_items\_quantity**: cantidad de ventas sin publicidad.

  

**Sales with advertising**

**Direct sells**

-   **direct\_items\_quantity**: amount of direct sales from
    advertising.
-   **direct\_units\_quantity**: number of units sold in direct sales.
-   **direct\_amount**: sum of the value of direct sales obtained from
    your Product Ad, in local currency.

**Indirect sales**

-   **indirect\_items\_quantity**: quantity of indirect sales from
    advertising.
-   **indirect\_units\_quantity**: number of units sold in assisted
    sales.
-   **indirect\_amount**: sum of the value of assisted sales obtained
    from your Product Ad, in local currency.

**advertising\_items\_quantity**: Quantity of sales by advertising.

**cvr**: Conversion rate.

**roas**: Return on advertising spend.

**units\_quantity**: Total quantity of sales.

**total\_amount**: Sum of the value of sales obtained from your Product
Ad, in local currency.

**impression\_share**: Percentage of times ads are shown considering all
the times they could be shown.

**top\_impression\_share**: Number of auctions won in the top search
positions among the number of auctions it could participate in.

**lost\_impression\_share\_by\_budget**: Percentage of times ads are not
shown considering all the times they could be shown and that didn't
happen because the budget is too low.

**lost\_impression\_share\_by\_ad\_rank**: Percentage of times ads are
not shown considering all the times they could be shown and that didn't
happen because your rank is lower than other sellers.

**acos\_benchmark**: Target ACOS (advertising cost of sales) used by ads
with good results in impressions and sales.

**picture\_id**: Item image ID at the MercadoLibre level.

**acos\_target**: Advertising cost of sales (ACOS) target used by ads
with good results in impressions and sales.

**strategy**: Campaign strategy type. It can be PROFITABILITY, INCREASE,
or VISIBILITY.

</div>
