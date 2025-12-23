# Listing JSON (derived from item page)

Source URL: https://www.mercadolibre.com.mx/moto-e15-dual-sim-64-gb-azul-acero-2-gb-ram/p/MLM49750290

Extracted fields (from embedded Product JSON + HTML):
- title: Moto E15 Dual SIM 64 GB azul acero 2 GB RAM
- brand: Motorola
- sku: MLM49750290
- price: 1392 MXN
- category_id: MLM1055
- listing_type_id: gold_special
- available_quantity: 6
- dimensions: height=16.567 cm, width=7.598 cm, weight=192 g
- pictures (sample): 6

Listing payload JSON (marketplace /items style):
```json
{
  "title": "Moto E15 Dual SIM 64 GB azul acero 2 GB RAM",
  "category_id": "MLM1055",
  "price": 1392,
  "currency_id": "MXN",
  "available_quantity": 6,
  "buying_mode": "buy_it_now",
  "listing_type_id": "gold_special",
  "condition": "new",
  "description": {
    "plain_text": "Memoria RAM: 2 GB. | Dispositivo liberado para que elijas la compañía telefónica que prefieras. | Pantalla LTPS de 6.7\". | Cámara delantera de 8Mpx. | Batería de 5.2 Ah. | Memoria interna de 64GB.  | Resistente a las salpicaduras."
  },
  "pictures": [
    {
      "source": "https://http2.mlstatic.com/D_NQ_NP_814961-MLA100058624587_122025-O.webp"
    },
    {
      "source": "https://http2.mlstatic.com/D_NQ_NP_786456-MLA91655001704_092025-O.webp"
    },
    {
      "source": "https://http2.mlstatic.com/D_NQ_NP_849600-MLA84615186435_052025-O.webp"
    },
    {
      "source": "https://http2.mlstatic.com/D_NQ_NP_938274-MLA84615186447_052025-O.webp"
    },
    {
      "source": "https://http2.mlstatic.com/D_NQ_NP_876968-MLA84317871558_052025-O.webp"
    },
    {
      "source": "https://http2.mlstatic.com/D_NQ_NP_682663-MLA84615062093_052025-O.webp"
    }
  ],
  "attributes": [
    {
      "id": "BRAND",
      "value_name": "Motorola"
    },
    {
      "id": "MODEL",
      "value_name": "Moto E15"
    },
    {
      "id": "ITEM_CONDITION",
      "value_name": "New"
    },
    {
      "id": "SELLER_SKU",
      "value_name": "MLM49750290"
    },
    {
      "id": "PACKAGE_HEIGHT",
      "value_name": "16.567 cm"
    },
    {
      "id": "PACKAGE_WIDTH",
      "value_name": "7.598 cm"
    },
    {
      "id": "PACKAGE_WEIGHT",
      "value_name": "192 g"
    },
    {
      "id": "PACKAGE_LENGTH",
      "value_name": "TBD"
    }
  ]
}
```

Notes:
- PACKAGE_LENGTH is not present on the page; keep as TBD and replace with real package length before API call.
- ITEM_CONDITION is assumed to be New based on typical catalog product state; confirm with actual item API if needed.
- If you need Global Selling JSON (/global/items), adjust currency to USD and add sites_to_sell.
