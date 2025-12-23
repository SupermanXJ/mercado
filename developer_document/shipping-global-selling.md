<div class="inner-content">

# Shipping

<div class="details__message">

This examples will guide you through shipping resources.

</div>

<table class="andes-table">
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead class="andes-table__head">
<tr class="header andes-table__row">
<th class="andes-table__header andes-table__header--left">Resource</th>
<th class="andes-table__header andes-table__header--left">Description</th>
<th class="andes-table__header andes-table__header--left">Example</th>
</tr>
</thead>
<tbody class="andes-table__body">
<tr class="odd andes-table__row">
<td class="andes-table__column andes-table__column--left"><strong>/marketplace/shipments/$SHIPMENT_ID</strong></td>
<td class="andes-table__column andes-table__column--left">Retrieves all delivery data.</td>
<td class="andes-table__column andes-table__column--left"><a href="#modal1">GET</a>
<div id="modal1" class="modalmask">
<div class="modalbox movedown">
<a href="#close" class="go-back">Go back.</a> <a href="#close" class="close" title="Close">X</a>
<h3 id="retrieves-all-delivery-data.">Retrieves all delivery data.</h3>
<pre class="language-javascript details__code-terminal-json"><code>curl -X GET -H &#39;Authorization: Bearer $ACCESS_TOKEN&#39; http://api.mercadolibre.com/marketplace/shipments/28254144429</code></pre>
 
<h3 id="response">Response</h3>
<pre class="language-javascript details__code-terminal-json"><code>{
    &quot;id&quot;: 28254144429,
    &quot;order_id&quot;: 2328110827,
    &quot;site_id&quot;: &quot;MLM&quot;,
    &quot;status&quot;: &quot;delivered&quot;,
    &quot;substatus&quot;: &quot;&quot;,
    &quot;date_created&quot;: &quot;2020-02-17T09:45:37.000-04:00&quot;,
    &quot;last_updated&quot;: &quot;2020-04-09T08:00:27.000-04:00&quot;,
    &quot;tracking_number&quot;: &quot;String&quot;,
    &quot;tracking_method&quot;: &quot;CBT CustomShipping&quot;,
    &quot;sender_id&quot;: 523132944,
    &quot;receiver_id&quot;: 441782523,
    &quot;receiver_address&quot;: {
        &quot;id&quot;: 1061239068,
        &quot;address_line&quot;: &quot;AV LAS ROSAS 1235&quot;,
        &quot;street_name&quot;: &quot;AV LAS ROSAS&quot;,
        &quot;street_number&quot;: &quot;1235&quot;,
        &quot;comment&quot;: &quot;Referencia: PUERTA ROJA, VENTANA VERDE, TIMBRE 3&quot;,
        &quot;zip_code&quot;: &quot;45200&quot;,
        &quot;city&quot;: {
            &quot;id&quot;: &quot;TUxNQ1pBUDM4NzE&quot;,
            &quot;name&quot;: &quot;Zapopan&quot;
        },
        &quot;state&quot;: {
            &quot;id&quot;: &quot;MX-JAL&quot;,
            &quot;name&quot;: &quot;Jalisco&quot;
        },
        &quot;country&quot;: {
            &quot;id&quot;: &quot;MX&quot;,
            &quot;name&quot;: &quot;Mexico&quot;
        },
        &quot;neighborhood&quot;: {
            &quot;id&quot;: null,
            &quot;name&quot;: &quot;Colonia Altamira&quot;
        },
        &quot;municipality&quot;: {
            &quot;id&quot;: null,
            &quot;name&quot;: null
        },
        &quot;agency&quot;: null,
        &quot;types&quot;: null,
        &quot;latitude&quot;: 20.665695,
        &quot;longitude&quot;: -103.402469,
        &quot;geolocation_type&quot;: &quot;RANGE_INTERPOLATED&quot;,
        &quot;geolocation_last_updated&quot;: &quot;2020-02-06T15:17:24Z&quot;,
        &quot;geolocation_source&quot;: &quot;google-maps&quot;,
        &quot;receiver_name&quot;: &quot;Pedro Funes&quot;,
        &quot;receiver_phone&quot;: &quot;123123123123&quot;
    },
    &quot;shipping_items&quot;: [
        {
            &quot;id&quot;: &quot;MLM755638064&quot;,
            &quot;description&quot;: &quot;Elemento De Prueba - Para Pruebas De Carga&quot;,
            &quot;quantity&quot;: 1,
            &quot;dimensions&quot;: &quot;10.0x10.0x10.0,318.0&quot;
        }
    ],
    &quot;date_first_printed&quot;: &quot;&quot;,
    &quot;logistic_type&quot;: &quot;default&quot;
}</code></pre>
<a href="https://global-selling.mercadolibre.com/devsite/manage-shipments">Learn more.</a>
</div>
</div></td>
</tr>
<tr class="even andes-table__row">
<td class="andes-table__column andes-table__column--left"><strong>/sites/$SITE_ID/shipping_methods</strong></td>
<td class="andes-table__column andes-table__column--left">Retrieves shipping modes available in a country.</td>
<td class="andes-table__column andes-table__column--left"><a href="#modal2">GET</a>
<div id="modal2" class="modalmask">
<div class="modalbox movedown">
<a href="#close" class="go-back">Go back</a> <a href="#close" class="close" title="Close">X</a>
<h3 id="retrieves-shipping-modes-available-in-a-country.">Retrieves shipping modes available in a country.</h3>
<pre class="language-javascript details__code-terminal-json"><code>curl -X GET -H &#39;Authorization: Bearer $ACCESS_TOKEN&#39; http://api.mercadolibre.com/sites/MLM/shipping_methods</code></pre>
 
