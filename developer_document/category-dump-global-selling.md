<div class="inner-content">

# Category dump

<div class="details__message">

The category tree is a structure where Mercado Libre organizes its
listings. Each country has its own category tree that is different from
each other. Listings can only be posted on the leaf categories of the
tree. Sometimes, the category tree changes because a new category is
created, or an existing category is split in two or more categories. All
the listings posted in the old category are automatically moved to the
new category.

</div>

  

## Contents

[→Download the category tree dump](#download)  
[→Category dump with attributes](#attributes)  
[→Error responses](#errors)  

  

## Download the category tree dump

This API returns the category tree in JSON format within a gzip-encoded
response. To get the categories for Global Selling, for example, use
this URL:  

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/sites/CBT/categories/all  > categoriesCBT.gz
```

This URL contains 2 headers that can be used to check when the last dump
was generated.

-   **X-Content-Created:** contains the date of the last generation.
-   **X-Content-MD5:** contains the MD5 checksum of the last generation.

``` language-javascript
curl -I -H 'Authorization: Bearer $ACCESS_TOKEN'https://api.mercadolibre.com/sites/CBT/categories/all
HTTP/1.1 200 OK
Server: nginx/1.0.4
Date: Tue, 24 Jul 2012 15:14:58 GMT
Content-Type: application/json;charset=UTF-8
Connection: keep-alive
X-MLAPI-Version: 1.9.5
Content-Encoding: gzip
X-Content-Created: 2012-07-24T14:00:59.716Z
X-Content-MD5: 943541196986770119b4af1e66bda2dc
```

## Category dump with attributes

Since categories have attributes of their own that you also need to map,
by making the following call you can get a file that contains the
category tree with each of it's attributes.

Request:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/sites/$SITE_ID/categories/all?withAttributes=true > mla.gz
```

Example:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/sites/CBT/categories/all?withAttributes=true > cbt.gz
```

## Error responses

| Code    | Error             | Description                             | Possible cause                                                                                                                      |
|---------|-------------------|-----------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------|
| **400** | site is not valid | The provided site ID is not recognized. | The site\_id is invalid, uses lowercase letters (e.g., `mla` instead of `MLA`), contains special characters, or is a numeric value. |

  

</div>
