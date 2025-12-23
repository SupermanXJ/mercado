<div class="inner-content">

## Manage Size Chart

The size chart allows buyers to have a better experience when choosing
their product, thus avoiding size changes and/or claims; so consider
using this functionality on your fashion listings.  
There are two possible types of size chart: **SPECIFIC** (custom,
created by the seller) or **BRAND** (pre-established by brand).

  

### Experience goals

-   Ensure that fashion publications are always created with a size
    chart.
-   Ensure that products are published with the right size chart.
-   Seek to make this task as easy as possible so that we do not have
    dropouts by users when choosing or creating a size chart.

  
  

## Create size charts in footwear

Remember [the technical
sheet](https://global-selling.mercadolibre.com/devsite/first-steps)
received when you upload the attribute required for the template, since
this technical sheet will have the attributes that you must send in the
size chart creation POST. If you send an attribute that is not on the
technical sheet, it will return an error.

  
![](https://http2.mlstatic.com/storage/developers-site-cms-admin/197548769221-Captura-de-Tela-2024-03-04-a-s-10.20.12.png)  
  

### Some considerations about attributes:

-   **names**: The name that identifies the Size Chart must be unique.
    Maximum length: 60 characters.

  

The name should be replicated for the site\_ids where the Size Guide
will be created, there is no need to translate it. The name should be
easy to reference, for example: "Girls' Shoe Size Guide", "Men's Oxford
Size Guide".

  

``` language-javascript
{
   "names": {
       "CBT": "SIZE CHART FOR CBT-MAN US-M",
       "MLM": "SIZE CHART FOR CBT-MAN US-M",
       "MLB": "SIZE CHART FOR CBT-MAN US-M",
       "MCO": "SIZE CHART FOR CBT-MAN US-M",
       "MLC": "SIZE CHART FOR CBT-MAN US-M"
   },
}
```

-   **domain\_id**: define this with [available domains for size chart
    documentation](https://global-selling.mercadolibre.com/devsite/first-steps#Available-domains-for-size-chart).
-   **site\_id**: always is CBT.
-   **type**: can be SPECIFIC or BRAND.
-   **main\_attribute**: it is filled according to the rule that the
    size chart has and will represent the main size that will be
    displayed in the publication (column that will be the main size).

  

You can recognize the available main attributes with tag
main\_attribute\_candidate when you're [consulting a size charts data
sheet](https://global-selling.mercadolibre.com/devsite/first-steps#Consulting-a-size-charts-data-sheet).

  

These are the rules for main attribute:

  
![](https://http2.mlstatic.com/storage/developers-site-cms-admin/218012075785-Captura-de-Tela-2023-07-11-a-s-14.01.50.png)  

<div class="andes-message andes-message--neutral">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--neutral site-carriers__message-title">

Note:

</div>

<div class="andes-message__text--neutral site-carriers__message-text">

<div>

In order to have the accurate Main Attribute to domains [please check
technical
specs](https://global-selling.mercadolibre.com/devsite/first-steps#Consulting-a-size-charts-data-sheet).

</div>

</div>

</div>

</div>

You have to send one for any name of the size chart (an array structure
with site\_id and id of the main\_attributes). The main\_attribute must
be the same for all site\_ids where the Size Guide will be used.

  

-   **secondary\_attribute**: it's optional and represents other
    standard, local or manufacturer sizes. Although the secondary
    attribute is optional, if used, it must adhere to the following
    structure.

  
![](https://http2.mlstatic.com/storage/developers-site-cms-admin/197548366069-Captura-de-Tela-2024-03-04-a-s-10.27.04.png)  

-   **Attributes**: please send all attributes recognized consulting
    domain data sheet with the required tag, for example GENDER, COLOR,
    FOOT\_LENGTH. In addition, you can send all optional attributes
    identified with grid\_filter tag, for example BRAND.
-   **Gender**: is one of mandatory attributes and remember that chart
    gender must match to item gender. The available ID are:

<!-- -->

-   Woman ID 339665
-   Man ID 339666
-   Girls ID 339668
-   Boys ID 339667
-   Gender neutral ID 110461
-   Gender neutral KID ID 1915949

<div class="andes-message andes-message--neutral">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--neutral site-carriers__message-title">

Note:

</div>

<div class="andes-message__text--neutral site-carriers__message-text">

<div>

Check [category predictor to consult other
gender](https://global-selling.mercadolibre.com/devsite/category-predictor).

</div>

</div>

</div>

</div>

  

-   **FOOT\_LENGTH and FOOT\_LENGTH\_TO**: are range attributes used to
    create measurement ranges within the specification of a size chart
    row. Valid range: 5-40 cm.
-   **Rows**: contains sizes related to the size chart.
-   **Size**: determine the picker information (descriptive detail of
    the size). First column can be set by the seller to change what we
    want to show as the size description. SIZE value must match with the
    SIZE CHART ROW in the main\_attribute. The first column of the size
    chart will always be identified under the id of the SIZE attribute.
    Validate your json before create size chart.

## Example of creating size chart in footwear

Request:

``` language-javascript
curl -X POST -H 'Authorization: Bearer $ACCESS_TOKEN' -H "Content-Type: application/json" https://api.mercadolibre.com/catalog/charts
```

Example:

``` language-javascript
curl --location 'https://api.mercadolibre.com/catalog/charts' \
--header 'Authorization: Bearer $ACCESS_TOKEN' \
--header 'Content-Type: application/json' \
--data '{
   "names": {
       "CBT": "SIZE CHART FOR MAN CBT US-M",
       "MLM": "SIZE CHART FOR MAN CBT US-M",
       "MLB": "SIZE CHART FOR MAN CBT US-M",
       "MCO": "SIZE CHART FOR MAN CBT US-M",
       "MLC": "SIZE CHART FOR MAN CBT US-M"
   },
   "domain_id": "SNEAKERS",
   "site_id": "CBT",
   "type": "SPECIFIC",
   "main_attribute": {
       "attributes": [
           { "site_id": "CBT", "id": "M_US_SIZE" },
           { "site_id": "MLB", "id": "M_US_SIZE" },
           { "site_id": "MLM", "id": "M_US_SIZE" },
           { "site_id": "MCO", "id": "M_US_SIZE" },
           { "site_id": "MLC", "id": "M_US_SIZE" }
       ]
   },
   "secondary_attribute": {
       "attributes": [
           { "site_id": "MLM", "id": "MX_SIZE" },
           { "site_id": "MLB", "id": "BR_SIZE" },
           { "site_id": "MCO", "id": "CO_SIZE" },
           { "site_id": "MLC", "id": "CL_SIZE" },
           { "site_id": "EU", "id": "EU_SIZE" },
           { "site_id": "UK", "id": "UK_SIZE" }
       ]
   },
   "attributes": [
       {
           "id": "GENDER",
           "values": [{ "id": "339666", "name": "Man" }]
       }
   ],
   "rows": [
       {
           "sites": ["CBT", "MLC", "MLB", "MLM", "MCO"],
           "attributes": [
               { "id": "FOOT_LENGTH", "values": [{ "name": "22 cm", "struct": { "number": 22.0, "unit": "cm" } }] },
               { "id": "FOOT_LENGTH_TO", "values": [{ "name": "24 cm", "struct": { "number": 24.0, "unit": "cm" } }] },
               { "id": "M_US_SIZE", "values": [{ "name": "5 US", "struct": { "number": 5, "unit": "US" } }] },
               { "id": "MX_SIZE", "values": [{ "name": "20 MX", "struct": { "number": 20.0, "unit": "MX" } }] },
               { "id": "BR_SIZE", "values": [{ "name": "35 BR", "struct": { "number": 35, "unit": "BR" } }] },
               { "id": "CO_SIZE", "values": [{ "name": "34 CO", "struct": { "number": 34, "unit": "CO" } }] },
               { "id": "CL_SIZE", "values": [{ "name": "34 CL", "struct": { "number": 34, "unit": "CL" } }] },
               { "id": "EU_SIZE", "values": [{ "name": "36 EU", "struct": { "number": 36, "unit": "EU" } }] },
               { "id": "UK_SIZE", "values": [{ "name": "4 UK", "struct": { "number": 4, "unit": "UK" } }] }
           ]
       }
   ]
}'
```

Response: **201 Created**

``` language-javascript
{
   "id": "1746997",
   "names": {
       "CBT": "SIZE CHART FOR MAN CBT US-M",
       "MLM": "SIZE CHART FOR MAN CBT US-M",
       "MLB": "SIZE CHART FOR MAN CBT US-M",
       "MCO": "SIZE CHART FOR MAN CBT US-M",
       "MLC": "SIZE CHART FOR MAN CBT US-M"
   },
   "domain_id": "SNEAKERS",
   "site_id": "CBT",
   "type": "SPECIFIC",
   "seller_id": 1422296917,
   "measure_type": "BODY_MEASURE",
   "main_attribute": {
       "attributes": [
           { "site_id": "CBT", "id": "M_US_SIZE" },
           { "site_id": "MLB", "id": "M_US_SIZE" },
           { "site_id": "MLM", "id": "M_US_SIZE" },
           { "site_id": "MCO", "id": "M_US_SIZE" },
           { "site_id": "MLC", "id": "M_US_SIZE" }
       ]
   },
   "secondary_attribute": {
       "attributes": [
           { "site_id": "CBT", "id": "EU_SIZE" },
           { "site_id": "MLC", "id": "CL_SIZE" },
           { "site_id": "MLB", "id": "BR_SIZE" },
           { "site_id": "MLM", "id": "MX_SIZE" },
           { "site_id": "MCO", "id": "CO_SIZE" }
       ]
   },
   "attributes": [
       { "id": "GENDER", "values": [{ "id": "339666", "name": "Man" }] }
   ],
   "rows": [
       {
           "id": "1746997:1",
           "sites": ["CBT", "MLC", "MLB", "MLM", "MCO"],
           "attributes": [
               { "id": "FOOT_LENGTH", "values": [{ "name": "22 cm", "struct": { "number": 22.0, "unit": "cm" } }] },
               { "id": "FOOT_LENGTH_TO", "values": [{ "name": "24 cm", "struct": { "number": 24.0, "unit": "cm" } }] },
               { "id": "BR_SIZE", "values": [{ "name": "35 BR", "struct": { "number": 35.0, "unit": "BR" } }] },
               { "id": "MX_SIZE", "values": [{ "name": "20 MX", "struct": { "number": 20.0, "unit": "MX" } }] },
               { "id": "CL_SIZE", "values": [{ "name": "34 CL", "struct": { "number": 34.0, "unit": "CL" } }] },
               { "id": "CO_SIZE", "values": [{ "name": "34 CO", "struct": { "number": 34.0, "unit": "CO" } }] },
               { "id": "M_US_SIZE", "values": [{ "name": "5 US", "struct": { "number": 5.0, "unit": "US" } }] },
               { "id": "EU_SIZE", "values": [{ "name": "36 EU", "struct": { "number": 36.0, "unit": "EU" } }] },
               { "id": "UK_SIZE", "values": [{ "name": "4 UK", "struct": { "number": 4.0, "unit": "UK" } }] }
           ]
       }
   ]
}
```

### Response fields

-   **id**: Unique identifier for the size chart.
-   **seller\_id**: The ID of the seller who created the chart.
-   **measure\_type**: Type of measurement (BODY\_MEASURE,
    CLOTHING\_MEASURE, or MIXED\_MEASURE).
-   **rows\[\].id**: Unique identifier for each row in format
    "chartId:rowNumber".

  

## Create charts in TOPS and BOTTOMS domains

<div class="andes-message andes-message--highlight">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--highlight site-carriers__message-title">

Important:

</div>

<div class="andes-message__text--highlight site-carriers__message-text">

<div>

Now it is available to associate a size chart to an item at TOPS and
BOTTOMS categories.  
The size charts of the TOPS and BOTTOMS domains, will be able to work
with list type attributes allowing multiple values (multivalued), for
example: for an attribute id: SIZE with name: S - L we will allow to
load multiple values in the attribute id: FILTRABLE\_SIZE with name:
S,M, L  
For TOPS and BOTTOMS categories, it will only be possible to create
publications from custom size charts (SPECIFIC). [Please check the
section Available domains for size
chart](https://global-selling.mercadolibre.com/devsite/first-steps#Available-domains-for-size-chart).  
Starting from February 2024, size guides can be created, specifying
attributes of garment measurements, such as garment length, garment
width, inseam, among others, according to the needs of each seller.

</div>

</div>

</div>

</div>

For [TOPS and BOTTOMS
domains](https://global-selling.mercadolibre.com/devsite/first-steps#Available-domains-for-size-chart),
such as: pants, shirts, dresses, among others. Should consult of the
list available domains for size chart. We included attributes of the
data **type value\_type: list** a **List**, which contains a set of
**international values** predetermined by Mercado Libre to specify
certain attributes of a customized size charts, additionally **you will
find the multivalued tag** that will allow you to create the charts with
one or more specific values within the list for each row, for example
tops: you can see that the size XLarge includes the values of the size
list from 3XL TO 6XL (3XL,4XL, 5XL.6XL) while the size Small corresponds
to a value of size XS and S. Also for bottoms use american size,
example: 0 US, 16 US, 24 US

  
![](https://http2.mlstatic.com/storage/developers-site-cms-admin/197544693999-Captura-de-Tela-2024-03-04-a-s-11.13.38.png)  

In **the TOPS and BOTTOMS domains only SPECIFIC charts can be used**, or
customized charts specified by each vendor. When [consulting the
technical data
sheet](https://global-selling.mercadolibre.com/devsite/first-steps#Consult-domain-data-sheet)
of the size charts you will see in the result a list data type that
determines a List, this attribute will indicate the possible values that
it can take, both its value\_id and its value\_name. **It is mandatory
for the values of filtrable sizes to exist in the technical spec.**

  

Example of creating a customized size charts with body measures from a
list:

  

Request:

``` language-javascript
curl -X POST 'https://api.mercadolibre.com/catalog/charts' -H 'Authorization: Bearer $ACCESS_TOKEN' -H 'Content-Type: application/json'
```

Example:

``` language-javascript
curl 'https://api.mercadolibre.com/catalog/charts' -H 'Authorization: Bearer $ACCESS_TOKEN' -H 'Content-Type: application/json' -d '{
   "names": {
       "CBT": "TSHIRT EX1",
       "MLM": "TSHIRT EX1",
       "MLB": "TSHIRT EX1",
       "MLC": "TSHIRT EX1",
       "MCO": "TSHIRT EX1"
   },
   "type": "SPECIFIC",
   "domain_id": "T_SHIRTS",
   "site_id": "CBT",
   "attributes": [
       { "id": "GENDER", "values": [{ "name": "Woman" }] }
   ],
   "main_attribute": {
       "attributes": [
           { "site_id": "CBT", "id": "SIZE" },
           { "site_id": "MLM", "id": "SIZE" },
           { "site_id": "MLB", "id": "SIZE" },
           { "site_id": "MLC", "id": "SIZE" },
           { "site_id": "MCO", "id": "SIZE" }
       ]
   },
   "rows": [
       {
           "sites": ["CBT", "MLM", "MLB", "MLC", "MCO"],
           "attributes": [
               { "id": "SIZE", "values": [{ "name": "Small" }] },
               { "id": "FILTRABLE_SIZE", "values": [{ "name": "XS" }, { "name": "S" }] },
               { "id": "CHEST_CIRCUMFERENCE_FROM", "values": [{ "name": "60 cm" }] },
               { "id": "CHEST_CIRCUMFERENCE_TO", "values": [{ "name": "65 cm" }] },
               { "id": "WAIST_CIRCUMFERENCE_FROM", "values": [{ "name": "100 cm" }] },
               { "id": "WAIST_CIRCUMFERENCE_TO", "values": [{ "name": "105 cm" }] },
               { "id": "PERSON_HEIGHT_FROM", "values": [{ "name": "1.54 cm" }] },
               { "id": "PERSON_HEIGHT_TO", "values": [{ "name": "1.55 cm" }] },
               { "id": "HIP_CIRCUMFERENCE_FROM", "values": [{ "name": "80 cm" }] },
               { "id": "HIP_CIRCUMFERENCE_TO", "values": [{ "name": "85 cm" }] },
               { "id": "NECK_CIRCUMFERENCE_FROM", "values": [{ "name": "15 cm" }] },
               { "id": "NECK_CIRCUMFERENCE_TO", "values": [{ "name": "18 cm" }] }
           ]
       }
   ]
}'
```

Response of creating a size charts with body measures from a List:

``` language-javascript
{
   "id": "812789",
   "names": {
       "CBT": "TSHIRT EX1",
       "MLM": "TSHIRT EX1",
       "MLB": "TSHIRT EX1",
       "MLC": "TSHIRT EX1",
       "MCO": "TSHIRT EX1"
   },
   "domain_id": "T_SHIRTS",
   "site_id": "CBT",
   "type": "SPECIFIC",
   "seller_id": 1161438226,
   "main_attribute": {
       "attributes": [
           { "site_id": "CBT", "id": "SIZE" },
           { "site_id": "MLM", "id": "SIZE" },
           { "site_id": "MLB", "id": "SIZE" },
           { "site_id": "MLC", "id": "SIZE" },
           { "site_id": "MCO", "id": "SIZE" }
       ]
   },
   "secondary_attribute": {
       "attributes": []
   },
   "attributes": [
       { "id": "GENDER", "values": [{ "id": "339665", "name": "Woman" }] }
   ],
   "rows": [
       {
           "id": "812789:1",
           "sites": ["CBT", "MLM", "MLB", "MLC", "MCO"],
           "attributes": [
               { "id": "SIZE", "values": [{ "name": "Small" }] },
               { "id": "FILTRABLE_SIZE", "values": [{ "id": "12917776", "name": "XS" }] },
               { "id": "CHEST_CIRCUMFERENCE_FROM", "values": [{ "name": "60 cm", "struct": { "number": 60.0, "unit": "cm" } }] },
               { "id": "CHEST_CIRCUMFERENCE_TO", "values": [{ "name": "65 cm", "struct": { "number": 65.0, "unit": "cm" } }] },
               { "id": "WAIST_CIRCUMFERENCE_FROM", "values": [{ "name": "100 cm", "struct": { "number": 100.0, "unit": "cm" } }] },
               { "id": "WAIST_CIRCUMFERENCE_TO", "values": [{ "name": "105 cm", "struct": { "number": 105.0, "unit": "cm" } }] },
               { "id": "PERSON_HEIGHT_FROM", "values": [{ "name": "1.54 cm", "struct": { "number": 1.54, "unit": "cm" } }] },
               { "id": "PERSON_HEIGHT_TO", "values": [{ "name": "1.55 cm", "struct": { "number": 1.55, "unit": "cm" } }] },
               { "id": "HIP_CIRCUMFERENCE_FROM", "values": [{ "name": "80 cm", "struct": { "number": 80.0, "unit": "cm" } }] },
               { "id": "HIP_CIRCUMFERENCE_TO", "values": [{ "name": "85 cm", "struct": { "number": 85.0, "unit": "cm" } }] },
               { "id": "NECK_CIRCUMFERENCE_FROM", "values": [{ "name": "15 cm", "struct": { "number": 15.0, "unit": "cm" } }] },
               { "id": "NECK_CIRCUMFERENCE_TO", "values": [{ "name": "18 cm", "struct": { "number": 18.0, "unit": "cm" } }] }
           ]
       }
   ]
}
```

## Create charts with clothes sizes

<div class="andes-message andes-message--highlight">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--highlight site-carriers__message-title">

Important:

</div>

<div class="andes-message__text--highlight site-carriers__message-text">

<div>

Starting Monday, July 8, 2024, a new possible value, "MIXED\_MEASURE",
will be added to the "measure\_type" field. By selecting
"MIXED\_MEASURE", it will be possible to include both garment and body
measurements in the same size guide.

</div>

</div>

</div>

</div>

Only for TOPS and BOTTOMS domains, after [consulting the size chart data
sheet](https://global-selling.mercadolibre.com/devsite/first-steps#Consulting-a-size-charts-data-sheet)
and recognizing which attributes have the CLOTHING\_MEASURE tag, you
will be able to create size charts only by specifying clothes sizes.

  

To consider:

-   The "**measure\_type**" field must be specified and its possible
    values: BODY\_MEASURE, CLOTHING\_MEASURE or MIXED\_MEASURE. This
    field refers to the type of measure that the seller will specify in
    the size chart. Once the size chart has been created, **this field
    cannot be modified**.
-   It is possible to have both garment and body measurements in the
    same size guide with the "measure\_type" MIXED\_MEASURE.
-   If the "**measure\_type**" field is not sent by default, the size
    chart will be of body measurements or BODY\_MEASURE and all
    [Validations will be based on this type of
    measurement](https://global-selling.mercadolibre.com/devsite/size-chart-validation).

Example of the creation of a customized size chart, with clothes sizes:

``` language-javascript
curl --location --request POST 'https://api.mercadolibre.com/catalog/charts' \
--header 'Authorization: Bearer $ACCESS_TOKEN' \
--header 'Content-Type: application/json' \
--data-raw '{
   "names": {
       "MLB": "Pants test Garment",
       "MCO": "Pants test Garment",
       "CBT": "Pants test Garment",
       "MLM": "Pants test Garment",
       "MLC": "Pants test Garment"
   },
   "domain_id": "PANTS",
   "site_id": "CBT",
   "type": "SPECIFIC",
   "measure_type": "CLOTHING_MEASURE",
   "main_attribute": {
       "attributes": [
           { "site_id": "CBT", "id": "SIZE" },
           { "site_id": "MLM", "id": "SIZE" },
           { "site_id": "MLB", "id": "SIZE" },
           { "site_id": "MLC", "id": "SIZE" },
           { "site_id": "MCO", "id": "SIZE" }
       ]
   },
   "secondary_attribute": {
       "attributes": []
   },
   "attributes": [
       { "id": "GENDER", "values": [{ "id": "339665", "name": "Woman" }] }
   ],
   "rows": [
       {
           "sites": ["MLM", "MLB", "MLC", "MCO", "CBT"],
           "attributes": [
               { "id": "SIZE", "values": [{ "name": "Small" }] },
               { "id": "PANTS_FILTRABLE_SIZES", "values": [{ "id": "4147746", "name": "26" }] },
               { "id": "GARMENT_LENGTH_FROM", "values": [{ "name": "15 cm", "struct": { "number": 15.0, "unit": "cm" } }] },
               { "id": "GARMENT_WAIST_WIDTH_FROM", "values": [{ "name": "16 cm", "struct": { "number": 16.0, "unit": "cm" } }] },
               { "id": "GARMENT_HIP_WIDTH_FROM", "values": [{ "name": "17 cm", "struct": { "number": 17.0, "unit": "cm" } }] },
               { "id": "GARMENT_THIGH_WIDTH_FROM", "values": [{ "name": "18 cm", "struct": { "number": 18.0, "unit": "cm" } }] },
               { "id": "GARMENT_INSEAM_LENGTH_FROM", "values": [{ "name": "19 cm", "struct": { "number": 19.0, "unit": "cm" } }] },
               { "id": "GARMENT_FRONT_RISE_FROM", "values": [{ "name": "20 cm", "struct": { "number": 20.0, "unit": "cm" } }] }
           ]
       }
   ]
}'
```

Example of the creation of a customized size chart, with MIXED\_MEASURE:

``` language-javascript
curl --location --request POST 'https://api.mercadolibre.com/catalog/charts' \
--header 'Authorization: Bearer $ACCESS_TOKEN' \
--header 'Content-Type: application/json' \
--data-raw '{
   "names": {
       "MLB": "T_SHIRTS MIXED_MEASURE",
       "MCO": "T_SHIRTS MIXED_MEASURE",
       "CBT": "T_SHIRTS MIXED_MEASURE",
       "MLM": "T_SHIRTS MIXED_MEASURE",
       "MLC": "T_SHIRTS MIXED_MEASURE"
   },
   "domain_id": "T_SHIRTS",
   "site_id": "CBT",
   "type": "SPECIFIC",
   "measure_type": "MIXED_MEASURE",
   "main_attribute": {
       "attributes": [
           { "site_id": "CBT", "id": "SIZE" },
           { "site_id": "MLM", "id": "SIZE" },
           { "site_id": "MLB", "id": "SIZE" },
           { "site_id": "MLC", "id": "SIZE" },
           { "site_id": "MCO", "id": "SIZE" }
       ]
   },
   "secondary_attribute": {
       "attributes": []
   },
   "attributes": [
       { "id": "GENDER", "values": [{ "id": "339666", "name": "Man" }] }
   ],
   "rows": [
       {
           "sites": ["MLM", "MLB", "MLC", "MCO", "CBT"],
           "attributes": [
               { "id": "SIZE", "values": [{ "name": "2XS" }] },
               { "id": "FILTRABLE_SIZE", "values": [{ "id": "12917836", "name": "2XS" }] },
               { "id": "CHEST_CIRCUMFERENCE_FROM", "values": [{ "name": "60 cm", "struct": { "number": 60.0, "unit": "cm" } }] },
               { "id": "WAIST_CIRCUMFERENCE_FROM", "values": [{ "name": "60 cm", "struct": { "number": 60.0, "unit": "cm" } }] },
               { "id": "PERSON_HEIGHT_FROM", "values": [{ "name": "60 cm", "struct": { "number": 60.0, "unit": "cm" } }] },
               { "id": "HIP_CIRCUMFERENCE_FROM", "values": [{ "name": "60 cm", "struct": { "number": 60.0, "unit": "cm" } }] },
               { "id": "NECK_CIRCUMFERENCE_FROM", "values": [{ "name": "60 cm", "struct": { "number": 60.0, "unit": "cm" } }] },
               { "id": "GARMENT_CHEST_WIDTH_FROM", "values": [{ "name": "11 cm", "struct": { "number": 11.0, "unit": "cm" } }] },
               { "id": "GARMENT_LENGTH_FROM", "values": [{ "name": "11 cm", "struct": { "number": 11.0, "unit": "cm" } }] },
               { "id": "GARMENT_SHOULDER_WIDTH_FROM", "values": [{ "name": "11 cm", "struct": { "number": 11.0, "unit": "cm" } }] },
               { "id": "GARMENT_SLEEVE_LENGTH_FROM", "values": [{ "name": "11 cm", "struct": { "number": 11.0, "unit": "cm" } }] }
           ]
       }
   ]
}'
```

To specify the list type field, you can send the value\_id or the
value\_name, in case of sending both parameters the value\_id has more
relevance than the value\_name.

## Get size chart by ID

Use this endpoint to retrieve an existing size chart by its unique
identifier.

  

Request:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/catalog/charts/$CHART_ID
```

Example:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/catalog/charts/1332046
```

Response: **200 OK**

  

``` language-javascript
{
   "id": "1332046",
   "names": {
       "MLC": "SIZE CHART FOR MAN CBT US-M",
       "MLM": "SIZE CHART FOR MAN CBT US-M",
       "MLB": "SIZE CHART FOR MAN CBT US-M",
       "CBT": "SIZE CHART FOR MAN CBT US-M",
       "MCO": "SIZE CHART FOR MAN CBT US-M"
   },
   "domain_id": "SNEAKERS",
   "site_id": "CBT",
   "type": "SPECIFIC",
   "seller_id": 1422296917,
   "measure_type": "BODY_MEASURE",
   "main_attribute": {
       "attributes": [
           { "site_id": "CBT", "id": "M_US_SIZE" },
           { "site_id": "MLM", "id": "M_US_SIZE" },
           { "site_id": "MLB", "id": "M_US_SIZE" },
           { "site_id": "MLC", "id": "M_US_SIZE" },
           { "site_id": "MCO", "id": "M_US_SIZE" }
       ]
   },
   "secondary_attribute": {
       "attributes": [
           { "site_id": "MCO", "id": "CO_SIZE" },
           { "site_id": "MLB", "id": "BR_SIZE" },
           { "site_id": "MLC", "id": "CL_SIZE" },
           { "site_id": "MLM", "id": "MX_SIZE" }
       ]
   },
   "attributes": [
       { "id": "GENDER", "values": [{ "id": "339666", "name": "Man" }] }
   ],
   "rows": [
       {
           "id": "1332046:1",
           "sites": ["MCO", "MLB", "CBT", "MLC", "MLM"],
           "attributes": [
               { "id": "FOOT_LENGTH", "values": [{ "name": "11 cm", "struct": { "number": 11.0, "unit": "cm" } }] },
               { "id": "FOOT_LENGTH_TO", "values": [{ "name": "12 cm", "struct": { "number": 12.0, "unit": "cm" } }] },
               { "id": "M_US_SIZE", "values": [{ "name": "5 US", "struct": { "number": 5.0, "unit": "US" } }] }
           ]
       }
   ]
}
```

![](https://http2.mlstatic.com/storage/developers-site-cms-admin/197543939377-Captura-de-Tela-2024-03-04-a-s-11.40.51.png)  
  

## Add rows to size chart

This endpoint allows you to add rows to an existing chart.

  

Request:

``` language-javascript
curl -X POST -H 'Authorization: Bearer $ACCESS_TOKEN' -H "Content-Type: application/json" https://api.mercadolibre.com/catalog/charts/$CHART_ID/rows
```

Example:

``` language-javascript
curl 'https://api.mercadolibre.com/catalog/charts/1746997/rows' -H 'Authorization: Bearer $ACCESS_TOKEN' -H 'Content-Type: application/json' -d '{
   "sites": ["CBT", "MLC", "MLB", "MLM", "MCO"],
   "attributes": [
       { "id": "FOOT_LENGTH", "values": [{ "name": "27 cm", "struct": { "number": 27.0, "unit": "cm" } }] },
       { "id": "FOOT_LENGTH_TO", "values": [{ "name": "29 cm", "struct": { "number": 29.0, "unit": "cm" } }] },
       { "id": "M_US_SIZE", "values": [{ "name": "7.5 US", "struct": { "number": 7.5, "unit": "US" } }] },
       { "id": "BR_SIZE", "values": [{ "name": "38 BR", "struct": { "number": 38.0, "unit": "BR" } }] },
       { "id": "MX_SIZE", "values": [{ "name": "25 MX", "struct": { "number": 25.0, "unit": "MX" } }] }
   ]
}'
```

Response: **201 Created**

  

The response returns the complete updated size chart with all rows,
including the newly added row with its assigned ID.

### Size chart

![](https://http2.mlstatic.com/storage/developers-site-cms-admin/191237526253-Captura-de-pantalla-2024-05-16-a-la-s--11.27.24-a.-m..png)  
  

## Update size chart rows

This endpoint allows you to add information to an existing row in the
size chart. It's impossible to modify the information of the rows. You
can not edit the main item (main\_attribute) of each queue (row) and
neither can you delete queues.  
It is possible to add information to a line that was not filled in.

Request:

``` language-javascript
curl -X PUT -H 'Authorization: Bearer $ACCESS_TOKEN' -H "Content-Type: application/json" https://api.mercadolibre.com/catalog/charts/$CHART_ID
```

Example:

``` language-javascript
curl -X PUT 'https://api.mercadolibre.com/catalog/charts/1746997' -H 'Authorization: Bearer $ACCESS_TOKEN' -H 'Content-Type: application/json' -d '{
   "rows": [
       {
           "id": "1746997:4",
           "sites": ["CBT", "MLM", "MLB", "MLC", "MCO"],
           "attributes": [
               { "id": "FOOT_LENGTH", "values": [{ "name": "30 cm", "struct": { "number": 30, "unit": "cm" } }] },
               { "id": "FOOT_LENGTH_TO", "values": [{ "name": "32 cm", "struct": { "number": 32, "unit": "cm" } }] },
               { "id": "BR_SIZE", "values": [{ "name": "42 BR", "struct": { "number": 42, "unit": "BR" } }] },
               { "id": "MX_SIZE", "values": [{ "name": "30 MX", "struct": { "number": 34, "unit": "MX" } }] },
               { "id": "EU_SIZE", "values": [{ "name": "44 EU", "struct": { "number": 44, "unit": "EU" } }] },
               { "id": "UK_SIZE", "values": [{ "name": "7 UK", "struct": { "number": 7, "unit": "UK" } }] }
           ]
       }
   ]
}'
```

Response: **200 OK**

  

The response returns the complete updated size chart with all rows
including the modifications.

## Modify size charts

From a previously created size charts it will only be possible to modify
the name field. If a mistake was made when creating the size charts,
e.g. in the main sizes or in the gender assignment, the [size charts
must be recreated](#Creating-size-chart-in-footwear).

  

<div class="andes-message andes-message--highlight">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--highlight site-carriers__message-title">

Important:

</div>

<div class="andes-message__text--highlight site-carriers__message-text">

<div>

Note that when modifying, you will not be able to edit the main size
(**main\_attribute**) of the charts, such as the value of the main size
of the (row) and the general attributes. **Size charts may not be
removed**.

</div>

</div>

</div>

</div>

Request:

``` language-javascript
curl -X PUT -H 'Authorization: Bearer $ACCESS_TOKEN' -H "Content-Type: application/json" https://api.mercadolibre.com/catalog/charts/$CHART_ID
```

Example:

``` language-javascript
curl -X PUT -H 'Authorization: Bearer $ACCESS_TOKEN' -H "Content-Type: application/json" -d '{
   "names": {
       "MLC": "New name MLC",
       "MLM": "New name MLM",
       "MLB": "New name MLB",
       "CBT": "New name CBT",
       "MCO": "New name MCO"
   }
}' https://api.mercadolibre.com/catalog/charts/1746997
```

Response: **200 OK**

## Delete size chart

<div class="andes-message andes-message--highlight">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--highlight site-carriers__message-title">

Important:

</div>

<div class="andes-message__text--highlight site-carriers__message-text">

<div>

Starting July 15, 2024, you will be able to delete unused size guides
that are not linked to any items.

</div>

</div>

</div>

</div>

By performing the following request you will be able to delete size
charts unlinked to items.

  

Request:

``` language-javascript
curl -X DELETE -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/catalog/charts/$CHART_ID
```

Example:

``` language-javascript
curl -X DELETE -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/catalog/charts/1398269
```

Response: **200 OK**

``` language-javascript
{
   "message": "Before removing the size chart, we'll check that it isn't linked to any listing. If it's still there after 24 hours, it means it's linked to one or more listings and you'll have to unlink it to remove it"
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

The size guide is not deleted immediately. According to the success
message from the API, we check that the entered size guide is not linked
to any item. If it is, and it still needs to be deleted, it is mandatory
to unlink the size guide from all items. After deleting a Size Guide, it
will be updated with `chart_status: "INACTIVE"` when a query or search
is performed.

</div>

</div>

</div>

</div>

## International Size Convert

<div class="andes-message andes-message--highlight">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--highlight site-carriers__message-title">

Important:

</div>

<div class="andes-message__text--highlight site-carriers__message-text">

<div>

New Feature: The size chart equivalence to local sizes is now done
automatically by Mercado Libre.

</div>

</div>

</div>

</div>

In order to facilitate the creation of the size guide, it is now
required to include only international sizes in the size chart.
Consequently, the inclusion of local sizes (Brazil, Mexico, Colombia,
and Chile) will be fully automated by our functionality, thus
simplifying the size chart creation process for sellers.

  

**Automatic equivalence is available for both tops & bottoms size charts
and for footwear**.

  

## Tops & Bottoms

![](https://http2.mlstatic.com/storage/developers-site-cms-admin/197543051955-Captura-de-Tela-2024-03-04-a-s-11.55.38.png)  
  
![](https://http2.mlstatic.com/storage/developers-site-cms-admin/197543000842-Captura-de-Tela-2024-03-04-a-s-11.56.16.png)  
  

## Footwear

![](https://http2.mlstatic.com/storage/developers-site-cms-admin/197542952498-Captura-de-Tela-2024-03-04-a-s-11.57.17.png)  
  

<div class="andes-message andes-message--highlight">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--highlight site-carriers__message-title">

Important:

</div>

<div class="andes-message__text--highlight site-carriers__message-text">

<div>

We recommend not adding photos, tables, or equivalence texts in the item
description, as the generation of these equivalences for countries will
now be done automatically.

</div>

</div>

</div>

</div>

## Search for size equivalences

To view international sizes, you can perform a GET request to list the
equivalences. This valuable information allows you to know the local
sizes of each country (Brazil, Mexico, Colombia and Chile) compared to
the international size.

  

The request requires three query params: **domain\_id, gender and
siteId**.

  

### Parameters

-   **domain\_id** (required): The domain identifier. See [available
    domains for size
    chart](https://global-selling.mercadolibre.com/devsite/first-steps#Available-domains-for-size-chart).
-   **gender** (required): The gender for the size chart. Available
    values: Woman, Man, Gender neutral, Girls, Boys, Gender neutral kid,
    Babies.
-   **site\_id** (optional): Filter by specific site. Available values:
    MLB, MLM, MCO, MLC.

  

Request:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/marketplace/sizechart/equivalences?site_id=$SITE_ID&domain_id=$DOMAIN_ID&gender=$GENDER
```

Example:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/marketplace/sizechart/equivalences?domain_id=T_SHIRTS&gender=Gender neutral kid
```

Response: **200 OK**

``` language-javascript
{
   "domain": "T_SHIRTS",
   "gender": "Gender neutral kid",
   "sizes": [
       {
           "international_size": "9 years",
           "equivalences": [
               { "site": "MLB", "size": "1 year" },
               { "site": "MCO", "size": "9 years" },
               { "site": "MLM", "size": "1 year" },
               { "site": "MLC", "size": "9 years" }
           ]
       },
       {
           "international_size": "12 years",
           "equivalences": [
               { "site": "MLB", "size": "4 years" },
               { "site": "MCO", "size": "12 years" },
               { "site": "MLM", "size": "4 years" },
               { "site": "MLC", "size": "12 years" }
           ]
       }
   ]
}
```

### Response fields

-   **domain**: The domain identifier.
-   **gender**: The gender filter applied.
-   **sizes**: Array of size equivalences.
-   **sizes\[\].international\_size**: The international size value.
-   **sizes\[\].equivalences**: Array of local equivalences per site.
-   **sizes\[\].equivalences\[\].site**: The site identifier (MLB, MLM,
    MCO, MLC).
-   **sizes\[\].equivalences\[\].size**: The equivalent local size.

## Errors

Below are the possible errors you may encounter when using the Size
Chart API endpoints.

  

### Create Size Chart - POST /catalog/charts

| Status code | Error code     | Error message                                                     | Description                                                                |
|-------------|----------------|-------------------------------------------------------------------|----------------------------------------------------------------------------|
| `400`       | `bad_request`  | Chart name must be at most 60 characters                          | The size chart name exceeds the maximum allowed length of 60 characters.   |
| `400`       | `bad_request`  | Attribute FOOT\_LENGTH with value 50 cm is out of range \[5, 40\] | The FOOT\_LENGTH value is outside the valid range (5-40 cm).               |
| `400`       | `bad_request`  | Invalid domain\_id                                                | The specified domain\_id is not valid for size charts.                     |
| `400`       | `bad_request`  | Attribute not found in technical spec                             | The attribute sent is not defined in the domain's technical specification. |
| `401`       | `unauthorized` | Invalid token                                                     | The access token is invalid or expired. Please refresh your token.         |

  

### Get Size Chart - GET /catalog/charts/$CHART\_ID

| Status code | Error code     | Error message        | Description                             |
|-------------|----------------|----------------------|-----------------------------------------|
| `404`       | `not_found`    | Size chart not found | The specified chart ID does not exist.  |
| `401`       | `unauthorized` | Invalid token        | The access token is invalid or expired. |

  

### Add Rows - POST /catalog/charts/$CHART\_ID/rows

| Status code | Error code     | Error message          | Description                                                          |
|-------------|----------------|------------------------|----------------------------------------------------------------------|
| `400`       | `bad_request`  | Invalid row attributes | The row attributes do not match the chart's technical specification. |
| `404`       | `not_found`    | Size chart not found   | The specified chart ID does not exist.                               |
| `401`       | `unauthorized` | Invalid token          | The access token is invalid or expired.                              |

  

### Update Rows - PUT /catalog/charts/$CHART\_ID

| Status code | Error code    | Error message                 | Description                                            |
|-------------|---------------|-------------------------------|--------------------------------------------------------|
| `400`       | `bad_request` | Cannot modify main\_attribute | The main\_attribute cannot be modified after creation. |
| `400`       | `bad_request` | Row ID not found              | The specified row ID does not exist in the chart.      |
| `404`       | `not_found`   | Size chart not found          | The specified chart ID does not exist.                 |

  

### Delete Size Chart - DELETE /catalog/charts/$CHART\_ID

| Status code | Error code    | Error message                 | Description                                                                             |
|-------------|---------------|-------------------------------|-----------------------------------------------------------------------------------------|
| `400`       | `bad_request` | Size chart is linked to items | Cannot delete a size chart that is linked to one or more items. Unlink the chart first. |
| `404`       | `not_found`   | Size chart not found          | The specified chart ID does not exist.                                                  |

  

### Search Equivalences - GET /marketplace/sizechart/equivalences

| Status code | Error code    | Error message                          | Description                                                                                                     |
|-------------|---------------|----------------------------------------|-----------------------------------------------------------------------------------------------------------------|
| `400`       | `bad_request` | Missing required parameter: domain\_id | The domain\_id parameter is required.                                                                           |
| `400`       | `bad_request` | Missing required parameter: gender     | The gender parameter is required.                                                                               |
| `400`       | `bad_request` | Invalid gender value                   | The gender value is not valid. Use one of: Woman, Man, Gender neutral, Girls, Boys, Gender neutral kid, Babies. |

  

Next: [Create Item with associate size
chart](https://global-selling.mercadolibre.com/devsite/create-an-item-with-size-chart).

</div>
