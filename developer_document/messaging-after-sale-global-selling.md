<div class="inner-content">

<div class="post-sale-messaging">

## Post-sale messages

Post-sale messaging is a tool that enables private communication between
sellers and buyers after a sale is completed. Through the **Messaging
API**, you can create, retrieve, and manage messages (including
attachments) for specific orders.

  

### How it works

-   **Initiating contact:** To improve user experience and reduce
    operational load, sellers must **choose a reason** when starting a
    new conversation. This helps avoid unnecessary automatic
    communications.
-   **Responding:** Buyers can contact the seller at any time. In these
    instances, the seller can respond normally without needing to select
    a reason.

See more about [after-sales service with
messages](https://sellers.mercadolibre.com/news/after-sales-service/).

</div>

## Parameters

| Parameter       | Type    | Description                                      |
|-----------------|---------|--------------------------------------------------|
| **from**        | object  | Message sender information                       |
| **to**          | object  | Message recipient information                    |
| **user\_id**    | integer | User ID (sender or recipient)                    |
| **text**        | string  | Message content                                  |
| **attachments** | array   | Attached files                                   |
| **site\_id**    | string  | Mercado Libre site (MLM, MLB, MCO, MLC)          |
| **limit**       | integer | Maximum number of results to return (pagination) |
| **offset**      | integer | Number of results to skip (pagination)           |

  

## Get messages by pack

Retrieve all messages associated with a specific order pack. This
endpoint returns the conversation history between seller and buyer,
including message content, attachments, moderation status, and
translation information.

Request:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/marketplace/messages/packs/$PACK_ID
```

Example:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' 'https://api.mercadolibre.com/marketplace/messages/packs/2315686468?limit=2&offset=0'
```

Response:

``` language-javascript
{
  "paging": {
    "limit": 2,
    "offset": 0,
    "total": 5
  },
  "conversation_status": {
    "claim_ids": null,
    "shipping_id": null,
    "status": "active",
    "status_date": "2020-02-26T17:37:42Z",
    "status_update_allowed": false,
    "substatus": null
  },
  "messages": [{
    "id": "2d45a5ad186041659e9a608f0c109dff",
    "site_id": "MLM",
    "client_id": 1344270061107690,
    "from": {
      "user_id": 523132944,
      "name": "TESTNICOCBT TESTNICOCBT"
    },
    "to": {
      "user_id": 441782523,
      "name": "Test Test"
    },
    "status": "available",
    "subject": null,
    "text": "This is a message to buyer",
    "message_date": {
      "received": "2020-03-13T15:14:10Z",
      "available": "2020-03-13T15:14:10Z",
      "notified": null,
      "created": "2020-03-13T15:14:10Z",
      "read": null
    },
    "message_moderation": {
      "status": "clean",
      "reason": null,
      "source": "online",
      "moderation_date": "2020-03-13T15:14:10Z"
    },
    "message_attachments": [{
      "filename": "471826944_ba20cdf4-26b4-4c21-a689-5eabe271ddb3.png",
      "original_filename": "FileName.png",
      "type": "image/png",
      "size": 536766,
      "potential_security_threat": false,
      "creation_date": "2020-03-13T15:14:10Z"
    }],
    "message_resources": [{
      "id": "2315686468",
      "name": "packs"
    }, {
      "id": "523132944",
      "name": "sellers"
    }],
    "conversation_first_message": false,
    "text_translated": "Este es un mensaje para el comprador"
  }]
}
```

### Response fields

**Paging object:**

-   **limit:** Maximum number of results returned.
-   **offset:** Number of results skipped.
-   **total:** Total number of messages in the conversation.

**Conversation Status object:**

-   **claim\_ids:** Array of claim IDs if a claim is associated (null if
    none).
-   **shipping\_id:** Shipment ID associated with the order.
-   **status:** Current conversation status (active, blocked).
-   **status\_date:** Date when the status was last updated (UTC).
-   **status\_update\_allowed:** Whether the conversation status can be
    changed.
-   **substatus:** Additional status detail.

**Messages array:**

-   **id:** Unique message identifier.
-   **site\_id:** Mercado Libre site (MLM, MLB, MCO, MLC).
-   **client\_id:** Application client ID that sent the message.
-   **from / to:** Sender and recipient information (user\_id, name).
-   **status:** Message availability status (available, blocked).
-   **text:** Original message content.
-   **text\_translated:** Message translated to the counterpart's
    language.
-   **conversation\_first\_message:** Whether this is the first message
    in the conversation.

**Message Date object:**

-   **received:** Timestamp when the message was received.
-   **available:** Timestamp when the message became available.
-   **notified:** Timestamp when the recipient was notified.
-   **created:** Timestamp when the message was created.
-   **read:** Timestamp when the message was read (null if unread).

**Message Moderation object:**

-   **status:** Moderation result (clean, blocked, pending).
-   **reason:** Reason for moderation action.
-   **source:** Where moderation occurred (online, offline).
-   **moderation\_date:** Timestamp of moderation.

**Message Attachments array:**

-   **filename:** System-generated filename.
-   **original\_filename:** Original file name uploaded by user.
-   **type:** MIME type of the file.
-   **size:** File size in bytes.
-   **potential\_security\_threat:** Whether the file was flagged as
    potentially harmful.
-   **creation\_date:** Timestamp when the attachment was uploaded.

<div class="andes-message andes-message--neutral">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--neutral site-carriers__message-title">

Note:

</div>

<div class="andes-message__text--neutral site-carriers__message-text">

<div>

All timestamps are in UTC timezone.

</div>

</div>

</div>

</div>

## Get message by ID

Retrieve a specific message using its unique identifier. This endpoint
is useful when you need to fetch details of a single message, such as
when processing a notification or displaying a specific message thread
item.

Request:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/marketplace/messages/$MESSAGE_ID
```

Example:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/marketplace/messages/2d45a5ad186041659e9a608f0c109dff
```

Response:

``` language-javascript
{
  "paging": null,
  "conversation_status": null,
  "messages": [{
    "id": "testmessage1123456",
    "site_id": "MLM",
    "client_id": 818828848883,
    "from": {
      "user_id": 1234567,
      "name": ""
    },
    "to": {
      "user_id": 7654321,
      "name": ""
    },
    "status": "available",
    "subject": null,
    "text": "This is a test message",
    "message_date": {
      "received": "2021-09-26T04:48:25Z",
      "available": "2021-09-26T04:48:25Z",
      "notified": "2021-09-26T04:48:25.000Z",
      "created": "2021-09-26T04:48:25Z",
      "read": null
    },
    "message_moderation": {
      "status": "clean",
      "reason": null,
      "source": "online",
      "moderation_date": "2021-09-26T04:48:25Z"
    },
    "message_attachments": null,
    "message_resources": [{
      "id": "2000002725708674",
      "name": "packs"
    }, {
      "id": "534272725",
      "name": "sellers"
    }],
    "conversation_first_message": false,
    "text_translated": "Este es un mensaje de prueba"
  }]
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

When retrieving a single message by ID, **paging** and
**conversation\_status** return null. Use Get Messages by Pack for
conversation context.

</div>

</div>

</div>

</div>

## Upload attachment

<div class="andes-message andes-message--highlight">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--highlight site-carriers__message-title">

Important:

</div>

<div class="andes-message__text--highlight site-carriers__message-text">

<div>

As of August 12, 2022, the **site\_id** parameter is mandatory when
uploading attachments.

</div>

</div>

</div>

</div>

Save a file to be attached to a message. Before sending a message with
an attachment, you must first upload the file using this endpoint. The
response returns a unique file ID that you will use when creating the
message.

Request:

``` language-javascript
curl -X POST -H 'Authorization: Bearer $ACCESS_TOKEN' \
-H 'Content-Type: multipart/form-data' \
-F 'file=@/path/to/file' \
'https://api.mercadolibre.com/marketplace/messages/attachments?site_id=$SITE_ID'
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

\- The POST must be sent as **multipart/form-data** with the file in the
**file** field.  
- Maximum file size: **25 MB**.  
- Maximum attachments per message: **25 files**.  
- Allowed MIME types:  
`text/plain`  
`image/png`  
`image/jpeg`  
`image/heif`  
`image/heic`  
`application/pdf`  
`application/msword`  
`application/vnd.ms-excel`  
`text/xml, application/xml`  
`application/octet-stream`  
If you upload a file type not listed, the API will return HTTP Status
Code 400.

</div>

</div>

</div>

</div>

Example:

``` language-javascript
curl -X POST -H 'Authorization: Bearer $ACCESS_TOKEN' \
-H 'Content-Type: multipart/form-data' \
-F 'file=@/home/user/documents/invoice.jpg' \
'https://api.mercadolibre.com/marketplace/messages/attachments?site_id=MLM'
```

Response:

``` language-javascript
{
  "id": "210438685_59f0f034-db1b-4ea6-8c5e-1d34e2092482.jpg"
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

Use the returned **id** in the **attachments** array when creating a
message.

</div>

</div>

</div>

</div>

## Create message

Send a new message to the buyer associated with a specific order pack.
Use this endpoint to communicate with buyers about their orders, provide
tracking information, or respond to inquiries.

Request:

``` language-javascript
curl -X POST -H 'Authorization: Bearer $ACCESS_TOKEN' \
-H 'Content-Type: application/json' \
-d '{"text": "$MESSAGE_TEXT", "text_translated": "$TRANSLATED_TEXT", "attachments": ["$ATTACHMENT_ID"]}' \
'https://api.mercadolibre.com/marketplace/messages/packs/$PACK_ID'
```

Example:

``` language-javascript
curl -X POST -H 'Authorization: Bearer $ACCESS_TOKEN' \
-H 'Content-Type: application/json' \
-d '{
  "text": "Your order has been shipped! Track it here.",
  "text_translated": "¡Tu pedido ha sido enviado! Rastréalo aquí.",
  "attachments": [
    "471826944_ba20cdf4-26b4-4c21-a689-5eabe271ddb3.png"
  ]
}' \
'https://api.mercadolibre.com/marketplace/messages/packs/2315686468'
```

Example (without attachments):

``` language-javascript
curl -X POST -H 'Authorization: Bearer $ACCESS_TOKEN' \
-H 'Content-Type: application/json' \
-d '{
  "text": "Thank you for your purchase!",
  "text_translated": "¡Gracias por tu compra!"
}' \
'https://api.mercadolibre.com/marketplace/messages/packs/2315686468'
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

