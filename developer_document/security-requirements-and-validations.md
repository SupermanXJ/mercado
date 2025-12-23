<div class="inner-content">

## Security requirements and validations

<div class="details__message">

In this documentation you will find security practices to implement that
are essential for your integration. Implementing them will allow you to
strengthen the core security processes of your development.

</div>

## Specific requirements

### Authentication

Authentication is a process that allows us to know the digital identity
of a user (previously registered) and consists of a series of mechanisms
that establish that this user is who he/she claims to be. These
mechanisms are usually grouped into 3 main categories:

Something I know (password);

Something I have (cell phone, authentication token, yubikey);

Something I am (biometrics).

  

It is the combination of these factors that generates **strong
authentication**.

IMG

![](https://http2.mlstatic.com/storage/developers-site-cms-admin/224673930786-Captura-de-tela-2023-04-25-113343.png)  

### Authorization

Authorization is the mechanism by which we control access to a resource,
generally based on the previously validated identity of a user. It is
important to differentiate this process from authentication: the purpose
of authentication is to determine the identity of a user, while the
purpose of authorization is to determine whether that identity has
sufficient permissions to perform the action it is trying to do. These
validations must be implemented in the backend.  
There are numerous methodologies for assembling authorization matrices.
Among the best known are RBAC, ABAC, ACL, MAC, among others:

  

IMG

![](https://http2.mlstatic.com/storage/developers-site-cms-admin/224673786593-Captura-de-tela-2023-04-25-113630.png)  
  
  

## Data validation

Data validation is the practice of validating that all values that do
not originate in our application are well structured both semantically
and syntactically, prior to processing, storing or transmitting them.

  

As a general rule and for application security, data validation should
be implemented in backend services, since they are flows that cannot be
modified by the end user, unlike frontend validations which aim to offer
a good user experience.

  

It is common practice to perform input validation on the frontend
(client-side), for example, by not letting the user advance in the flow
if he/she does not input something structured as an email in an email
field. This is valid from a functional point of view but we have to keep
in mind that at a security level, a user can ignore client-side
validations and thus send malicious data to applications. Therefore, all
input validations that we perform client-side must also be performed
server-side.

  

### Syntactic validation

By syntactic validation we mean that the value is correctly formed with
respect to the expected data type or structure.

  

For primitive data types such as **float, double, char, boolean, short**
or **long**, a recommended strategy is to perform typecasting. The
simplified idea is as follows: HTTP is a text-based protocol, so, every
basic type value that comes to us in a request is fundamentally a String
(or array of chars) with a certain encoding.

  

In the syntax stage, our goal is to convert the String to the
corresponding basic values we are expecting. For example:

  

If we expect a **user\_id**, which we know is an **Int**, we can perform
a validation of the style:

IMG

![](https://http2.mlstatic.com/storage/developers-site-cms-admin/224673663931-Captura-de-tela-2023-04-25-113846.png)  
  

### Semantic validation

Semantic validation involves understanding whether the value is correct
in terms of the context in which it is being used.

In the context of basic data types we can think of examples such as the
following:

The amount of a transaction must not be negative and must have at most
two rounding zeros.

An order number must not be negative and must be integer.

A last name must not have special or non-printable characters.

A user\`s date of birth must not be less than the year 1900.

  

In the context of complex data types we can think of the following
examples:

Even if an office documents is well formed, we need to check if it has
macros presents with potentially vulnerable or malicious code.

If we are receiving images, determine whats is the maximum and minimum
weight they should have, if we should deleted the matadata, or if it
only informationn related to an image.

  

### Warning!

### Allow list vs Block list

Within the validation methodologies we can use two main strategies:
**Block list** and **Allow List**. In simple terms, a blocklist
methodology consists of defining and looking for all the unexpected
values for each input. For example:

  

IMG

![](https://http2.mlstatic.com/storage/developers-site-cms-admin/224673497921-Captura-de-tela-2023-04-25-114133.png)  

The general problem with this strategy is that it is complex to know all
the dangerous or unexpected characters, and even if we have the whole
list today, technologies and standards change, leaving the blocklist
possibly outdated and vulnerable.

  

Instead, it is recommended to use an **Allow list** strategy that
consists of defining the characters or input formats expected by the
application. The rationale is as follows, it is much easier to know and
define what data I am expecting than to know what data I am not
expecting.

  

Following this strategy, we must be as restrictive as possible, avoiding
at all times, to receive input data containing for example: "." or "/".

  

In case the character list is very permissive because the application
requires it, it will be necessary to implement additional controls to
avoid undesired behavior.

  

For example:

-   If the parameter is directed from a query to a database, it is
    necessary to parameterize the queries.
-   If the parameter we expect is very specific, we must implement
    regular expressions to validate the data we expect.
-   If the parameter is returned to the frontend, additional validations
    must be implemented such as: encoding or sanitization.

</div>
