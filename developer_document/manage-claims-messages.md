<div class="inner-content">

## Messages claims

<div class="details__message">

The management of messages within a Mercado Libre claim is crucial for
efficiently handling communications between users and customer service
regarding transaction issues. The primary goal is to provide quick and
effective responses to users' concerns, offering solutions that address
and resolve specific problems. This practice not only helps maintain
customer satisfaction but also strengthens the quality of service on the
platform, ensuring an optimal user experience and fostering trust in
Mercado Libre.

</div>

## Retrieve all messages of a claim

Messages in a claim constitute the main channel through which the
involved parties express their requests and argue their positions. This
form of communication is essential for a clear and effective exchange of
information, facilitating an informed and fair resolution of disputes.

<div class="andes-message andes-message--neutral">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--neutral site-carriers__message-title">

Note:

</div>

<div class="andes-message__text--neutral site-carriers__message-text">

<div>

**Only** your own moderated messages, marked with the status
"moderated," will be displayed. The counterpart's messages that have
also passed moderation will be automatically filtered. This policy
ensures clear and controlled communication, maintaining order and
relevance in the information exchange during the claim process.

</div>

</div>

</div>

</div>

**Call:**

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' 
https://api.mercadolibre.com/marketplace/v2/claims/$CLAIM_ID/messages
```

**Example:**

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/marketplace/v2/claims/5294629673/messages
```

**Response:**

``` language-javascript
 [
   {
       "sender_role": "complainant",
       "receiver_role": "respondent",
       "message": "No estoy de acuerdo\n",
       "translated_message": "I don't agree",
       "date_created": "2024-08-22T18:36:48.000-04:00",
       "last_updated": "2024-08-22T18:36:48.000-04:00",
       "message_date": "2024-08-22T18:36:48.000-04:00",
       "date_read": "2024-11-04T19:01:48Z",
       "attachments": [],
       "status": "available",
       "stage": "claim",
       "message_moderation": {
           "status": "clean",
           "reason": "",
           "source": "online",
           "date_moderated": "2024-08-22T22:36:47Z"
       },
       "repeated": false
   },
   {
       "sender_role": "respondent",
       "receiver_role": "complainant",
       "message": "Este es un mensaje de test del respondent al complainant",
       "translated_message": null,
       "date_created": "2024-08-22T18:21:20.000-04:00",
       "last_updated": "2024-08-22T18:21:20.000-04:00",
       "message_date": "2024-08-22T18:21:20.000-04:00",
       "date_read": "2024-08-22T22:21:21Z",
       "attachments": [
           {
               "filename": "1317418851_9efe5db7-1910-4184-932b-bb6279c15e37.jpg",
               "original_filename": "queja.jpg",
               "size": 16704,
               "date_created": "2024-08-22T18:21:19.000-04:00",
               "type": "image/jpeg"
           }
       ],
       "status": "available",
       "stage": "claim",
       "message_moderation": {
           "status": "clean",
           "reason": "",
           "source": "online",
           "date_moderated": "2024-08-22T22:21:19Z"
       },
       "repeated": false
   },
   {
       "sender_role": "complainant",
       "receiver_role": "respondent",
       "message": "imagen",
       "translated_message": "picture",
       "date_created": "2024-08-22T18:13:09.000-04:00",
       "last_updated": "2024-08-22T18:13:09.000-04:00",
       "message_date": "2024-08-22T18:13:09.000-04:00",
       "date_read": "2024-08-22T22:13:15Z",
       "attachments": [
           {
               "filename": "1517482146_31489bf8-95e3-4a2d-bcff-3c57771fb7c4.png",
               "original_filename": "Captura de pantalla 2024-08-22 a la(s) 4.12.28?p.m..png",
               "size": 166960,
               "date_created": "2024-08-22T18:13:09.000-04:00",
               "type": "image/png"
           }
       ],
       "status": "available",
       "stage": "claim",
       "message_moderation": {
           "status": "clean",
           "reason": "",
           "source": "online",
           "date_moderated": "2024-08-22T22:13:09Z"
       },
       "repeated": false
   },
   {
       "sender_role": "complainant",
       "receiver_role": "respondent",
       "message": "hola requiero una devolución test",
       "translated_message": "Hello I require a test return",
       "date_created": "2024-08-22T17:46:54.000-04:00",
       "last_updated": "2024-08-22T17:46:54.000-04:00",
       "message_date": "2024-08-22T17:46:54.000-04:00",
       "date_read": "2024-08-22T22:12:39Z",
       "attachments": [],
       "status": "available",
       "stage": "claim",
       "message_moderation": {
           "status": "clean",
           "reason": "",
           "source": "online",
           "date_moderated": "2024-08-22T21:46:54Z"
       },
       "repeated": false
   },
   {
       "sender_role": "complainant",
       "receiver_role": "respondent",
       "message": "Prueba test",
       "translated_message": "Prueba test",
       "date_created": "2024-08-22T17:31:37.000-04:00",
       "last_updated": "2024-08-22T17:31:37.000-04:00",
       "message_date": "2024-08-22T17:31:37.000-04:00",
       "date_read": "2024-08-22T21:32:21Z",
       "attachments": [],
       "status": "available",
       "stage": "claim",
       "message_moderation": {
           "status": "clean",
           "reason": "",
           "source": "online",
           "date_moderated": "2024-08-22T21:31:36Z"
       },
       "repeated": false
   }
]
```