\- The **attachments** array contains file IDs obtained from the [Upload
attachment](#Upload-save-messages) endpoint.  
- If you don't need to attach files, omit the **attachments** field from
the request body.  
- Use **text\_translated** to provide the message in the buyer's
language for better communication.  
- To include a clickable link, use HTML anchor tags:
`<a href="your_url">Your tracking link</a>`

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

\- There are messaging limits in place. If you receive a 403 error
indicating you cannot send more messages, it typically means the seller
has already responded and must wait for the buyer's reply, or the
conversation has reached its messaging cap.  
- If you receive an error indicating that it is not possible to send the
message, check the conversation status and blocking reasons in the
[Blocked
messages](https://global-selling.mercadolibre.com/devsite/blocked-messages-gs)
documentation.

</div>

</div>

</div>

</div>

## Get attachment

Download an attachment file from a message. Use this endpoint to
retrieve files that were shared in the post-sale conversation, such as
invoices, shipping labels, or product images.

Request:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' 'https://api.mercadolibre.com/marketplace/messages/attachments/$ATTACHMENT_ID?tag=$TAG&site_id=$SITE_ID'
```

Example:

``` language-javascript
curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' 'https://api.mercadolibre.com/marketplace/messages/attachments/76601286_5946e4c4-168a-45fd-945e-b8f0c306c58d.png?tag=post_sale&site_id=MLM'
```

Response:

If the request is successful, the endpoint returns the **binary file
content** directly. Save the response to a file with the appropriate
extension.

In case the file cannot be accessed, the server response will be:

``` language-javascript
{
  "message": "File can not be accessed, try it later",
  "error": null,
  "status": 500,
  "cause": []
}
```

In case the access token is not sent, the response will be:

``` language-javascript
{
  "message": "Access token is required",
  "error": "bad_request",
  "status": 400,
  "cause": []
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

The **attachment\_id** is obtained from the
**message\_attachments\[\].filename** field in the message response.

</div>

</div>

</div>

</div>

##  Errors

| Error code | Message                                                       | Solution                                                                                                                                                             |
|------------|---------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 400        | Attachment empty or null                                      | Attach a valid file to the request                                                                                                                                   |
|            | File name cannot include characters such as: /, \\            | Remove special characters (/ and \\) from the filename                                                                                                               |
|            | File size exceeds 25 Mb                                       | Reduce the file size to under 25 MB                                                                                                                                  |
|            | Message exceeds allowed number of attachments: 25             | Reduce the number of attachments to 25 or fewer                                                                                                                      |
|            | Messages id empty or invalid                                  | Provide a valid message ID in the request                                                                                                                            |
|            | The specified message id: {id} does not exists                | Verify the message ID exists using Get Messages by Pack                                                                                                              |
|            | Not allowed messages from multiple orders                     | Ensure all message IDs belong to the same order                                                                                                                      |
|            | The limit param must be greater than 0                        | Set the limit query parameter to a value greater than 0                                                                                                              |
|            | Invalid offset or limit param                                 | Verify offset and limit are valid positive integers                                                                                                                  |
|            | Access token is required                                      | Include a valid access token in the Authorization header                                                                                                             |
|            | Text is required                                              | Include a non-empty text field when creating a message                                                                                                               |
| 403        | User access token invalid for resource {resource\_id}         | Use an access token that has permission to access this resource                                                                                                      |
|            | Can not identify the user                                     | Ensure the access token belongs to the seller of this order                                                                                                          |
|            | You are not allowed to execute the option OTHER again         | The seller has reached the messaging limit. Wait for buyer response or check [Blocked messages](https://global-selling.mercadolibre.com/devsite/blocked-messages-gs) |
| 404        | The message with id: {id} could not be retrieved from storage | The message was not found. Try again in a few seconds or verify the ID                                                                                               |
|            | Order do not exists                                           | Verify the pack\_id is correct and the order exists                                                                                                                  |
| 500        | Requested file could not be obtained                          | The file cannot be accessed. Try again later                                                                                                                         |
|            | File can not be saved, try it later                           | Server error when saving the file. Retry the upload                                                                                                                  |
|            | File can not be accessed, try it later                        | The attachment is temporarily unavailable. Retry after a few seconds                                                                                                 |

  

**Next**: [Pending
messages](https://global-selling.mercadolibre.com/devsite/pending-messages-gs).

</div>
