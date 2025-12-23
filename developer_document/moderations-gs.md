<div class="inner-content">

## Moderations

<div class="details__message">

The resource **/infractions** provides relevant information related to
the moderations detected in any of the published elements (items,
questions, answers and reviews of the product). Remember the seller is
warned the first time. Then, he is warned again and suspended for 2 days
(unable to operate on the platform). Finally, the seller received an
ultimatum and will be suspended for 5 days (unable to operate on the
platform).

</div>

  

## Get infractions by user

We recommend that you identify the reason (reason) and solution (remedy)
to apply in the language corresponding to the site of the infraction or
in English, and in addition, you can identify and summarize the
moderations for miscategorized posts.

-   items
-   questions or answers
-   products review

Request:

``` language-javascript
curl -H 'Authorization: Bearer $ACCESS_TOKEN' -X GET https://api.mercadolibre.com/marketplace/moderations/infractions/$USER_ID
```

Example:

``` language-javascript
curl -H 'Authorization: Bearer $ACCESS_TOKEN' -X GET https://api.mercadolibre.com/marketplace/moderations/infractions/12345678
```

Response:

``` language-javascript
{
   "infractions": [
       {
            "id": "632617313",
            "date_created": "2020-12-03T03:18:15.338-0400",
            "user_id": "123455",
            "related_item_id": "MLM123456",
            "element_id": "MLM123456",
            "element_type": "ITM",
            "site_id": "MLM",
            "reason": "Low quality cover image.",
            "remedy": "In order to maintain visibility, make sure that the first image has a solid white background created with an image editor. Do not add edges, logos or watermarks."
        }
   ],
   "paging": {
       "offset": 0,
       "limit": 2,
       "total": 20671
   },
   "sorting_type": "date_created_desc"
}
```

### Response fields

**id**: unique identifier of the infraction.  
**date\_created**: date the infraction occurred.  
**user\_id**: the user who carried out the infraction.  
**related\_item\_id**: unique identifier of the post related to the item
that owns the infraction. If the violation is in a post, the value of
this attribute will equal the value of the element\_id attribute.  
**element\_id**: unique identifier of the item that owns the violation.
It is dependent on the element\_type attribute.  
**element\_type**: type of element, the values can be: ITM (listing),
QUE (questions and answers) and REV (reviews /product opinion).  
**site\_id**: marketplace site of the item with the infraction.  
**reason**: text (html) that describes the reason and infractions
policy.  
**remedy**: text (html) that indicates the action, only in cases where
it is recoverable. For example, "Remove personal data from listing".

  

<div class="andes-message andes-message--neutral">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--neutral site-carriers__message-title">

Note:

</div>

<div class="andes-message__text--neutral site-carriers__message-text">

<div>

