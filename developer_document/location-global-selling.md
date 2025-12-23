<div class="inner-content">

# Location

<div class="details__message">

The following examples will be used to obtain the locations available.

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
<td class="andes-table__column andes-table__column--left"><strong>/countries</strong></td>
<td class="andes-table__column andes-table__column--left">Returns country information.</td>
<td class="andes-table__column andes-table__column--left"><a href="#modal1">GET</a>
<div id="modal1" class="modalmask">
<div class="modalbox movedown">
<a href="#close" class="go-back">Go back</a> <a href="#close" class="close" title="Close">X</a>
<h3 id="search-for-a-country">Search for a country</h3>
<pre class="language-javascript details__code-terminal-json"><code>curl -X GET -H &#39;Authorization: Bearer $ACCESS_TOKEN&#39; https://api.mercadolibre.com/countries</code></pre>
<h3 id="response">Response</h3>
<pre class="language-javascript details__code-terminal-json"><code>[
    {
        &quot;id&quot;: &quot;AR&quot;,
        &quot;name&quot;: &quot;Argentina&quot;,
        &quot;locale&quot;: &quot;es_AR&quot;,
        &quot;currency_id&quot;: &quot;ARS&quot;
    },
    {
        &quot;id&quot;: &quot;AU&quot;,
        &quot;name&quot;: &quot;Australia&quot;,
        &quot;locale&quot;: &quot;en_US&quot;,
        &quot;currency_id&quot;: &quot;USD&quot;
    },
    {
        &quot;id&quot;: &quot;BO&quot;,
        &quot;name&quot;: &quot;Bolivia&quot;,
        &quot;locale&quot;: &quot;es_BO&quot;,
        &quot;currency_id&quot;: &quot;BOB&quot;
    },
    {
        &quot;id&quot;: &quot;BR&quot;,
        &quot;name&quot;: &quot;Brasil&quot;,
        &quot;locale&quot;: &quot;pt_BR&quot;,
        &quot;currency_id&quot;: &quot;BRL&quot;
    },
    {
        &quot;id&quot;: &quot;CA&quot;,
        &quot;name&quot;: &quot;Canada&quot;,
        &quot;locale&quot;: &quot;en_US&quot;,
        &quot;currency_id&quot;: &quot;USD&quot;
    },
    {
        &quot;id&quot;: &quot;CL&quot;,
        &quot;name&quot;: &quot;Chile&quot;,
        &quot;locale&quot;: &quot;es_CL&quot;,
        &quot;currency_id&quot;: &quot;CLP&quot;
    },
    {
        &quot;id&quot;: &quot;CN&quot;,
        &quot;name&quot;: &quot;China&quot;,
        &quot;locale&quot;: &quot;en_US&quot;,
        &quot;currency_id&quot;: &quot;USD&quot;
    },
    {
        &quot;id&quot;: &quot;CO&quot;,
        &quot;name&quot;: &quot;Colombia&quot;,
        &quot;locale&quot;: &quot;es_CO&quot;,
        &quot;currency_id&quot;: &quot;COP&quot;
    },
    {
        &quot;id&quot;: &quot;CR&quot;,
        &quot;name&quot;: &quot;Costa Rica&quot;,
        &quot;locale&quot;: &quot;es_CR&quot;,
        &quot;currency_id&quot;: &quot;CRC&quot;
    },
    {
        &quot;id&quot;: &quot;CU&quot;,
        &quot;name&quot;: &quot;Cuba&quot;,
        &quot;locale&quot;: &quot;es_CU&quot;,
        &quot;currency_id&quot;: &quot;CUC&quot;
    },
    {
        &quot;id&quot;: &quot;EC&quot;,
        &quot;name&quot;: &quot;Ecuador&quot;,
        &quot;locale&quot;: &quot;es_EC&quot;,
        &quot;currency_id&quot;: &quot;USD&quot;
    },
    {
        &quot;id&quot;: &quot;SV&quot;,
        &quot;name&quot;: &quot;El Salvador&quot;,
        &quot;locale&quot;: &quot;es_SV&quot;,
        &quot;currency_id&quot;: &quot;USD&quot;
    },
    {
        &quot;id&quot;: &quot;FR&quot;,
        &quot;name&quot;: &quot;France&quot;,
        &quot;locale&quot;: &quot;en_US&quot;,
        &quot;currency_id&quot;: &quot;USD&quot;
    },
    {
        &quot;id&quot;: &quot;DE&quot;,
        &quot;name&quot;: &quot;Germany&quot;,
        &quot;locale&quot;: &quot;en_US&quot;,
        &quot;currency_id&quot;: &quot;USD&quot;
    },
    {
        &quot;id&quot;: &quot;GB&quot;,
        &quot;name&quot;: &quot;Great Britain&quot;,
        &quot;locale&quot;: &quot;en_US&quot;,
        &quot;currency_id&quot;: &quot;USD&quot;
    },
    {
        &quot;id&quot;: &quot;GT&quot;,
        &quot;name&quot;: &quot;Guatemala&quot;,
        &quot;locale&quot;: &quot;es_GT&quot;,
        &quot;currency_id&quot;: &quot;GTQ&quot;
    },
    {
        &quot;id&quot;: &quot;HN&quot;,
        &quot;name&quot;: &quot;Honduras&quot;,
        &quot;locale&quot;: &quot;es_HN&quot;,
        &quot;currency_id&quot;: &quot;HNL&quot;
    },
    {
        &quot;id&quot;: &quot;HK&quot;,
        &quot;name&quot;: &quot;Hong Kong&quot;,
        &quot;locale&quot;: &quot;en_US&quot;,
        &quot;currency_id&quot;: &quot;USD&quot;
    },
    {
        &quot;id&quot;: &quot;IN&quot;,
        &quot;name&quot;: &quot;India&quot;,
        &quot;locale&quot;: &quot;en_US&quot;,
        &quot;currency_id&quot;: &quot;USD&quot;
    },
    {
        &quot;id&quot;: &quot;IT&quot;,
        &quot;name&quot;: &quot;Italy&quot;,
        &quot;locale&quot;: &quot;en_US&quot;,
        &quot;currency_id&quot;: &quot;USD&quot;
    },
    {
        &quot;id&quot;: &quot;JP&quot;,
        &quot;name&quot;: &quot;Japan&quot;,
        &quot;locale&quot;: &quot;en_US&quot;,
        &quot;currency_id&quot;: &quot;USD&quot;
    },
    {
        &quot;id&quot;: &quot;MX&quot;,
        &quot;name&quot;: &quot;Mexico&quot;,
        &quot;locale&quot;: &quot;es_MX&quot;,
        &quot;currency_id&quot;: &quot;MXN&quot;
    },
    {
        &quot;id&quot;: &quot;MC&quot;,
        &quot;name&quot;: &quot;Monaco&quot;,
        &quot;locale&quot;: &quot;en_US&quot;,
        &quot;currency_id&quot;: &quot;USD&quot;
    },
    {
        &quot;id&quot;: &quot;NI&quot;,
        &quot;name&quot;: &quot;Nicaragua&quot;,
        &quot;locale&quot;: &quot;es_NI&quot;,
        &quot;currency_id&quot;: &quot;NIO&quot;
    },
    {
        &quot;id&quot;: &quot;PA&quot;,
        &quot;name&quot;: &quot;Panamá&quot;,
        &quot;locale&quot;: &quot;es_PA&quot;,
        &quot;currency_id&quot;: &quot;USD&quot;
    },
    {
        &quot;id&quot;: &quot;PY&quot;,
        &quot;name&quot;: &quot;Paraguay&quot;,
        &quot;locale&quot;: &quot;es_PY&quot;,
        &quot;currency_id&quot;: &quot;PYG&quot;
    },
    {
        &quot;id&quot;: &quot;PE&quot;,
        &quot;name&quot;: &quot;Peru&quot;,
        &quot;locale&quot;: &quot;es_PE&quot;,
        &quot;currency_id&quot;: &quot;PEN&quot;
    },
    {
        &quot;id&quot;: &quot;PT&quot;,
        &quot;name&quot;: &quot;Portugal&quot;,
        &quot;locale&quot;: &quot;pt_PT&quot;,
        &quot;currency_id&quot;: &quot;EUR&quot;
    },
    {
        &quot;id&quot;: &quot;PR&quot;,
        &quot;name&quot;: &quot;Puerto Rico&quot;,
        &quot;locale&quot;: &quot;es_PR&quot;,
        &quot;currency_id&quot;: &quot;USD&quot;
    },
    {
        &quot;id&quot;: &quot;DO&quot;,
        &quot;name&quot;: &quot;República Dominicana&quot;,
        &quot;locale&quot;: &quot;es_DO&quot;,
        &quot;currency_id&quot;: &quot;DOP&quot;
    },
    {
        &quot;id&quot;: &quot;KR&quot;,
        &quot;name&quot;: &quot;South Korea&quot;,
        &quot;locale&quot;: &quot;en_US&quot;,
        &quot;currency_id&quot;: &quot;USD&quot;
    },
    {
        &quot;id&quot;: &quot;ES&quot;,
        &quot;name&quot;: &quot;Spain&quot;,
        &quot;locale&quot;: &quot;en_US&quot;,
        &quot;currency_id&quot;: &quot;USD&quot;
    },
    {
        &quot;id&quot;: &quot;TR&quot;,
        &quot;name&quot;: &quot;Turkey&quot;,
        &quot;locale&quot;: &quot;en_US&quot;,
        &quot;currency_id&quot;: &quot;USD&quot;
    },
    {
        &quot;id&quot;: &quot;US&quot;,
        &quot;name&quot;: &quot;United States of America&quot;,
        &quot;locale&quot;: &quot;en_US&quot;,
        &quot;currency_id&quot;: &quot;USD&quot;
    },
    {
        &quot;id&quot;: &quot;UY&quot;,
        &quot;name&quot;: &quot;Uruguay&quot;,
        &quot;locale&quot;: &quot;es_UY&quot;,
        &quot;currency_id&quot;: &quot;UYU&quot;
    },
    {
        &quot;id&quot;: &quot;VE&quot;,
        &quot;name&quot;: &quot;Venezuela&quot;,
        &quot;locale&quot;: &quot;es_VE&quot;,
        &quot;currency_id&quot;: &quot;VES&quot;
    }
]</code></pre>
</div>
</div></td>
</tr>
</tbody>
<tbody class="andes-table__body">
<tr class="odd andes-table__row">
<td class="andes-table__column andes-table__column--left"><strong>/countries/$COUNTRY_ID</strong></td>
<td class="andes-table__column andes-table__column--left">Returns country information by country_id.</td>
<td class="andes-table__column andes-table__column--left"><a href="#modal2">GET</a>
<div id="modal2" class="modalmask">
<div class="modalbox movedown">
<a href="#close" class="go-back">Go back</a> <a href="#close" class="close" title="Close">X</a>
<h3 id="search-for-a-country-by-id">Search for a country by id</h3>
<pre class="language-javascript details__code-terminal-json"><code>curl -X GET -H &#39;Authorization: Bearer $ACCESS_TOKEN&#39; https://api.mercadolibre.com/countries/AR</code></pre>
<h3 id="response-1">Response</h3>
<pre class="language-javascript details__code-terminal-json"><code>{
    &quot;id&quot;: &quot;AR&quot;,
    &quot;name&quot;: &quot;Argentina&quot;,
    &quot;locale&quot;: &quot;es_AR&quot;,
    &quot;site&quot;: &quot;MLA&quot;,
    &quot;currency_id&quot;: &quot;ARS&quot;,
    &quot;decimal_separator&quot;: &quot;,&quot;,
    &quot;thousands_separator&quot;: &quot;.&quot;,
    &quot;time_zone&quot;: &quot;GMT-03:00&quot;,
    &quot;time_zone_name&quot;: &quot;America/Buenos_Aires&quot;,
    &quot;geo_information&quot;: {
        &quot;location&quot;: {
            &quot;latitude&quot;: -38.416096,
            &quot;longitude&quot;: -63.616673
        }
    },
    &quot;states&quot;: [
        {
            &quot;id&quot;: &quot;AR-B&quot;,
            &quot;name&quot;: &quot;Buenos Aires&quot;
        },
        {
            &quot;id&quot;: &quot;AR-C&quot;,
            &quot;name&quot;: &quot;Capital Federal&quot;
        },
        {
            &quot;id&quot;: &quot;AR-K&quot;,
            &quot;name&quot;: &quot;Catamarca&quot;
        },
        {
            &quot;id&quot;: &quot;AR-H&quot;,
            &quot;name&quot;: &quot;Chaco&quot;
        },
        {
            &quot;id&quot;: &quot;AR-U&quot;,
            &quot;name&quot;: &quot;Chubut&quot;
        },
        {
            &quot;id&quot;: &quot;AR-W&quot;,
            &quot;name&quot;: &quot;Corrientes&quot;
        },
        {
            &quot;id&quot;: &quot;AR-X&quot;,
            &quot;name&quot;: &quot;Córdoba&quot;
        },
        {
            &quot;id&quot;: &quot;AR-E&quot;,
            &quot;name&quot;: &quot;Entre Ríos&quot;
        },
        {
            &quot;id&quot;: &quot;AR-P&quot;,
            &quot;name&quot;: &quot;Formosa&quot;
        },
        {
            &quot;id&quot;: &quot;AR-Y&quot;,
            &quot;name&quot;: &quot;Jujuy&quot;
        },
        {
            &quot;id&quot;: &quot;AR-L&quot;,
            &quot;name&quot;: &quot;La Pampa&quot;
        },
        {
            &quot;id&quot;: &quot;AR-F&quot;,
            &quot;name&quot;: &quot;La Rioja&quot;
        },
        {
            &quot;id&quot;: &quot;AR-M&quot;,
            &quot;name&quot;: &quot;Mendoza&quot;
        },
        {
            &quot;id&quot;: &quot;AR-N&quot;,
            &quot;name&quot;: &quot;Misiones&quot;
        },
        {
            &quot;id&quot;: &quot;AR-Q&quot;,
            &quot;name&quot;: &quot;Neuquén&quot;
        },
        {
            &quot;id&quot;: &quot;AR-R&quot;,
            &quot;name&quot;: &quot;Río Negro&quot;
        },
        {
            &quot;id&quot;: &quot;AR-A&quot;,
            &quot;name&quot;: &quot;Salta&quot;
        },
        {
            &quot;id&quot;: &quot;AR-J&quot;,
            &quot;name&quot;: &quot;San Juan&quot;
        },
        {
            &quot;id&quot;: &quot;AR-D&quot;,
            &quot;name&quot;: &quot;San Luis&quot;
        },
        {
            &quot;id&quot;: &quot;AR-Z&quot;,
            &quot;name&quot;: &quot;Santa Cruz&quot;
        },
        {
            &quot;id&quot;: &quot;AR-S&quot;,
            &quot;name&quot;: &quot;Santa Fe&quot;
        },
        {
            &quot;id&quot;: &quot;AR-G&quot;,
            &quot;name&quot;: &quot;Santiago del Estero&quot;
        },
        {
            &quot;id&quot;: &quot;AR-V&quot;,
            &quot;name&quot;: &quot;Tierra del Fuego&quot;
        },
        {
            &quot;id&quot;: &quot;AR-T&quot;,
            &quot;name&quot;: &quot;Tucumán&quot;
        }
    ]
}</code></pre>
</div>
</div></td>
</tr>
</tbody>
<tbody class="andes-table__body">
<tr class="odd andes-table__row">
<td class="andes-table__column andes-table__column--left"><strong>/states/$STATE_ID</strong></td>
<td class="andes-table__column andes-table__column--left">Returns state information by state_id.</td>
<td class="andes-table__column andes-table__column--left"><a href="#modal4">GET</a>
<div id="modal4" class="modalmask">
<div class="modalbox movedown">
<a href="#close" class="go-back">Go back</a> <a href="#close" class="close" title="Close">X</a>
<h3 id="search-for-a-state-by-id">Search for a state by id</h3>
<pre class="language-javascript details__code-terminal-json"><code>curl -X GET -H &#39;Authorization: Bearer $ACCESS_TOKEN&#39; https://api.mercadolibre.com/states/AR-B</code></pre>
<h3 id="response-2">Response</h3>
<pre class="language-javascript details__code-terminal-json"><code>{
    &quot;id&quot;: &quot;AR-B&quot;,
    &quot;name&quot;: &quot;Buenos Aires&quot;,
    &quot;country&quot;: {
        &quot;id&quot;: &quot;AR&quot;,
        &quot;name&quot;: &quot;Argentina&quot;
    },
    &quot;site&quot;: &quot;MLA&quot;,
    &quot;geo_information&quot;: {
        &quot;location&quot;: {
            &quot;latitude&quot;: -37.2017285,
            &quot;longitude&quot;: -59.8410697
        }
    },
    &quot;time_zone&quot;: &quot;GMT-03:00&quot;,
    &quot;time_zone_name&quot;: &quot;America/Buenos_Aires&quot;,
    &quot;cities&quot;: [
        {
            &quot;id&quot;: &quot;QVItQjEyIERlIE9jdHVicmU&quot;,
            &quot;name&quot;: &quot;12 De Octubre&quot;
        },
        {
            &quot;id&quot;: &quot;TUxBQzI1RDIwMzQ&quot;,
            &quot;name&quot;: &quot;25 de Mayo&quot;
        },
        {
            &quot;id&quot;: &quot;TUxBQzlERTU5MTA&quot;,
            &quot;name&quot;: &quot;9 de Julio&quot;
        },
        {
            &quot;id&quot;: &quot;TUxBQ0FETzQ2Nzc&quot;,
            &quot;name&quot;: &quot;Adolfo Alsina&quot;
        },
        {
            &quot;id&quot;: &quot;TUxBQ0FETzY3Mjk&quot;,
            &quot;name&quot;: &quot;Adolfo Gonzales Chaves&quot;
        },
        {
            &quot;id&quot;: &quot;TUxBQ0FHVWE1Yjkz&quot;,
            &quot;name&quot;: &quot;Aguas Verdes&quot;
        },
        {
            &quot;id&quot;: &quot;TUxBQ0FMQjYwODM&quot;,
            &quot;name&quot;: &quot;Alberti&quot;
        },
        {
            &quot;id&quot;: &quot;TUxBQ0FWRTc5OTQ1&quot;,
            &quot;name&quot;: &quot;Avellaneda&quot;
        },
        {
            &quot;id&quot;: &quot;TUxBQ0FZQTc2MzA&quot;,
            &quot;name&quot;: &quot;Ayacucho&quot;
        },
        {
            &quot;id&quot;: &quot;TUxBQ0FaVTgxMjA&quot;,
            &quot;name&quot;: &quot;Azul&quot;
        },
        {
            &quot;id&quot;: &quot;TUxBQ0JBSDI0OTNk&quot;,
            &quot;name&quot;: &quot;Bahía Blanca&quot;
        },
        {
            &quot;id&quot;: &quot;TUxBQ0JBTDk4NTE&quot;,
            &quot;name&quot;: &quot;Balcarce&quot;
        },
        {
            &quot;id&quot;: &quot;...&quot;,
            &quot;name&quot;: &quot;... (more cities)&quot;
        }
    ]
}</code></pre>
</div>
</div></td>
</tr>
</tbody>
<tbody class="andes-table__body">
<tr class="odd andes-table__row">
<td class="andes-table__column andes-table__column--left"><strong>/cities/$CITY_ID</strong></td>
<td class="andes-table__column andes-table__column--left">Returns city information by city_id.</td>
<td class="andes-table__column andes-table__column--left"><a href="#modal5">GET</a>
<div id="modal5" class="modalmask">
<div class="modalbox movedown">
<a href="#close" class="go-back">Go back</a> <a href="#close" class="close" title="Close">X</a>
<h3 id="search-for-a-city-by-id">Search for a city by id</h3>
<pre class="language-javascript details__code-terminal-json"><code>curl -X GET -H &#39;Authorization: Bearer $ACCESS_TOKEN&#39; https://api.mercadolibre.com/cities/Q04tQkpCZWlqaW5n</code></pre>
<h3 id="response-3">Response</h3>
<pre class="language-javascript details__code-terminal-json"><code>{
    &quot;id&quot;: &quot;Q04tQkpCZWlqaW5n&quot;,
    &quot;name&quot;: &quot;Beijing&quot;,
    &quot;site&quot;: &quot;&quot;,
    &quot;state&quot;: {
        &quot;id&quot;: &quot;CN-BJ&quot;,
        &quot;name&quot;: &quot;Beijing&quot;
    },
    &quot;country&quot;: {
        &quot;id&quot;: &quot;CN&quot;,
        &quot;name&quot;: &quot;China&quot;
    },
    &quot;geo_information&quot;: null
}</code></pre>
</div>
</div></td>
</tr>
</tbody>
</table>

  