### Response Fields

A GET response to the /claims/$CLAIMS\_ID/messages resource will provide
the following parameters:

-   **sender\_role**: The player who sent the message:
    -   **complainant**
    -   **respondent**
-   **receiver\_role**: The player to whom the message is addressed:
    -   **complainant**
    -   **respondent**
-   **message**: Message text
-   **translated\_message**: Message translation (only if the message
    requires translation: label CBT)
-   **date\_created**: Date when the message was created
-   **last\_updated**: Date of the last update
-   **message\_date**: Date when the message was sent
-   **date\_read**: Indicates the date when the message was read
-   **attachments**: List of message attachments:
    -   **filename**
    -   **original\_filename**
    -   **size**
    -   **date\_created**
    -   **type**
-   **status**: Status of the message:
    -   **available**
    -   **moderated**
    -   **rejected**
    -   **pending\_translation**
-   **stage**: The stage in which the message was sent
-   **message\_moderation**: The result of the moderation process.
    -   **status**: Possible values:
        -   **clean**: The message is clean.
        -   **rejected**: The message was moderated.
        -   **pending**: Moderation is in progress.
        -   **non\_moderated**: Moderation was not applied, e.g., in
            older cases.
    -   **reason**: Reason for moderating the message:
        -   **OUT\_OF\_PLACE\_LANGUAGE**: Inappropriate language.
    -   **source**: Moderation modality. Possible values:
        -   **online**: Moderation occurs during message creation.
            Currently, the only modality.
    -   **date\_moderated**: Date when moderation was performed.
-   **repeated**

## Replying to Messages and Attaching Files

Responding effectively and attaching relevant documentation allows for
more efficient problem-solving, enhancing customer satisfaction and
ensuring service quality. During a claim, all participants, except the
**warehouse\_dispatcher** player, have the opportunity to send at least
one message.

Messages may include attachments. If a participant wishes to include an
attachment in their message, they must first upload the file following
the steps detailed in the "Uploading Attachments" section. Once
uploaded, the user can use the filename generated by the Attachments API
to incorporate it into their message, as illustrated in the provided
examples.

This communication structure not only facilitates a smoother and more
documented exchange of information but also optimizes the claim
management process, allowing for quicker and more transparent resolution
of disputes.

<div class="andes-message andes-message--neutral">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--neutral site-carriers__message-title">

Note:

</div>

<div class="andes-message__text--neutral site-carriers__message-text">

<div>

