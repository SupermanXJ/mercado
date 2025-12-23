<div class="inner-content">

## Shipping compensations

From now on, the carriers will inform Mercado Libre about the
measurements of the shipping package. With these measurements, we
recalculate the shipping cost and then charge the difference to the
seller based on what we previously charged at checkout. This surplus to
the shipping cost is called **shipping compensation**. See more [about
Shipping fees](https://global-selling.mercadolibre.com/help/22925).

  

## Recommended technical flow:

1\. See if your [shipping
cost](https://global-selling.mercadolibre.com/devsite/compensations?nocache=true#Shipping-costs)
has a shipping **compensation** in the **senders** section.  
2. If it does, call the [get shipment
compensation](https://global-selling.mercadolibre.com/devsite/compensations?nocache=true#Get-shipment-compensation)
endpoint for more information about declared and validated costs and
dimensions.  
3. For [free shipping
items](https://global-selling.mercadolibre.com/devsite/compensations?nocache=true#Free-shipping-compensation),
you can take a look at how much your cost changed since we validated
your declared dimensions.

  

## Shipping costs

You can see the new array named **compensations** included in the
[Shipment cost
response](https://global-selling.mercadolibre.com/devsite/manage-shipments#cost).

  

Response:

``` language-javascript
[...]
"senders": [
     {
         "user_id": 456789,
         "cost": 177.85,
         "compensations":[
           {
             "amount": 173.27,
             "reason": "incorrect_dimensions",
             "comment": "Incorrect package dimensions"
           }
         ],
         "save": 76.22,
         "discounts": [
             {
                 "rate": 0.3,
                 "type": "mandatory",
                 "promoted_amount": 76.22
             }
         ],
     "compensation": 0
     }
 ]
}
```

**compensations**: compensations calculated based on reason (i.e.
incorrect dimensions).

  

## Get shipment compensation

Consult the shipping compensation generated for a specific shipment ID.

  

### Parameters

**shipment\_id**: the shipment unique identifier.  
**weight\_unit**: the weight unit (**g**, **kg**, **lb** or **oz**) to
be considered by the response. If not parameterized, we will consider
the default units defined by the seller's country.  
**dimensions\_unit**: the dimensions unit (**mm**, **cm**, **m**, **in**
or **ft**) to be considered by the response. If not parameterized, we
will consider the default units defined by the seller's country.

  

Request:

``` language-javascript
curl -H 'Authorization: Bearer $ACCESS_TOKEN' -X GET https://api.mercadolibre.com/marketplace/shipments/$SHIPMENT_ID/compensation_costs?weight_unit=$WEIGHT_UNIT&dimensions_unit=$DIMENSIONS_UNIT
```

Example:

``` language-javascript
curl -H 'Authorization: Bearer $ACCESS_TOKEN' -X GET https://api.mercadolibre.com/marketplace/shipments/12345/compensation_costs?weight_unit=g&dimensions_unit=cm
```

Response:

``` language-javascript
{
   "dimension_by": "seller",
   "package": {
       "declared": {
           "weight": {
               "net": 900,
               "billable": 900,
               "volumetric": 900,
               "unit": "g"
           },
           "dimensions": {
               "length": 15,
               "width": 10,
               "height": 30,
               "unit": "cm"
           },
           "bucket": {
               "min": 501,
               "max": 1000,
               "unit": "g"
           }
       },
       "validated": {
           "weight": {
               "net": 1200,
               "billable": 1200,
               "volumetric": 20,
               "unit": "g"
           },
           "dimensions": {
               "length": 10,
               "width": 5,
               "height": 2,
               "unit": "cm"
           },
           "bucket": {
               "min": 1001,
               "max": 1500,
               "unit": "g"
           }
       }
   },
   "costs": {
       "currency_id": "USD",
       "compensation": 25,
       "declared": {
          "sender": {
              "cost": 15,
          },
          "receiver": {
              "cost": 0,
          }
       },
       "validated": {
          "sender": {
              "cost": 40,
          },
          "receiver": {
              "cost": 0,
          }
       }
   }
}
```

### Response fields

**dimension\_by**: contains information about who declared the
dimensions used at checkout. The declared dimensions can either be **by
the seller** or **by meli** (when validated by Mercado Libre).  
**package**: data about the declared and validated package's weight and
dimensions, alongside in which bucket (weight range) the billable weight
fell into at charge time. The weight and dimension units can be
parameterized according to preference.  
**costs**: contains information about declared and validated sender and
receiver costs, calculated based on the package's declared and validated
measurements, respectively. Furthermore, we use these costs to determine
the final compensation cost to be charged on the seller's behalf.  
**bucket**: the bucket refers to the weight range on the shipping cost
tables that determines the base shipping cost for the package.

  

### Errors

When an error occurs, the API returns a response with the following
structure. The **cause** array provides additional details about the
specific validation error:

``` language-javascript
{
 "message": "invalid parameter",
 "error": "bad_request",
 "status": 400,
 "cause": [
   {
     "error": "weight_unit",
     "message": "invalid"
   }
 ]
}
```

  

| Status | Error                              | Message                              | Solution                                                                                                                                             |
|--------|------------------------------------|--------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------|
| 400    | bad\_request                       | invalid parameter                    | Check the `cause` array for details. Verify that `weight_unit` is one of: g, kg, lb, oz. Verify that `dimensions_unit` is one of: mm, cm, m, in, ft. |
| 403    | forbidden                          | Access denied                        | Verify that your access token has the required permissions for this resource.                                                                        |
| 404    | not\_found\_shipping\_id           | Shipping Id not found                | The shipment ID does not exist. Verify the shipment ID is correct.                                                                                   |
| 404    | not\_found                         | Resource not found                   | The resource path is invalid. Check that the shipment ID is not empty.                                                                               |
| 404    | shipping\_compensation\_not\_found | Shipment compensation was not found. | The shipment exists but has no compensation associated.                                                                                              |
| 500    | internal\_server\_error            | internal server error                | Contact support if the issue persists.                                                                                                               |

## Free shipping compensation

Search the free shipping compensation that is generated based on the
difference between declared dimensions versus Mercado Libre's validated
dimensions. These dimensions can generate a shipment compensation if
they are different enough to end up in another shipping cost bucket.

  

### Parameters

**item\_id**: the item unique identifier.  
**weight\_unit**: the weight unit (**g**, **kg**, **lb** or **oz**) to
be considered by the response. If not parameterized, we will consider
the default units defined by the seller's country.  
**dimensions\_unit**: the dimensions unit (**mm**, **cm**, **m**, **in**
or **ft**) to be considered by the response. If not parameterized, we
will consider the default units defined by the seller's country.

  

Request:

``` language-javascript
curl -H 'Authorization: Bearer $ACCESS_TOKEN' -X GET https://api.mercadolibre.com/marketplace/items/$ITEM_ID/shipping_compensation?weight_unit=$WEIGHT_UNIT&dimensions_unit=$DIMENSIONS_UNIT
```

Example:

``` language-javascript
curl -H 'Authorization: Bearer $ACCESS_TOKEN' -X GET https://api.mercadolibre.com/marketplace/items/MLM1234567/shipping_compensation?weight_unit=kg&dimensions_unit=cm
```

Response:

``` language-javascript
{
   "dimension_by": "seller",
   "package": {
       "declared": {
           "weights": {
               "net": 1.2,
               "billable": 1.2,
               "volumetric": 0.2,
               "unit": "kg"
           },
           "dimensions": {
               "length": 10,
               "width": 10,
               "height": 10,
               "unit": "cm"
           },
           "bucket": {
               "min": 1,
               "max": 1.5,
               "unit": "kg"
           }
       },
       "validated": {
           "weights": {
               "net": 1.8,
               "billable": 1.8,
               "volumetric": 0.6,
               "unit": "kg"
           },
           "dimensions": {
               "length": 20,
               "width": 15,
               "height": 10,
               "unit": "cm"
           },
           "bucket": {
               "min": 1.5,
               "max": 2.0,
               "unit": "kg"
           }
       }
   },
   "costs": {
       "currency_id": "USD",
       "compensation": 25,
       "declared": {
          "sender": {
              "cost": 15,
          }
       },
       "validated": {
          "sender": {
              "cost": 40
          }
       }
   }
}
```

### Response fields

**dimension\_by**: contains information about who declared the
dimensions used at checkout. The declared dimensions can either be **by
the seller** or **by meli** (when validated by Mercado Libre).  
**package**: data about the declared and validated package's weight and
dimensions, alongside in which bucket (weight range) the billable weight
fell into at charge time. The weight and dimension units can be
parameterized according to preference.  
**costs**: contains information about declared and validated sender and
receiver costs, calculated based on the package's declared and validated
measurements, respectively. Furthermore, we use these costs to determine
the final compensation cost to be charged on the seller's behalf.  
**bucket**: the bucket refers to the weight range on the shipping cost
tables that determines the base shipping cost for the package.

  

### Errors

When an error occurs, the API returns a response with the following
structure. The **cause** array provides additional details about the
specific validation error:

``` language-javascript
{
 "message": "invalid parameter",
 "error": "bad_request",
 "status": 400,
 "cause": [
   {
     "error": "ITEM_ID",
     "message": "Invalid Parameter"
   }
 ]
}
```

  

| Status | Error                             | Message                                   | Solution                                                                                                                      |
|--------|-----------------------------------|-------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------|
| 400    | bad\_request                      | invalid parameter                         | Check the `cause` array for details. The error may indicate an invalid `ITEM_ID` format, `weight_unit`, or `dimensions_unit`. |
| 403    | forbidden                         | Access denied                             | Verify that your access token has the required permissions for this resource.                                                 |
| 404    | item\_not\_found                  | The item was not found.                   | The item ID does not exist. Verify the item ID is correct.                                                                    |
| 404    | not\_found                        | Resource not found                        | The resource path is invalid. Check that the item ID is not empty.                                                            |
| 404    | validated\_dimensions\_not\_found | Item validated dimensions were not found. | The item exists but Mercado Libre has not yet validated its dimensions.                                                       |
| 422    | item\_not\_free\_shipping         | Item is not free shipping.                | This endpoint only works with items that have free shipping enabled.                                                          |
| 500    | internal\_server\_error           | internal server error                     | Contact support if the issue persists.                                                                                        |

</div>
