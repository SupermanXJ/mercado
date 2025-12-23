<div class="inner-content">

## Working with Clips

<div class="details__message">

When posting a new listing, we all know that high-quality images can
make a big difference in attracting buyers—but video can be even more
effective. This guide shows you how to upload, get info, and delete
Clips via API, making the process more integrated and automated than
ever before. Until now, this was only possible through the Global
Selling interface.

</div>

## Considerations for Uploading Clips

-   Clips can only be uploaded for active items.
-   Clips can only be uploaded on the seller's local sites.

The video file must meet the following requirements:

-   Format: MP4, MOV, MPEG, or AVI.
-   Duration: minimum 10 seconds, maximum 61 seconds.
-   Maximum file size: 280 MB.
-   Minimum resolution: 360x640 pixels.
-   Vertical video.

## Upload a Clip

Allows you to upload a clip for a CBT item and specify the sites where
you want it to be available.

Call:

    curl -X POST -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/marketplace/items/{cbt_item_id}/clips/upload
    -H 'Content-Type: multipart/form-data' \
    -F 'file=@{path_to_video_file}' \
    -F 'sites=[
    {
    "site_id":"{site_id_1}",
    "logistic_type":"{logistic_type_1}"
    },
    {
    "site_id":"{site_id_2}",
    "logistic_type":"{logistic_type_2}"
    },
    {
    "site_id":"{site_id_3}",
    "logistic_type":"{logistic_type_3}"
    }
    ]' \

Example:

    curl -X POST -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/marketplace/items/{cbt_item_id}/clips/upload
    -H 'Content-Type: multipart/form-data' \
    -F 'file=@"/Users/karacuna/Downloads/2lkKvX.mp4"' \
    -F 'sites=[
    {
    "site_id":"MLM",
    "logistic_type":"remote"
    },
    {
    "site_id":"MCO",
    "logistic_type":"remote"
    }
    ]' \

<div class="andes-message andes-message--highlight">

<img src="data:image/svg+xml;base64,PHN2ZyAyMDAwIF0oaHR0cDogY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24iIGhlaWdodD0iMTYiIHN2ZyIpIHZpZXdib3g9IjAgMCAxNiAxNiIgd2lkdGg9IjE2IiB3d3cudzMub3JnIHhtbG5zPSJbaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciPjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+PGNpcmNsZSBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbi1vdXRlciIgY3g9IjgiIGN5PSI4IiByPSI3LjI1IiBzdHJva2Utd2lkdGg9IjEuNSI+PC9jaXJjbGU+PGcgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAxNikiPjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24taW5uZXIiIGN4PSI4IiBjeT0iMTEuMTUyIiByPSIxIiB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDIyLjMwMykiPjwvY2lyY2xlPjwvZz48L2c+PC9zdmc+" class="andes-message__icon" />

<div class="andes-message__content">

<div class="andes-message__title andes-message__title--highlight">

Important:

</div>

<div class="andes-message__text--highlight" style="color:white">

If "Sites" is left empty, the clip will be uploaded to all available
sites.

</div>

</div>

</div>

Response:

    {
        "status": "accepted",
        "clip_uuid": "550e8400-e29b-41d4-a716-446655440000",
        "site_ids": [
            {
                "site_id": "MLM",
                "logistic_type": "remote"
            },
            {
                "site_id": "MCO",
                "logistic_type": "remote"
            }
        ]
    }

Example of an error response:

    {
        "message": "Video resolution is lower than 360x640 pixels.",
        "error_status": "bad_request",
        "status": 400
    }

<div class="andes-message andes-message--highlight">

<img src="data:image/svg+xml;base64,PHN2ZyAyMDAwIF0oaHR0cDogY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24iIGhlaWdodD0iMTYiIHN2ZyIpIHZpZXdib3g9IjAgMCAxNiAxNiIgd2lkdGg9IjE2IiB3d3cudzMub3JnIHhtbG5zPSJbaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciPjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+PGNpcmNsZSBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbi1vdXRlciIgY3g9IjgiIGN5PSI4IiByPSI3LjI1IiBzdHJva2Utd2lkdGg9IjEuNSI+PC9jaXJjbGU+PGcgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAxNikiPjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24taW5uZXIiIGN4PSI4IiBjeT0iMTEuMTUyIiByPSIxIiB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDIyLjMwMykiPjwvY2lyY2xlPjwvZz48L2c+PC9zdmc+" class="andes-message__icon" />

