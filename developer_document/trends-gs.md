<div class="inner-content">

## Trends

<div class="details__message">

With the resource /trends you can find out which are the 50 products
most sought after by users in Mercado Libre. The trends are updated
weekly ([Argentina](https://tendencias.mercadolibre.com.ar/),
[Brazil](https://tendencias.mercadolivre.com.br/),
[Chile](https://tendencias.mercadolibre.cl/),
[Mexico](https://tendencias.mercadolibre.com.mx/),
[Colombia](https://tendencias.mercadolibre.com.co/),
[Uruguay](https://tendencias.mercadolibre.com.uy/),
[Peru](https://tendencias.mercadolibre.com.pe/)) and you can also query
them as follows.

</div>

<div class="andes-message andes-message--neutral">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--neutral site-carriers__message-title">

Note: The API integrates 3 criteria

</div>

<div class="andes-message__text--neutral site-carriers__message-text">

<div>

\- The fastest growing searches are calculated over the last 2 weeks. (A
comparison of both weeks is performed)  
- The most wanted and most popular searches are the result of the last
week.  
This information is renewed weekly.

</div>

</div>

</div>

</div>

![](https://http2.mlstatic.com/storage/developers-site-cms-admin/248596260563-Captura-de-Tela-2022-07-22-a-s-14.19.54.png)  

## Search for trends by country

Request:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/trends/$SITE_ID
```

Example:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/trends/MLA
```

Response:

``` language-javascript
[
 {
   "keyword": "alfombras",
   "url": "https://hogar.mercadolibre.com.ar/textiles-decoracion-alfombras-carpetas/alfombras"
 },
 {
   "keyword": "lavarropa automatico",
   "url": "https://listado.mercadolibre.com.ar/lavado-lavarropas-lavasecarropas/lavarropas-automaticos"
 },
 {
   "keyword": "smart tv 32",
   "url": "https://televisores.mercadolibre.com.ar/televisores/smart-tv-32"
 },
 {
   "keyword": "celular xiaomi",
   "url": "https://celulares.mercadolibre.com.ar/xiaomi"
 },
 {
   "keyword": "xbox series x",
   "url": "https://listado.mercadolibre.com.ar/xbox-series-x"
 }
]
```

**Response fields**

This service returns an array of 50 objects in JSON format, organized as
follows:

-   **First 10 elements:** correspond to the searches with the highest
    growth.
-   **Next 20 elements:** represent the most wanted searches by users.
-   **Last 20 elements:** show the most popular trends of the week.

Each object within the array contains the following fields:

-   **keyword** (String): Term or product that users have searched for.
-   **url** (String): Link that directs to the search results related to
    that term.

  

## Trends by country and category

If you also want to know what the trends are in a specific category, you
must add the {category\_id} parameter in addition to the country.

Request:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/trends/$SITE_ID/$CATEGORY_ID
```

Example:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/trends/MLA/MLA1246
```

Response:

``` language-javascript
[
 {
   "keyword": "mesa manicura plegable",
   "url": "https://listado.mercadolibre.com.ar/mesa-manicura-plegable#trend"
 },
 {
   "keyword": "afeitadora cleancut",
   "url": "https://listado.mercadolibre.com.ar/afeitadora-cleancut#trend"
 },
 {
   "keyword": "kit de barberia",
   "url": "https://listado.mercadolibre.com.ar/kit-de-barberia#trend"
 },
 {
   "keyword": "natura",
   "url": "https://listado.mercadolibre.com.ar/natura#trend"
 },
 {
   "keyword": "philips one blade",
   "url": "https://listado.mercadolibre.com.ar/philips-one-blade#trend"
 }
]
```

  

## Errors

The following table lists the possible errors returned by the Trends
API:

| Status\_code | Error code        | Error message                    | Description                                                   |
|--------------|-------------------|----------------------------------|---------------------------------------------------------------|
| 400          | bad\_request      | Malformed access\_token: $TOKEN  | When the access token is invalid or malformed.                |
| 403          | Not authorized    | Not authorized for public trends | When the user does not have authorization to access trends.   |
| 404          | Not found         | Not found public trends          | When the site ID or category ID is invalid or does not exist. |
| 404          | route\_not\_found | Route /trends/ not found         | When the $SITE\_ID parameter is not included in the request.  |

</div>