<h3 id="response-1">Response</h3>
<pre class="language-javascript details__code-terminal-json"><code>[
    {
        &quot;id&quot;: 509245,
        &quot;name&quot;: &quot;Next Day Agency&quot;,
        &quot;type&quot;: &quot;next_day&quot;,
        &quot;deliver_to&quot;: &quot;agency&quot;,
        &quot;status&quot;: &quot;active&quot;,
        &quot;site_id&quot;: &quot;MLM&quot;,
        &quot;free_options&quot;: [],
        &quot;shipping_modes&quot;: [
            &quot;me2&quot;
        ],
        &quot;company_id&quot;: null,
        &quot;company_name&quot;: null,
        &quot;min_time&quot;: 24,
        &quot;max_time&quot;: 24,
        &quot;currency_id&quot;: &quot;MXN&quot;
    },
    {
        &quot;id&quot;: 509247,
        &quot;name&quot;: &quot;Three Days&quot;,
        &quot;type&quot;: &quot;three_days&quot;,
        &quot;deliver_to&quot;: &quot;address&quot;,
        &quot;status&quot;: &quot;active&quot;,
        &quot;site_id&quot;: &quot;MLM&quot;,
        &quot;free_options&quot;: [],
        &quot;shipping_modes&quot;: [
            &quot;me2&quot;
        ],
        &quot;company_id&quot;: null,
        &quot;company_name&quot;: null,
        &quot;min_time&quot;: 72,
        &quot;max_time&quot;: 72,
        &quot;currency_id&quot;: &quot;MXN&quot;
    },
    {
        &quot;id&quot;: 502245,
        &quot;name&quot;: &quot;Envío internacional&quot;,
        &quot;type&quot;: &quot;standard&quot;,
        &quot;deliver_to&quot;: &quot;address&quot;,
        &quot;status&quot;: &quot;active&quot;,
        &quot;site_id&quot;: &quot;MLM&quot;,
        &quot;free_options&quot;: [],
        &quot;shipping_modes&quot;: [
            &quot;me1&quot;
        ],
        &quot;company_id&quot;: 17501140,
        &quot;company_name&quot;: &quot;CBT México&quot;,
        &quot;min_time&quot;: null,
        &quot;max_time&quot;: null,
        &quot;currency_id&quot;: &quot;MXN&quot;
    },
    {
        &quot;id&quot;: 504745,
        &quot;name&quot;: &quot;Estándar a sucursal de correo&quot;,
        &quot;type&quot;: &quot;standard&quot;,
        &quot;deliver_to&quot;: &quot;agency&quot;,
        &quot;status&quot;: &quot;active&quot;,
        &quot;site_id&quot;: &quot;MLM&quot;,
        &quot;free_options&quot;: [
            &quot;no&quot;
        ],
        &quot;shipping_modes&quot;: [
            &quot;me2&quot;
        ],
        &quot;company_id&quot;: 17502340,
        &quot;company_name&quot;: &quot;Mercado Envios&quot;,
        &quot;min_time&quot;: null,
        &quot;max_time&quot;: null,
        &quot;currency_id&quot;: &quot;MXN&quot;
    },
    {
        &quot;id&quot;: 507845,
        &quot;name&quot;: &quot;Prioritario a sucursal de correo&quot;,
        &quot;type&quot;: &quot;same_day&quot;,
        &quot;deliver_to&quot;: &quot;agency&quot;,
        &quot;status&quot;: &quot;active&quot;,
        &quot;site_id&quot;: &quot;MLM&quot;,
        &quot;free_options&quot;: [],
        &quot;shipping_modes&quot;: [
            &quot;me2&quot;
        ],
        &quot;company_id&quot;: null,
        &quot;company_name&quot;: null,
        &quot;min_time&quot;: 0,
        &quot;max_time&quot;: 24,
        &quot;currency_id&quot;: &quot;MXN&quot;
    },
    {
        &quot;id&quot;: 509246,
        &quot;name&quot;: &quot;Two Days Agency&quot;,
        &quot;type&quot;: &quot;two_days&quot;,
        &quot;deliver_to&quot;: &quot;agency&quot;,
        &quot;status&quot;: &quot;active&quot;,
        &quot;site_id&quot;: &quot;MLM&quot;,
        &quot;free_options&quot;: [],
        &quot;shipping_modes&quot;: [
            &quot;me2&quot;
        ],
        &quot;company_id&quot;: null,
        &quot;company_name&quot;: null,
        &quot;min_time&quot;: 48,
        &quot;max_time&quot;: 48,
        &quot;currency_id&quot;: &quot;MXN&quot;
    },
    {
        &quot;id&quot;: 504045,
        &quot;name&quot;: &quot;Prioritario a domicilio&quot;,
        &quot;type&quot;: &quot;same_day&quot;,
        &quot;deliver_to&quot;: &quot;address&quot;,
        &quot;status&quot;: &quot;active&quot;,
        &quot;site_id&quot;: &quot;MLM&quot;,
        &quot;free_options&quot;: [
            &quot;country&quot;
        ],
        &quot;shipping_modes&quot;: [
            &quot;me2&quot;
        ],
        &quot;company_id&quot;: 17501740,
        &quot;company_name&quot;: &quot;99minutos&quot;,
        &quot;min_time&quot;: null,
        &quot;max_time&quot;: null,
        &quot;currency_id&quot;: &quot;MXN&quot;
    },
    {
        &quot;id&quot;: 501345,
        &quot;name&quot;: &quot;Express a domicilio&quot;,
        &quot;type&quot;: &quot;express&quot;,
        &quot;deliver_to&quot;: &quot;address&quot;,
        &quot;status&quot;: &quot;active&quot;,
        &quot;site_id&quot;: &quot;MLM&quot;,
        &quot;free_options&quot;: [
            &quot;country&quot;
        ],
        &quot;shipping_modes&quot;: [
            &quot;me2&quot;
        ],
        &quot;company_id&quot;: 17500540,
        &quot;company_name&quot;: &quot;DHL&quot;,
        &quot;min_time&quot;: 0,
        &quot;max_time&quot;: 72,
        &quot;currency_id&quot;: &quot;MXN&quot;
    },
    {
        &quot;id&quot;: 501645,
        &quot;name&quot;: &quot;Envío internacional&quot;,
        &quot;type&quot;: &quot;standard&quot;,
        &quot;deliver_to&quot;: &quot;address&quot;,
        &quot;status&quot;: &quot;active&quot;,
        &quot;site_id&quot;: &quot;MLM&quot;,
        &quot;free_options&quot;: [
            &quot;country&quot;
        ],
        &quot;shipping_modes&quot;: [
            &quot;me1&quot;
        ],
        &quot;company_id&quot;: 17501140,
        &quot;company_name&quot;: &quot;CBT México&quot;,
        &quot;min_time&quot;: null,
        &quot;max_time&quot;: null,
        &quot;currency_id&quot;: &quot;MXN&quot;
    },
    {
        &quot;id&quot;: 504645,
        &quot;name&quot;: &quot;Express a sucursal de correo&quot;,
        &quot;type&quot;: &quot;express&quot;,
        &quot;deliver_to&quot;: &quot;agency&quot;,
        &quot;status&quot;: &quot;active&quot;,
        &quot;site_id&quot;: &quot;MLM&quot;,
        &quot;free_options&quot;: [
            &quot;no&quot;
        ],
        &quot;shipping_modes&quot;: [
            &quot;me2&quot;
        ],
        &quot;company_id&quot;: 17502340,
        &quot;company_name&quot;: &quot;Mercado Envios&quot;,
        &quot;min_time&quot;: null,
        &quot;max_time&quot;: null,
        &quot;currency_id&quot;: &quot;MXN&quot;
    },
    {
        &quot;id&quot;: 507745,
        &quot;name&quot;: &quot;Prioritario a sucursal de correo&quot;,
        &quot;type&quot;: &quot;same_day&quot;,
        &quot;deliver_to&quot;: &quot;agency&quot;,
        &quot;status&quot;: &quot;active&quot;,
        &quot;site_id&quot;: &quot;MLM&quot;,
        &quot;free_options&quot;: [],
        &quot;shipping_modes&quot;: [
            &quot;me2&quot;
        ],
        &quot;company_id&quot;: 17501740,
        &quot;company_name&quot;: &quot;99minutos&quot;,
        &quot;min_time&quot;: null,
        &quot;max_time&quot;: null,
        &quot;currency_id&quot;: &quot;MXN&quot;
    },
    {
        &quot;id&quot;: 509445,
        &quot;name&quot;: &quot;Three Days Agency&quot;,
        &quot;type&quot;: &quot;three_days&quot;,
        &quot;deliver_to&quot;: &quot;agency&quot;,
        &quot;status&quot;: &quot;active&quot;,
        &quot;site_id&quot;: &quot;MLM&quot;,
        &quot;free_options&quot;: [],
        &quot;shipping_modes&quot;: [
            &quot;me2&quot;
        ],
        &quot;company_id&quot;: null,
        &quot;company_name&quot;: null,
        &quot;min_time&quot;: 72,
        &quot;max_time&quot;: 72,
        &quot;currency_id&quot;: &quot;MXN&quot;
    },
    {
        &quot;id&quot;: 509450,
        &quot;name&quot;: &quot;Normal&quot;,
        &quot;type&quot;: &quot;standard&quot;,
        &quot;deliver_to&quot;: &quot;address&quot;,
        &quot;status&quot;: &quot;active&quot;,
        &quot;site_id&quot;: &quot;MLM&quot;,
        &quot;free_options&quot;: [],
        &quot;shipping_modes&quot;: [
            &quot;me2&quot;
        ],
        &quot;company_id&quot;: null,
        &quot;company_name&quot;: null,
        &quot;min_time&quot;: 96,
        &quot;max_time&quot;: 2400,
        &quot;currency_id&quot;: &quot;MXN&quot;
    },
    {
        &quot;id&quot;: 509446,
        &quot;name&quot;: &quot;Four Days&quot;,
        &quot;type&quot;: &quot;four_days&quot;,
        &quot;deliver_to&quot;: &quot;address&quot;,
        &quot;status&quot;: &quot;active&quot;,
        &quot;site_id&quot;: &quot;MLM&quot;,
        &quot;free_options&quot;: [],
        &quot;shipping_modes&quot;: [
            &quot;me2&quot;
        ],
        &quot;company_id&quot;: null,
        &quot;company_name&quot;: null,
        &quot;min_time&quot;: 96,
        &quot;max_time&quot;: 96,
        &quot;currency_id&quot;: &quot;MXN&quot;
    },
    {
        &quot;id&quot;: 509449,
        &quot;name&quot;: &quot;Express Agency&quot;,
        &quot;type&quot;: &quot;express&quot;,
        &quot;deliver_to&quot;: &quot;agency&quot;,
        &quot;status&quot;: &quot;active&quot;,
        &quot;site_id&quot;: &quot;MLM&quot;,
        &quot;free_options&quot;: [],
        &quot;shipping_modes&quot;: [
            &quot;me2&quot;
        ],
        &quot;company_id&quot;: null,
        &quot;company_name&quot;: null,
        &quot;min_time&quot;: 48,
        &quot;max_time&quot;: 72,
        &quot;currency_id&quot;: &quot;MXN&quot;
    },
    {
        &quot;id&quot;: 509145,
        &quot;name&quot;: &quot;Next Day&quot;,
        &quot;type&quot;: &quot;next_day&quot;,
        &quot;deliver_to&quot;: &quot;address&quot;,
        &quot;status&quot;: &quot;active&quot;,
        &quot;site_id&quot;: &quot;MLM&quot;,
        &quot;free_options&quot;: [],
        &quot;shipping_modes&quot;: [
            &quot;me2&quot;
        ],
        &quot;company_id&quot;: null,
        &quot;company_name&quot;: null,
        &quot;min_time&quot;: 24,
        &quot;max_time&quot;: 24,
        &quot;currency_id&quot;: &quot;MXN&quot;
    },
    {
        &quot;id&quot;: 509448,
        &quot;name&quot;: &quot;Express&quot;,
        &quot;type&quot;: &quot;express&quot;,
        &quot;deliver_to&quot;: &quot;address&quot;,
        &quot;status&quot;: &quot;active&quot;,
        &quot;site_id&quot;: &quot;MLM&quot;,
        &quot;free_options&quot;: [],
        &quot;shipping_modes&quot;: [
            &quot;me2&quot;
        ],
        &quot;company_id&quot;: null,
        &quot;company_name&quot;: null,
        &quot;min_time&quot;: 48,
        &quot;max_time&quot;: 72,
        &quot;currency_id&quot;: &quot;MXN&quot;
    },
    {
        &quot;id&quot;: 509545,
        &quot;name&quot;: &quot;Normal Agency&quot;,
        &quot;type&quot;: &quot;standard&quot;,
        &quot;deliver_to&quot;: &quot;agency&quot;,
        &quot;status&quot;: &quot;active&quot;,
        &quot;site_id&quot;: &quot;MLM&quot;,
        &quot;free_options&quot;: [],
        &quot;shipping_modes&quot;: [
            &quot;me2&quot;
        ],
        &quot;company_id&quot;: null,
        &quot;company_name&quot;: null,
        &quot;min_time&quot;: 96,
        &quot;max_time&quot;: 2400,
        &quot;currency_id&quot;: &quot;MXN&quot;
    },
    {
        &quot;id&quot;: 509447,
        &quot;name&quot;: &quot;Four Days Agency&quot;,
        &quot;type&quot;: &quot;four_days&quot;,
        &quot;deliver_to&quot;: &quot;agency&quot;,
        &quot;status&quot;: &quot;active&quot;,
        &quot;site_id&quot;: &quot;MLM&quot;,
        &quot;free_options&quot;: [],
        &quot;shipping_modes&quot;: [
            &quot;me2&quot;
        ],
        &quot;company_id&quot;: null,
        &quot;company_name&quot;: null,
        &quot;min_time&quot;: 96,
        &quot;max_time&quot;: 96,
        &quot;currency_id&quot;: &quot;MXN&quot;
    },
    {
        &quot;id&quot;: 501845,
        &quot;name&quot;: &quot;Estándar&quot;,
        &quot;type&quot;: &quot;standard&quot;,
        &quot;deliver_to&quot;: &quot;address&quot;,
        &quot;status&quot;: &quot;active&quot;,
        &quot;site_id&quot;: &quot;MLM&quot;,
        &quot;free_options&quot;: [
            &quot;country&quot;
        ],
        &quot;shipping_modes&quot;: [
            &quot;me1&quot;
        ],
        &quot;company_id&quot;: null,
        &quot;company_name&quot;: null,
        &quot;min_time&quot;: null,
        &quot;max_time&quot;: null,
        &quot;currency_id&quot;: &quot;MXN&quot;
    },
    {
        &quot;id&quot;: 501846,
        &quot;name&quot;: &quot;Express&quot;,
        &quot;type&quot;: &quot;express&quot;,
        &quot;deliver_to&quot;: &quot;address&quot;,
        &quot;status&quot;: &quot;active&quot;,
        &quot;site_id&quot;: &quot;MLM&quot;,
        &quot;free_options&quot;: [
            &quot;country&quot;
        ],
        &quot;shipping_modes&quot;: [
            &quot;me1&quot;
        ],
        &quot;company_id&quot;: null,
        &quot;company_name&quot;: null,
        &quot;min_time&quot;: null,
        &quot;max_time&quot;: null,
        &quot;currency_id&quot;: &quot;MXN&quot;
    },
    {
        &quot;id&quot;: 501245,
        &quot;name&quot;: &quot;Estándar a domicilio&quot;,
        &quot;type&quot;: &quot;standard&quot;,
        &quot;deliver_to&quot;: &quot;address&quot;,
        &quot;status&quot;: &quot;active&quot;,
        &quot;site_id&quot;: &quot;MLM&quot;,
        &quot;free_options&quot;: [
            &quot;country&quot;
        ],
        &quot;shipping_modes&quot;: [
            &quot;me2&quot;
        ],
        &quot;company_id&quot;: 17500540,
        &quot;company_name&quot;: &quot;DHL&quot;,
        &quot;min_time&quot;: 72,
        &quot;max_time&quot;: null,
        &quot;currency_id&quot;: &quot;MXN&quot;
    },
    {
        &quot;id&quot;: 509345,
        &quot;name&quot;: &quot;Two Days&quot;,
        &quot;type&quot;: &quot;two_days&quot;,
        &quot;deliver_to&quot;: &quot;address&quot;,
        &quot;status&quot;: &quot;active&quot;,
        &quot;site_id&quot;: &quot;MLM&quot;,
        &quot;free_options&quot;: [],
        &quot;shipping_modes&quot;: [
            &quot;me2&quot;
        ],
        &quot;company_id&quot;: null,
        &quot;company_name&quot;: null,
        &quot;min_time&quot;: 48,
        &quot;max_time&quot;: 48,
        &quot;currency_id&quot;: &quot;MXN&quot;
    }
]</code></pre>
<a href="https://global-selling.mercadolibre.com/devsite/manage-shipments">Learn more.</a>
</div>
</div></td>
</tr>
<tr class="odd andes-table__row">
<td class="andes-table__column andes-table__column--left"><strong>/sites/$SITE_ID/shipping_options?zip_code_from=$ZIP_CODE&amp;zip_code_to=$ZIP_CODE&amp;dimensions=$DIMENSIONS</strong></td>
<td class="andes-table__column andes-table__column--left">Retrieves the cost of a shipping. Shipping cost calculator per country.</td>
<td class="andes-table__column andes-table__column--left"><a href="#modal3">GET</a>
<div id="modal3" class="modalmask">
<div class="modalbox movedown">
<a href="#close" class="go-back">Go back</a> <a href="#close" class="close" title="Close">X</a>
<h3 id="retrieves-the-cost-of-a-shipping.-shipping-cost-calculator-per-country.">Retrieves the cost of a shipping. Shipping cost calculator per country.</h3>
<pre class="language-javascript details__code-terminal-json"><code>curl -X GET -H &#39;Authorization: Bearer $ACCESS_TOKEN&#39; http://api.mercadolibre.com/sites/MLM/shipping_options?zip_code_from=04500&amp;zip_code_to=05000&amp;dimensions=10x10x20,500</code></pre>
 
