<div class="inner-content">

## Size Chart Validations

<div class="details__message">

In order to improve the experience in fashion publications, we have a
size guide where sellers can detail the measurements of their products
to buyers. This functionality allows to reduce the number of questions,
returns due to problems with sizes and increase sales.  
Review the documentation to [see how to upload a size
chart](https://global-selling.mercadolibre.com/devsite/manage-size-chart).

</div>

## Recommendations for fashion publications

-   Complete [the technical sheet for the
    item](https://global-selling.mercadolibre.com/devsite/first-steps#Check-product-specification-sheet-of-domain).
-   Review genders by country using the
    **/catalog\_domains/$DOMAIN\_ID/attributes/GENDER** resource so that
    your publications reference genders recognized by Mercado Libre.
-   Upload all the [required
    attributes](https://global-selling.mercadolibre.com/devsite/atributtes-global-selling),
    as well as
    [variations](https://global-selling.mercadolibre.com/devsite/variations-global-selling)
    in your publications.
-   Identify if any [quality
    requirements](https://global-selling.mercadolibre.com/devsite/listings-quality-gs)
    are not complied with and take the necessary actions.
-   Confirm if the domain has attributes configured for the size guide.
-   For applicable domains, use at least the gender and brand fields [to
    find a suitable size guide to associate with your
    publication](https://global-selling.mercadolibre.com/devsite/first-steps).
-   Specifies the attributes of type GRID\_ID and GRID\_ROW\_ID as
    appropriate, when [creating or modifying the
    publication](https://global-selling.mercadolibre.com/devsite/manage-size-chart).

## Validations to create size charts

In order to maintain size charts with quality information, we have
created validations that, through error messages, will inform us of the
actions to be taken by the seller before [creating a size
chart](https://global-selling.mercadolibre.com/devsite/manage-size-chart),
which are detailed below:

  

1\. The value {VALUE\_NAME} specified for the gender attribute is not a
valid value in [the product specification sheet of the
domain](https://global-selling.mercadolibre.com/devsite/first-steps#Check-the-product-specification-sheet-of-the-size-chart).

``` language-javascript
{
    "error": "chart_tech_specs_not_found",
    "message": "Chart technical specification not found for SITE:{SITE_ID}-DOMAIN:{DOMAIN_ID}-GENDER:{VALUE_NAME}",
    "status": 404
}
```

2\. A main attribute or main\_attribute has not been specified.

``` language-javascript
{
    "error": "main_attribute_missing_error",
    "message": "Main attribute for site {SITE_ID} is missing.",
    "status": 400
}
```

3\. The attribute {ATTRIBUTE\_ID} chosen as main\_attribute is not a
valid attribute, you should [consult the product specification
sheet](https://global-selling.mercadolibre.com/devsite/first-steps#Check-the-product-specification-sheet-of-the-size-chart)
of the size chart, which will provide information on possible candidate
attributes.

``` language-javascript
{
    "code": "invalid_main_attribute_id",
    "message": "Chart main attribute with ID {ATTRIBUTE_ID} is invalid."
}
```

4\. There are required attributes {ATTRIBUTE\_ID} within the product
specification sheet of the size chart, which were not specified. The
message adds detailed information of the row
{ROW\_MAIN\_ATTRIBUTE\_VALUE\_NAME} where there is missing information.

``` language-javascript
{
    "code": "required_row_attribute_not_found",
    "message": "Required attribute {ATTRIBUTE_ID} was not found in row {MAIN_ATTRIBUTE_ID} {ROW_MAIN_ATTRIBUTE_VALUE_NAME}.",
    "cell": {
        "attribute_id": "{ATTRIBUTE_ID}",
        "row": {
            "id": null,
            "main_attribute": {
                "id": "{MAIN_ATTRIBUTE_ID}",
                "value": "{ROW_MAIN_ATTRIBUTE_VALUE_NAME}"
            }
        }
    }
}
```

5\. The value {VALUE\_NAME} entered in the attribute {ATTRIBUTE\_ID} is
not valid, you should refer to [the product specification
sheet](https://global-selling.mercadolibre.com/devsite/first-steps#Check-the-product-specification-sheet-of-the-size-chart)
of the size chart for the list of values you can use. The message adds
detailed information for the {ROW\_MAIN\_ATTRIBUTE\_VALUE\_NAME} row
with the error.

``` language-javascript
{
    "code": "invalid_row_attribute_value",
    "message": "Attribute {ATTRIBUTE_ID} in row {MAIN_ATTRIBUTE_ID} {VALUE_NAME} has an invalid value.",
    "cell": {
        "attribute_id": "{ATTRIBUTE_ID}",
        "row": {
            "id": null,
            "main_attribute": {
                "id": "{MAIN_ATTRIBUTE_ID}",
                "value": "{ROW_MAIN_ATTRIBUTE_VALUE_NAME}"
            }
        }
    }
}
```

6\. The value {VALUE\_NAME} of the attribute {ATTRIBUTE\_ID} is outside
the allowed range, range information is added. The message adds detailed
information for the row {ROW\_MAIN\_ATTRIBUTE\_VALUE\_NAME} with the
error.

``` language-javascript
{
    "code": "value_out_of_range",
    "message": "The value {VALUE_NAME} of the {ATTRIBUTE_ID} attribute of the row main attribute {MAIN_ATTRIBUTE_ID} {ROW_MAIN_ATTRIBUTE_VALUE_NAME} is out of range. The value must be within the range: {MINIMUM_RANGE} - {MAXIMUM_RANGE}",
    "cell": {
        "attribute_id": "{ATTRIBUTE_ID}",
        "row": {
            "id": null,
            "main_attribute": {
                "id": "{MAIN_ATTRIBUTE_ID}",
                "value": "{ROW_MAIN_ATTRIBUTE_VALUE_NAME}"
            }
        }
    }
}
```

7\. The value {VALUE\_NAME} of the main attribute is incorrect as it is
making use of words like gender, colors, etc. It should only contain
words that relate to size. The message adds detailed information for the
row {ROW\_MAIN\_ATTRIBUTE\_VALUE\_NAME} with the error.

``` language-javascript
{
    "code": "invalid_attribute_value",
    "message": "The value {VALUE_NAME} of the attribute {ATTRIBUTE_ID} is incorrect. The value must contain only words related to SIZE",
    "cell": {
        "attribute_id": "{ATTRIBUTE_ID}",
        "row": {
            "id": null,
            "main_attribute": {
                "id": "{MAIN_ATTRIBUTE_ID}",
                "value": "{ROW_MAIN_ATTRIBUTE_VALUE_NAME}"
            }
        }
    }
}
```

8\. You are trying to associate a custom or specific size guide that
does not belong to the actual seller.

``` language-javascript
{
    "department": "structured-data",
    "cause_id": 2617,
    "type": "error",
    "code": "invalid.fashion_grid.seller_id.values",
    "references": [
        "item.seller_id"
    ],
    "message": "The size chart {CHART_ID} doesn't belong to the seller id [{SELLER_ID}]"
}
```

9\. The values of the FILTRABLE\_SIZE field for the same size guide are
either numeric or alphanumeric, no combination of data types is allowed
in the attribute.

``` language-javascript
{
    "code": "value_is_not_the_same_type",
    "message": "All FILTRABLE_SIZE values must be the same type, only numbers or alphanumeric",
    "cell": {
        "attribute_id": "FILTRABLE_SIZE",
        "row": {
            "id": null,
            "main_attribute": {
                "id": "{MAIN_ATTRIBUTE_ID}",
                "value": "{ROW_MAIN_ATTRIBUTE_VALUE_NAME}"
            }
        }
    }
}
```

10\. The {ATTRIBUTE\_ID} attribute should not be in the size chart, this
error is due to the fact that you are trying to enter an attribute of
type BODY\_MEASURE or CLOTHING\_MEASURE, and the size chart has a
different size type configured than the attribute. Size charts can only
have one size type.

``` language-javascript
{
    "code": "invalid_row_attribute",
    "message": "Attribute {ATTRIBUTE_ID} found in row {MAIN_ATTRIBUTE_ID} {ROW_MAIN_ATTRIBUTE_VALUE_NAME} is not valid and should not be present in the chart rows.",
    "cell": {
        "attribute_id": "{ATTRIBUTE_ID}",
        "row": {
            "id": null,
            "main_attribute": {
                "id": "{MAIN_ATTRIBUTE_ID}",
                "value": "{ROW_MAIN_ATTRIBUTE_VALUE_NAME}"
            }
        }
    }
}
```

## Validations for associating a chart to a listing

For some domains in the Fashion, it is mandatory to [associate a size
chart to the
listings](https://global-selling.mercadolibre.com/devsite/create-an-item-with-size-chart),
that's why we validate that the information in the listing is consistent
by using error messages seeking for corrective action by the seller,
which we detail below.

  

<div class="andes-message andes-message--neutral">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--neutral site-carriers__message-title">

Notes:

</div>

<div class="andes-message__text--neutral site-carriers__message-text">

<div>

In the validations of the requirement of a size guide for Live Listing,
are not considered adjustments such as:  
- Stock and price changes in the publication.  
- Paused or closed status changes in the publication  
This means that, the error will not appear at the moment you make a PUT
to the /items/ resource

</div>

</div>

</div>

</div>

<div class="andes-message andes-message--highlight">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--highlight site-carriers__message-title">

Important - Validation Types:

</div>

<div class="andes-message__text--highlight site-carriers__message-text">

<div>

The validations below include two types:  
- **ERROR**: Blocking validation. The item cannot be created or
published until the error is resolved.  
- **WARNING**: Non-blocking validation. The item can be created but may
have quality issues or limited visibility.

</div>

</div>

</div>

</div>

  

1\. The SIZE\_GRID\_ID attribute does not exist in the publication:

``` language-javascript
{
    "code": "missing.fashion_grid.grid_id.values",
    "message": "Attribute [SIZE_GRID_ID] is missing",
    "type": "ERROR",
    "cause_id": 2610,
    "references": [
        "item.attributes"
    ],
    "department": "structured-data",
    "validation": "fashion-validator",
    "custom_data": {}
}
```

2\. For the publication where there is the SIZE\_GRID\_ID attribute, but
there is no attribute that specifies the row SIZE\_GRID\_ROW\_ID. This
also applies to item variations - each variation must have its own
SIZE\_GRID\_ROW\_ID:

``` language-javascript
{
    "code": "missing.fashion_grid.grid_row_id.values",
    "message": "Attribute [SIZE_GRID_ROW_ID] is missing",
    "type": "ERROR",
    "cause_id": 2611,
    "references": [
        "item.attributes"
    ],
    "department": "structured-data",
    "validation": "fashion-validator",
    "custom_data": {}
}
```

3\. For the publication and/or its variations the attribute SIZE is not
specified:

``` language-javascript
{
    "code": "missing.fashion_grid.size.values",
    "message": "Attribute [SIZE] is missing",
    "type": "ERROR",
    "cause_id": 2612,
    "references": [
        "item.attributes"
    ],
    "department": "structured-data",
    "validation": "fashion-validator",
    "custom_data": {}
}
```

4\. The publication with the SIZE\_GRID\_ID attribute specification, but
the table code sent is invalid, for example when the publication
associates with a size chart of another category:

``` language-javascript
{
    "code": "invalid.fashion_grid.grid_id.values",
    "message": "Attribute [SIZE_GRID_ID] is not valid",
    "type": "ERROR",
    "cause_id": 2613,
    "references": [
        "item.name"
    ],
    "department": "structured-data",
    "validation": "fashion-validator",
    "custom_data": {}
}
```

5\. The publication has the attribute specification SIZE\_GRID\_ID and
SIZE\_GRID\_ROW\_ID but the id sent in row is invalid, it does not exist
in the table specified in grid\_id:

``` language-javascript
{
    "code": "invalid.fashion_grid.grid_row_id.values",
    "message": "Attribute [SIZE_GRID_ROW_ID] is not valid",
    "type": "ERROR",
    "cause_id": 2614,
    "references": [
        "item.name"
    ],
    "department": "structured-data",
    "validation": "fashion-validator",
    "custom_data": {}
}
```

6\. The SIZE\_GRID\_ID provided does not exist or is invalid. This
occurs when the size chart was deleted or the ID is incorrect:

``` language-javascript
{
    "code": "size_grid.id.not_found",
    "message": "Size chart: Size chart not found",
    "type": "ERROR",
    "status": 422
}
```

7\. The size attribute of the publication or variation must consistently
match that of the row in the table you are selecting; they must be
identical if the SIZE of the publication or variation is invalid in this
comparison:

``` language-javascript
{
    "code": "invalid.fashion_grid.size.values",
    "message": "Attribute [SIZE] is not valid",
    "type": "WARNING",
    "cause_id": 2615,
    "references": [
        "item.name"
    ],
    "department": "structured-data",
    "validation": "fashion-validator",
    "custom_data": {}
}
```

8\. The attributes detailed in the table must correspond consistently
with the information in the publication, for example, the GENDER
attribute in the table must be the same as the one in the publication:

``` language-javascript
{
    "code": "invalid.fashion_grid.size.values",
    "message": "Attribute [GENDER] is not valid",
    "type": "WARNING",
    "cause_id": 2616,
    "references": [
        "item.name"
    ],
    "department": "structured-data",
    "validation": "fashion-validator",
    "custom_data": {}
}
```

9\. You are trying to associate a custom or specific size guide that
does not belong to the actual seller.

``` language-javascript
{
    "department": "structured-data",
    "cause_id": 2617,
    "type": "error",
    "code": "invalid.fashion_grid.seller_id.values",
    "references": [
        "item.seller_id"
    ],
    "message": "The size chart {CHART_ID} doesn't belong to the seller id [{SELLER_ID}]"
}
```

10\. The values of the FILTRABLE\_SIZE field for the same size guide are
either numeric or alphanumeric, no combination of data types is allowed
in the attribute.

``` language-javascript
{
    "code": "value_is_not_the_same_type",
    "message": "All FILTRABLE_SIZE values must be the same type, only numbers or alphanumeric",
    "cell": {
        "attribute_id": "FILTRABLE_SIZE",
        "row": {
            "id": null,
            "main_attribute": {
                "id": "{MAIN_ATTRIBUTE_ID}",
                "value": "{ROW_MAIN_ATTRIBUTE_VALUE_NAME}"
            }
        }
    }
}
```

11\. The {ATTRIBUTE\_ID} attribute should not be in the size chart, this
error is due to the fact that you are trying to enter an attribute of
type BODY\_MEASURE or CLOTHING\_MEASURE, and the size chart has a
different size type configured than the attribute. Size charts can only
have one size type.

``` language-javascript
{
    "code": "invalid_row_attribute",
    "message": "Attribute {ATTRIBUTE_ID} found in row {MAIN_ATTRIBUTE_ID} {ROW_MAIN_ATTRIBUTE_VALUE_NAME} is not valid and should not be present in the chart rows.",
    "cell": {
        "attribute_id": "{ATTRIBUTE_ID}",
        "row": {
            "id": null,
            "main_attribute": {
                "id": "{MAIN_ATTRIBUTE_ID}",
                "value": "{ROW_MAIN_ATTRIBUTE_VALUE_NAME}"
            }
        }
    }
}
```

**Next**: [Fashion photo
quality](https://global-selling.mercadolibre.com/devsite/recommendations-for-photo-quality).

</div>