<div class="andes-message__content">

<div class="andes-message__title andes-message__title--highlight">

Important:

</div>

<div class="andes-message__text--highlight" style="color:white">

Uploading clips is subject to a limit set by the daily review capacity
of the moderation team, which is capped at 1,000 clips per day.

</div>

</div>

</div>

## Get Clips info of an item

Returns all clips for a CBT item and their status by site.

Call:

    curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/marketplace/items/$cbt_item_id/clips

Example:

    curl -X GET -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/marketplace/items/CBT2215534590/clips

Response:

    {
        "parent_item_id": "CBT2215534590",
        "parent_user_id": "757729744",
        "clips": [
            {
                "clip_uuid": "46875e1b-4210-4fdc-b189-e9cc144bd211",
                "metadata": [
                    {
                        "site_id": "MCO",
                        "logistic_type": "remote",
                        "item_id": "MCO2753472790",
                        "user_id": 798579194,
                        "moderation_status": "PUBLISHED"
                    },
                    {
                        "site_id": "MLM",
                        "logistic_type": "remote",
                        "item_id": "MLM2193219951",
                        "user_id": 757732742,
                        "moderation_status": "REJECTED",
                        "moderation_reasons": {
                            "VIDEO_PROCESSING_ERROR": "It was not possible to process your video file. Please try uploading a new one.",
                            "DUPLICATED_VIDEO": "This video had already been uploaded before."
                        }
                    }
                ]
            },
            {
                "clip_uuid": "b56847e2-0d0e-4770-84fe-4141814e6fd7",
                "metadata": [
                    {
                        "site_id": "MCO",
                        "logistic_type": "remote",
                        "item_id": "MCO2753472790",
                        "user_id": 798579194,
                        "moderation_status": "UNDER_REVIEW"
                    }
                ]
            },
            {
                "clip_uuid": "9705bf50-0ceb-435c-b5c9-010e0a8914af",
                "metadata": [
                    {
                        "site_id": "MLC",
                        "logistic_type": "remote",
                        "item_id": "MLC2789734556",
                        "user_id": 757732112,
                        "moderation_status": "UNDER_REVIEW"
                    }
                ]
            },
            {
                "clip_uuid": "4e737ded-5d48-472f-8c6e-9c9ac9a87d53",
                "metadata": [
                    {
                        "site_id": "MLM",
                        "logistic_type": "remote",
                        "item_id": "MLM2193219951",
                        "user_id": 757732742,
                        "moderation_status": "UNDER_REVIEW"
                    },
                    {
                        "site_id": "MLC",
                        "logistic_type": "remote",
                        "item_id": "MLC2789734556",
                        "user_id": 757732112,
                        "moderation_status": "UNDER_REVIEW"
                    }
                ]
            },
            {
                "clip_uuid": "c69658ac-f1f8-4860-b56b-be9f285a9edf",
                "metadata": [
                    {
                        "site_id": "MCO",
                        "logistic_type": "remote",
                        "item_id": "MCO2753472790",
                        "user_id": 798579194,
                        "moderation_status": "UNDER_REVIEW"
                    },
                    {
                        "site_id": "MLM",
                        "logistic_type": "remote",
                        "item_id": "MLM2193219951",
                        "user_id": 757732742,
                        "moderation_status": "UNDER_REVIEW"
                    }
                ]
            }
        ]
    }

Example of an error response:

    {
        "message": "Item not found: CBT999",
        "error_status": "not_found",
        "status": 404
    }

Possible Statuses:

-   UNDER\_REVIEW: Moderation ongoing.
-   REJECTED: Rejected due to content or technical specifications.
-   PUBLISHED: Approved and published.
-   TRANSCODING\_REJECTED, PAUSED: Technical or commercial status.

<div class="andes-message andes-message--highlight">

<img src="data:image/svg+xml;base64,PHN2ZyAyMDAwIF0oaHR0cDogY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24iIGhlaWdodD0iMTYiIHN2ZyIpIHZpZXdib3g9IjAgMCAxNiAxNiIgd2lkdGg9IjE2IiB3d3cudzMub3JnIHhtbG5zPSJbaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciPjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+PGNpcmNsZSBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbi1vdXRlciIgY3g9IjgiIGN5PSI4IiByPSI3LjI1IiBzdHJva2Utd2lkdGg9IjEuNSI+PC9jaXJjbGU+PGcgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAxNikiPjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24taW5uZXIiIGN4PSI4IiBjeT0iMTEuMTUyIiByPSIxIiB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDIyLjMwMykiPjwvY2lyY2xlPjwvZz48L2c+PC9zdmc+" class="andes-message__icon" />

