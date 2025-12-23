<div class="inner-content">

## Product Reviews

<div class="details__message">

Once the product has been delivered to the buyer, they will be able to
share their experience by indicating how many stars they would give the
product, leaving a comment, and in the case of Fashion products,
indicating whether the item matched their expectations. This allows
sellers to track the average star rating of their products. In Mercado
Libre, the stars and number of reviews are displayed under the listing
title.

</div>

<img src="https://http2.mlstatic.com/storage/developers-site-cms-admin/DevSite/289299676147-review.png" width="700" height="291" alt="Product reviews display example" />  
  

### Get Item Reviews

Retrieve reviews for a specific item using its item ID.

#### Parameters

-   **limit** (Integer, optional): Maximum number of reviews to return.
    Default: 5. Must be a positive integer less than 10000.
-   **offset** (Integer, optional): Number of reviews to skip for
    pagination. Default: 0. Must be a positive integer less
    than 1000000.
-   **catalog\_product\_id** (String, optional): Catalog product ID to
    filter reviews for catalog items.

Request:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/reviews/item/$ITEM_ID
```

Example:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/reviews/item/MLM15482175
```

Response:

``` language-javascript
{
  "paging": {
    "total": 3,
    "limit": 5,
    "offset": 0,
    "kvs_total": 3,
    "reviews_with_comment": 3
  },
  "reviews": [
    {
      "id": 60934080,
      "reviewable_object": {
        "id": "MLM769281453",
        "type": "product"
      },
      "date_created": "2020-05-02T13:18:21Z",
      "status": "published",
      "title": "Es un excelente teléfono muy recomendable...!!!",
      "content": "Buen producto excelente calidad. Trabaja correctamente y sus actualizaciones bien.",
      "rate": 5,
      "valorization": 0,
      "likes": 0,
      "dislikes": 0,
      "reviewer_id": 0,
      "buying_date": "2020-04-16T04:00:00Z",
      "relevance": 10,
      "forbidden_words": 0
    },
    {
      "id": 61913880,
      "reviewable_object": {
        "id": "MLM771812030",
        "type": "product"
      },
      "date_created": "2020-05-13T11:08:42Z",
      "status": "published",
      "title": "Excelente",
      "content": "Excelente compra! todo nuevo como lo comenta la publicación.",
      "rate": 5,
      "valorization": 0,
      "likes": 0,
      "dislikes": 0,
      "reviewer_id": 0,
      "buying_date": "2020-04-27T04:00:00Z",
      "relevance": 9,
      "forbidden_words": 20
    },
    {
      "id": 60318050,
      "reviewable_object": {
        "id": "MLM769281453",
        "type": "product"
      },
      "date_created": "2020-04-24T21:31:55Z",
      "status": "published",
      "title": "perfecto",
      "content": "Muy bien ekipo sellado nuevo conforme.",
      "rate": 5,
      "valorization": 0,
      "likes": 0,
      "dislikes": 0,
      "reviewer_id": 0,
      "buying_date": "2020-04-20T04:00:00Z",
      "relevance": 6,
      "forbidden_words": 0
    }
  ],
  "rating_average": 5,
  "stars": 5,
  "rating_levels": {
    "one_star": 0,
    "two_star": 0,
    "three_star": 0,
    "four_star": 0,
    "five_star": 3
  },
  "helpful_reviews": {
    "best_max_stars": null,
    "best_min_stars": null
  },
  "attributes": [],
  "quanti_attributes": [],
  "quali_attributes": [],
  "metadata": {}
}
```

### Response Fields

**paging**: Pagination information for the results.

-   **total**: Total number of reviews available.
-   **limit**: Maximum number of reviews returned per request.
-   **offset**: Number of reviews skipped.
-   **kvs\_total**: Total count from key-value store.
-   **reviews\_with\_comment**: Number of reviews that include a written
    comment.

**reviews**: Array of product reviews.

-   **id**: Unique identifier of the review.
-   **reviewable\_object**: Object containing information about the
    reviewed item.
    -   **id**: Item ID being reviewed.
    -   **type**: Type of reviewable object (e.g., "product").
-   **date\_created**: Date and time when the review was created (ISO
    8601 format).
-   **status**: Review status (e.g., "published", "pending").
-   **title**: Review title provided by the buyer.
-   **content**: Full text content of the review.
-   **rate**: Star rating given by the buyer (1 to 5).
-   **valorization**: Numeric value indicating the review's quality
    score.