The response you will not see the items written out in duplicates and
only the items in which the states can be final (forbidden) or temporary
(waiting\_for\_patch, held, pending\_documentation) appear. If you want
to check if a user is suspended you can check the status =&gt; list
=&gt; allow through the api of
[users](https://global-selling.mercadolibre.com/devsite/manage-users-global-selling).
In case that field is **false**, it means that it is suspended.

</div>

</div>

</div>

</div>

<div class="andes-message andes-message--highlight">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--highlight site-carriers__message-title">

Important:

</div>

<div class="andes-message__text--highlight site-carriers__message-text">

<div>

In case the user is suspended, please [check the account configuration
in the Help site](https://global-selling.mercadolibre.com/help).

</div>

</div>

</div>

</div>

## Consult infractions with filter

### Available filters

<table class="andes-table">
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead class="andes-table__head">
<tr class="header andes-table__row">
<th class="andes-table__header andes-table__header--left">Filter</th>
<th class="andes-table__header andes-table__header--left">Description</th>
<th class="andes-table__header andes-table__header--left">Options</th>
<th class="andes-table__header andes-table__header--left">Default</th>
</tr>
</thead>
<tbody class="andes-table__body">
<tr class="odd andes-table__row">
<td class="andes-table__column andes-table__column--left"><strong>related_item_id</strong></td>
<td class="andes-table__column andes-table__column--left">Post ID associated with the moderation</td>
<td class="andes-table__column andes-table__column--left">-</td>
<td class="andes-table__column andes-table__column--left">-</td>
</tr>
<tr class="even andes-table__row">
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd andes-table__row">
<td class="andes-table__column andes-table__column--left"><strong>element_id</strong></td>
<td class="andes-table__column andes-table__column--left">Id of the moderate element</td>
<td class="andes-table__column andes-table__column--left">-</td>
<td class="andes-table__column andes-table__column--left">-</td>
</tr>
<tr class="even andes-table__row">
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd andes-table__row">
<td class="andes-table__column andes-table__column--left"><strong>element_type</strong></td>
<td class="andes-table__column andes-table__column--left">Moderate element type</td>
<td class="andes-table__column andes-table__column--left">ITM (item)<br />
REV (review)<br />
QUE (question/aswer)</td>
<td class="andes-table__column andes-table__column--left">-</td>
</tr>
<tr class="even andes-table__row">
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd andes-table__row">
<td class="andes-table__column andes-table__column--left"><strong>date_created_since</strong></td>
<td class="andes-table__column andes-table__column--left">Filtering start date</td>
<td class="andes-table__column andes-table__column--left">Format: YYYY-MM-DD</td>
<td class="andes-table__column andes-table__column--left">-</td>
</tr>
<tr class="even andes-table__row">
<td class="andes-table__column andes-table__column--left"><strong>date_created_to</strong></td>
<td class="andes-table__column andes-table__column--left">Filtering end date</td>
<td class="andes-table__column andes-table__column--left">Format: YYYY-MM-DD</td>
<td class="andes-table__column andes-table__column--left">-</td>
</tr>
<tr class="odd andes-table__row">
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even andes-table__row">
<td class="andes-table__column andes-table__column--left"><strong>limit</strong></td>
<td class="andes-table__column andes-table__column--left">Number of infractions returned</td>
<td class="andes-table__column andes-table__column--left">Integer from 1 to 20</td>
<td class="andes-table__column andes-table__column--left">20</td>
</tr>
<tr class="odd andes-table__row">
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even andes-table__row">
<td class="andes-table__column andes-table__column--left"><strong>offset</strong></td>
<td class="andes-table__column andes-table__column--left">Offset for paging</td>
<td class="andes-table__column andes-table__column--left"></td>
<td class="andes-table__column andes-table__column--left">0</td>
</tr>
<tr class="odd andes-table__row">
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even andes-table__row">
<td class="andes-table__column andes-table__column--left"><strong>sort</strong></td>
<td class="andes-table__column andes-table__column--left">Sort results by creation date, ascending or descending</td>
<td class="andes-table__column andes-table__column--left">date_created_asc, date_created_desc</td>
<td class="andes-table__column andes-table__column--left">date_created_desc</td>
</tr>
</tbody>
</table>

Request:

``` language-javascript
curl -H 'Authorization: Bearer $ACCESS_TOKEN' -X GET https://api.mercadolibre.com/marketplace/moderations/infractions/$USER_ID?date_created_since=AAAA-MM-DD&limit=XX&offset=X
```

Example:

``` language-javascript
curl -H 'Authorization: Bearer $ACCESS_TOKEN' -X GET https://api.mercadolibre.com/marketplace/moderations/infractions/12345678?date_created_since=2020-12-15&limit=1&offset=0
```

Response:

``` language-javascript
{
   "infractions": [
        {
            "id": "632617313",
            "date_created": "2020-12-03T03:18:15.338-0400",
            "user_id": "123455",
            "related_item_id": "MLM123456",
            "element_id": "MLM123456",
            "element_type": "ITM",
            "site_id": "MLM",
            "reason": "Low quality cover image.",
            "remedy": "In order to maintain visibility, make sure that the first image has a solid white background created with an image editor. Do not add edges, logos or watermarks."
        }],
   "paging": {
       "offset": 0,
       "limit": 1,
       "total": 20671
   },
   "sorting_type": "date_created_desc"
}
```

### Response when no infractions are found

When no infractions match the query criteria, the **infractions** field
will be **null** instead of an empty array:

``` language-javascript
{
   "infractions": null,
   "paging": {
       "offset": 0,
       "limit": 10,
       "total": 0
   },
   "sorting_type": "date_created_desc"
}
```

  

## HTTP response code references

### Successful responses

| Code       | Description                                                      |
|------------|------------------------------------------------------------------|
| **200 OK** | Request processed successfully. Returns the list of infractions. |

### Error responses

| Code    | Error                                    | Description                                    | Possible cause                                                         |
|---------|------------------------------------------|------------------------------------------------|------------------------------------------------------------------------|
| **400** | bad\_request                             | Invalid or empty user id                       | The user\_id parameter is not a valid numeric value.                   |
| **400** | bad\_request                             | limit max value is 20                          | The limit parameter exceeds the maximum allowed value of 20.           |
| **400** | bad\_request                             | date\_created\_since invalid date time format. | The date format is incorrect. Use YYYY-MM-DD format.                   |
| **403** | forbidden                                | Can not identify the user.                     | The user\_id does not exist or you don't have permission to access it. |
| **403** | PA\_UNAUTHORIZED\_RESULT\_FROM\_POLICIES | At least one policy returned UNAUTHORIZED.     | The access token is invalid, expired, or missing required permissions. |

### Error response example

When a request fails due to authorization issues:

``` language-javascript
{
   "status": 403,
   "code": "PA_UNAUTHORIZED_RESULT_FROM_POLICIES",
   "message": "At least one policy returned UNAUTHORIZED.",
   "blocked_by": "PolicyAgent"
}
```

When a request fails due to invalid parameters:

``` language-javascript
{
   "message": "Invalid Parameter",
   "error": "Bad Request",
   "status": 400,
   "cause": [
       "Invalid or empty user id"
   ]
}
```

</div>
