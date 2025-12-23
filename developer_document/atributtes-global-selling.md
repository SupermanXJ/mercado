<div class="inner-content">

## Attributes

<div class="andes-message andes-message--highlight">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--highlight site-carriers__message-title">

Important:

</div>

<div class="andes-message__text--highlight site-carriers__message-text">

<div>

Soon will be mandatory change all PUT Global items API adding /global
**https://api.mercadolibre.com/global/items**. You can starting update
now your endpoints.

</div>

</div>

</div>

</div>

<div class="details__message">

An attribute serves to represent a characteristic of your item, such as
Microwave Brand and Model. These can be added at the time of publication
and later you can modify them, delete them or add new ones. In the
following documentation, you will be able to know the types of possible
attributes, the mandatory ones, how to identify penalties, among other
actions.

</div>

## Check attributes by category

Remember attributes vary by category, and you can find them at the
following request.

Request:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/categories/$CATEGORY_ID/attributes
```

Example:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/categories/CBT391873/attributes
```

Response:

``` language-javascript
[
  {
    "id": "BRAND",
    "name": "Brand",
    "tags": {
      "catalog_required": true
    },
    "hierarchy": "PARENT_PK",
    "relevance": 1,
    "value_type": "string",
    "value_max_length": 255,
    "values": [
      {
        "id": "498493",
        "name": "47 Street"
      },
      {
        "id": "2787048",
        "name": "Alliance"
      },
      {
        "id": "56202",
        "name": "Ana Hickmann"
      },
      {
        "id": "350205",
        "name": "Axis"
      },
      {
        "id": "1157003",
        "name": "Barbie"
      },
      {
        "id": "23688",
        "name": "Benetton"
      },
      {
        "id": "428830",
        "name": "Blaquè"
      },
      {
        "id": "2787047",
        "name": "Cabotine"
      },
      {
        "id": "2787050",
        "name": "Ciel"
      },
      {
        "id": "33243",
        "name": "Disney"
      },
      {
        "id": "433272",
        "name": "Ed Hardy"
      },
      {
        "id": "1229482",
        "name": "Eyelit"
      },
      {
        "id": "428690",
        "name": "Hot Wheels"
      },
      {
        "id": "2786085",
        "name": "Kevingston"
      },
      {
        "id": "2786711",
        "name": "Monster High"
      },
      {
        "id": "498496",
        "name": "Muaa"
      },
      {
        "id": "2787049",
        "name": "Petit"
      },
      {
        "id": "2786636",
        "name": "Portsaid"
      },
      {
        "id": "240356",
        "name": "Prototype"
      },
      {
        "id": "2787044",
        "name": "Samba"
      },
      {
        "id": "428844",
        "name": "Stone"
      },
      {
        "id": "2427441",
        "name": "Valeria Mazza"
      },
      {
        "id": "2705514",
        "name": "Violetta"
      },
      {
        "id": "1162047",
        "name": "Yves Rocher"
      }
    ],
    "attribute_group_id": "OTHERS",
    "attribute_group_name": "Others"
  },
  {
    "id": "LINE",
    "name": "Line",
    "tags": {
      "hidden": true
    },
    "hierarchy": "PARENT_PK",
    "relevance": 1,
    "value_type": "string",
    "value_max_length": 255,
    "attribute_group_id": "OTHERS",
    "attribute_group_name": "Others"
  },
  {
    "id": "PERFUME_NAME",
    "name": "Name",
    "tags": {
    },
    "hierarchy": "PARENT_PK",
    "relevance": 1,
    "value_type": "string",
    "value_max_length": 255,
    "attribute_group_id": "OTHERS",
    "attribute_group_name": "Others"
  },
  {
    "id": "VERSION",
    "name": "Version",
    "tags": {
      "hidden": true
    },
    "hierarchy": "PARENT_PK",
    "relevance": 1,
    "value_type": "string",
    "value_max_length": 255,
    "attribute_group_id": "OTHERS",
    "attribute_group_name": "Others"
  },
  {
    "id": "GENDER",
    "name": "Gender",
    "tags": {
    },
    "hierarchy": "PARENT_PK",
    "relevance": 1,
    "value_type": "list",
    "values": [
      {
        "id": "110461",
        "name": "Gender neutral"
      },
      {
        "id": "339665",
        "name": "Female"
      },
      {
        "id": "339666",
        "name": "Male"
      },
      {
        "id": "339667",
        "name": "Boys"
      },
      {
        "id": "339668",
        "name": "Girls"
      },
      {
        "id": "371795",
        "name": "Babies"
      }
    ],
    "attribute_group_id": "OTHERS",
    "attribute_group_name": "Others"
  },
  {
    "id": "PERFUME_TYPE",
    "name": "Type",
    "tags": {
      "fixed": true
    },
    "hierarchy": "PARENT_PK",
    "relevance": 1,
    "value_type": "string",
    "value_max_length": 255,
    "values": [
      {
        "id": "188085",
        "name": "Body splash"
      }
    ],
    "attribute_group_id": "OTHERS",
    "attribute_group_name": "Others"
  },
  {
    "id": "UNIT_VOLUME",
    "name": "Unit volume",
    "tags": {
    },
    "hierarchy": "CHILD_PK",
    "relevance": 1,
    "value_type": "number_unit",
    "value_max_length": 255,
    "allowed_units": [
      {
        "id": "mL",
        "name": "mL"
      }
    ],
    "default_unit": "mL",
    "attribute_group_id": "OTHERS",
    "attribute_group_name": "Others"
  },
  {
    "id": "SET_PIECES",
    "name": "Set pieces",
    "tags": {
      "multivalued": true
    },
    "hierarchy": "CHILD_DEPENDENT",
    "relevance": 1,
    "value_type": "string",
    "value_max_length": 255,
    "values": [
      {
        "id": "2215606",
        "name": "Body lotion"
      },
      {
        "id": "2215605",
        "name": "Shower gel"
      }
    ],
    "attribute_group_id": "OTHERS",
    "attribute_group_name": "Others"
  },
  {
    "id": "AGE_GROUP",
    "name": "Age",
    "tags": {
    },
    "hierarchy": "FAMILY",
    "relevance": 1,
    "value_type": "list",
    "values": [
      {
        "id": "1065183",
        "name": "Kids"
      },
      {
        "id": "1065182",
        "name": "Adults"
      },
      {
        "id": "371795",
        "name": "Babies"
      }
    ],
    "attribute_group_id": "OTHERS",
    "attribute_group_name": "Others"
  },
  {
    "id": "UNITS_PER_PACKAGE",
    "name": "Units per package",
    "tags": {
    },
    "hierarchy": "ITEM",
    "relevance": 1,
    "value_type": "number",
    "value_max_length": 18,
    "attribute_group_id": "OTHERS",
    "attribute_group_name": "Others"
  },
  {
    "id": "QUANTITY",
    "name": "Quantity",
    "tags": {
    },
    "hierarchy": "ITEM",
    "relevance": 1,
    "value_type": "number",
    "value_max_length": 18,
    "attribute_group_id": "OTHERS",
    "attribute_group_name": "Others"
  },
  {
    "id": "UNIT_TYPE",
    "name": "Unit type",
    "tags": {
    },
    "hierarchy": "ITEM",
    "relevance": 1,
    "value_type": "list",
    "values": [
      {
        "id": "6937304",
        "name": "L"
      },
      {
        "id": "7350718",
        "name": "mL"
      }
    ],
    "attribute_group_id": "OTHERS",
    "attribute_group_name": "Others"
  },
  {
    "id": "GTIN",
    "name": "Universal product code",
    "tags": {
      "multivalued": true,
      "variation_attribute": true,
      "used_hidden": true,
      "validate": true
    },
    "hierarchy": "PRODUCT_IDENTIFIER",
    "relevance": 1,
    "type": "product_identifier",
    "value_type": "string",
    "value_max_length": 255,
    "tooltip": "How do I recognize it? It is an 8 to 14 digit number next to the barcode, on the product box or on its label. ![Universal product code](https://http2.mlstatic.com/static/org-img/sd-landings/assets/pi-tooltip.png)",
    "attribute_group_id": "OTHERS",
    "attribute_group_name": "Others",
    "hint": "It may be an EAN, UPC or another GTIN."
  },
  {
    "id": "RELEASE_YEAR",
    "name": "Release year",
    "tags": {
      "hidden": true
    },
    "hierarchy": "FAMILY",
    "relevance": 2,
    "value_type": "number",
    "value_max_length": 18,
    "attribute_group_id": "OTHERS",
    "attribute_group_name": "Others"
  },
  {
    "id": "UPC",
    "name": "UPC",
    "tags": {
      "hidden": true,
      "multivalued": true,
      "variation_attribute": true,
      "validate": true
    },
    "hierarchy": "PRODUCT_IDENTIFIER",
    "relevance": 2,
    "type": "product_identifier",
    "value_type": "string",
    "value_max_length": 255,
    "attribute_group_id": "OTHERS",
    "attribute_group_name": "Others"
  },
  {
    "id": "MPN",
    "name": "MPN",
    "tags": {
      "hidden": true,
      "multivalued": true,
      "variation_attribute": true
    },
    "hierarchy": "PRODUCT_IDENTIFIER",
    "relevance": 2,
    "type": "product_identifier",
    "value_type": "string",
    "value_max_length": 255,
    "attribute_group_id": "OTHERS",
    "attribute_group_name": "Others"
  },
  {
    "id": "EAN",
    "name": "EAN",
    "tags": {
      "hidden": true,
      "multivalued": true,
      "variation_attribute": true,
      "validate": true
    },
    "hierarchy": "PRODUCT_IDENTIFIER",
    "relevance": 2,
    "type": "product_identifier",
    "value_type": "string",
    "value_max_length": 255,
    "attribute_group_id": "OTHERS",
    "attribute_group_name": "Others"
  },
  {
    "id": "ORIGIN",
    "name": "Origin",
    "tags": {
      "hidden": true
    },
    "hierarchy": "FAMILY",
    "relevance": 2,
    "value_type": "string",
    "value_max_length": 255,
    "attribute_group_id": "OTHERS",
    "attribute_group_name": "Others"
  },
  {
    "id": "ITEM_CONDITION",
    "name": "Item condition",
    "tags": {
      "hidden": true
    },
    "hierarchy": "ITEM",
    "relevance": 2,
    "value_type": "list",
    "values": [
      {
        "id": "2230284",
        "name": "New"
      }
    ],
    "attribute_group_id": "OTHERS",
    "attribute_group_name": "Others"
  },
  {
    "id": "MODEL",
    "name": "Model",
    "tags": {
      "hidden": true
    },
    "hierarchy": "PARENT_PK",
    "relevance": 1,
    "value_type": "string",
    "value_max_length": 255,
    "attribute_group_id": "OTHERS",
    "attribute_group_name": "Others"
  },
  {
    "id": "SELLER_SKU",
    "name": "SKU",
    "tags": {
      "hidden": true,
      "variation_attribute": true
    },
    "hierarchy": "ITEM",
    "relevance": 1,
    "value_type": "string",
    "value_max_length": 255,
    "attribute_group_id": "OTHERS",
    "attribute_group_name": "Others"
  },
  {
    "id": "IS_FLAMMABLE",
    "name": "Is flammable",
    "tags": {
      "hidden": true,
      "read_only": true
    },
    "hierarchy": "FAMILY",
    "relevance": 2,
    "value_type": "boolean",
    "values": [
      {
        "id": "242084",
        "name": "No",
        "metadata": {
          "value": false
        }
      },
      {
        "id": "242085",
        "name": "Yes",
        "metadata": {
          "value": true
        }
      }
    ],
    "attribute_group_id": "OTHERS",
    "attribute_group_name": "Others"
  },
  {
    "id": "IS_KIT",
    "name": "Is kit",
    "tags": {
      "hidden": true
    },
    "hierarchy": "ITEM",
    "relevance": 2,
    "value_type": "boolean",
    "values": [
      {
        "id": "242084",
        "name": "No",
        "metadata": {
          "value": false
        }
      },
      {
        "id": "242085",
        "name": "Yes",
        "metadata": {
          "value": true
        }
      }
    ],
    "attribute_group_id": "OTHERS",
    "attribute_group_name": "Others"
  },
  {
    "id": "DESCRIPTIVE_TAGS",
    "name": "Descriptive tags",
    "tags": {
      "hidden": true,
      "multivalued": true,
      "read_only": true
    },
    "hierarchy": "ITEM",
    "relevance": 2,
    "value_type": "string",
    "value_max_length": 255,
    "attribute_group_id": "OTHERS",
    "attribute_group_name": "Others"
  },
  {
    "id": "PACKAGE_LENGTH",
    "name": "Package length",
    "tags": {
      "hidden": true,
      "variation_attribute": true
    },
    "hierarchy": "ITEM",
    "relevance": 2,
    "value_type": "number_unit",
    "value_max_length": 255,
    "allowed_units": [
      {"id": "km", "name": "km"},
      {"id": "ft", "name": "ft"},
      {"id": "pulgadas", "name": "pulgadas"},
      {"id": "m", "name": "m"},
      {"id": "mm", "name": "mm"},
      {"id": "µm", "name": "µm"},
      {"id": "hh", "name": "hh"},
      {"id": "U", "name": "U"},
      {"id": "nm", "name": "nm"},
      {"id": "in", "name": "in"},
      {"id": "\"", "name": "\""},
      {"id": "cm", "name": "cm"},
      {"id": "yd", "name": "yd"}
    ],
    "default_unit": "cm",
    "attribute_group_id": "OTHERS",
    "attribute_group_name": "Others"
  },
  {
    "id": "PACKAGE_WEIGHT",
    "name": "Package weight",
    "tags": {
      "hidden": true,
      "variation_attribute": true
    },
    "hierarchy": "ITEM",
    "relevance": 2,
    "value_type": "number_unit",
    "value_max_length": 255,
    "allowed_units": [
      {"id": "mcg", "name": "mcg"},
      {"id": "oz", "name": "oz"},
      {"id": "g", "name": "g"},
      {"id": "t", "name": "t"},
      {"id": "kg", "name": "kg"},
      {"id": "mg", "name": "mg"},
      {"id": "lb", "name": "lb"}
    ],
    "default_unit": "g",
    "attribute_group_id": "OTHERS",
    "attribute_group_name": "Others"
  },
  {
    "id": "PACKAGE_WIDTH",
    "name": "Package width",
    "tags": {
      "hidden": true,
      "variation_attribute": true
    },
    "hierarchy": "ITEM",
    "relevance": 2,
    "value_type": "number_unit",
    "value_max_length": 255,
    "allowed_units": [
      {"id": "km", "name": "km"},
      {"id": "ft", "name": "ft"},
      {"id": "pulgadas", "name": "pulgadas"},
      {"id": "m", "name": "m"},
      {"id": "mm", "name": "mm"},
      {"id": "µm", "name": "µm"},
      {"id": "hh", "name": "hh"},
      {"id": "U", "name": "U"},
      {"id": "nm", "name": "nm"},
      {"id": "in", "name": "in"},
      {"id": "\"", "name": "\""},
      {"id": "cm", "name": "cm"},
      {"id": "yd", "name": "yd"}
    ],
    "default_unit": "cm",
    "attribute_group_id": "OTHERS",
    "attribute_group_name": "Others"
  },
  {
    "id": "PACKAGE_HEIGHT",
    "name": "Package height",
    "tags": {
      "hidden": true,
      "variation_attribute": true
    },
    "hierarchy": "ITEM",
    "relevance": 2,
    "value_type": "number_unit",
    "value_max_length": 255,
    "allowed_units": [
      {"id": "km", "name": "km"},
      {"id": "ft", "name": "ft"},
      {"id": "pulgadas", "name": "pulgadas"},
      {"id": "m", "name": "m"},
      {"id": "mm", "name": "mm"},
      {"id": "µm", "name": "µm"},
      {"id": "hh", "name": "hh"},
      {"id": "U", "name": "U"},
      {"id": "nm", "name": "nm"},
      {"id": "in", "name": "in"},
      {"id": "\"", "name": "\""},
      {"id": "cm", "name": "cm"},
      {"id": "yd", "name": "yd"}
    ],
    "default_unit": "cm",
    "attribute_group_id": "OTHERS",
    "attribute_group_name": "Others"
  },
  {
    "id": "PRODUCT_FEATURES",
    "name": "Product features",
    "tags": {
      "hidden": true,
      "multivalued": true,
      "read_only": true
    },
    "hierarchy": "ITEM",
    "relevance": 2,
    "value_type": "list",
    "values": [
      {"id": "7435885", "name": "Contains liquid"},
      {"id": "7435883", "name": "Fragile"},
      {"id": "7435888", "name": "With expiration"},
      {"id": "7575917", "name": "Disinfectant and sanitizer"}
    ],
    "attribute_group_id": "OTHERS",
    "attribute_group_name": "Others"
  },
  {
    "id": "PRODUCT_CHEMICAL_FEATURES",
    "name": "Product chemical features",
    "tags": {
      "hidden": true,
      "multivalued": true,
      "read_only": true
    },
    "hierarchy": "ITEM",
    "relevance": 2,
    "value_type": "list",
    "values": [
      {"id": "7651070", "name": "Flammable"},
      {"id": "7651071", "name": "Aerosol"},
      {"id": "7651072", "name": "Oxidizer"},
      {"id": "7651073", "name": "Corrosive"},
      {"id": "7651074", "name": "Explosive"},
      {"id": "7651075", "name": "Toxic or infectious"}
    ],
    "attribute_group_id": "OTHERS",
    "attribute_group_name": "Others"
  },
  {
    "id": "FOODS_AND_DRINKS",
    "name": "Foods and drinks",
    "tags": {
      "hidden": true,
      "multivalued": true,
      "read_only": true
    },
    "hierarchy": "ITEM",
    "relevance": 2,
    "value_type": "list",
    "values": [
      {"id": "7575926", "name": "For humans"},
      {"id": "7575927", "name": "For animals"}
    ],
    "attribute_group_id": "OTHERS",
    "attribute_group_name": "Others"
  },
  {
    "id": "MEDICINES",
    "name": "Medicines",
    "tags": {
      "hidden": true,
      "multivalued": true,
      "read_only": true
    },
    "hierarchy": "ITEM",
    "relevance": 2,
    "value_type": "list",
    "values": [
      {"id": "7575930", "name": "For humans with a medical prescription"},
      {"id": "7575931", "name": "For humans without a medical prescription"},
      {"id": "7575932", "name": "For animals with a medical prescription"},
      {"id": "7575933", "name": "For animals without a medical prescription"}
    ],
    "attribute_group_id": "OTHERS",
    "attribute_group_name": "Others"
  },
  {
    "id": "BATTERIES_FEATURES",
    "name": "Batteries features",
    "tags": {
      "hidden": true,
      "multivalued": true,
      "read_only": true
    },
    "hierarchy": "ITEM",
    "relevance": 2,
    "value_type": "list",
    "values": [
      {"id": "7575934", "name": "Stand-alone lithium (loose or isolated)"},
      {"id": "7575935", "name": "Lithium installed"},
      {"id": "7575936", "name": "For cars (lead-acid)"}
    ],
    "attribute_group_id": "OTHERS",
    "attribute_group_name": "Others"
  },
  {
    "id": "SHIPMENT_PACKING",
    "name": "Shipment packing",
    "tags": {
      "hidden": true,
      "multivalued": true,
      "read_only": true
    },
    "hierarchy": "ITEM",
    "relevance": 2,
    "value_type": "list",
    "values": [
      {"id": "7435891", "name": "Bag"},
      {"id": "7435892", "name": "Box"},
      {"id": "7575937", "name": "Envelope"},
      {"id": "7575938", "name": "Voluminous"},
      {"id": "7575939", "name": "Self-shipping"}
    ],
    "attribute_group_id": "OTHERS",
    "attribute_group_name": "Others"
  },
  {
    "id": "ADDITIONAL_INFO_REQUIRED",
    "name": "Additional info required",
    "tags": {
      "hidden": true,
      "multivalued": true,
      "read_only": true
    },
    "hierarchy": "ITEM",
    "relevance": 2,
    "value_type": "list",
    "values": [
      {"id": "7435893", "name": "Has IMEI"},
      {"id": "7435894", "name": "Has serial number"}
    ],
    "attribute_group_id": "OTHERS",
    "attribute_group_name": "Others"
  },
  {
    "id": "IS_SUITABLE_FOR_SHIPMENT",
    "name": "Is suitable for shipment",
    "tags": {
      "hidden": true,
      "read_only": true
    },
    "hierarchy": "ITEM",
    "relevance": 2,
    "value_type": "boolean",
    "values": [
      {"id": "242084", "name": "No", "metadata": {"value": false}},
      {"id": "242085", "name": "Yes", "metadata": {"value": true}}
    ],
    "attribute_group_id": "OTHERS",
    "attribute_group_name": "Others"
  }
]
```

