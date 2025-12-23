<div class="inner-content">

## Search products

Before list a product in the catalog, you must confirm, using the
product search engine, the correct product that you will sell, if it is
active and its characteristics. This resource allows you to identify the
products to publish directly in the catalog and/or through [associated
publications](https://global-selling.mercadolibre.com/devsite/catalog-listing-gs#List-from-an-existing-post).

  

### Parameters

**status**: It may be that although the product is identified within our
catalog, it isn't yet eligible to be associated with a publication.

-   **status=active**: returns those products that can already be chosen
    to be associated with a publication. .
-   **status=inactive**: returns those products that aren´t yet eligible
    to associate with a publication.

<div class="andes-message andes-message--neutral">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--neutral site-carriers__message-title">

Note:

</div>

<div class="andes-message__text--neutral site-carriers__message-text">

<div>

If you don't send this parameter, by default it will bring the active
results.

</div>

</div>

</div>

</div>

-   **product\_identifier**: **(dependent required)** string with the
    universal product code. Example: GTIN which includes the different
    PIs (EAN, UPC, ISBN, etc). It is mandatory and you will get only a
    product.
-   **offset**: (optional) position from which the search results are
    returned, default = **0**.
-   **limit**: (optional) number of results returned by the search,
    default = **10**.
-   **q**: **(dependent required)** words or phrase or product
    attributes with search keys, it is important to take into account
    that in this field you can send as many details of the attributes of
    your publication as necessary, in this way in the response you will
    obtain more accurate searches and you will avoid possible
    moderations due to bad production of the publications market, This
    parameter is mandatory if the product\_identifier is not sent in the
    request.  
    Example: **vacuum wireless**

  

<div class="andes-message andes-message--neutral">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--neutral site-carriers__message-title">

Note:

</div>

<div class="andes-message__text--neutral site-carriers__message-text">

<div>

q and product\_identifier are required dependent, at least one of them
must be present in the request.

</div>

</div>

</div>

</div>

Request with **product\_identifier** parameter:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/marketplace/products/search?status=$STATUS_ID&product_identifier=$PRODUCT_IDENTIFIER
```

Example:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/marketplace/products/search?status=active&product_identifier=0123456789
```

Response:

``` language-javascript
{
   "product_identifier": "6941059633686",
   "paging": {
       "total": 1,
       "offset": 0,
       "limit": 10
   },
   "results": [
       {
           "id": "CBT15276372",
           "status": "active",
           "domain_id": "CBT-CELLPHONES",
           "settings": {
               "listing_strategy": "open"
           },
           "name": "Xiaomi Redmi Note 8 Pro - Dark blue - 128 GB - 6 GB",
           "main_features": null,
           "attributes": [
               {
                   "id": "BRAND",
                   "name": "Brand",
                   "value_id": "59387",
                   "value_name": "Xiaomi"
               },
               {
                   "id": "LINE",
                   "name": "Line",
                   "value_id": "199791",
                   "value_name": "Redmi"
               },
               {
                   "id": "MODEL",
                   "name": "Model",
                   "value_id": "7863873",
                   "value_name": "Note 8 Pro"
               },
               {
                   "id": "IS_DUAL_SIM",
                   "name": "Is Dual SIM",
                   "value_id": "242085",
                   "value_name": "Yes"
               },
               {
                   "id": "COLOR",
                   "name": "Color",
                   "value_id": "52033",
                   "value_name": "Dark blue"
               },
               {
                   "id": "INTERNAL_MEMORY",
                   "name": "Internal memory",
                   "value_id": "84611",
                   "value_name": "128 GB"
               },
               {
                   "id": "RAM",
                   "name": "RAM memory",
                   "value_id": "469448",
                   "value_name": "6 GB"
               },
               {
                   "id": "MAIN_COLOR",
                   "name": "Main color",
                   "value_id": "2450293",
                   "value_name": "Blue"
               },
               {
                   "id": "OPERATING_SYSTEM_NAME",
                   "name": "Operating system name",
                   "value_id": "7403813",
                   "value_name": "Android"
               },
               {
                   "id": "OPERATING_SYSTEM_ORIGINAL_VERSION",
                   "name": "Operating system original version",
                   "value_id": "7207107",
                   "value_name": "9.0 ft"
               },
               {
                   "id": "OPERATING_SYSTEM_LAST_COMPATIBLE_VERSION",
                   "name": "Operating system last compatible version",
                   "value_id": "9123308",
                   "value_name": "10"
               },
               {
                   "id": "DISPLAY_SIZE",
                   "name": "Display size",
                   "value_id": "7838050",
                   "value_name": "6.53 \""
               },
               {
                   "id": "DISPLAY_RESOLUTION_TYPE",
                   "name": "Display resolution type",
                   "value_id": "9568930",
                   "value_name": "Full HD+"
               },
               {
                   "id": "DISPLAY_RESOLUTION",
                   "name": "Display resolution",
                   "value_id": "7209646",
                   "value_name": "1080 px x 2340 px"
               },
               {
                   "id": "MAIN_REAR_CAMERA_RESOLUTION",
                   "name": "Main rear camera resolution",
                   "value_id": "7863872",
                   "value_name": "64 Mpx"
               },
               {
                   "id": "REAR_CAMERA_RECORDING_RESOLUTION",
                   "name": "Rear camera recording resolution",
                   "value_id": "7199630",
                   "value_name": "3840 px x 2160 px"
               },
               {
                   "id": "MAIN_FRONT_CAMERA_RESOLUTION",
                   "name": "Main front camera resolution",
                   "value_id": "7209628",
                   "value_name": "20 Mpx"
               },
               {
                   "id": "BATTERY_CAPACITY",
                   "name": "Battery capacity",
                   "value_id": "106671",
                   "value_name": "4500 mAh"
               },
               {
                   "id": "WITH_FINGERPRINT_READER",
                   "name": "With fingerprint reader",
                   "value_id": "242085",
                   "value_name": "Yes"
               },
               {
                   "id": "WITH_FACIAL_RECOGNITION",
                   "name": "With facial recognition",
                   "value_id": "242085",
                   "value_name": "Yes"
               },
               {
                   "id": "NUMBER_OF_SIM_CARD_SLOTS",
                   "name": "SIM card slots number",
                   "value_id": "2087802",
                   "value_name": "2"
               },
               {
                   "id": "SIM_SIZES",
                   "name": "Compatible SIM card sizes",
                   "value_id": "80453",
                   "value_name": "Nano-SIM"
               },
               {
                   "id": "WITH_ESIM",
                   "name": "With eSIM",
                   "value_id": "242084",
                   "value_name": "No"
               },
               {
                   "id": "OPERATING_SYSTEM_PERSONALIZATION_ORIGINAL_SHELL",
                   "name": "Operating system personalization original shell",
                   "value_id": "7410173",
                   "value_name": "MIUI 10"
               },
               {
                   "id": "OPERATING_SYSTEM_PERSONALIZATION_LAST_COMPATIBLE_SHELL",
                   "name": "Operating system personalization last compatible shell",
                   "value_id": "9189158",
                   "value_name": "MIUI 12"
               },
               {
                   "id": "RELEASE_YEAR",
                   "name": "Release year",
                   "value_id": "5057727",
                   "value_name": "2019"
               },
               {
                   "id": "WEIGHT",
                   "name": "Weight",
                   "value_id": "7863869",
                   "value_name": "199.8 g"
               },
               {
                   "id": "HEIGHT",
                   "name": "Height",
                   "value_id": "7863870",
                   "value_name": "161.35 mm"
               },
               {
                   "id": "WIDTH",
                   "name": "Width",
                   "value_id": "6964390",
                   "value_name": "76.4 mm"
               },
               {
                   "id": "DEPTH",
                   "name": "Depth",
                   "value_id": "7863877",
                   "value_name": "8.79 mm"
               },
               {
                   "id": "DISPLAY_TECHNOLOGY",
                   "name": "Display technology",
                   "value_id": "80490",
                   "value_name": "IPS"
               },
               {
                   "id": "DISPLAY_TYPE",
                   "name": "Display type",
                   "value_id": "9607915",
                   "value_name": "Dot Drop Display"
               },
               {
                   "id": "DISPLAY_ASPECT_RATIO",
                   "name": "Display aspect ratio",
                   "value_id": "9571055",
                   "value_name": "19.5 - 9"
               },
               {
                   "id": "DISPLAY_PIXELS_PER_INCH",
                   "name": "Pixels per inch",
                   "value_id": "7863871",
                   "value_name": "395 ppi"
               },
               {
                   "id": "DISPLAY_REFRESH_RATE",
                   "name": "Display refresh rate",
                   "value_id": "7873264",
                   "value_name": "60 Hz"
               },
               {
                   "id": "DISPLAY_MAX_BRIGHTNESS",
                   "name": "Display max brightness",
                   "value_id": "1160581",
                   "value_name": "500 cd/m²"
               },
               {
                   "id": "WITH_TOUCHSCREEN_DISPLAY",
                   "name": "With touchscreen display",
                   "value_id": "242085",
                   "value_name": "Yes"
               },
               {
                   "id": "WITH_PHYSICAL_QWERTY_KEYBOARD",
                   "name": "With physical QWERTY keyboard",
                   "value_id": "242084",
                   "value_name": "No"
               },
               {
                   "id": "WITH_CAMERA",
                   "name": "With camera",
                   "value_id": "242085",
                   "value_name": "Yes"
               },
               {
                   "id": "CAMERAS_MAIN_FEATURES",
                   "name": "Cameras main features",
                   "value_id": "",
                   "value_name": "64MP HD, Ultra nightscape mode, AI scene detection 5.0, Smart ultra-wide angle mode, Ultra wide-angle edge distortion correction, AI Beautify, Burst mode, Tilt-shift, Level display, Custom watermark, Pro mode, Portrait mode background blur adjustment, 3D "
               },
               {
                   "id": "REAR_CAMERAS_NUMBER",
                   "name": "Rear cameras number",
                   "value_id": "7505958",
                   "value_name": "4"
               },
               {
                   "id": "REAR_CAMERAS_RESOLUTION",
                   "name": "Rear cameras resolution",
                   "value_id": "7863878",
                   "value_name": "64 Mpx/8 Mpx/2 Mpx/2 Mpx"
               },
               {
                   "id": "REAR_CAMERA_APERTURE",
                   "name": "Rear camera aperture",
                   "value_id": "7863867",
                   "value_name": "f 1.9/f 2.2/f 2.4/f 2.4"
               },
               {
                   "id": "FRONT_CAMERAS_NUMBER",
                   "name": "Front cameras number",
                   "value_id": "7477216",
                   "value_name": "1"
               },
               {
                   "id": "FRONT_CAMERA_RECORDING_RESOLUTION",
                   "name": "Front camera recording resolution",
                   "value_id": "7173215",
                   "value_name": "1920 px x 1080 px"
               },
               {
                   "id": "FRONT_CAMERA_APERTURE",
                   "name": "Front camera aperture",
                   "value_id": "7408577",
                   "value_name": "f 2.0"
               },
               {
                   "id": "WITH_FRONT_CAMERA_FLASH",
                   "name": "With front camera flash",
                   "value_id": "242084",
                   "value_name": "No"
               },
               {
                   "id": "DIGITAL_ZOOM",
                   "name": "Digital zoom",
                   "value_id": "7199637",
                   "value_name": "10x"
               },
               {
                   "id": "MOBILE_NETWORK",
                   "name": "Network",
                   "value_id": "367876",
                   "value_name": "4G/LTE"
               },
               {
                   "id": "WITH_MEMORY_CARD_SLOT",
                   "name": "With memory card slot",
                   "value_id": "242085",
                   "value_name": "Yes"
               },
               {
                   "id": "MEMORY_CARD_TYPES",
                   "name": "Memory card types",
                   "value_id": "7199655",
                   "value_name": "MicroSD"
               },
               {
                   "id": "MAX_MEMORY_CARD_CAPACITY",
                   "name": "Max memory card capacity",
                   "value_id": "6901713",
                   "value_name": "512 GB"
               },
               {
                   "id": "PROCESSOR_MODEL",
                   "name": "Processor model",
                   "value_id": "7863868",
                   "value_name": "MediaTek Helio G90T"
               },
               {
                   "id": "CPU_MODELS",
                   "name": "CPU models",
                   "value_id": "",
                   "value_name": "2x2.05 GHz Cortex-A76, 6x2 GHz Cortex-A55"
               },
               {
                   "id": "PROCESSOR_CORES_NUMBER",
                   "name": "Processor cores number",
                   "value_id": "7206961",
                   "value_name": "8"
               },
               {
                   "id": "PROCESSOR_SPEED",
                   "name": "Processor speed",
                   "value_id": "7863876",
                   "value_name": "2.05 GHz"
               },
               {
                   "id": "GPU_MODEL",
                   "name": "GPU model",
                   "value_id": "7863875",
                   "value_name": "Mali-G76 MC4"
               },
               {
                   "id": "GPU_SPEED",
                   "name": "GPU speed",
                   "value_id": "8282451",
                   "value_name": "800 MHz"
               },
               {
                   "id": "CHARGE_CONNECTOR_TYPE",
                   "name": "Charge connector type",
                   "value_id": "8275367",
                   "value_name": "USB-C"
               },
               {
                   "id": "WITH_USB_CONNECTOR",
                   "name": "With USB connector",
                   "value_id": "242085",
                   "value_name": "Yes"
               },
               {
                   "id": "WITH_3_5_JACK",
                   "name": "With 3.5 jack",
                   "value_id": "242085",
                   "value_name": "Yes"
               },
               {
                   "id": "WITH_WIFI",
                   "name": "With Wi-Fi",
                   "value_id": "242085",
                   "value_name": "Yes"
               },
               {
                   "id": "WITH_GPS",
                   "name": "With GPS",
                   "value_id": "242085",
                   "value_name": "Yes"
               },
               {
                   "id": "WITH_BLUETOOTH",
                   "name": "With Bluetooth",
                   "value_id": "242085",
                   "value_name": "Yes"
               },
               {
                   "id": "WITH_NFC",
                   "name": "With NFC",
                   "value_id": "242085",
                   "value_name": "Yes"
               },
               {
                   "id": "WITH_MINI_HDMI",
                   "name": "With mini HDMI",
                   "value_id": "242084",
                   "value_name": "No"
               },
               {
                   "id": "WITH_RADIO",
                   "name": "With radio",
                   "value_id": "242085",
                   "value_name": "Yes"
               },
               {
                   "id": "WITH_TV_TUNER",
                   "name": "With TV tuner",
                   "value_id": "242084",
                   "value_name": "No"
               },
               {
                   "id": "WITH_IRIS_RECOGNITION",
                   "name": "With iris recognition",
                   "value_id": "242084",
                   "value_name": "No"
               },
               {
                   "id": "WITH_ACCELEROMETER",
                   "name": "With accelerometer",
                   "value_id": "242085",
                   "value_name": "Yes"
               },
               {
                   "id": "WITH_PROXIMITY_SENSOR",
                   "name": "With proximity sensor",
                   "value_id": "242085",
                   "value_name": "Yes"
               },
               {
                   "id": "WITH_GYROSCOPE",
                   "name": "With gyroscope",
                   "value_id": "242085",
                   "value_name": "Yes"
               },
               {
                   "id": "WITH_COMPASS",
                   "name": "With compass",
                   "value_id": "242085",
                   "value_name": "Yes"
               },
               {
                   "id": "WITH_BAROMETER",
                   "name": "With barometer",
                   "value_id": "242084",
                   "value_name": "No"
               },
               {
                   "id": "WITH_HEART_RATE_SENSOR",
                   "name": "With heart rate sensor",
                   "value_id": "242084",
                   "value_name": "No"
               },
               {
                   "id": "IS_SPLASH_RESISTANT",
                   "name": "Is splash resistant",
                   "value_id": "242084",
                   "value_name": "No"
               },
               {
                   "id": "IS_WATER_RESISTANT",
                   "name": "Is water resistant",
                   "value_id": "242084",
                   "value_name": "No"
               },
               {
                   "id": "IS_WATERPROOF",
                   "name": "Is waterproof",
                   "value_id": "242084",
                   "value_name": "No"
               },
               {
                   "id": "IS_DUST_RESISTANT",
                   "name": "Is dust resistant",
                   "value_id": "242084",
                   "value_name": "No"
               },
               {
                   "id": "BATTERY_TYPE",
                   "name": "Battery type",
                   "value_id": "7573636",
                   "value_name": "Lithium polymer"
               },
               {
                   "id": "WITH_FAST_CHARGING",
                   "name": "With fast charging",
                   "value_id": "242085",
                   "value_name": "Yes"
               },
               {
                   "id": "WITH_WIRELESS_CHARGING",
                   "name": "With wireless charging",
                   "value_id": "242084",
                   "value_name": "No"
               },
               {
                   "id": "WITH_REMOVABLE_BATTERY",
                   "name": "With removable battery",
                   "value_id": "242084",
                   "value_name": "No"
               }
           ],
           "pictures": [
               {
                   "id": "913045-MLA40439594053_012020",
                   "url": "https://mla-s2-p.mlstatic.com/913045-MLA40439594053_012020-F.jpg"
               },
               {
                   "id": "776667-MLA40439594078_012020",
                   "url": "https://mla-s2-p.mlstatic.com/776667-MLA40439594078_012020-F.jpg"
               },
               {
                   "id": "753973-MLA40439594094_012020",
                   "url": "https://mla-s1-p.mlstatic.com/753973-MLA40439594094_012020-F.jpg"
               },
               {
                   "id": "965222-MLA40439594093_012020",
                   "url": "https://mla-s2-p.mlstatic.com/965222-MLA40439594093_012020-F.jpg"
               },
               {
                   "id": "929508-MLA40439008858_012020",
                   "url": "https://mla-s2-p.mlstatic.com/929508-MLA40439008858_012020-F.jpg"
               },
               {
                   "id": "700774-MLA40439594043_012020",
                   "url": "https://mla-s2-p.mlstatic.com/700774-MLA40439594043_012020-F.jpg"
               }
           ]
       }
   ]
}
```

Request with **q parameter** example:

  

If you want to split terms you must use %20 which corresponds to ASCII
code.

  

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/marketplace/products/search?q=vacuum%20wireless
```

Request **full parameters** example:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/marketplace/products/search?q=vacuum%20wireless&limit=100&product_identifier=06971664930214&status=inactive&offset=10'
```

Response:

``` language-javascript
{
    "id": "CBT21031553",
    "status": "active",
    "domain_id": "CBT-VACUUM_AND_STEAM_CLEANERS",
    "settings": {
        "listing_strategy": "open"
    },
    "name": "Makita Hepa DVC261ZX11 2 L - Turquoise - 18V - 60 Hz",
    "main_features": [],
    "attributes": [
        {
            "id": "BRAND",
            "name": "Brand",
            "value_id": "104585",
            "value_name": "Makita"
        },
    ],
    "pictures": [
        {
            "id": "812833-MLM45394284850_032021",
            "url": "https://http2.mlstatic.com/D_NQ_NP_812833-MLM45394284850_032021-F.jpg"
        }
    ],
    "marketplaces": {
        "active": [
            "MLM"
        ],
        "inactive": [
            "MCO",
            "MLC"
        ],
        "not_available": [
            "MLB"
        ]
    }
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

Marketplaces field refers to marketplaces status for a cbt product in
local marketplaces.

</div>

</div>

</div>

</div>

## Error

| Http Code | Error                | Message                                    | Description                                        |
|-----------|----------------------|--------------------------------------------|----------------------------------------------------|
|           |                      |                                            |                                                    |
| 400       | query\_params\_error | params error, check dev site documentation | Query params are not valid to perform the request. |

  

## Determine the product to sell

For an item to be published in the catalog and purchased, it must be
associated with a sufficiently specific product such that the buyer can
know precisely what they are buying and for which Mercado Libre has
created the content (products with status= active in the
resource/products/{product\_id}).

  

## Product by ID

Once the product has been identified within the domain, you can find out
the main characteristics with of global and marketplace products.

Request:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/products/$PRODUCT_ID
```

Example with global id:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/products/CBT15239253
```

Response:

``` language-javascript
 
{
    "id": "CBT15239253",
    "status": "inactive",
    "sold_quantity": 0,
    "domain_id": "CBT-CELLPHONES",
    "permalink": "",
    "name": "Xiaomi Redmi Note 8 Pro",
    "buy_box_winner": null,
    "pickers": null,
    "pictures": null,
    "main_features": null,
    "attributes": [
        {
            "id": "BRAND",
            "name": "Brand",
            "value_id": "59387",
            "value_name": "Xiaomi",
            "values": [
                {
                    "id": "59387",
                    "name": "Xiaomi"
                }
            ]
        }
    ],
    "short_description": {
        "type": "",
        "content": ""
    },
    "parent_id": null,
    "children_ids": [
        "CBT15239254",
        "CBT15239255",
        "CBT15239256"
    ],
    "settings": {
        "listing_strategy": "open"
    }
}
```

### Considerations

-   Then, you can use the attributes obtained from marketplace products
    to create professional quality listings.
-   When the product has **status:inactive** the **pictures**,
    **pickers** and **main\_features** fields will come with null. And
    the fields inside **short\_description** come empty.

<div class="andes-message andes-message--highlight">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--highlight site-carriers__message-title">

Important:

</div>

<div class="andes-message__text--highlight site-carriers__message-text">

<div>

The catalog publication content is provided by Mercado Libre. Therefore,
the seller is responsible for confirming that the product to be
associated matches the specific characteristics displayed on the
platform.  
In the event that there is a difference between what the user buys and
the associated product, it is possible that claims and/or cancellations
are generated that will negatively impact their reputation and as a
consequence of this the disqualification to publish in the catalog,
eventually leading to account suspension.

</div>

</div>

</div>

</div>

  

## Parents and children products

In many domains there are two levels of products:

**Superior level products (parents)** that group specific products and
are not in themselves suitable to be purchased. Example: Motorola Moto
G6. This doesn´t have the capacity or color specified.  
**Terminal level products (children)** sufficiently specified to be
purchased. Example: Motorola G6 32GB índigo oscuro.

Example of a parent product (it is not specific and cannot be
purchased):

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/products/CBT15239253
```

Response:

``` language-javascript
{
    "id": "CBT15239253",
    "status": "inactive",
    "sold_quantity": 0,
    "domain_id": "CBT-CELLPHONES",
    "permalink": "",
    "name": "Xiaomi Redmi Note 8 Pro",
    "buy_box_winner": null,
    "pickers": null,
    "pictures": null,
    "main_features": null,
    "attributes": [
        {
            "id": "BRAND",
            "name": "Brand",
            "value_id": "59387",
            "value_name": "Xiaomi",
            "values": [
                {
                    "id": "59387",
                    "name": "Xiaomi"
                }
            ]
        }
    ],
    "short_description": {
        "type": "",
        "content": ""
    },
    "parent_id": null,
    "children_ids": [
        "CBT15239254",
        "CBT15239255",
        "CBT15239256"
    ],
    "settings": {
        "listing_strategy": "open"
    }
}
```

Example of a children product (specific and can be used to publish and
buy if active):

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/products/CBT15239254
```

Response:

``` language-javascript
{
    "id": "CBT15239254",
    "status": "active",
    "sold_quantity": 0,
    "domain_id": "CBT-CELLPHONES",
    "permalink": "",
    "name": "Xiaomi Redmi Note 8 Pro - Mineral grey - 64 GB - 6 GB",
    "buy_box_winner": null,
    "pickers": null,
    "pictures": [
        {
            "id": "895078-MLA40022201260_122019",
            "url": "https://mla-s2-p.mlstatic.com/895078-MLA40022201260_122019-F.jpg",
            "suggested_for_picker": [],
            "max_width": 661,
            "max_height": 1326
        }
    ],
    "main_features": null,
    "attributes": [
        {
            "id": "BRAND",
            "name": "Brand",
            "value_id": "59387",
            "value_name": "Xiaomi",
            "values": [
                {
                    "id": "59387",
                    "name": "Xiaomi"
                }
            ]
        }
    ],
    "short_description": {
        "type": "",
        "content": ""
    },
    "parent_id": "CBT15239253",
    "children_ids": [],
    "settings": {
        "listing_strategy": "open"
    }
}
```

What interests us for the purposes of publishing is:

**children\_ids**

-   If the field is empty it is a children product which is specific
    enough to publish.
-   If this array contains IDs of other products, it means that the
    current catalog\_product\_id corresponds to a parent product (not
    fully specified). To list in the catalog we must look for the
    specific product among its children\_ids.

**status**

-   In order to create a catalog publication, the product must have
    **status=active**.
-   The **parent** products never will have **status=active** because
    they are not comparable.

**Next**: [Catalog
listing](https://global-selling.mercadolibre.com/devsite/catalog-listing-gs).

</div>