If you decide not to include an attachment, you do not need to include
the 'attachments' field in the POST body. This flexibility simplifies
the messaging process when no additional documentation is required,
speeding up communication and maintaining efficiency in claim
management.

</div>

</div>

</div>

</div>

The POST should be performed as **form.data** with **file = file
location**.

Users can exchange a variety of useful documents, such as photos,
instruction manuals, and invoices, in JPG, PNG, and PDF formats, as long
as they do not exceed 5 MB in size.

Additionally, the filename should be concise, not exceeding 125
characters, and should be composed of letters, numbers, periods,
hyphens, and underscores (`a-zA-Z0-9._-`). These regulations ensure that
file exchanges are carried out efficiently and organized, facilitating
management and access to relevant information during the claim process.

## Uploading Attachments

Files can be attached to messages by sending a POST request to the
'attachments' endpoint. This functionality enables the inclusion of
relevant documentation directly into the conversation, allowing for more
complete and effective communication during the claim resolution
process.

**Call:**

``` language-javascript
curl -X POST -H 'Authorization: Bearer $ACCESS_TOKEN' 

{
 "file"=$FILE_PATH
}

https://api.mercadolibre.com/marketplace/v2/claims/$CLAIM/attachments
```

**Example:**

``` language-javascript
curl -X POST -H 'Authorization: Bearer $ACCESS_TOKEN' 

{
 "file"=@/Users/user/Desktop/file.jpg
}

https://api.mercadolibre.com/marketplace/v2/claims/5294629673/attachments
```

**Response:**

``` language-javascript
{
   "user_id": 1317418851,
   "file_name": "9984c9c8-97da-4e85-860e-d016fbbe61fe.jpeg"
}
```

## Create a Message with the Uploaded File

A player is enabled to send a message **only** if they have the
'send\_message' action assigned to their profile. To verify if this
action is available, the player must check the 'available\_actions' in
the Claim details. This structure ensures that only authorized
participants can interact in the claim process, maintaining organization
and communication efficiency.

The actions that allow sending messages to other claim participants vary
depending on the claim's stage and current status. These actions are
essential for facilitating effective and strategic communication between
the involved parties, dynamically adapting to the specific needs and
circumstances of each claim.

Actions:

| Action                         | Available for            | Receiver    | Claim Stage |
|--------------------------------|--------------------------|-------------|-------------|
| send\_message\_to\_complainant | respondent - mediator    | complainant | claim       |
| send\_message\_to\_respondent  | complainant - mediator   | respondent  | claim       |
| send\_message\_to\_mediator    | complainant - respondent | mediator    | dispute     |

**Parameters:**

| Query params   | Values                            | Value Details                                   |
|----------------|-----------------------------------|-------------------------------------------------|
| message        | String (required)                 | Message in a claim. Cannot be empty.            |
| receiver\_role | mediator, complainant, respondent | Receiver's role. Must be a valid role.          |
| attachments    | Array of strings                  | Name of the previously attached file (optional) |

**Call:**

``` language-javascript
curl -X POST -H 'Authorization: Bearer $ACCESS_TOKEN' 
{
 "receiver_role": "complainant| mediator| respondent",
 "message": "CLAIM MESSAGE",
 "attachments":  ["1317418851_9efe5db7-1910-4184-932b-bb6279c15e37.jpg" ]
}
https://api.mercadolibre.com/marketplace/v2/claims/$CLAIM_ID/actions/send-message
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

The list of attachments will display all the files returned in the
previous POST that are associated with the message, presenting them in
an ordered manner and separated by commas. This feature facilitates
quick and comprehensive visualization of the attached documents,
optimizing information management during the exchange of messages in the
claim process.

</div>

</div>

</div>

</div>

**Attachment example:**

``` language-javascript
curl -X POST -H 'Authorization: Bearer $ACCESS_TOKEN' 
{
 "receiver_role": "complainant",
 "message": "This is a test message",
 "attachments":  ["1317418851_9efe5db7-1910-4184-932b-bb6279c15e37.jpg" ]
}