## Types of possible attributes

There are different types of attributes, so the values to be supported
will depend on them. Types of attributes can be viewed by entering the
attribute API of the relevant category and querying the value\_type
field. The possible types are:

  

### string

You can complete this type of attributes with free text, including
letters and numbers indistinctively.

**Considerations**: for this attributes, there is a list of suggested
values, but you can also enter new ones which are not included in such
list. For new values, you should only send us the name, but for known
values, you can send us the id as the name. We encourage you to see the
suggested values in the API!

  

### number

These attributes can be only completed with numeric values.

**Considerations**: for this type of attributes there is a list of
suggested values, but you can also enter new ones that are not included
in that list. For new values, you should only send us the name, but for
known values, you can send us the id as well as the name. We encourage
you to see the suggested values in the API!

  

### number\_unit

Attributes made up of a numeric value and a unit. You can view the units
available for such attributes in the attribute API.

<div class="andes-message andes-message--neutral">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--neutral site-carriers__message-title">

Notes:

</div>

<div class="andes-message__text--neutral site-carriers__message-text">

<div>

\- The attributes format will be validated when making or changing a
listing, that is, checking that the above described format is
followed.  
- For all the above types of attributes, the value\_max\_length field
shows the maximum number of characters to be uploaded in attribute
value.

</div>

