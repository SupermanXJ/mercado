<div class="inner-content">

## Application and permissions

<div class="details__message">

With this API you can access full details about your application, simply
include the app\_id in the API request. In addition, get information
about grants, users and revoke grants of users.

</div>

  
  

## Applications details

Request:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' http://api.mercadolibre.com/applications/$APP_ID
```

Example:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' http://api.mercadolibre.com/applications/5685250730848580
```

Response:

``` language-javascript
{
   "id": 5685250730848580,
   "site_id": "CBT",
   "name": "TestAuth",
   "description": "Auth test",
   "thumbnail": "https://http2.mlstatic.com/storage/platsec-applications-dev-mngr/prod-applications-fe/1679436423519_1198410922.png",
   "catalog_product_id": null,
   "item_id": null,
   "price": null,
   "currency_id": null,
   "short_name": "Auth",
   "url": "http://globalselling.mercadolibre.com/devcenter/auth",
   "callback_url": "https://dle.rae.es/",
   "sandbox_mode": true,
   "project_id": null,
   "active": true,
   "max_requests_per_hour": 18000,
   "scopes": [
       "write",
       "read",
       "offline_access"
   ],
   "notifications_callback_url": "https://dle.rae.es/",
   "notifications_topics": [
       "items",
       "marketplace_items",
       "marketplace_questions"
   ],
   "domains": [],
   "certification_status": "not_certified",
   "token_type": "",
   "use_pkce": false,
   "date_created": "2023-03-21T18:07:03.000-04:00",
   "blocked": false,
   "blocked_date": "",
   "blocked_reason": "",
   "disabled": false,
   "disabled_date": ""
}
```

## Applications authorized by user

