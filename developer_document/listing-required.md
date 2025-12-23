<div class="inner-content">

## Listing Required

A global item is required to create a catalog listing when at least one
of its associated marketplace items has the
**catalog\_listing\_eligible** tag and, additionally, the assigned
catalog product has the **listing\_strategy field: catalog\_required**.
In this case, Mercado Libre may moderate the publication by requesting
that it be published in the catalog [using the optin
resource](https://global-selling.mercadolibre.com/devsite/catalog-listing-gs).

  

## Forewarning items

### Parameters

-   **offset**: (optional) position from which the search results are
    returned, default = 0
-   **limit**: (optional) number of results returned by the search,
    default = 10

Basic request:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/marketplace/items/catalog-forewarning
```

Full Params Request:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/marketplace/items/catalog-forewarning?limit=100&offset=50
```

Response:

``` language-javascript
{
    "results": [
        "CBT1474622328",
        "CBT1590480986",
        "CBT1491506053",
    ],
    "paging": {
        "total": 4,
        "offset": 0,
        "limit": 10
    }
}
```

  
  

**Next**: [Catalog
competition](https://global-selling.mercadolibre.com/devsite/catalog-competition-gs).

</div>
