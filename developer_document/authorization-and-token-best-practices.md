<div class="inner-content">

## Authorization and Token Best Practices

<div class="details__message">

At Mercado Libre we watch over the safety of our users every day when
launching new features on the platform, and we want your application to
be part of this process too!  
When developing an application it is important to be attentive to how
the code is written in order to protect it against potential fraud or
information theft, so keep in mind the following recommendations to
mitigate any possible vulnerabilities.

</div>

## Obtain access token by sending body parameters

When you POST to the /oauth/token resource to get the access token, you
should send the
[parameters](https://developers.mercadolibre.com.ar/en_us/authentication-and-authorization#Refresh-token)
in the body and not as a query. This will allow a much more secure
exchange of information!

Exemple:

``` language-javascript
curl -X POST \
-H 'accept: application/json' \
-H 'content-type: application/x-www-form-urlencoded' \
'https://api.mercadolibre.com/oauth/token' \
-d 'grant_type=authorization_code' \
-d 'client_id=$client_id' \
-d 'client_secret=$client_secret' \
-d 'code=$code' \
-d 'redirect_uri=$redirect_uri'
```

## ID generation to obtain an access token

As an optional measure to increase security in the processes to obtain
access tokens, we recommend that you generate a secure type random value
and send it as a state parameter.  
For example to create the secure random id, in Java:

``` language-javascript
SecureRandom random = new SecureRandom();
```

Example adding state:

``` language-javascript
curl -X  GET https://auth.mercadolibre.com.ar/authorization?response_type=code&client_id=$APP_ID&state=ABC123&redirect_uri=$REDIRECT_URL
```

You will receive the authorization code and also the secure identifier
in the specified return URL:

``` language-javascript
https://YOUR_REDIRECT_URI?code=$SERVER_GENERATED_AUTHORIZATION_CODE&state=ABC123
```

Remember to check the value to make sure that the response belongs to a
request initiated by your application!

 

## Use of same redirect URI

Remember to send as redirect\_uri the same URL you set when creating
your application!

<img src="https://http2.mlstatic.com/storage/developers-site-cms-admin/DevSite/335689631167-autenticacion-seguridad.png" width="643" height="173" />

[See
more](https://developers.mercadolibre.com.ar/en_us/authentication-and-authorization#Authentication)

 

## Validation of URLs to receive notifications

First validate the origin to know that you are receiving notifications
only from Mercado Libre and then keep in mind to check the URLs when
receiving notifications to make sure that the resources that your
application is going to consult are valid.

## Access token on all requests

In every call you make to the Mercado Libre API, remember to add the
access token in all public and private resources.

  

</div>