To access all the applications authorized by a user, just send a GET
request as a user\_id and access token. In addition, you can see
[Permissions granted to
Applications](https://global-selling.mercadolibre.com/apps/permissions).

  

Request:

``` language-javascript
curl -H 'Authorization: Bearer $ACCESS_TOKEN' -X GET https://api.mercadolibre.com/users/$USER_ID/applications
```

Example:

``` language-javascript
curl -H 'Authorization: Bearer $ACCESS_TOKEN' -X GET https://api.mercadolibre.com/users/481241763/applications
```

The response would be an array of applications with the following
format:

``` language-javascript
[
    {
        "user_id": 481241763,
        "app_id": 7982740196824807,
        "date_created": "2019-10-18T16:30:44.000-04:00",
        "scopes": [
            "offline_access",
            "read",
            "write"
        ]
    },
    {
        "user_id": 481241763,
        "app_id": 1503799861804470,
        "date_created": "2020-02-05T13:00:48.000-04:00",
        "scopes": [
            "offline_access",
            "read",
            "write"
        ]
    }
]
```

## Users granted permissions to app

Request:

``` language-javascript
curl -H 'Authorization: Bearer $ACCESS_TOKEN' -X GET https://api.mercadolibre.com/applications/$APP_ID/grants
```

Example:

``` language-javascript
curl -H 'Authorization: Bearer $ACCESS_TOKEN' -X GET https://api.mercadolibre.com/applications/1503799861804470/grants
```

Response:

``` language-javascript
{
  "grants": [
    {
      "user_id": 481241763,
      "app_id": 1503799861804470,
      "date_created": "2020-02-05T13:00:48.000-04:00",
      "scopes": [
        "offline_access",
        "read",
        "write"
      ]
    }
  ],
  "paging": {
    "total": 1,
    "limit": 50,
    "offset": 0
  }
}
```

## Fields description

**user\_id**: user identifier.  
**app\_id**: application identifier.  
**date\_created**: date the authorization was created  
**scopes**: permissions given to the application: read, write and
offline\_access.

  

## Revoke user authorization

Request:

``` language-javascript
curl -H 'Authorization: Bearer $ACCESS_TOKEN' -X DELETE https://api.mercadolibre.com/users/$USER_ID/applications/$APP_ID
```

Response:

``` language-javascript
{
    "user_id":"998877",
    "app_id":"1234567891011",
    "msg":"Autorización eliminada"
}
```

  

## Application Consumption Metrics

To access the details of all MeLi resource consumption by your
application, simply perform the following GET:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/applications/v1/$APP_ID/consumed-applications?date_start=2025-08-01&date_end=2025-08-20
```

Response:

``` language-javascript
{
    "app_id": 5555737222442288,
    "total_request": 3773948444,
    "request_by_status": [
        {
            "total_request": 1,
            "status": 412,
            "percentage": 0
        },
        {
            "total_request": 108,
            "status": 502,
            "percentage": 0.0000029
        },
        {
            "total_request": 253,
            "status": 534,
            "percentage": 0.0000067
        },
        {
            "total_request": 680,
            "status": 423,
            "percentage": 0.000018
        },
        {
            "total_request": 15587,
            "status": 503,
            "percentage": 0.000413
        },
        {
            "total_request": 19393,
            "status": 405,
            "percentage": 0.0005139
        },
        {
            "total_request": 56464,
            "status": 499,
            "percentage": 0.0014962
        },
        {
            "total_request": 64834,
            "status": 204,
            "percentage": 0.0017179
        },
        {
            "total_request": 74716,
            "status": 535,
            "percentage": 0.0019798
        },
        {
            "total_request": 150226,
            "status": 500,
            "percentage": 0.0039806
        },
        {
            "total_request": 202157,
            "status": 409,
            "percentage": 0.0053566
        },
        {
            "total_request": 425759,
            "status": 422,
            "percentage": 0.0112815
        },
        {
            "total_request": 638862,
            "status": 201,
            "percentage": 0.0169282
        },
        {
            "total_request": 1999743,
            "status": 400,
            "percentage": 0.0529881
        },
        {
            "total_request": 4764611,
            "status": 429,
            "percentage": 0.12625
        },
        {
            "total_request": 7441701,
            "status": 206,
            "percentage": 0.1971861
        },
        {
            "total_request": 12630990,
            "status": 401,
            "percentage": 0.334689
        },
        {
            "total_request": 29612527,
            "status": 404,
            "percentage": 0.7846564
        },
        {
            "total_request": 91749024,
            "status": 403,
            "percentage": 2.4311149
        },
        {
            "total_request": 3624100808,
            "status": 200,
            "percentage": 96.0294202
        }
    ],
    "top_apis_consumed": [
        {
            "resource_id": "read.items-visits",
            "resource_name": "METRICS",
            "hierarchy1": "VISITS",
            "hierarchy2": "USER_ITEM_VISITS",
            "percentage_request_successful": 94.4858993
        },
        {
            "resource_id": "public-read.items-prices-api",
            "resource_name": "PUBLIC_SYNC",
            "hierarchy1": "PRICES",
            "hierarchy2": "CHECK_PRICES",
            "percentage_request_successful": 99.6489243
        },
        {
            "resource_id": "items-public.multigetapi",
            "resource_name": "PUBLIC_SYNC",
            "hierarchy1": "ITEMS",
            "hierarchy2": "MULTIGET_SEARCH",
            "percentage_request_successful": 99.952714
        },
        {
            "resource_id": "public.pc-open-platform-api",
            "resource_name": "COMMUNICATION",
            "hierarchy1": "CLAIMS",
            "hierarchy2": "RETURN_DETAILS",
            "percentage_request_successful": 91.8956306
        },
        {
            "resource_id": "public.pc-open-platform-api",
            "resource_name": "COMMUNICATION",
            "hierarchy1": "CLAIMS",
            "hierarchy2": "RETURN_DETAILS",
            "percentage_request_successful": 0.0014296
        },
        {
            "resource_id": "public.shipping-mandatory-api",
            "resource_name": "SALES_SHIPMENTS",
            "hierarchy1": "SHIPPING_COSTS_SLA",
            "hierarchy2": "CHECK_SHIPPING_COSTS",
            "percentage_request_successful": 99.8737551
        },
        {
            "resource_id": "public.shipping-shipments-api",
            "resource_name": "SALES_SHIPMENTS",
            "hierarchy1": "MERCADO_SHIPMENTS",
            "hierarchy2": "MANAGE_SHIPMENTS",
            "percentage_request_successful": 99.9241283
        },
        {
            "resource_id": "public-postsale-read.supply-messages-gateway",
            "resource_name": "MESSAGING",
            "hierarchy1": "REASONS",
            "hierarchy2": "CHECK_REASONS_AND_MESSAGES_BY_ID",
            "percentage_request_successful": 99.8578694
        }
    ],
    "top_apis_consumed_error": [
        {
            "resource_id": "public.pc-open-platform-api",
            "errors_by_resource_id": 9272595,
            "resource_name": "COMMUNICATION",
            "hierarchy1": "CLAIMS",
            "hierarchy2": "RETURN_DETAILS",
            "percentage_errors": 8.1029398
        },
        {
            "resource_id": "read.items-visits",
            "errors_by_resource_id": 4200509,
            "resource_name": "METRICS",
            "hierarchy1": "VISITS",
            "hierarchy2": "USER_ITEM_VISITS",
            "percentage_errors": 5.5141007
        },
        {
            "resource_id": "public-read.items-prices-api",
            "errors_by_resource_id": 2041039,
            "resource_name": "PUBLIC_SYNC",
            "hierarchy1": "PRICES",
            "hierarchy2": "CHECK_PRICES",
            "percentage_errors": 0.3510757
        },
        {
            "resource_id": "public-postsale-read.supply-messages-gateway",
            "errors_by_resource_id": 135181,
            "resource_name": "MESSAGING",
            "hierarchy1": "REASONS",
            "hierarchy2": "CHECK_REASONS_AND_MESSAGES_BY_ID",
            "percentage_errors": 0.1421306
        },
        {
            "resource_id": "public.shipping-mandatory-api",
            "errors_by_resource_id": 912460,
            "resource_name": "SALES_SHIPMENTS",
            "hierarchy1": "SHIPPING_COSTS_SLA",
            "hierarchy2": "CHECK_SHIPPING_COSTS",
            "percentage_errors": 0.1262449
        },
        {
            "resource_id": "public.shipping-shipments-api",
            "errors_by_resource_id": 600915,
            "resource_name": "SALES_SHIPMENTS",
            "hierarchy1": "MERCADO_SHIPMENTS",
            "hierarchy2": "MANAGE_SHIPMENTS",
            "percentage_errors": 0.0758717
        },
        {
            "resource_id": "items-public.multigetapi",
            "errors_by_resource_id": 376990,
            "resource_name": "PUBLIC_SYNC",
            "hierarchy1": "ITEMS",
            "hierarchy2": "MULTIGET_SEARCH",
            "percentage_errors": 0.047286
        }
    ]
}
```

### Considerations

-   The date parameter is optional. If not provided, the resource will
    return consumption data for the last 15 days.
-   The information is updated as D-1, meaning you will always have
    consumption up to the day prior to the current date.
-   We recommend that searches be performed with monthly intervals
    rather than very large intervals, because due to the amount of data,
    the search may take too long and result in a “timeout” error.

**Next**: [Design
considerations](https://global-selling.mercadolibre.com/devsite/design-considerations-global-selling).

</div>