<h3 id="response-2">Response</h3>
<pre class="language-javascript details__code-terminal-json"><code>{
    &quot;destination&quot;: {
        &quot;zip_code&quot;: &quot;05000&quot;,
        &quot;city&quot;: {
            &quot;id&quot;: &quot;TUxNQ0NVQTgxNTY&quot;,
            &quot;name&quot;: &quot;Cuajimalpa De Morelos&quot;
        },
        &quot;state&quot;: {
            &quot;id&quot;: &quot;MX-DIF&quot;,
            &quot;name&quot;: &quot;Distrito Federal&quot;
        },
        &quot;country&quot;: {
            &quot;id&quot;: &quot;MX&quot;,
            &quot;name&quot;: &quot;Mexico&quot;
        },
        &quot;extended_attributes&quot;: {
            &quot;status&quot;: &quot;active&quot;
        }
    },
    &quot;options&quot;: [
        {
            &quot;id&quot;: 669295533,
            &quot;option_hash&quot;: &quot;696c9b0168b9c8e81467104c9f8629be&quot;,
            &quot;name&quot;: &quot;Express a domicilio&quot;,
            &quot;currency_id&quot;: &quot;MXN&quot;,
            &quot;list_cost&quot;: 94,
            &quot;cost&quot;: 94,
            &quot;base_cost&quot;: 94,
            &quot;display&quot;: &quot;optional&quot;,
            &quot;shipping_method_id&quot;: 501345,
            &quot;shipping_method_type&quot;: &quot;express&quot;,
            &quot;shipping_option_type&quot;: &quot;address&quot;,
            &quot;estimated_delivery_time&quot;: {
                &quot;type&quot;: &quot;known_frame&quot;,
                &quot;date&quot;: &quot;2020-05-12T00:00:00.000-05:00&quot;,
                &quot;unit&quot;: &quot;hour&quot;,
                &quot;offset&quot;: {
                    &quot;date&quot;: &quot;2020-05-13T00:00:00.000-05:00&quot;,
                    &quot;shipping&quot;: 24
                },
                &quot;time_frame&quot;: {
                    &quot;from&quot;: null,
                    &quot;to&quot;: null
                },
                &quot;pay_before&quot;: null,
                &quot;shipping&quot;: 24,
                &quot;handling&quot;: 72,
                &quot;schedule&quot;: null
            },
            &quot;discount&quot;: {
                &quot;rate&quot;: 0,
                &quot;type&quot;: &quot;none&quot;,
                &quot;show_loyal_benefit&quot;: false,
                &quot;promoted_amount&quot;: 0
            },
            &quot;tags&quot;: []
        },
        {
            &quot;id&quot;: 677181626,
            &quot;option_hash&quot;: &quot;3883db0fc668ab1b5191c4f34c39a7e5&quot;,
            &quot;name&quot;: &quot;Estándar a domicilio&quot;,
            &quot;currency_id&quot;: &quot;MXN&quot;,
            &quot;list_cost&quot;: 79,
            &quot;cost&quot;: 79,
            &quot;base_cost&quot;: 79,
            &quot;display&quot;: &quot;always&quot;,
            &quot;shipping_method_id&quot;: 501245,
            &quot;shipping_method_type&quot;: &quot;standard&quot;,
            &quot;shipping_option_type&quot;: &quot;address&quot;,
            &quot;estimated_delivery_time&quot;: {
                &quot;type&quot;: &quot;known&quot;,
                &quot;date&quot;: &quot;2020-05-12T00:00:00.000-05:00&quot;,
                &quot;unit&quot;: &quot;hour&quot;,
                &quot;offset&quot;: {
                    &quot;date&quot;: null,
                    &quot;shipping&quot;: null
                },
                &quot;time_frame&quot;: {
                    &quot;from&quot;: null,
                    &quot;to&quot;: null
                },
                &quot;pay_before&quot;: null,
                &quot;shipping&quot;: 24,
                &quot;handling&quot;: 72,
                &quot;schedule&quot;: null
            },
            &quot;discount&quot;: {
                &quot;rate&quot;: 0,
                &quot;type&quot;: &quot;none&quot;,
                &quot;show_loyal_benefit&quot;: false,
                &quot;promoted_amount&quot;: 0
            },
            &quot;tags&quot;: []
        },
        {
            &quot;id&quot;: 542116804,
            &quot;option_hash&quot;: &quot;a501cd3613f10350ec5e97dfa397eb50&quot;,
            &quot;name&quot;: &quot;Express a sucursal de correo&quot;,
            &quot;currency_id&quot;: &quot;MXN&quot;,
            &quot;list_cost&quot;: 94,
            &quot;cost&quot;: 94,
            &quot;base_cost&quot;: 94,
            &quot;display&quot;: &quot;optional&quot;,
            &quot;shipping_method_id&quot;: 504645,
            &quot;shipping_method_type&quot;: &quot;express&quot;,
            &quot;shipping_option_type&quot;: &quot;agency&quot;,
            &quot;estimated_delivery_time&quot;: {
                &quot;type&quot;: &quot;known&quot;,
                &quot;date&quot;: &quot;2020-05-12T00:00:00.000-05:00&quot;,
                &quot;unit&quot;: &quot;hour&quot;,
                &quot;offset&quot;: {
                    &quot;date&quot;: null,
                    &quot;shipping&quot;: null
                },
                &quot;time_frame&quot;: {
                    &quot;from&quot;: null,
                    &quot;to&quot;: null
                },
                &quot;pay_before&quot;: null,
                &quot;shipping&quot;: 24,
                &quot;handling&quot;: 72,
                &quot;schedule&quot;: null
            },
            &quot;discount&quot;: {
                &quot;rate&quot;: 0,
                &quot;type&quot;: &quot;none&quot;,
                &quot;show_loyal_benefit&quot;: false,
                &quot;promoted_amount&quot;: 0
            },
            &quot;tags&quot;: []
        },
        {
            &quot;id&quot;: 676245365,
            &quot;option_hash&quot;: &quot;1af7c5b15519a118cb5c1e552103e2d7&quot;,
            &quot;name&quot;: &quot;Prioritario a sucursal de correo&quot;,
            &quot;currency_id&quot;: &quot;MXN&quot;,
            &quot;list_cost&quot;: 72,
            &quot;cost&quot;: 72,
            &quot;base_cost&quot;: 72,
            &quot;display&quot;: &quot;recommended&quot;,
            &quot;shipping_method_id&quot;: 507845,
            &quot;shipping_method_type&quot;: &quot;same_day&quot;,
            &quot;shipping_option_type&quot;: &quot;agency&quot;,
            &quot;estimated_delivery_time&quot;: {
                &quot;type&quot;: &quot;known&quot;,
                &quot;date&quot;: &quot;2020-05-12T00:00:00.000-05:00&quot;,
                &quot;unit&quot;: &quot;hour&quot;,
                &quot;offset&quot;: {
                    &quot;date&quot;: null,
                    &quot;shipping&quot;: null
                },
                &quot;time_frame&quot;: {
                    &quot;from&quot;: null,
                    &quot;to&quot;: null
                },
                &quot;pay_before&quot;: null,
                &quot;shipping&quot;: 24,
                &quot;handling&quot;: 72,
                &quot;schedule&quot;: null
            },
            &quot;discount&quot;: {
                &quot;rate&quot;: 0,
                &quot;type&quot;: &quot;none&quot;,
                &quot;show_loyal_benefit&quot;: false,
                &quot;promoted_amount&quot;: 0
            },
            &quot;tags&quot;: []
        }
    ],
    &quot;buyer&quot;: {
        &quot;id&quot;: null,
        &quot;loyalty_level&quot;: null,
        &quot;shipping_level&quot;: null
    },
    &quot;custom_message&quot;: {
        &quot;reason&quot;: &quot;&quot;,
        &quot;display_mode&quot;: null
    }
}</code></pre>
<a href="https://global-selling.mercadolibre.com/devsite/manage-shipments">Learn more.</a>
</div>
</div></td>
</tr>
<tr class="even andes-table__row">
<td class="andes-table__column andes-table__column--left"><strong>/users/$CUST_ID/shipping_preferences</strong></td>
<td class="andes-table__column andes-table__column--left">Retrieves the cost of a shipping. Shipping cost calculator per country.</td>
<td class="andes-table__column andes-table__column--left"><a href="#modal8">GET</a>
<div id="modal8" class="modalmask">
<div class="modalbox movedown">
<a href="#close" class="go-back">Go back</a> <a href="#close" class="close" title="Close">X</a>
<h3 id="retrieves-all-shipping-modes-and-services-available-to-user.">Retrieves all shipping modes and services available to user.</h3>
<pre class="language-javascript details__code-terminal-json"><code>curl -X GET -H &#39;Authorization: Bearer $ACCESS_TOKEN&#39; http://api.mercadolibre.com/users/523132944/shipping_preferences</code></pre>
 
