<div class="inner-content">

## Listings quality

<div class="andes-message andes-message--highlight">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNSIgdmlld2JveD0iMCAwIDE1IDE1IiB3aWR0aD0iMTUiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--highlight site-carriers__message-title">

Important:

</div>

<div class="andes-message__text--highlight site-carriers__message-text">

Mercado Libre is updating the way it measures the Listing quality. As a
result, the /health API will be discontinued and replaced by the
/performance API, which encompasses all the metrics and actions
necessary to increase the quality of posts.

</div>

</div>

</div>

  

<div class="details__message">

The /performance resource allows you to show users (sellers) the quality
of their listings, knowing which actions have been completed and which
are pending. This way, they can achieve their listing goals and increase
the quality of their listings, improving item exposure and also the
selling and buying experience.

</div>

  

## Quality levels by site

The quality level is separated by the `level_wording` field in the
following way:

| Site        | Bad quality | Average quality | Good quality |
|-------------|-------------|-----------------|--------------|
| MLB         | Básica      | Satisfatória    | Profissional |
| MLA         | Básica      | Estándar        | Profesional  |
| CBT         | Basic       | Standard        | Professional |
| Other sites | Básica      | Estándar        | Profesional  |

  

## Quality detail by item

To find out the quality level of an item, you have the /performance
resource. Here, you can see all the quality data of the item, the number
of objectives met and the applicable actions. You also know the level in
which it falls.

<div class="andes-message andes-message--highlight">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--highlight site-carriers__message-title">

Important:

</div>

<div class="andes-message__text--highlight site-carriers__message-text">

All data from the previous /health API was aggregated into 1 endpoint,
with no need to perform further queries for more details.

</div>

</div>

</div>

  

Request:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/item/$ITEM_ID/performance
```

Example:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/item/MLA1435540505/performance
```

Response:

``` language-javascript
{
   "entity_type": "ITEM",
   "entity_id": "MLA1435540505",
   "score": 69,
   "level": "Good",
   "level_wording": "Profesional",
   "calculated_at": "2024-07-02T14:56:58Z",
   "buckets": [
       {
           "key": "CHARACTERISTICS",
           "type": "",
           "status": "PENDING",
           "score": 74.337616,
           "title": "Datos del producto",
           "calculated_at": "2024-07-02T14:56:58Z",
           "variables": [
               {
                   "key": "GTIN",
                   "status": "COMPLETED",
                   "score": 100,
                   "calculated_at": "2024-07-02T14:56:58Z",
                   "title": "Indicá el código universal de tu producto para no perder exposición",
                   "rules": [
                       {
                           "key": "HAS_GTIN",
                           "status": "COMPLETED",
                           "progress": 1,
                           "mode": "OPPORTUNITY",
                           "calculated_at": "2024-07-02T14:56:58Z",
                           "wordings": {
                               "title": "Asegurate de completar el código que pertenezca a este producto para estar más arriba en los resultados de búsqueda.",
                               "label": "Completar código universal",
                               "link": "https://www.mercadolibre.com.ar/syi/core/modify?taskId=universal_code_no_variations&itemId=MLA1435540505"
                           }
                       }
                   ]
               },
               {
                   "key": "PICTURES",
                   "status": "PENDING",
                   "score": 33.333336,
                   "calculated_at": "2024-07-02T14:56:58Z",
                   "title": "Mejorá las fotos para tener más visitas",
                   "rules": [
                       {
                           "key": "PICTURES_QUANTITY_MIN",
                           "status": "PENDING",
                           "progress": 0.33333334,
                           "mode": "OPPORTUNITY",
                           "calculated_at": "2024-07-02T14:56:58Z",
                           "wordings": {
                               "title": "Agregá más fotos para mostrar tu producto desde diferentes ángulos, subí 3 como mínimo.",
                               "label": "Agregar fotos",
                               "link": "https://www.mercadolibre.com.ar/syi/core/modify?taskId=picture_uploader_task&itemId=MLA1435540505"
                           }
                       }
                   ]
               }
           ]
       },
       {
           "key": "OFFER",
           "type": "",
           "status": "PENDING",
           "score": 61.111107,
           "title": "Condiciones de venta",
           "calculated_at": "2024-07-02T14:56:58Z",
           "variables": [
               {
                   "key": "FREE_SHIPPING",
                   "status": "COMPLETED",
                   "score": 100,
                   "calculated_at": "2024-07-02T14:56:58Z",
                   "title": "Ofrecé envío gratis para que tu publicación sea más competitiva",
                   "rules": [
                       {
                           "key": "HAS_FREE_SHIPPING",
                           "status": "COMPLETED",
                           "progress": 1,
                           "mode": "OPPORTUNITY",
                           "calculated_at": "2024-07-02T14:56:58Z",
                           "wordings": {
                               "title": "Ofrecé envío gratis para que tu publicación sea más competitiva",
                               "label": "Modificar envío",
                               "link": "https://www.mercadolibre.com.ar/syi/core/modify?taskId=shipping_task&itemId=MLA1435540505"
                           }
                       }
                   ]
               }
           ]
       }
   ]
}
```

  