<div class="andes-message__content">

<div class="andes-message__title andes-message__title--highlight">

Important:

</div>

<div class="andes-message__text--highlight" style="color:white">

Changing the "moderation\_status" from UNDER\_REVIEW to any other
status, as well as publishing the video if it passes moderation, takes
between 24 and 48 hours. This is the estimated timeframe needed to
complete the moderation review process.

</div>

</div>

</div>

## Delete a Clip

Deletes a clip from a CBT item on one or more sites.

Call:

    curl -X DELETE -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/marketplace/items/$cbt_item_id/clips/$clip_relation_id
    -H 'Content-Type: multipart/form-data' \
    -F 'file=@{path_to_video_file}' \
    -F 'sites=[
    {
    "site_id":"{site_id_1}",
    "logistic_type":"{logistic_type_1}"
    },
    {
    "site_id":"{site_id_2}",
    "logistic_type":"{logistic_type_2}"
    },
    {
    "site_id":"{site_id_3}",
    "logistic_type":"{logistic_type_3}"
    }
    ]' \

Example:

    curl -X DELETE -H 'Authorization: Bearer $ACCESS_TOKEN' https://api.mercadolibre.com/marketplace/items/CBT2215534590/clips/c69658ac-f1f8-4860-b56b-be9f285a9edf
    -H 'Content-Type: multipart/form-data' \
    -F 'file=@{path_to_video_file}' \
    -F 'sites=[
    {
    "site_id":"MLM",
    "logistic_type":"remote"
    },
    {
    "site_id":"MLC",
    "logistic_type":"remote"
    },
    {
    "site_id":"MLB",
    "logistic_type":"remote"
    }
    ]' \

<div class="andes-message andes-message--highlight">

<img src="data:image/svg+xml;base64,PHN2ZyAyMDAwIF0oaHR0cDogY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24iIGhlaWdodD0iMTYiIHN2ZyIpIHZpZXdib3g9IjAgMCAxNiAxNiIgd2lkdGg9IjE2IiB3d3cudzMub3JnIHhtbG5zPSJbaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciPjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+PGNpcmNsZSBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbi1vdXRlciIgY3g9IjgiIGN5PSI4IiByPSI3LjI1IiBzdHJva2Utd2lkdGg9IjEuNSI+PC9jaXJjbGU+PGcgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAxNikiPjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24taW5uZXIiIGN4PSI4IiBjeT0iMTEuMTUyIiByPSIxIiB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDIyLjMwMykiPjwvY2lyY2xlPjwvZz48L2c+PC9zdmc+" class="andes-message__icon" />

<div class="andes-message__content">

<div class="andes-message__title andes-message__title--highlight">

Important:

</div>

<div class="andes-message__text--highlight" style="color:white">

If "Sites" is left empty, the clip will be deleted from all available
sites.

</div>

</div>

</div>

Response:

    [
        {
            "status": "DELETED",
            "site_id": "MLM",
            "logistic_type": "remote"
        },
        {
            "status": "NOT_FOUND",
            "site_id": "MLC",
            "logistic_type": "remote"
        },
        {
            "status": "NOT_FOUND",
            "site_id": "MLB",
            "logistic_type": "remote"
        },
        {
            "status": "ERROR",
            "site_id": "MCO",
            "logistic_type": "remote"
        }
    ]

Example of an error response:

    {
        "message": "Item not found: CBT999",
        "error_status": "not_found",
        "status": 404
    }

<div class="andes-message andes-message--highlight">

<img src="data:image/svg+xml;base64,PHN2ZyAyMDAwIF0oaHR0cDogY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24iIGhlaWdodD0iMTYiIHN2ZyIpIHZpZXdib3g9IjAgMCAxNiAxNiIgd2lkdGg9IjE2IiB3d3cudzMub3JnIHhtbG5zPSJbaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciPjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+PGNpcmNsZSBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbi1vdXRlciIgY3g9IjgiIGN5PSI4IiByPSI3LjI1IiBzdHJva2Utd2lkdGg9IjEuNSI+PC9jaXJjbGU+PGcgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAxNikiPjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24taW5uZXIiIGN4PSI4IiBjeT0iMTEuMTUyIiByPSIxIiB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDIyLjMwMykiPjwvY2lyY2xlPjwvZz48L2c+PC9zdmc+" class="andes-message__icon" />