<h3 id="response-3">Response</h3>
<pre class="language-javascript details__code-terminal-json"><code>{
    &quot;local_pick_up&quot;: false,
    &quot;modes&quot;: [
        &quot;custom&quot;,
        &quot;not_specified&quot;,
        &quot;me1&quot;
    ],
    &quot;trusted_user&quot;: false,
    &quot;custom_calculator&quot;: &quot;CBT&quot;,
    &quot;picking_type&quot;: null,
    &quot;thermal_printer&quot;: null,
    &quot;option&quot;: &quot;in&quot;,
    &quot;tags&quot;: [],
    &quot;carrier_pickup&quot;: false,
    &quot;items_combination&quot;: &quot;disabled&quot;,
    &quot;services&quot;: [
        182441
    ],
    &quot;logistics&quot;: [
        {
            &quot;mode&quot;: &quot;me1&quot;,
            &quot;types&quot;: [
                {
                    &quot;type&quot;: &quot;default&quot;,
                    &quot;carrier_pickup&quot;: [],
                    &quot;services&quot;: [
                        182441
                    ],
                    &quot;default&quot;: true,
                    &quot;status&quot;: &quot;active&quot;
                }
            ]
        },
        {
            &quot;mode&quot;: &quot;custom&quot;,
            &quot;types&quot;: [
                {
                    &quot;type&quot;: &quot;custom&quot;,
                    &quot;carrier_pickup&quot;: [],
                    &quot;services&quot;: null,
                    &quot;default&quot;: true,
                    &quot;status&quot;: &quot;active&quot;
                }
            ]
        },
        {
            &quot;mode&quot;: &quot;not_specified&quot;,
            &quot;types&quot;: [
                {
                    &quot;type&quot;: &quot;not_specified&quot;,
                    &quot;carrier_pickup&quot;: [],
                    &quot;services&quot;: null,
                    &quot;default&quot;: true,
                    &quot;status&quot;: &quot;active&quot;
                }
            ]
        }
    ],
    &quot;content_declaration_disabled&quot;: false,
    &quot;mandatory_invoice_data&quot;: false,
    &quot;site_id&quot;: &quot;MLM&quot;,
    &quot;free_configurations&quot;: [
        {
            &quot;condition&quot;: {
                &quot;value&quot;: null,
                &quot;type&quot;: &quot;all&quot;
            },
            &quot;rule&quot;: {
                &quot;default&quot;: true,
                &quot;free_mode&quot;: &quot;country&quot;,
                &quot;value&quot;: null
            }
        }
    ],
    &quot;mandatory_settings&quot;: {}
}</code></pre>
<a href="https://global-selling.mercadolibre.com/devsite/manage-shipments">Learn more.</a>
</div>
</div></td>
</tr>
<tr class="odd andes-table__row">
<td class="andes-table__column andes-table__column--left"><strong>/marketplace/shipments/$SHIPMENT_ID/labels</strong></td>
<td class="andes-table__column andes-table__column--left">Allows print the ticket for send the order.</td>
<td class="andes-table__column andes-table__column--left"><a href="#modal9">GET</a>
<div id="modal9" class="modalmask">
<div class="modalbox movedown">
<a href="#close" class="go-back">Go back</a> <a href="#close" class="close" title="Close">X</a>
<h3 id="allows-print-the-ticket-for-send-the-order.">Allows print the ticket for send the order.</h3>
<pre class="language-javascript details__code-terminal-json"><code>curl -X GET -H &#39;Authorization: Bearer $ACCESS_TOKEN&#39; http://api.mercadolibre.com/marketplace/shipments/28242489394/labels</code></pre>
 
