<div class="inner-content">

## SEC Stamp and Energy Efficiency Label for CBT

<div class="andes-message andes-message--neutral">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--neutral site-carriers__message-title">

Note:

</div>

<div class="andes-message__text--neutral site-carriers__message-text">

<div>

This resource only applies to Chile.

</div>

</div>

</div>

</div>

The Chilean government mandates specific procedures for the sale of
electronic products. If you work with sellers who are listing products
on the Chile site, it's crucial to adhere to these requirements to
prevent potential moderation. Below is a detailed list specifying the
criteria for this category of products:

  

-   Low-voltage electrical items (e.g., cables, extension cords, and
    other power connection products) without Safety Certification
    (issued by the SEC).
-   Operate on electricity or fuels and are subject to energy efficiency
    labeling requirements (e.g., refrigerators, air conditioners, and
    others). Per regulations, products lacking the mandatory energy
    efficiency label are prohibited from public view.
-   Mimic electricity-operated toys, featuring shapes such as animals,
    characters, people, or scale models, in contravention of IEC 60335-1
    and the guidelines of the Superintendence of Electricity and Fuels
    (SEC).

For more information about, consult the
[FAQ](https://global-selling.mercadolibre.com/help/31842) and [Learning
Center](https://global-selling.mercadolibre.com/learning-center/news/how-to-list-electrical-and-fuel-products-in-chile).

  
  

## SEC Stamp

### Upload the stamp image

You can upload your image by searching for your product's stamp and
associating it to your image path.

  

As an example, this image will probably be like this:

![](https://http2.mlstatic.com/storage/developers-site-cms-admin/205761250256-Captura-de-Tela-2023-11-30-a-s-09.05.08.png)  
  

Request:

``` language-javascript
curl 'https://api.mercadolibre.com/pictures/items/upload' -H 'Authorization: Bearer $ACCESS_TOKEN' -F 'file=@"yourImagePath"'
```

For this request, you will have a response containing an ID, that is the
first field.

  

Response:

``` language-javascript
{
    "id": "964943-CBT72035468960_102023",
    "max_size": "524x748",
    "dominant_color": null,
    "hash": "63105727d28a35c56a115811d2c44eb7",
    "crop": {
        "validated": false,
        "x_offset": null,
        "x_size": null,
        "y_offset": null,
        "y_size": null
    },
    "variations": [
        {
            "size": "524x748",
            "secure_url": "https://http2.mlstatic.com/D_NQ_NP_964943-CBT72035468960_102023-F.jpg",
            "url": "http://http2.mlstatic.com/D_NQ_NP_964943-CBT72035468960_102023-F.jpg"
        }
    ]
}
```

**Take that ID to use in the next request**.

  

## Associate SEC Stamp attribute to item

Now, you will need [to
create](https://global-selling.mercadolibre.com/devsite/global-items#Create-an-Global-Site-item)
or
[update](https://global-selling.mercadolibre.com/devsite/global-items#Modify-Global-item-details)
a CBT item, referring to the image uploaded before.

  

Note that, for this example, your ID is 964943-CBT72035468960\_102023.
Here you need to change this field for the ID you got in the previous
step.

  

### Body of SEC Stamp Label

``` language-javascript
{
    "id": "SEC_STAMP",
    "name": "SEC stamp",
    "value_id": null,
    "value_name": "964943-CBT72035468960_102023",
    "value_struct": null,
    "values": [
        {
            "id": null,
            "name": "964943-CBT72035468960_102023",
            "struct": null,
            "source": null
        }
    ],
    "attribute_group_id": "OTHERS",
    "attribute_group_name": "Others",
    "source": null,
    "value_type": "picture_id"
}
```

## Energy Efficiency Label

### Upload the stamp image

The Energy Efficiency Label is also a requirement to sell some CBT
items, if it is your case, you should follow the next steps to include
the picture of it and the information related.

  

As an example, this label will be something like this:

![](https://http2.mlstatic.com/storage/developers-site-cms-admin/205760685300-Captura-de-Tela-2023-11-30-a-s-09.15.03.png)  
  

## Associate Energy Efficiency Stamp

Now, you will need [to
create](https://global-selling.mercadolibre.com/devsite/global-items#Create-an-Global-Site-item)
or
[update](https://global-selling.mercadolibre.com/devsite/global-items#Modify-Global-item-details)
a CBT item, referring to the image uploaded before.

  

Note that, for this example, your ID is 964943-CBT72035468960\_102023.
Here you need to change this field for the ID you got in the previous
step.

  

### Body of Energy efficiency Label

``` language-javascript
{
    "id": "ENERGY_EFFICIENCY_LABEL",
    "name": "Energy efficiency label",
    "value_id": null,
    "value_name": "964943-CBT72035468960_102023",
    "value_struct": null,
    "values": [
        {
            "id": null,
            "name": "964943-CBT72035468960_102023",
            "struct": null,
            "source": null
        }
    ],
    "attribute_group_id": "OTHERS",
    "attribute_group_name": "Others",
    "source": null,
    "value_type": "picture_id"
}
```

## Verify the attributes

After creating or updating your item with the SEC Stamp or Energy
Efficiency Label attributes, you can verify that the attributes were
applied correctly by retrieving the item information.

  

### Request

``` language-javascript
curl -X GET 'https://api.mercadolibre.com/items/$ITEM_ID' \
  -H 'Authorization: Bearer $ACCESS_TOKEN'
```

  

### Response

In the response, look for the `attributes` array to confirm your
SEC\_STAMP or ENERGY\_EFFICIENCY\_LABEL attribute is present with the
correct picture\_id:

  

``` language-javascript
{
    "id": "CBT1234567890",
    "title": "Your Product Title",
    "attributes": [
        {
            "id": "SEC_STAMP",
            "name": "SEC stamp",
            "value_id": null,
            "value_name": "964943-CBT72035468960_102023",
            "value_type": "picture_id"
        },
        {
            "id": "ENERGY_EFFICIENCY_LABEL",
            "name": "Energy efficiency label",
            "value_id": null,
            "value_name": "964943-CBT72035468960_102023",
            "value_type": "picture_id"
        }
    ]
}
```

  

<div class="andes-message andes-message--highlight">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--highlight site-carriers__message-title">

Tip:

</div>

<div class="andes-message__text--highlight site-carriers__message-text">

<div>

You can also verify the stamp images directly on the item's page in the
marketplace to ensure they are displayed correctly to buyers.

</div>

</div>

</div>

</div>

</div>