### Response fields

**Main response object:**

-   **entity\_type** (String): Type of entity being evaluated. Values:
    "ITEM".
-   **entity\_id** (String): The item ID being evaluated.
-   **score** (Float): Quality score from 0 to 100.
-   **level** (String): Quality level. Values: "Bad", "Average", "Good".
-   **level\_wording** (String): Localized quality level name based on
    site (e.g., "Profesional", "Profissional", "Professional").
-   **calculated\_at** (String): ISO 8601 timestamp of when the quality
    was calculated.
-   **buckets** (Array): Array of bucket objects containing quality
    metrics grouped by category.

**Bucket object:**

-   **key** (String): Bucket identifier. Values: "CHARACTERISTICS",
    "OFFER".
-   **type** (String): Bucket type (usually empty).
-   **status** (String): Bucket status. Values: "PENDING", "COMPLETED".
-   **score** (Float): Bucket score from 0 to 100.
-   **title** (String): Localized bucket title.
-   **calculated\_at** (String): ISO 8601 timestamp.
-   **variables** (Array): Array of variable objects with specific
    quality metrics.

**Variable object:**

-   **key** (String): Variable identifier (e.g., "GTIN", "PICTURES",
    "TITLE", "FREE\_SHIPPING").
-   **status** (String): Variable status. Values: "PENDING",
    "COMPLETED".
-   **score** (Float): Variable score from 0 to 100.
-   **calculated\_at** (String): ISO 8601 timestamp.
-   **title** (String): Localized variable title with action suggestion.
-   **rules** (Array): Array of rule objects with specific validation
    criteria.

**Rule object:**

-   **key** (String): Rule identifier (e.g., "HAS\_GTIN",
    "PICTURES\_QUANTITY\_MIN").
-   **status** (String): Rule status. Values: "PENDING", "COMPLETED".
-   **progress** (Float): Progress value from 0 to 1.
-   **mode** (String): Rule mode. Values: "OPPORTUNITY", "WARNING".
-   **calculated\_at** (String): ISO 8601 timestamp.
-   **wordings** (Object): Contains localized text for title, label, and
    link.

  

### Errors

Possible API errors:

| Status\_code | Error code   | Error message                                      | Description                                                                                             |
|--------------|--------------|----------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| 400          | bad\_request | The request sent is not valid                      | When the request format is incorrect or malformed.                                                      |
| 400          | bad\_request | Entity not calculated: Site CBT is not supported   | When querying performance for a CBT (Cross Border Trade) item. This endpoint only supports local items. |
| 401          | unauthorized | Caller must be the seller of the item              | When the item does not belong to the access\_token user.                                                |
| 403          | forbidden    | You do not have permission to access this resource | When there are permission issues with the access\_token.                                                |
| 404          | not\_found   | Not found item performance                         | When performance data has not been generated for the item yet.                                          |

</div>