<h3 id="response-return-the-file-to-download-the-shipping-label.">Response:<br />
Return the file to download the shipping label.</h3>
<a href="https://global-selling.mercadolibre.com/devsite/manage-shipments">Learn more.</a>
</div>
</div></td>
</tr>
<tr class="even andes-table__row">
<td class="andes-table__column andes-table__column--left"><strong>/marketplace/shipments/$SHIPMENT_ID/tracking</strong></td>
<td class="andes-table__column andes-table__column--left">This endpoint allows you to report the tracking of a shipment, which must be entered by parameter.</td>
<td class="andes-table__column andes-table__column--left"><a href="#modal10">POST</a>
<div id="modal10" class="modalmask">
<div class="modalbox movedown">
<a href="#close" class="go-back">Go back</a> <a href="#close" class="close" title="Close">X</a>
<h3 id="this-endpoint-allows-you-to-report-the-tracking-of-a-shipment-which-must-be-entered-by-parameter.">This endpoint allows you to report the tracking of a shipment, which must be entered by parameter.</h3>
<pre class="language-javascript details__code-terminal-json"><code>curl -X POST -H &#39;Authorization: Bearer $ACCESS_TOKEN&#39; https://api.mercadolibre.com/marketplace/shipments/28262122315/tracking
  -d &#39;{
    &quot;tracking_id&quot;: &quot;String&quot;,
    &quot;tracking_url&quot;: &quot;http://carrier.com&quot;,
    &quot;carrier&quot;: &quot;name carrier&quot;
}&#39;</code></pre>
 
<h3 id="response-4">Response</h3>
<pre class="language-javascript details__code-terminal-json"><code>{
    &quot;status&quot;: &quot;success&quot;
}</code></pre>
<a href="https://global-selling.mercadolibre.com/devsite/manage-shipments">Learn more.</a>
</div>
</div></td>
</tr>
</tbody>
</table>

</div>
