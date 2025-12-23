<div class="inner-content">

## Paging results

<div class="details__message">

You can define the page size of the result list. There are 2 parameters:
Limit and Offset. Both parameters define the size block of the results.
This article is based on the search example, but you can use paging on
every resource that presents on its response information about "paging",
like follows:

</div>

``` language-javascript
[...]
  "paging": {
    "total": 285,
    "offset": 0,
    "limit": 50,
  }
[...]
```

  
[<img src="https://http2.mlstatic.com/storage/developers-site-cms-admin/s3/range-slider.png" class="alignnone size-full wp-image-785" width="300" height="45" alt="range-slider" />](https://http2.mlstatic.com/storage/developers-site-cms-admin/s3/range-slider.png)  

## Default values

Default values are offset=0 and limit=50.

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/sites/MLM/search?q=ipad
```

In the paging section of the JSON response, you can see the total number
of items that match the search and the offset value with the default
limit applied.

``` language-javascript
[...]
  "paging": {
    "total": 285,
    "offset": 0,
    "limit": 50,
  }
[...]
```

  

## Limit

To reduce the page size you can change the limit parameter. For example,
if you are interested in retrieving just the first 3 items:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/sites/MLM/search?q=ipod nano&limit=3
```

This action retrieves a JSON data with an array of 3 items as shown:

``` language-javascript
{
  "site_id": "MLM",
  "query": "ipod nano",
  "paging": {
    "total": 284,
    "offset": 0,
    "limit": 3,
  },
  "results": [
    {...},
    {...},
    {...},
  ],
  "sort": {...},
  "available_sorts": [...],
  "filters": [...],
  "available_filters": [...],
}
```

## Offset

By using the offset attribute, you can move the lower limit of the
result block. For example, if you are interested in retrieving the 50
items that follow the default response:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/sites/MLM/search?q=ipod nano&offset=50
{
  "site_id": "MLM",
  "query": "ipod nano",
  "paging": {
    "total": 285,
    "offset": 50,
    "limit": 50,
  },
  "results": [...],
  "sort": {...},
  "available_sorts": [...],
  "filters": [...],
  "available_filters": [...],
}
```

This response retrieves 50 items starting from the first fifty items.

  

## Define a range of results

It is possible to combine both parameters. You can retrieve items from
the third to the sixth item in the original search result:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/sites/MLM/search?q=ipod nano&offset=3&limit=3
```

This action retrieves a JSON data with an array of 5 items as shown:

``` language-javascript
{
  "site_id": "MLM",
  "query": "ipod nano",
  "paging": {
    "total": 285,
    "offset": 3,
    "limit": 3,
  },
  "results": [
    {...},
    {...},
    {...},
  ],
  "sort": {...},
  "available_sorts": [...],
  "filters": [...],
  "available_filters": [...],
}
```

</div>