</div>

</div>

</div>

  

### boolean

It only allows for two values: one corresponding to a positive value and
the other corresponding to a negative one.

**Considerations:** you should send the value id, which you can query in
the attribute API.

  

### list

The values property lists the possible values that this attribute may
take, there should always be at least one.  
**Considerations**: if you wish to enter a value that is not in the
list, you can do so by sending your custom value in value\_name with the
value\_id that is closest to yours. For example, if you are selling a
mobile Air Conditioner but the attribute PRODUCT\_TYPE does not have a
value that exactly represents your item, you can use the value\_id of
the value Portable but in the value\_name send Mobile.

  

## Special behaviors

The tags property specifies particular attribute behaviors. Find below a
list of the possible values that may be included, along with a behavior
description.

-   **allow\_variations**:It allows the item to vary by attribute. For
    this reason, you should check that the allow\_variations tag is set
    in "true" in order to upload the variations. To learn more about how
    to add them, please read the documentation about
    [Variations](../../devsite/variations-global-selling).
-   **defines\_picture**:it shows that the attribute defines the
    picture. For example, Color for shoes.The use of this tag will show
    how to display the different components in the flows. Take into
    account that this behavior only applies to attributes that allow for
    variations.
-   **fixed**:it shows that there is a fixed value for the category and
    that all the items listed under this section should have such value.
    For example, if you are selling a Microwave Oven in the category
    MLB232411 corresponding to Microwave Ovens -&gt; Other Brands -&gt;
    18 Litres, such category includes the VOLUMEN\_CAPACITY attribute
    with values 18 Litres, 20 Litres, etc. but for such category we
    already know that the appropriate value is 18 Litres. So you do not
    need to send it when listing because we autocomplete it for you.