## Response fields

### Countries response fields

| Field                    | Description                                                                                                                         |
|--------------------------|-------------------------------------------------------------------------------------------------------------------------------------|
| **id**                   | Country identifier (ISO 3166-1 alpha-2 code).                                                                                       |
| **name**                 | Country name.                                                                                                                       |
| **locale**               | Locale code for the country (language and region).                                                                                  |
| **site**                 | Mercado Libre site identifier (e.g., MLA for Argentina, MLB for Brazil, MLM for Mexico). Empty for countries without a marketplace. |
| **currency\_id**         | Default currency for the country.                                                                                                   |
| **decimal\_separator**   | Character used as decimal separator.                                                                                                |
| **thousands\_separator** | Character used as thousands separator.                                                                                              |
| **time\_zone**           | Time zone offset (e.g., GMT-03:00).                                                                                                 |
| **time\_zone\_name**     | Time zone name (e.g., America/Buenos\_Aires).                                                                                       |
| **geo\_information**     | Geographic coordinates containing latitude and longitude.                                                                           |
| **states**               | List of states/provinces with their id and name.                                                                                    |

### States response fields

| Field                | Description                                                                         |
|----------------------|-------------------------------------------------------------------------------------|
| **id**               | State identifier (format: COUNTRY-STATE code).                                      |
| **name**             | State/province name.                                                                |
| **country**          | Parent country object with id and name.                                             |
| **site**             | Mercado Libre site identifier. Empty for states in countries without a marketplace. |
| **geo\_information** | Geographic coordinates containing latitude and longitude.                           |
| **time\_zone**       | Time zone offset. Can be null.                                                      |
| **time\_zone\_name** | Time zone name. Can be empty.                                                       |
| **cities**           | List of cities with their id and name.                                              |