https://api.mercadolibre.com/marketplace/v2/claims/5294629673/actions/send-message
```

**Response:**

``` language-javascript
"status 201 created"
```

**Example with no attachment:**

``` language-javascript
curl -X POST -H 'Authorization: Bearer $ACCESS_TOKEN' 
{ 
 "receiver_role": "complainant",
 "message": "Prueba sin archivo",
 "attachments":  []
}

https://api.mercadolibre.com/marketplace/v2/claims/5294629673/actions/send-message
```

**Response:**

``` language-javascript
"status 201 created"
```

## Download the file

**Call:**

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' 
https://api.mercadolibre.com/marketplace/v2/claims/$CLAIM_ID/attachments/$ATTACHMENTS_ID/download
```

**Example:**

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/post-purchase/v1/claims/5294629673/attachments/1517482146_31489bf8-95e3-4a2d-bcff-3c57771fb7c4.png/download
```

## Get file information

**Call:**

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' 
https://api.mercadolibre.com/post-purchase/v1/claims/$CLAIM_ID/attachments/$ATTACHMENTS_ID
```

**Example:**

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/post-purchase/v1/claims/5294629673/attachments/example.png
```

**Response:**

``` language-javascript
{
   "filename": "1517482146_31489bf8-95e3-4a2d-bcff-3c57771fb7c4.png",
   "original_filename": "Captura de pantalla 2024-08-22 a la(s) 4.12.28?p.m..png",
   "size": 166960,
   "date_created": "2024-08-22T18:13:09.000-04:00",
   "type": "image/png"
}
```

## Error Responses

When interacting with the Claims Messages API, you may encounter various
error responses. Below are the possible HTTP status codes and their
meanings:

### HTTP Status Codes

| Status Code      | Description                   | Common Causes                                                                                     |
|------------------|-------------------------------|---------------------------------------------------------------------------------------------------|
| 200 OK           | Request successful            | The request was processed correctly.                                                              |
| 201 Created      | Resource created successfully | Message or attachment was created successfully.                                                   |
| 400 Bad Request  | Invalid request               | Empty message body, invalid parameters, malformed request, or duplicate action already performed. |
| 401 Unauthorized | Authentication failed         | Missing or invalid access token, expired token.                                                   |
| 403 Forbidden    | Access denied                 | User not authorized to access the claim, or PolicyAgent denied the request.                       |
| 404 Not Found    | Resource not found            | Claim ID or attachment does not exist.                                                            |

### Error Response Examples

**401 Unauthorized - Missing Authorization Header:**

``` language-javascript
{
    "code": 401,
    "error": "unauthorized_request_error",
    "message": "Invalid caller.id",
    "cause": null
}
```

**400 Bad Request - Malformed Access Token:**

``` language-javascript
{
    "message": "Malformed access_token: INVALID_TOKEN",
    "error": "bad_request",
    "status": 400,
    "cause": []
}
```

**403 Forbidden - Policy Agent Denied Access:**

``` language-javascript
{
    "code": "PA_UNAUTHORIZED_RESULT_FROM_POLICIES",
    "blocked_by": "PolicyAgent",
    "message": "At least one policy returned UNAUTHORIZED.",
    "status": 403
}
```

**404 Not Found - Claim Not Found:**

``` language-javascript
{
    "code": 404,
    "error": "not_found_error",
    "message": "Claim not found. claimId: 9999999999999",
    "cause": null
}
```

<div class="andes-message andes-message--neutral">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--neutral site-carriers__message-title">

Important:

</div>

<div class="andes-message__text--neutral site-carriers__message-text">

<div>

When attempting to access a claim that does not exist or that the user
is not authorized to view, the API may return a **403 Forbidden**
response instead of a **404 Not Found**. This is a security measure
implemented by the PolicyAgent to prevent information disclosure about
the existence of resources.

</div>

</div>

</div>

</div>

Next: [Claims
resolutions](https://global-selling.mercadolibre.com/devsite/manage-claim-resolutions)

</div>