-   **hidden**: attributes with this property are not shown in the sell
    flow, but they can be uploaded via the API.
-   **inferred**:it shows that there is an inferred value for the
    attribute. That value cannot be modified. For example, in the
    category of iPhone under cell phones, the attribute LINE is fixed
    with the value iPhone, and it is inferred that the brand is Apple.
-   **multivalued**:attributes can be completed with more than one
    value, separated by commas.
-   **others**: this tag is for internal use.
-   **product\_pk**: this tag helps identify the attributes that are
    part of the pk of a product. From it, we can uniquely identify a
    product from the catalogue.
-   **read\_only**: this tag is for internal use. Attributes with this
    tag cannot be uploaded or changed by the sellers.
-   **required**: to list the item, the attribute should be completed.
-   **restricted\_values**: this tag is for internal use.
-   **variation\_attribute**: if the item allows for variations, this
    attribute can be listed with a different value for each variation.
    For example, in any electronics listing with variations by color,
    product identifier codes can be uploaded for each variation. A value
    for this attribute can also be uploaded if the item does not have
    any variation.

## Mandatory attributes

<div class="andes-message andes-message--highlight">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--highlight site-carriers__message-title">

Important:

</div>

<div class="andes-message__text--highlight site-carriers__message-text">

<div>

To standardize the sales conditions in bulk sales domains such as
floors, coatings, and others, when publishing or modifying listings, you
must provide the mandatory attributes Sales Unit (SALE\_UNIT) and Yield
of Sales Unit (YIELD\_OF\_SALES\_UNIT).

</div>

</div>

</div>

</div>

Querying the resource /categories/$CATEGORY\_ID/technical\_specs/input
you can find out which are the mandatory attributes by category and
complete them in advance to avoid the publications to be affected in
their ranking in search results. You can identify the mandatory
attributes mandatory with the tag "required".  
Request:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/categories/$CATEGORY_ID/technical_specs/input
```

Example:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/categories/CBT1055/technical_specs/input
```

Response:

``` language-javascript
{
"groups":[
  {
    "id":"MAIN",
    "label":"Características principales",
    "relevance":1,
    "ui_config":{
    },
    "components":[
      {
        "component":"TEXT_INPUT",
        "label":"Brand",
        "ui_config":{
        },
        "attributes":[
          {
            "id":"BRAND",
            "name":"Brand",
            "value_type":"string",
            "value_max_length":255,
            "tags":[
              "catalog_required",
              "required"
            ],
            "hierarchy":"PARENT_PK",
            "relevance":1
          }
        ],
        "unified_units":[
        ]
      },
      {
      },
      {
      },
      {
      },
      {
      },
      {
      },
      {
      },
      {
      }
    ]
  },
  {
  }
]
}
```

<div class="andes-message andes-message--neutral">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--neutral site-carriers__message-title">

Notes:

</div>

<div class="andes-message__text--neutral site-carriers__message-text">

<div>

\- The attributes marked as required in the resource
/categories/$CATEGORY\_ID/attributes are mandatory when listing, if they
are not present an error will be generated.  
- The attributes marked as mandatory in this new resource and that are
not present in /categories/$CATEGORY\_ID/attributes, will only affect
the ranking on search results. Take into account that to identify the
items that are losing their rank, you should check the
incomplete\_technical\_specs tag.

</div>

</div>

</div>

</div>

  

With the resource /categories/$CATEGORY\_ID/technical\_specs/output you
can show your products as they are displayed in Mercado Libre, this way,
your listings will be organized with the same data sheet.

  

### How to identify penalized items

