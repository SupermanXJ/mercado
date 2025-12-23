<div class="inner-content">

## Authentication and Authorization

<div class="details__message">

To start using our resources, you need to develop the processes of
Authentication and Authorization to get access tokens. This way, you can
work with the private resources for each user once authorization is
granted by your application.

</div>

## Send access token by header

For security, you must send the access token by header every time you
make calls to the API. The header for the Authorization is:

``` language-javascript
curl -H 'Authorization: Bearer APP_USR-12345678-031820-X-12345678'
```

And for example, making a GET to the /users/me resource it would be:

``` language-javascript
curl -H 'Authorization: Bearer APP_USR-12345678-031820-X-12345678' \
https://api.mercadolibre.com/users/me
```

  

## Authentication

Is used to verify a person's identity based on one or several factors,
ensuring the sender's data are correct. Although there are different
methods, in Global Selling we authenticate ourselves by entering our
username and password.

  

## Authorization

Is the process whereby we allow someone or something to access private
resources. In this process, it must be defined which resources and
operations can be performed ("read only" or "read and write"). **How get
authorization?** Via the OAuth 2.0 Protocol, which is one of the most
widely used protocols in open platforms (Twitter, Facebook, etc.) and a
secure method to work with private resources. This protocol offers:
confidentiality, integrity and availability.

  

## Server side flow

In Mercado Libre we are using Authorization Code Grant Type. Is better
suited for applications executing the server-side code such as,
applications developed in Java, Grails, Go, etc. The process you will be
performing is as follows:

<img src="https://http2.mlstatic.com/storage/developers-site-cms-admin/141286798674-Captura-de-Tela-2025-12-15-a-s-14.38.45.png" class="alignnone size-full wp-image-8028" width="700" height="550" alt="flujo_serverside" />  
  

## Get access token

### 1. Login and Authenticate with your Mercado Libre account

You can use the same user who created the application to test the flow.

<img src="https://http2.mlstatic.com/storage/developers-site-cms-admin/141286798674-Captura-de-Tela-2025-12-15-a-s-14.38.53.png" class="alignnone size-full wp-image-8028" style="width:100.0%" alt="login_screen" />  
  

<div class="andes-message andes-message--neutral">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--neutral site-carriers__message-title">

Notes:

</div>

<div class="andes-message__text--neutral site-carriers__message-text">

<div>