<div class="andes-message__content">

<div class="andes-message__title andes-message__title--highlight">

Important:

</div>

<div class="andes-message__text--highlight" style="color:white">

Clips can be deleted regardless of their assigned 'moderation\_status'
category.

</div>

</div>

</div>

## Errors

### Upload errors (POST /marketplace/items/{cbt\_item\_id}/clips/upload)

| HTTP Code | Error                   | Message                                                                             | Details                                                                                                    | Solution                                                                                                                                                                                                                                                                                                                                                                                                                                   |
|-----------|-------------------------|-------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 404       | not\_found              | Item not found: {cbt\_item\_id}                                                     | The CBT item id was not found                                                                              | Enter a valid CBT item id                                                                                                                                                                                                                                                                                                                                                                                                                  |
| 401       | unauthorized            | invalid access token                                                                | Invalid token                                                                                              | Make sure your application scopes are "read" and "write"<span style="color:#e84a5f">.</span> Update the token<span style="color:#e84a5f">.</span>                                                                                                                                                                                                                                                                                          |
| 401       | unauthorized            | User does not have permission to access this resource                               | The user does not have permissions to upload clips<span style="color:#e84a5f">.</span>                     | The user is a test user not whitelisted, or the CBT user was not found or does not exist<span style="color:#e84a5f">.</span>                                                                                                                                                                                                                                                                                                               |
| 400       | bad\_request            | INVALID\_EXTENSION                                                                  | File type not allowed<span style="color:#e84a5f">.</span>                                                  | Upload a video file with mp4, mov, mpeg, or avi extensions<span style="color:#e84a5f">.</span>                                                                                                                                                                                                                                                                                                                                             |
| 400       | bad\_request            | Invalid JSON format for 'sites'                                                     | JSON format for the "sites" field does not meet the required structure<span style="color:#e84a5f">.</span> | Check the JSON format, make sure to include "site\_id" and "logistic\_type"<span style="color:#e84a5f">.</span>                                                                                                                                                                                                                                                                                                                            |
| 400       | bad\_request            | INVALID\_MIN\_VIDEO\_DURATION                                                       | The video duration is shorter than allowed<span style="color:#e84a5f">.</span>                             | Make sure the video duration is longer than 10 seconds<span style="color:#e84a5f">.</span>                                                                                                                                                                                                                                                                                                                                                 |
| 400       | bad\_request            | INVALID\_MAX\_VIDEO\_DURATION                                                       | The video duration is longer than allowed<span style="color:#e84a5f">.</span>                              | Make sure the video does not exceed 61 seconds<span style="color:#e84a5f">.</span>                                                                                                                                                                                                                                                                                                                                                         |
| 400       | not\_found              | The itemId does not exist, is invalid, inactive, or does not belong to the seller   | The Cbt item is not active or does not belong to the seller<span style="color:#e84a5f">.</span>            | Make sure the CBT item is active and belongs to the CBT user making the request<span style="color:#e84a5f">.</span>                                                                                                                                                                                                                                                                                                                        |
| 400       | bad\_request            | The 'file' field is required<span style="color:#e84a5f">.</span>                    | The request does not include the 'file' field<span style="color:#e84a5f">.</span>                          | Add the "file" field in the request<span style="color:#e84a5f">.</span>                                                                                                                                                                                                                                                                                                                                                                    |
| 400       | bad\_request            | REQUIRED\_VIDEO                                                                     | The request does not include a video file<span style="color:#e84a5f">.</span>                              | Attach a video file in the "file" field of the request<span style="color:#e84a5f">.</span>                                                                                                                                                                                                                                                                                                                                                 |
| 400       | bad\_request            | Request Entity Too Large                                                            | The video file size exceeds the limit (280MB)<span style="color:#e84a5f">.</span>                          | Upload a video that does not exceed 280 MB<span style="color:#e84a5f">.</span>                                                                                                                                                                                                                                                                                                                                                             |
| 400       | bad\_request            | Error processing video file<span style="color:#e84a5f">.</span>                     | An I/O error occurred while trying to read the video properties<span style="color:#e84a5f">.</span>        | The file may be slightly damaged or was exported in a non-standard format<span style="color:#e84a5f">.</span> Preprocess the video in tools like HandBrake and save it as a new file<span style="color:#e84a5f">.</span> Open the file in a video editor and make sure to use common export settings, like 'MP4' with the 'H<span style="color:#e84a5f">.</span>264' video codec and 'AAC' audio codec<span style="color:#e84a5f">.</span> |
| 400       | bad\_request            | La calidad del video es menor a 360x640 pixeles<span style="color:#e84a5f">.</span> | The video resolution is lower than the required minimum<span style="color:#e84a5f">.</span>                | Rescale the video to a higher resolution using editing tools (HandBrake)<span style="color:#e84a5f">.</span> Set the resolution to at least 360x640 pixels<span style="color:#e84a5f">.</span>                                                                                                                                                                                                                                             |
| 500       | internal\_server\_error | (Any error from server)                                                             | Error associated with saving information in databases or connections<span style="color:#e84a5f">.</span>   | Retry the request<span style="color:#e84a5f">.</span>                                                                                                                                                                                                                                                                                                                                                                                      |