With the resource items/search? you can list, in the field "results",
all the penalized items that have the incomplete\_technical\_specs tag.
This way, you will identify the publications that are losing rank in the
search results to improve their quality. To find out in detail the
reasons why your publications are losing rank, you should check [the
quality
resources](https://global-selling.mercadolibre.com/devsite/find-out-how-the-sellers-are-in-relation-to-the-loading-of-attributes-gs).

  
  

## Gender of a publication

<div class="andes-message andes-message--neutral">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--neutral site-carriers__message-title">

Note:

</div>

<div class="andes-message__text--neutral site-carriers__message-text">

<div>

Starting from late July 2023, we will begin impacting domains that
contain the gender attribute, which will be changed to a "list", adding
a new option called "Gender neutral kid", as well as a new validation
that will prevent creating items where the title refers to a gender
different from the one specified in "GENDER". In order to carry out
tests on this change and adapt integrations, we have pre-configured a
testing domain SNEAKERS\_TEST

</div>

</div>

</div>

</div>

In some domains **/domains/$DOMAIN\_ID/technical\_specs** you will find
the main attribute for the gender, **"id": "GENDER"**. More information
on domains and categories can be found
[here](https://global-selling.mercadolibre.com/devsite/categories-listings-global-selling).

  

This attribute aims to detail the gender of an item, enabling easier
segmentation when buyers want to perform selective searches within the
listings. Example: Hydraulic Disc Bicycle - Adult.

  
![](https://http2.mlstatic.com/storage/developers-site-cms-admin/219224449253-Captura-de-Pantalla-2023-06-27-a-la-s--13.17.21.png)  
  

The gender attribute is a closed list that only allows the following
options:

``` language-javascript
{
"attributes": [{
  "id": "GENDER",
  "name": "Gender",
  "value_type": "list",
  "tags": [
    "catalog_listing_required",
    "grid_template_required",
    "grid_filter",
    "catalog_required",
    "required"
  ],
  "values": [{
      "id": "339665",
      "name": "Woman"
    },
    {
      "id": "339666",
      "name": "Man"
    },
    {
      "id": "339668",
      "name": "Girls"
    },
    {
      "id": "339667",
      "name": "Boys"
    },
    {
      "id": "110461",
      "name": "Gender neutral"
    },
    {
      "id": "19159491",
      "name": "Gender neutral kid"
    },
    {
      "id": "371795",
      "name": "Babies"
    }
  ],
  "hierarchy": "PARENT_PK",
  "relevance": 1
}],
}
```

The option "Gender neutral" will be focused on segmenting unisex
publications for adults, while "Gender neutral kid" will be only focused
on unisex publications for children.

  

The GENDER attribute is mainly found in fashion domains, for which you
must remember that the [size
chart](https://global-selling.mercadolibre.com/devsite/first-steps) is
mandatory. After the PUT or POST of the /items resource, if you used a
gender that is not listed in the technical specifications, it will
display the following error, preventing the creation of the new
publication until you make the respective correction:

``` language-javascript
{
"department": "structured-data",
"cause_id": 2516,
"type": "error",
"code": "error.item.attribute.business_conditional.value_name",
"references": [
  "item.name"
],
"message": "Attribute [GENDER] is not valid"
}
```

Additionally, the title attribute for items where GENDER is required
will be validated, and it will return an error if the "title" refers to
a different gender than the one specified in the "id": "GENDER"
attribute. You can check the details of the
[validations](https://global-selling.mercadolibre.com/devsite/validations-cbt).

  

## Specify not applicable attributes

If any specification does not apply to the product you are posting, it
is important to mark it as N/A (Not Applicable). To that end, you should
send:

-   Value\_id = "-1"
-   Value\_name = Null

In the items API, in order to display the attributes N/A the parameter
include\_internal\_attributes=true must be added, since if the request
is made without it, the attributes N/A will not be displayed.

<span class="pre-label">Request:</span>

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/items/$ITEM_ID?attributes=attributes&include_internal_attributes=true
```

<span class="pre-label">Example:</span>

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' http://api.mercadolibre.com/items/CBT926430395?attributes=attributes&include_internal_attributes=true
```

<span class="pre-label">Response:</span>

``` language-javascript
{
"attributes": [
  {
    "value_id": "517584",
    "value_name": "Shoe",
    "value_struct": null,
    "values": [
      {
        "id": "517584",
        "name": "Shoe",
        "struct": null
      }
    ],
    "attribute_group_id": "OTHERS",
    "attribute_group_name": "Others",
    "id": "FOOTWEAR_TYPE",
    "name": "Footwear type"
  },
  {
    "attribute_group_name": "Others",
    "id": "GENDER",
    "name": "Gender",
    "value_id": "371795",
    "value_name": "Babies",
    "value_struct": null,
    "values": [
      {
        "id": "371795",
        "name": "Babies",
        "struct": null
      }
    ],
    "attribute_group_id": "OTHERS"
  },
  {
    "value_struct": null,
    "values": [
      {
        "id": null,
        "name": "No Brand",
        "struct": null
      }
    ],
    "attribute_group_id": "OTHERS",
    "attribute_group_name": "Others",
    "id": "MODEL",
    "name": "Model",
    "value_id": null,
    "value_name": "No Brand"
  }
]
}
```

## Create ítem with atribute N/A

``` language-javascript
curl -X PUT -H 'Authorization: Bearer $ACCESS_TOKEN' http://api.mercadolibre.com/global/items/CBT926679282
-d '{
"attributes": [
  {
    "id": "BRAND",
    "name": "Brand",
    "value_name": "DOMINIQ"
  },
  {
    "id": "FOOTWEAR_TYPE",
    "value_id": "517583",
    "value_name": "Sneaker"
  },
  {
    "value_name": "Babies",
    "id": "GENDER",
    "value_id": "371795"
  },
  {
    "value_id": "2230284",
    "value_name": "New",
    "id": "ITEM_CONDITION"
  },
  {
    "value_name": "A-59081-6",
    "value_struct": null,
    "id": "MODEL"
  },
  {
    "id": "PACKAGE_HEIGHT",
    "name": "Package height",
    "value_name": "10 cm"
  },
  {
    "value_name": "10 cm",
    "id": "PACKAGE_LENGTH"
  },
  {
    "id": "PACKAGE_WEIGHT",
    "value_name": "0.7 lb"
  },
  {
    "name": "Package width",
    "value_name": "10 cm",
    "id": "PACKAGE_WIDTH"
  },
  {
    "name": "COLOR",
    "value_id": "52019"
  }
]
}'
```

## Change an active post and indicate an attribute is not applicable (N/A)

``` language-javascript
curl -X PUT -H 'Authorization: Bearer $ACCESS_TOKEN' -H "Content-Type: application/json" -H "Accept: application/json" -d
{ "attributes": [{
    "id": "COLOR",
    "value_id": "52049"
  },
  {
    "id": "VOLTAGE",
    "value_name": "198813"
  },
  {
    "id": "DIAMETER",
    "value_id": "-1",
    "value_name": null
  },
  {
    "id": "LATERAL_OSCILLATION",
    "value_id": "242085"
  }
]
}
```

### Considerations

-   Attributes with allow\_variations tag cannot be N/A.
-   If a value\_id -1 attribute is sent, but the value\_name has a value
    other than null, it will be disregarded as if it has never been
    sent. This is because, from the item API, it is verified whether the
    N/A specification has been sent, and both fields are read to
    consider an N/A attribute.
-   So far, if you send N/A, it can only be replaced for a value (When
    making a PUT, the attribute cannot be null).

  

## Exclusions and implications of behaviors

| Matrix of exclusions |          |       |                   |                      |                  |        |
|----------------------|----------|-------|-------------------|----------------------|------------------|--------|
|                      | Required | Fixed | Allow\_variations | Variation\_attribute | Defines\_Picture | Hidden |
| Required             |          |       |                   |                      |                  | X      |
| Fixed                |          |       | X                 | X                    | X                |        |
| Allow\_variations    |          | X     |                   | X                    |                  |        |
| Variation\_attribute |          | X     | X                 |                      | X                |        |
| Defines\_Picture     |          | X     |                   | X                    |                  |        |
| Hidden               | X        |       |                   |                      |                  |        |

  

## Benefit

Item information will be more comprehensive and relevant, with
attributes displayed in a VIP data sheet to avoid questions and
friction.

  

## Create an item with attributes

Imagine that you want to sell a Microwave Oven about which you know
brand, model, and capacity. First, you should select the category in
which you want to list it and, then, you should query the attributes for
such category:

Request:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/categories/$CATEGORY_ID/attributes
```

Example:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/categories/CBT11796/attributes
```

Response:

``` language-javascript
[
{
  "id": "BRAND",
  "name": "Brand",
  "tags": {
    "catalog_required": true
  },
  "hierarchy": "PARENT_PK",
  "relevance": 1,
  "value_type": "string",
  "value_max_length": 255,
  "values": [
    {"id": "515916", "name": "Addnice"},
    {"id": "14810", "name": "Adidas"},
    {"id": "515915", "name": "Atomik"},
    {"id": "7143714", "name": "Carter's"},
    {"id": "515911", "name": "Cheeky"},
    {"id": "433277", "name": "Grisino"},
    {"id": "515914", "name": "Little Akiabara"},
    {"id": "515909", "name": "Mimo & Co"},
    {"id": "415948", "name": "Topper"},
    {"id": "515913", "name": "Tropicana"}
  ],
  "attribute_group_id": "OTHERS",
  "attribute_group_name": "Others"
},
{
  "id": "MODEL",
  "name": "Model",
  "tags": {"catalog_required": true},
  "hierarchy": "PARENT_PK",
  "relevance": 1,
  "value_type": "string",
  "value_max_length": 255,
  "attribute_group_id": "OTHERS",
  "attribute_group_name": "Others"
},
{
  "id": "COLOR",
  "name": "Color",
  "tags": {"allow_variations": true, "defines_picture": true},
  "hierarchy": "CHILD_PK",
  "relevance": 1,
  "value_type": "string",
  "value_max_length": 255,
  "values": [
    {"id": "52019", "name": "Dark green"},
    {"id": "283160", "name": "Turquoise"},
    {"id": "52022", "name": "Water"},
    {"id": "52028", "name": "Blue"},
    {"id": "52049", "name": "Black"},
    {"id": "52053", "name": "Silver"}
  ],
  "attribute_group_id": "OTHERS",
  "attribute_group_name": "Others"
},
{
  "id": "SIZE",
  "name": "Size",
  "tags": {"allow_variations": true},
  "hierarchy": "CHILD_PK",
  "relevance": 1,
  "value_type": "string",
  "value_max_length": 255,
  "attribute_group_id": "OTHERS",
  "attribute_group_name": "Others"
},
{
  "id": "GENDER",
  "name": "Gender",
  "tags": {"fixed": true},
  "hierarchy": "FAMILY",
  "relevance": 1,
  "value_type": "list",
  "values": [{"id": "371795", "name": "Babies"}],
  "attribute_group_id": "OTHERS",
  "attribute_group_name": "Others"
},
{
  "id": "FOOTWEAR_TYPE",
  "name": "Footwear type",
  "tags": {"required": true},
  "hierarchy": "FAMILY",
  "relevance": 1,
  "value_type": "string",
  "value_max_length": 255,
  "values": [
    {"id": "517583", "name": "Sneaker"},
    {"id": "517587", "name": "Crochet shoe"},
    {"id": "517586", "name": "Flip-flop"},
    {"id": "517585", "name": "Sandal"},
    {"id": "517584", "name": "Shoe"},
    {"id": "517588", "name": "Slipper"}
  ],
  "attribute_group_id": "OTHERS",
  "attribute_group_name": "Others"
},
{
  "id": "GTIN",
  "name": "Universal product code",
  "tags": {"multivalued": true, "variation_attribute": true, "used_hidden": true, "validate": true},
  "hierarchy": "PRODUCT_IDENTIFIER",
  "relevance": 1,
  "type": "product_identifier",
  "value_type": "string",
  "value_max_length": 255,
  "tooltip": "How do I recognize it? It is an 8 to 14 digit number next to the barcode, on the product box or on its label.",
  "attribute_group_id": "OTHERS",
  "attribute_group_name": "Others",
  "hint": "It may be an EAN, UPC or another GTIN."
},
{
  "id": "ITEM_CONDITION",
  "name": "Item condition",
  "tags": {"hidden": true},
  "hierarchy": "ITEM",
  "relevance": 2,
  "value_type": "list",
  "values": [{"id": "2230284", "name": "New"}],
  "attribute_group_id": "OTHERS",
  "attribute_group_name": "Others"
},
{
  "id": "SELLER_SKU",
  "name": "SKU",
  "tags": {"hidden": true, "variation_attribute": true},
  "hierarchy": "ITEM",
  "relevance": 1,
  "value_type": "string",
  "value_max_length": 255,
  "attribute_group_id": "OTHERS",
  "attribute_group_name": "Others"
},
{
  "id": "PACKAGE_LENGTH",
  "name": "Package length",
  "tags": {"hidden": true, "variation_attribute": true},
  "hierarchy": "ITEM",
  "relevance": 2,
  "value_type": "number_unit",
  "value_max_length": 255,
  "allowed_units": [{"id": "cm", "name": "cm"}, {"id": "mm", "name": "mm"}, {"id": "m", "name": "m"}],
  "default_unit": "cm",
  "attribute_group_id": "OTHERS",
  "attribute_group_name": "Others"
},
{
  "id": "PACKAGE_WEIGHT",
  "name": "Package weight",
  "tags": {"hidden": true, "variation_attribute": true},
  "hierarchy": "ITEM",
  "relevance": 2,
  "value_type": "number_unit",
  "value_max_length": 255,
  "allowed_units": [{"id": "g", "name": "g"}, {"id": "kg", "name": "kg"}, {"id": "lb", "name": "lb"}],
  "default_unit": "g",
  "attribute_group_id": "OTHERS",
  "attribute_group_name": "Others"
},
{
  "id": "PACKAGE_WIDTH",
  "name": "Package width",
  "tags": {"hidden": true, "variation_attribute": true},
  "hierarchy": "ITEM",
  "relevance": 2,
  "value_type": "number_unit",
  "value_max_length": 255,
  "allowed_units": [{"id": "cm", "name": "cm"}, {"id": "mm", "name": "mm"}, {"id": "m", "name": "m"}],
  "default_unit": "cm",
  "attribute_group_id": "OTHERS",
  "attribute_group_name": "Others"
},
{
  "id": "PACKAGE_HEIGHT",
  "name": "Package height",
  "tags": {"hidden": true, "variation_attribute": true},
  "hierarchy": "ITEM",
  "relevance": 2,
  "value_type": "number_unit",
  "value_max_length": 255,
  "allowed_units": [{"id": "cm", "name": "cm"}, {"id": "mm", "name": "mm"}, {"id": "m", "name": "m"}],
  "default_unit": "cm",
  "attribute_group_id": "OTHERS",
  "attribute_group_name": "Others"
}
]
```

Then, you just need to analyze the available attributes, their types and
suggested values to make the listing JSON, including the attributes
section. Find below how to do it:

``` language-javascript
curl -X POST -H 'Authorization: Bearer $ACCESS_TOKEN' http://api.mercadolibre.com/items
-d '{
"listing_type_id": "gold_pro",
"title": "Test Item - for LoadTest tests",
"available_quantity": 100,
"category_id": "CBT11796",
"buying_mode": "buy_it_now",
"currency_id": "USD",
"condition": "new",
"site_id": "CBT",
"price": 15.1,
"sale_terms": [
  {"id": "WARRANTY_TIME", "value_name": "90 days"},
  {"id": "WARRANTY_TYPE", "value_id": "2230279"}
],
"attributes": [
  {"id": "PACKAGE_HEIGHT", "value_name": "10 cm"},
  {"id": "PACKAGE_WIDTH", "value_name": "10 cm"},
  {"id": "PACKAGE_LENGTH", "value_name": "10 cm"},
  {"id": "PACKAGE_WEIGHT", "value_name": "0.7 lb"},
  {"id": "BRAND", "value_name": "DOMINIQ"},
  {"id": "FOOTWEAR_TYPE", "value_id": "517583"},
  {"id": "GENDER", "value_id": "371795"},
  {"id": "ITEM_CONDITION", "value_id": "2230284"},
  {"id": "MODEL", "value_name": "A-59081-6"}
],
"pictures": [
  {
    "id": "691535-MLA29134565196_012019",
    "max_size": "500x500",
    "quality": "",
    "secure_url": "https://www.mercadolibre.com/jm/img?s=STC&v=O&f=proccesing_image_es.jpg",
    "size": "500x500",
    "url": "http://www.mercadolibre.com/jm/img?s=STC&v=O&f=proccesing_image_es.jpg"
  }
],
"description": {"plain_text": "this is a test item"}
}'
```

Remember:

-   Attributes can be added to items at any time during their life
    cycle.
-   If the attribute has a suggested\_values list, you can send either
    one of those values or a new one. To send new values you must only
    send the value\_name but for the existing values, sending the
    value\_id is enough.
-   For list-type attributes, you should only send values included in
    such list. Sending only the value\_id is enough. If you wish to
    enter a value that is not on the list, you can do so by sending your
    custom value in value\_name with the value\_id that is closest to
    yours.
-   All the main attributes are identified as MAIN in the field
    attribute\_group\_id while, the secondary attributes will be
    differentiated under other values such as: DELT.
-   Take into account that in categories that include primary and
    secondary colors, as an exception, it will not be necessary that all
    the variations duplicate both attributes.

  

## Change and/or add attributes

Once the listing is created, you can add new attributes or change the
existing ones. Let's assume that you want to change the Microwave Oven
Model and add the Number of Programs. First, we suggest you should make
a GET to know the attributes already filled out (for example, Model).  
Request:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/items/$ITEM_ID
```

<span class="pre-label">Example:</span>

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' http://api.mercadolibre.com/items/CBT926679283
```

<span class="pre-label">Response:</span>

``` language-javascript
{
"id": "CBT926679283",
"site_id": "CBT",
"title": "Test Item - For Loadtest Tests",
"subtitle": null,
"seller_id": 523130418,
"category_id": "CBT11796",
"official_store_id": null,
"price": 15.1,
"base_price": 15.1,
"original_price": null,
"currency_id": "USD",
"initial_quantity": 100,
"available_quantity": 50,
"sold_quantity": 0,
"sale_terms": [
  {"id": "WARRANTY_TYPE", "name": "Type of warranty", "value_id": "2230279", "value_name": "Factory warranty"},
  {"id": "WARRANTY_TIME", "name": "Warranty time", "value_id": null, "value_name": "90 days"}
],
"buying_mode": "buy_it_now",
"listing_type_id": "gold_pro",
"start_time": "2020-05-11T23:09:18.000Z",
"stop_time": "2040-05-06T04:00:00.000Z",
"condition": "new",
"permalink": "",
"thumbnail": "http://cbt-s2-p.mlstatic.com/691535-MLA29134565196_012019-I.jpg",
"secure_thumbnail": "https://cbt-s2-p.mlstatic.com/691535-MLA29134565196_012019-I.jpg",
"pictures": [
  {
    "id": "691535-MLA29134565196_012019",
    "url": "http://cbt-s2-p.mlstatic.com/691535-MLA29134565196_012019-O.jpg",
    "secure_url": "https://cbt-s2-p.mlstatic.com/691535-MLA29134565196_012019-O.jpg",
    "size": "500x500",
    "max_size": "500x500",
    "quality": ""
  }
],
"video_id": null,
"descriptions": [{"id": "CBT926679283-2654908016"}],
"accepts_mercadopago": true,
"non_mercado_pago_payment_methods": [],
"shipping": {
  "mode": "not_specified",
  "methods": [],
  "tags": [],
  "dimensions": null,
  "local_pick_up": false,
  "free_shipping": false,
  "logistic_type": "not_specified",
  "store_pick_up": false
},
"international_delivery_mode": "none",
"seller_address": {
  "city": {"id": "Q04tQ1FDaG9uZ3Fpbmc", "name": "Chongqing"},
  "state": {"id": "CN-CQ", "name": "Chongqing"},
  "country": {"id": "CN", "name": "China"},
  "id": 1086581840
},
"seller_contact": null,
"location": {},
"coverage_areas": [],
"attributes": [
  {"id": "BRAND", "name": "Brand", "value_id": null, "value_name": "DOMINIQ", "attribute_group_id": "OTHERS"},
  {"id": "FOOTWEAR_TYPE", "name": "Footwear type", "value_id": "517583", "value_name": "Sneaker", "attribute_group_id": "OTHERS"},
  {"id": "GENDER", "name": "Gender", "value_id": "371795", "value_name": "Babies", "attribute_group_id": "OTHERS"},
  {"id": "ITEM_CONDITION", "name": "Item condition", "value_id": "2230284", "value_name": "New", "attribute_group_id": "OTHERS"},
  {"id": "MODEL", "name": "Model", "value_id": null, "value_name": "A-59081-6", "attribute_group_id": "OTHERS"},
  {"id": "PACKAGE_HEIGHT", "name": "Package height", "value_id": null, "value_name": "10 cm", "attribute_group_id": "OTHERS"},
  {"id": "PACKAGE_LENGTH", "name": "Package length", "value_id": null, "value_name": "10 cm", "attribute_group_id": "OTHERS"},
  {"id": "PACKAGE_WEIGHT", "name": "Package weight", "value_id": null, "value_name": "0.7 lb", "attribute_group_id": "OTHERS"},
  {"id": "PACKAGE_WIDTH", "name": "Package width", "value_id": null, "value_name": "10 cm", "attribute_group_id": "OTHERS"}
],
"warnings": [],
"listing_source": "",
"variations": [],
"status": "active",
"sub_status": [],
"tags": ["immediate_payment"],
"catalog_product_id": null,
"domain_id": "CBT-BABIES_FOOTWEAR",
"parent_item_id": null,
"differential_pricing": null,
"deal_ids": [],
"automatic_relist": false,
"date_created": "2020-05-11T23:09:18.000Z",
"last_updated": "2020-05-11T23:09:22.000Z",
"health": null,
"catalog_listing": false
}
```

**You will need to load this attribute when you make a PUT not to lose
information.**  
Ready to make an update? Make a PUT including new attributes, such as
Number of Programs, and those you already had (such as Model).

  

``` language-javascript
curl -X PUT -H 'Authorization: Bearer $ACCESS_TOKEN' http://api.mercadolibre.com/global/items/CBT926679283
-d '{
"attributes": [
  {"id": "BRAND", "name": "Brand", "value_name": "DOMINIQ"},
  {"id": "FOOTWEAR_TYPE", "value_id": "517583", "value_name": "Sneaker"},
  {"value_name": "Babies", "id": "GENDER", "value_id": "371795"},
  {"value_id": "2230284", "value_name": "New", "id": "ITEM_CONDITION"},
  {"value_name": "A-59081-6", "value_struct": null, "id": "MODEL"},
  {"id": "PACKAGE_HEIGHT", "name": "Package height", "value_name": "10 cm"},
  {"value_name": "10 cm", "id": "PACKAGE_LENGTH"},
  {"id": "PACKAGE_WEIGHT", "value_name": "0.7 lb"},
  {"name": "Package width", "value_name": "10 cm", "id": "PACKAGE_WIDTH"},
  {"name": "COLOR", "value_id": "52019"}
]
}'
```

## Delete attributes

The correct way to eliminate the attribute value is by sending **null**
in the "value\_id" and "value\_name" fields. This way, the attribute
remains in the item, but without value. If any data is required and you
try to send "null", we will return a bad request with the following
error code: **"code": "item.attributes.deleted\_required"** <span
class="pre-label">Request:</span>

``` language-javascript
curl -X PUT -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/global/items/$ITEM_ID
```

<span class="pre-label">Example:</span>

``` language-javascript
curl -X PUT -H 'Authorization: Bearer $ACCESS_TOKEN' 'http://api.mercadolibre.com/global/items/CBT926679283
-d '{
"attributes": [
  {"id": "BRAND", "name": "Brand", "value_name": "DOMINIQ"},
  {"id": "FOOTWEAR_TYPE", "value_id": "517583", "value_name": "Sneaker"},
  {"value_name": "Babies", "id": "GENDER", "value_id": "371795"},
  {"value_id": "2230284", "value_name": "New", "id": "ITEM_CONDITION"},
  {"value_name": "A-59081-6", "value_struct": null, "id": "MODEL"},
  {"id": "PACKAGE_HEIGHT", "name": "Package height", "value_name": "10 cm"},
  {"value_name": "10 cm", "id": "PACKAGE_LENGTH"},
  {"id": "PACKAGE_WEIGHT", "value_name": "0.7 lb"},
  {"name": "Package width", "value_name": "10 cm", "id": "PACKAGE_WIDTH"}
]
}'
```

<span class="pre-label">Response:</span>

``` language-javascript
{
"id": "CBT926679283",
"site_id": "CBT",
"title": "Test Item - For Loadtest Tests",
"subtitle": null,
"seller_id": 523130418,
"category_id": "CBT11796",
"official_store_id": null,
"price": 15.1,
"base_price": 15.1,
"original_price": null,
"inventory_id": null,
"currency_id": "USD",
"initial_quantity": 100,
"available_quantity": 100,
"sold_quantity": 0,
"sale_terms": [
  {"id": "WARRANTY_TYPE", "name": "Type of warranty", "value_id": "2230279", "value_name": "Factory warranty"},
  {"id": "WARRANTY_TIME", "name": "Warranty time", "value_id": null, "value_name": "90 days"}
],
"buying_mode": "buy_it_now",
"listing_type_id": "gold_pro",
"start_time": "2020-05-11T23:09:18.000Z",
"stop_time": "2040-05-06T04:00:00.000Z",
"end_time": "2040-05-06T04:00:00.000Z",
"expiration_time": "2020-07-30T23:09:18.000Z",
"condition": "new",
"permalink": "",
"pictures": [
  {
    "id": "691535-MLA29134565196_012019",
    "url": "http://mla-s2-p.mlstatic.com/691535-MLA29134565196_012019-O.jpg",
    "secure_url": "https://mla-s2-p.mlstatic.com/691535-MLA29134565196_012019-O.jpg",
    "size": "500x500",
    "max_size": "500x500",
    "quality": ""
  }
],
"video_id": null,
"descriptions": [{"id": "CBT926679283-2654908016"}],
"accepts_mercadopago": true,
"non_mercado_pago_payment_methods": [],
"shipping": {
  "mode": "not_specified",
  "local_pick_up": false,
  "free_shipping": false,
  "methods": [],
  "dimensions": null,
  "tags": [],
  "logistic_type": "not_specified",
  "store_pick_up": false
},
"international_delivery_mode": "none",
"seller_address": {
  "id": 1086581840,
  "comment": "",
  "address_line": "498 NW 3rd Av",
  "zip_code": "12345",
  "city": {"id": "Q04tQ1FDaG9uZ3Fpbmc", "name": "Chongqing"},
  "state": {"id": "CN-CQ", "name": "Chongqing"},
  "country": {"id": "CN", "name": "China"},
  "latitude": "",
  "longitude": "",
  "search_location": {"neighborhood": {"id": "", "name": ""}, "city": {"id": "", "name": ""}, "state": {"id": "", "name": ""}}
},
"seller_contact": null,
"location": {},
"geolocation": {"latitude": "", "longitude": ""},
"coverage_areas": [],
"attributes": [
  {"id": "MODEL", "name": "Model", "value_id": null, "value_name": "A-59081-6", "attribute_group_id": "OTHERS", "attribute_group_name": "Others"},
  {"id": "BRAND", "name": "Brand", "value_id": null, "value_name": "DOMINIQ", "attribute_group_id": "OTHERS", "attribute_group_name": "Others"},
  {"id": "PACKAGE_WEIGHT", "name": "Package weight", "value_id": null, "value_name": "0.7 lb", "attribute_group_id": "OTHERS", "attribute_group_name": "Others"},
  {"id": "GENDER", "name": "Gender", "value_id": "371795", "value_name": "Babies", "attribute_group_id": "OTHERS", "attribute_group_name": "Others"},
  {"id": "PACKAGE_HEIGHT", "name": "Package height", "value_id": null, "value_name": "10 cm", "attribute_group_id": "OTHERS", "attribute_group_name": "Others"},
  {"id": "ITEM_CONDITION", "name": "Item condition", "value_id": "2230284", "value_name": "New", "attribute_group_id": "OTHERS", "attribute_group_name": "Others"},
  {"id": "FOOTWEAR_TYPE", "name": "Footwear type", "value_id": "517583", "value_name": "Sneaker", "attribute_group_id": "OTHERS", "attribute_group_name": "Others"},
  {"id": "PACKAGE_WIDTH", "name": "Package width", "value_id": null, "value_name": "10 cm", "attribute_group_id": "OTHERS", "attribute_group_name": "Others"},
  {"id": "PACKAGE_LENGTH", "name": "Package length", "value_id": null, "value_name": "10 cm", "attribute_group_id": "OTHERS", "attribute_group_name": "Others"}
],
"warnings": [],
"listing_source": "",
"variations": [],
"thumbnail": "http://cbt-s2-p.mlstatic.com/691535-MLA29134565196_012019-I.jpg",
"secure_thumbnail": "https://cbt-s2-p.mlstatic.com/691535-MLA29134565196_012019-I.jpg",
"status": "active",
"sub_status": [],
"tags": ["immediate_payment"],
"catalog_product_id": null,
"domain_id": "CBT-BABIES_FOOTWEAR",
"seller_custom_field": null,
"parent_item_id": null,
"differential_pricing": null,
"deal_ids": [],
"automatic_relist": false,
"date_created": "2020-05-11T23:09:18.000Z",
"last_updated": "2020-05-11T23:14:41.463Z",
"health": null,
"catalog_listing": false,
"item_relations": []
}
```

## Errors

Below are the most common errors you may encounter when working with the
Attributes API.

### 404 - Category not found

Returned when the specified category ID does not exist or is invalid.

``` language-javascript
{
  "message": "Category not found: INVALID_CAT_123",
  "error": "not_found",
  "status": 404,
  "cause": []
}
```

### 403 - Forbidden

Returned when the request is blocked due to security restrictions,
invalid characters in the request, or insufficient permissions.

``` language-javascript
{
  "message": "Forbidden",
  "error": "forbidden",
  "status": 403,
  "cause": []
}
```

### 400 - Required attribute missing

Returned when attempting to create or update an item without providing a
required attribute.

``` language-javascript
{
  "message": "Item must have the required attribute: BRAND",
  "error": "validation_error",
  "status": 400,
  "cause": [
    {
      "code": "item.attributes.missing_required",
      "message": "Attribute BRAND is required for this category"
    }
  ]
}
```

### 400 - Invalid attribute value

Returned when an attribute value does not match the expected type or
format.

``` language-javascript
{
  "message": "Invalid value for attribute",
  "error": "validation_error",
  "status": 400,
  "cause": [
    {
      "code": "item.attributes.invalid_value",
      "message": "The value 'abc' is not valid for attribute PACKAGE_WEIGHT. Expected number_unit format."
    }
  ]
}
```

### 400 - Gender attribute validation error

Returned when the GENDER attribute value does not match the item title
or is not valid for the category.

``` language-javascript
{
  "department": "structured-data",
  "cause_id": 2516,
  "type": "error",
  "code": "error.item.attribute.business_conditional.value_name",
  "references": [
    "item.name"
  ],
  "message": "Attribute [GENDER] is not valid"
}
```

### 400 - Cannot delete required attribute

Returned when attempting to set a required attribute to null (N/A).

``` language-javascript
{
  "message": "Cannot delete required attribute",
  "error": "validation_error",
  "status": 400,
  "cause": [
    {
      "code": "item.attributes.deleted_required",
      "message": "Attribute BRAND is required and cannot be deleted"
    }
  ]
}
```

### 400 - Value not in list

Returned when providing a value that is not included in the allowed
values for a list-type attribute.

``` language-javascript
{
  "message": "Invalid value for list attribute",
  "error": "validation_error",
  "status": 400,
  "cause": [
    {
      "code": "item.attributes.invalid_list_value",
      "message": "Value 'invalid_value' is not allowed for attribute ITEM_CONDITION"
    }
  ]
}
```

### 400 - Value exceeds maximum length

Returned when the attribute value exceeds the maximum allowed length
defined in value\_max\_length.

``` language-javascript
{
  "message": "Value too long",
  "error": "validation_error",
  "status": 400,
  "cause": [
    {
      "code": "item.attributes.value_too_long",
      "message": "Attribute MODEL value exceeds maximum length of 255 characters"
    }
  ]
}
```

  

**Next**: [Product
identifiers](https://global-selling.mercadolibre.com/devsite/product-identifiers-gs).

</div>