\- You can also [use test
users](https://global-selling.mercadolibre.com/devsite/start-testing-global-selling).  
- Remember that the user who logs in must be a manager, so the obtained
access\_token has sufficient permissions to perform the requests.  
- If the user is an operator or partner, the grant will be invalid.  
- The following events may cause an access\_token to become invalid
before its expiration time:

-   The user changes their password.
-   The application refreshes its App Secret.
-   The user revokes permissions to your application.
-   The application is not used to make any request to
    https://api.mercadolibre.com/ for 4 months.

</div>

</div>

</div>

</div>

  

### 2. Place the URL in your browser to get authorization

**APP\_ID:** id of application.  
**YOUR\_URL:** the redirect URI that you add when creating the app.

``` language-javascript
https://global-selling.mercadolibre.com/authorization?response_type=code&client_id=$APP_ID&redirect_uri=$YOUR_URL
```

You will receive the following parameters are optional and only apply if
the app has enabled the **PKCE** flow (Proof Key for Code Exchange):

-   **code\_challenge:** verification code generated from code\_verifier
    and encrypted with code\_challenge\_method.
-   **code\_challenge\_method:** method used to generate the code
    challenge. The following values are currently supported:
    -   S256: specifies that the code\_challenge is using the SHA-256
        encryption algorithm.
    -   plain: the same code\_verifier is sent as code\_challenge. For
        security reasons, it is not recommended to use this method.

<div class="andes-message andes-message--warning">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div class="andes-message__text--warning site-carriers__message-text">

The redirect\_uri has to match exactly what is registered in your
application settings to avoid access errors; the URL cannot contain
variable information.

</div>

</div>

</div>

<img src="https://http2.mlstatic.com/storage/developers-site-cms-admin/141286798674-Captura-de-Tela-2025-12-15-a-s-14.39.05.png" class="alignnone size-full wp-image-8028" style="width:100.0%" alt="redirect_uri_error" />  
  

### 3. Users will be redirected to the following screen to accept associate the application with their account

<img src="https://http2.mlstatic.com/storage/developers-site-cms-admin/141286798674-Captura-de-Tela-2025-12-15-a-s-14.39.10.png" class="alignnone size-full wp-image-8028" style="width:100.0%" alt="authorization_screen" />  
  

Once they click in Authorize, you will get a confirmation message and at
the URL, the parameter CODE has been added.

``` language-javascript
http://YOUR_REDIRECT_URI?code=$TG-CODE
```

This code will be used when an access\_token needs to be generated, it
will grant access to our API.

  

### 4. Changing the code for access token

#### Mandatory parameters

**grant\_type:** authorization\_code, it shows that the desired
operation is to exchange the "code" for an access\_token.  
**client\_id:** is the APP ID of the application that you created.  
**client\_secret:** Secret Key generated when the app was created.  
**code:** The authorization code obtained in the previous step.  
**redirect\_uri:** Redirect URI set for your application.

``` language-javascript
curl -X POST -H 'accept: application/json' -H 'content-type: application/x-www-form-urlencoded' https://api.mercadolibre.com/oauth/token?grant_type=authorization_code&client_id=$APP_ID&client_secret=$CLIENT_SECRET&code=$TG_CODE&redirect_uri=$REDIRECT_URL
```

Response:

``` language-javascript
{
    "access_token": "APP_USR-5387223166827464-090515-8cc4448aac10d5105474e135355a8321-8035443",
    "token_type": "bearer",
    "expires_in": 10800,
    "scope": "offline_access read write",
    "user_id": 8035443,
    "refresh_token": "TG-5b9032b4e4b0714aed1f959f-8035443"
}
```

The **access\_token is valid for 6 hours from the moment it was
generated.** To get more time, we recommend get **refresh token (new
access\_token which is valid for 6 months).** Save it to use each time
it expires. We only allow using the last refresh token generated.
Additionally, remember that the refresh token is single-use, and you
will receive a new one with each token refresh process.

  

### 5. Refresh token

#### Mandatory parameters

**grant\_type:** refresh\_token It shows that the desired operation is
to refresh a token.  
**refresh\_token:** Refresh token from the approval step previously
saved.  
**client\_id:** Is the APP ID of the application that you created.  
**client\_secret:** Secret Key generated when the app was created.

Request:

``` language-javascript
curl -X POST https://api.mercadolibre.com/oauth/token?grant_type=refresh_token&client_id=$APP_ID&client_secret=$SECRET_KEY&refresh_token=$REFRESH_TOKEN
```

Response:

``` language-javascript
{
    "access_token": "APP_USR-5387223166827464-090515-b0ad156bce700509ef81b273466faa15-8035443",
    "token_type": "bearer",
    "expires_in": 10800,
    "scope": "offline_access read write",
    "user_id": 8035443,
    "refresh_token": "TG-5b9032b4e4b0714aed1f959f-8035443"
}
```

  

## Errors

| Error                    | Description                                                                                                                                                                                              |
|--------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| invalid\_client          | Invalid client\_id and/or client\_secret provided.                                                                                                                                                       |
| invalid\_grant           | The provided authorization grant is invalid, expired or revoked; the client\_id or redirect uri do not match the original. The authorization\_code or refresh\_token do not exist, or have been deleted. |
| invalid\_scope           | The requested scope is invalid, unknown or malformed. The values allowed for parameter scope are: "offline\_access", "write", "read".                                                                    |
| invalid\_request         | The request is missing a required parameter, includes an unsupported parameter or parameter value, there is some duplicated value or is otherwise malformed.                                             |
| unsupported\_grant\_type | The values allowed for grant\_type are "authorization\_code" or "refresh\_token".                                                                                                                        |
| forbidden                | The call is not authorized to access this resource. It could be possibly using the token of another user.                                                                                                |

  

## Revokes types

-   **Revocation of authorization:** by revoking the authorization
    between the seller's account and your application (either by the
    integrator or the seller), the access\_token and refresh\_token will
    be invalidated. You can check the users who have no grant with your
    application from the "Manage Permissions" option (in My
    Application's dashboard), or by using the call to access the [users
    who have granted licenses to your
    application.](https://global-selling.mercadolibre.com/devsite/application-manager-gs#Users-that-granted-permissions-to-your-application)
-   **Internal revocation:** there are some internal flows that cause
    users' credentials to be deleted, preventing integrators from being
    able to continue working on behalf of vendors; in these cases, it is
    necessary to complete the authorization/authentication flow again.
    These flows are triggered primarily by deletion of user sections.
    The reasons are various, but the most common are password change,
    device unlinkage, or fraud. [Learn how to revoke a user's
    authorization to your
    application.](https://global-selling.mercadolibre.com/pampa/profile)

<div class="andes-message andes-message--neutral">

<img src="data:image/svg+xml;base64,PHN2ZyBjbGFzcz0iYW5kZXMtbWVzc2FnZV9faWNvbiIgaGVpZ2h0PSIxNiIgdmlld2JveD0iMCAwIDE2IDE2IiB3aWR0aD0iMTYiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+CjxnIGZpbGw9Im5vbmUiIGZpbGwtcnVsZT0iZXZlbm9kZCI+CjxjaXJjbGUgY2xhc3M9ImFuZGVzLW1lc3NhZ2VfX2ljb24tb3V0ZXIiIGN4PSI4IiBjeT0iOCIgcj0iNy4yNSIgc3Ryb2tlLXdpZHRoPSIxLjUiPjwvY2lyY2xlPgo8ZyB0cmFuc2Zvcm09Im1hdHJpeCgxIDAgMCAtMSAwIDE2KSI+CjxwYXRoIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBkPSJNNy4wMyAzLjg3OWgxLjk0bC0uMjQzIDUuMzMzSDcuMjczeiI+PC9wYXRoPgo8Y2lyY2xlIGNsYXNzPSJhbmRlcy1tZXNzYWdlX19pY29uLWlubmVyIiBjeD0iOCIgY3k9IjExLjE1MiIgcj0iMSIgdHJhbnNmb3JtPSJtYXRyaXgoMSAwIDAgLTEgMCAyMi4zMDMpIj48L2NpcmNsZT4KPC9nPgo8L2c+Cjwvc3ZnPg==" class="andes-message__icon" />

<div class="andes-message__content">

<div
class="andes-message__title andes-message__title--neutral site-carriers__message-title">

Important:

</div>

<div class="andes-message__text--neutral site-carriers__message-text">

For this last stream, we have only detailed some examples, not all
available cases.

</div>

</div>

</div>

  

**Next:**
[Users](https://global-selling.mercadolibre.com/devsite/manage-users-global-selling)

</div>