### Cities response fields

| Field                | Description                                                                         |
|----------------------|-------------------------------------------------------------------------------------|
| **id**               | City identifier (encoded string).                                                   |
| **name**             | City name.                                                                          |
| **site**             | Mercado Libre site identifier. Empty for cities in countries without a marketplace. |
| **state**            | Parent state object with id and name.                                               |
| **country**          | Parent country object with id and name.                                             |
| **geo\_information** | Geographic coordinates. Can be null if not available.                               |

  

## HTTP response code references

### Successful responses

| Code       | Description                                                       |
|------------|-------------------------------------------------------------------|
| **200 OK** | Request processed successfully. Returns the location information. |

### Error responses

| Code    | Error       | Description        | Possible cause                                                           |
|---------|-------------|--------------------|--------------------------------------------------------------------------|
| **400** | invalid\_id | Invalid country ID | The country\_id provided is not a valid ISO country code.                |
| **404** | not\_found  | Country not found  | The specified country\_id does not exist.                                |
| **404** | not\_found  | State not found    | The specified state\_id does not exist.                                  |
| **404** | not\_found  | City not found     | The specified city\_id does not exist.                                   |
| **404** | not\_found  | Resource not found | The resource path is invalid (e.g., /states/ or /cities/ without an ID). |

### Error response examples

#### Invalid country ID (400)

``` language-javascript
{
    "message": "Validation errors",
    "error": "invalid_id",
    "status": 400,
    "cause": [
        "Invalid country ID"
    ]
}
```

#### Country not found (404)

``` language-javascript
{
    "message": "Country not found",
    "error": "not_found",
    "status": 404,
    "cause": []
}
```

#### State not found (404)

``` language-javascript
{
    "message": "State not found",
    "error": "not_found",
    "status": 404,
    "cause": []
}
```

#### City not found (404)

``` language-javascript
{
    "message": "City not found",
    "error": "not_found",
    "status": 404,
    "cause": []
}
```

#### Resource path not found (404)

``` language-javascript
{
    "message": "Resource /states/ not found.",
    "error": "not_found",
    "status": 404,
    "cause": []
}
```

</div>