### Get errors (GET /items/{cbt\_item\_id}/clips)

| HTTP Code | Error                   | Message                                                                                                                                                 | Details                                                                                                     | Solution                                                                                                                                          |
|-----------|-------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------|
| 404       | not\_found              | Item not found: {cbt\_item\_id}                                                                                                                         | The CBT item id was not found                                                                               | Enter a valid CBT item id                                                                                                                         |
| 401       | authentication\_error   | Authentication Error                                                                                                                                    | Invalid token                                                                                               | Make sure your application scopes are "read" and "write"<span style="color:#e84a5f">.</span> Update the token<span style="color:#e84a5f">.</span> |
| 401       | unauthorized            | User does not have permission to access this resource                                                                                                   | The user does not have permissions to query clips<span style="color:#e84a5f">.</span>                       | The user is a test user not whitelisted, or the CBT user was not found or does not exist<span style="color:#e84a5f">.</span>                      |
| 404       | not\_found              | No clips found for itemId: {cbt\_item\_id}                                                                                                              | The CBT item exists, but has no associated clips<span style="color:#e84a5f">.</span>                        | Make sure to verify that the correct CBT item exists<span style="color:#e84a5f">.</span>                                                          |
| 500       | internal\_server\_error | Unexpected error: The itemId does not exist<span style="color:#e84a5f">.</span><span style="color:#e84a5f">.</span><span style="color:#e84a5f">.</span> | Error associated with saving information in databases or the connection<span style="color:#e84a5f">.</span> | Retry the request<span style="color:#e84a5f">.</span>                                                                                             |

### Delete errors (DELETE /items/{cbt\_item\_id})

| HTTP Code | Error                   | Message                                                                                                                                                 | Details                                                                                                     | Solution                                                                                                                                          |
|-----------|-------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------|
| 404       | not\_found              | Item not found: {cbt\_item\_id}                                                                                                                         | The CBT item id was not found                                                                               | Enter a valid CBT item id                                                                                                                         |
| 401       | authentication\_error   | Authentication Error                                                                                                                                    | Invalid token                                                                                               | Make sure your application scopes are "read" and "write"<span style="color:#e84a5f">.</span> Update the token<span style="color:#e84a5f">.</span> |
| 403       | unauthorized            | User does not have permission to access this resource                                                                                                   | The user does not have permissions to delete clips<span style="color:#e84a5f">.</span>                      | The user is a test user not whitelisted, or the CBT user was not found or does not exist<span style="color:#e84a5f">.</span>                      |
| 404       | not\_found              | No valid sites found for itemId: {cbt\_item\_id}                                                                                                        | The sites provided in the request are not found                                                             | Make sure the sites are correct and exist for the CBT item<span style="color:#e84a5f">.</span>                                                    |
| 404       | not\_found              | The clipUuid: {clip\_uuid} was not found in the clips of itemId: {cbt\_item\_id}                                                                        | The clip was not found<span style="color:#e84a5f">.</span>                                                  | Make sure the clip\_relation\_id is correct<span style="color:#e84a5f">.</span>                                                                   |
| 500       | internal\_server\_error | Unexpected error: The itemId does not exist<span style="color:#e84a5f">.</span><span style="color:#e84a5f">.</span><span style="color:#e84a5f">.</span> | Error associated with saving information in databases or the connection<span style="color:#e84a5f">.</span> | Retry the request<span style="color:#e84a5f">.</span>                                                                                             |

</div>