-   **likes**: Number of users who found this review helpful.
-   **dislikes**: Number of users who found this review unhelpful.
-   **reviewer\_id**: Reviewer's user ID (obfuscated, always returns 0).
-   **buying\_date**: Date when the product was purchased (ISO 8601
    format).
-   **relevance**: Numeric score indicating the review's relevance
    ranking.
-   **forbidden\_words**: Numeric indicator for content moderation
    flags.

**rating\_average**: Average star rating across all reviews (decimal
value from 1.0 to 5.0).

**stars**: Overall star rating displayed for the item.

**rating\_levels**: Breakdown of reviews by star rating.

-   **one\_star**: Count of 1-star reviews.
-   **two\_star**: Count of 2-star reviews.
-   **three\_star**: Count of 3-star reviews.
-   **four\_star**: Count of 4-star reviews.
-   **five\_star**: Count of 5-star reviews.

**helpful\_reviews**: Information about the most helpful reviews.

-   **best\_max\_stars**: Most helpful positive review (null if none
    available).
-   **best\_min\_stars**: Most helpful critical review (null if none
    available).

**attributes**: Array of product attributes mentioned in reviews.

**quanti\_attributes**: Array of quantitative attributes from reviews.

**quali\_attributes**: Array of qualitative attributes from reviews.

**metadata**: Additional metadata about the reviews response.

  

<div class="andes-message andes-message--neutral">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--neutral site-carriers__message-title">

Note:

</div>

<div class="andes-message__text--neutral site-carriers__message-text">

<div>

The information in the **reviewer\_id** parameter is obfuscated and
always returns the value (0) for privacy protection.

</div>

</div>

</div>

</div>

  

## Catalog Item Reviews

To retrieve reviews for catalog items, use the `catalog_product_id`
query parameter along with the item ID. This allows you to access
aggregated reviews from all items linked to the same catalog product.

Request:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/reviews/item/$ITEM_ID?catalog_product_id=$CATALOG_PRODUCT_ID
```

Example:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/reviews/item/MLB1632704547?catalog_product_id=MLB14186226
```

Response:

``` language-javascript
{
  "paging": {
    "total": 55,
    "limit": 5,
    "offset": 0,
    "kvs_total": 55,
    "reviews_with_comment": 50
  },
  "reviews": [
    {
      "id": 90579197,
      "reviewable_object": {
        "id": "MLB14186226",
        "type": "product"
      },
      "date_created": "2020-12-29T12:06:45Z",
      "status": "published",
      "title": "Excelente custo beneficio",
      "content": "Excelente custo beneficio com recursos de celulares top (carregamento sem fio, carrega outros devices como proprio fone, boa capacidade de memoria, rapido, acabamento bonito, tela plana). Como pequena desvantagem: o tamanho da tela poderia ser um pouquiho maior, o que para alguns pode ser uma vantagem.",
      "rate": 5,
      "valorization": 1,
      "likes": 1,
      "dislikes": 0,
      "reviewer_id": 0,
      "buying_date": "2020-11-24T04:00:00Z",
      "relevance": 46,
      "forbidden_words": 50
    }
  ],
  "rating_average": 4.6,
  "stars": 5,
  "rating_levels": {
    "one_star": 3,
    "two_star": 0,
    "three_star": 3,
    "four_star": 5,
    "five_star": 44
  },
  "helpful_reviews": {
    "best_max_stars": null,
    "best_min_stars": null
  },
  "attributes": [],
  "quanti_attributes": [],
  "quali_attributes": [],
  "metadata": {}
}
```

  

## Errors

The following table lists the possible errors returned by the Product
Reviews API:

| Status\_code | Error code   | Error message                             | Description                                                                                         |
|--------------|--------------|-------------------------------------------|-----------------------------------------------------------------------------------------------------|
| 400          | unauthorized | String $ITEM\_ID is not valid             | When the item ID does not follow the correct format (site prefix + numeric ID, e.g., MLM123456789). |
| 400          | bad\_request | Not valid limit                           | When the limit parameter exceeds the maximum allowed value.                                         |
| 400          | bad\_request | Not valid offset                          | When the offset parameter exceeds the maximum allowed value.                                        |
| 403          | forbidden    | At least one policy returned UNAUTHORIZED | When the access token is invalid, expired, or lacks the required permissions.                       |

  

</div>
