<div class="inner-content">

# Design considerations

<div class="details__message">

When you start working with our API, you must take into account some
basic concepts as JSON format, handling errors, reducing responses,
using OPTIONS for API discovery, and pagination (limit and offset).

</div>

## JSON format

Is an open standard based on lightweight text designed for the exchange
of readable data. You can read these types of messages through a
browser, specific tools (Ex: Postman) or from any development that
consumes the Mercado Libre API. For a JSONP response, add a callback
parameter as follows:

  
Example:

``` language-javascript
curl -X GET https://api.mercadolibre.com/currencies/MXN?callback=foo
```

<span class="pre-label">Response:</span>

``` language-javascript
foo([
    200,
    {
        "Cache-Control": [
            "max-age=3600,stale-while-revalidate=1800, stale-if-error=7200"
        ],
        "Content-Type": [
            "text/javascript;charset=UTF-8"
        ]
    },
    {
        "id": "MXN",
        "symbol": "$",
        "description": "Peso Mexicano",
        "decimal_places": 2
    }
]);
```

As you can see, the response is an array with 3 values:

-   HTTPS status code
-   HTTPS response headers
-   Body of the response

All JSONP responses will always be 200 OK. This is in order to give you
the chance to handle 30x, 40x, and 50x responses on the client side. The
real response data is in the array.

  

## Error format

The standard format of an error is as follows:

``` language-javascript
{
  "message": "human readable text",
  "error": "machine_readable_error_code",
  "status": 400,
  "cause": [ ]
}
```

## Reduce responses

To have shorter answers, with less data, you can add the attributes
parameter with a comma by separating the list of fields that should be
included in the response.

``` language-javascript
curl -X GET https://api.mercadolibre.com/currencies?attributes=id
```

<span class="pre-label">Response:</span>

``` language-javascript
[
    {
        "id": "ARS"
    },
    {
        "id": "BOB"
    },
    {
        "id": "BRL"
    },
    {
        "id": "CLF"
    },
    {
        "id": "CLP"
    },
    {
        "id": "COP"
    },
    {
        "id": "CRC"
    },
    {
        "id": "CUC"
    },
    {
        "id": "CUP"
    },
    {
        "id": "DOP"
    },
    {
        "id": "EUR"
    },
    {
        "id": "GTQ"
    },
    {
        "id": "HNL"
    },
    {
        "id": "MXN"
    },
    {
        "id": "NIO"
    },
    {
        "id": "PAB"
    },
    {
        "id": "PEN"
    },
    {
        "id": "PYG"
    },
    {
        "id": "USD"
    },
    {
        "id": "UYU"
    },
    {
        "id": "VEF"
    },
    {
        "id": "VES"
    }
]
```

## Using OPTIONS

The API will deliver documentation in JSON format using the OPTIONS HTTP
method. This allows you to discover any endpoint's available methods,
attributes, and connections dynamically.

``` language-javascript
curl -X OPTIONS https://api.mercadolibre.com/currencies
```

<span class="pre-label">Response:</span>

``` language-javascript
{
  "name": "Currencies",
  "description": "Returns information corresponding to the ISO of the currencies used in MercadoLibre.",
  "attributes": {
    "id": "Currency ID (ISO Code)",
    "description": "Official currency denomination",
    "symbol": "ISO symbol to represent the currency",
    "decimal_places": "Number of decimals handled with the currency"
  },
  "methods": [
    {
      "method": "GET",
      "example": "/currencies/",
      "description": "Returns the list with all currencies."
    },
    {
      "method": "GET",
      "example": "/currencies/:id",
      "description": "Returns information regarding a specific currency."
    }
  ],
  "related_resources": [],
  "connections": {
    "id": "/currencies/:id"
  }
}
```

The response includes:

-   **name**: The resource name
-   **description**: What the endpoint does
-   **attributes**: Available fields and their descriptions
-   **methods**: Supported HTTP methods with examples
-   **connections**: Related endpoints you can navigate to

  

## Results pagination

You can define the page size of the result list. There are 2 parameters:
limit and offset. Both parameters define the size block of the results.
This article is based on the search example, but you can use pagination
on each resource that is presented in the "pagination" response
information, as shown below:

``` language-javascript
"paging": {
  "total": 285,
  "offset": 0,
  "limit": 50
}
```

![](https://http2.mlstatic.com/storage/developers-site-cms-admin/DevSite/331847941519-range-slider.png)  
  

### Default values

The default values are **offset=0** and **limit=50** for most search and
listing endpoints. In the pagination section of the JSON response, you
can see the total number of items matching the search and the offset
value with the default limit applied.

``` language-javascript
curl -X GET https://api.mercadolibre.com/sites/MLM/search?q=iphone
```

<span class="pre-label">Response:</span>

``` language-javascript
{
  "site_id": "MLM",
  "query": "iphone",
  "paging": {
    "total": 285,
    "offset": 0,
    "limit": 50
  },
  "results": [...],
  "sort": {...},
  "available_sorts": [...],
  "filters": [...],
  "available_filters": [...]
}
```

  

### Limit

To reduce the page size, you can change the limit parameter. For
example, if you are interested in recovering only the first 3 items:

``` language-javascript
curl -X GET https://api.mercadolibre.com/sites/MLM/search?q=iphone&limit=3
```

<span class="pre-label">Response:</span>

``` language-javascript
{
  "site_id": "MLM",
  "query": "iphone",
  "paging": {
    "total": 285,
    "offset": 0,
    "limit": 3
  },
  "results": [
    {...},
    {...},
    {...}
  ],
  "sort": {...},
  "available_sorts": [...],
  "filters": [...],
  "available_filters": [...]
}
```

  

### Offset

By using the offset attribute, you can move the lower limit of the
result block. For example, if you are interested in recovering the 50
items that follow the default response:

``` language-javascript
curl -X GET https://api.mercadolibre.com/sites/MLM/search?q=iphone&offset=50
```

<span class="pre-label">Response:</span>

``` language-javascript
{
  "site_id": "MLM",
  "query": "iphone",
  "paging": {
    "total": 285,
    "offset": 50,
    "limit": 50
  },
  "results": [...],
  "sort": {...},
  "available_sorts": [...],
  "filters": [...],
  "available_filters": [...]
}
```

This response retrieves 50 items starting from the first fifty.

  

### Define a range of results

It is possible to combine both parameters. You can retrieve items from
the third to the sixth in the original search result:

``` language-javascript
curl -X GET https://api.mercadolibre.com/sites/MLM/search?q=iphone&offset=3&limit=3
```

<span class="pre-label">Response:</span>

``` language-javascript
{
  "site_id": "MLM",
  "query": "iphone",
  "paging": {
    "total": 285,
    "offset": 3,
    "limit": 3
  },
  "results": [
    {...},
    {...},
    {...}
  ],
  "sort": {...},
  "available_sorts": [...],
  "filters": [...],
  "available_filters": [...]
}
```

  

**Next**: [Best practices for listing
items](https://global-selling.mercadolibre.com/devsite/introduction-globalselling).

</div>
