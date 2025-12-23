<div class="inner-content">

## CyberSecurity Best Practices

<div class="details__message">

In this documentation you will find extra information on various
practices that will complement your secure development. We invite you to
consider them in order to considerably improve the security of your
integration.

</div>

## Log auditing and logging

It is essential to have concrete evidence that allows us to understand
what is happening in our application (to alert us) and what happened at
a certain time with a certain user, endpoint or resource.

  

To implement this, we have several possible alternatives:

**Logging**: the term log is used to refer to the record of events that
are occurring or have occurred in an application or system. Generally
the events are of 5 main types: informational, debugging, warning, error
and alert.

**Audit**: is a set of records that provide evidence of the set of
activities that affected a resource or event over time.

**Monitoring**: is a diagnostic tool that we use to know the status of
the application.

  

### Warnings!

Logging of sensitive data.

Logging of sensitive information, personal data, secrets or confidential
information should be avoided as much as possible.

  

## Protection against automated attacks

There are some cases in which we want a user to be able to use some
functionality of our application but in a limited way to avoid abuse of
the functionality. A clear example of this can be the login: we want the
user to be able to enter email and password to validate the credentials
but we also want to prevent malicious users from abusing the
functionality by sending thousands of passwords and mails to validate
users.

  

It is important to mention that in this instance we are not trying to
defend against denial of service attacks.

  

### Rate Limiting

Rate limiting is the practice of limiting traffic to the application or
its components based on a certain rate. The idea behind this practice is
to establish a finite number of times that the user will be able to
access the desired functionality. For example, **a user will be able to
make 5 money transfers per hour**.

[Reference of Rate Limit strategies and
techniques](https://cloud.google.com/architecture/rate-limiting-strategies-techniques).

  

### Captcha

The objective of CAPTCHA is to avoid automation by giving the user an
option to **recover** from the detection of anomalous behavior by
presenting a challenge that only a human could solve correctly.

  
![](https://http2.mlstatic.com/storage/developers-site-cms-admin/243855508690-Captura-de-Pantalla-2022-09-15-a-la-s--11.21.00.png)  

In general, the reCAPTCHA engine is delegated to detect anomalous
behavior or thresholds based on which to display the CAPTCHA. There is
the alternative of reCAPTCHA v3 in which the service returns a score and
we can decide when to show the user the challenge and when not to show
it.

[reCAPTCHA Implementation
Reference](https://developers.google.com/recaptcha).

  

## Secrets

Sometimes it is necessary to use some secret in our applications, for
example, access credentials to a database, a key to consume some service
or some random value to sign messages.

  

In these cases, a bad practice can occur, which consists of leaving the
secrets hardcoded in the code. By doing this, the secret becomes
available to everyone with access to it.

  

### How to implement it?

The best practices for storing secrets or keys indicate that you should
use the environment variables to store these secrets or use a host
external to the source code of the application, where all the
credentials for the operation of the application are stored.

  

The same hosting can be configuration files, databases or specialized
services for storing secrets such as those available in the services of
different cloud providers, and must be strongly protected against access
by outsiders, including other local users on the same system.

  

### Warnings!

In many occasions, when using versioning systems, we mistakenly leave
the secret in the code and when we realize it, we make a new commit. By
doing this, the secret is still in the repository.

  

We recommend that if a secret was put into code, **it should be removed
from the code as recommended above and replaced with a new one** . In
case this is not possible, we recommend you to remove the affected
commit [(guía para
Github)](https://docs.github.com/en/free-pro-team@latest/github/authenticating-to-github/removing-sensitive-data-from-a-repository).

  

## Third-party software dependencies

In many occasions the third party dependencies that we include in our
software have vulnerabilities or are directly malicious.

  

For these reasons, it is very important that we pay attention to the
security of the third-party components that we include, so when choosing
a dependency, we must choose the most recent version and without
reported vulnerabilities.

  

## Applied Cryptography

Before applying any cryptographic technique, it is necessary to analyze
the type of data to be protected and its status (at rest, in transit or
in use) in order to ensure that the technique to be used will meet the
required need. In general, if when analyzing the type of data that needs
to be protected, it is identified that:

-   It must be reversible (return to its original state) what must be
    applied is an encryption technique;
-   It must not be reversible, the appropriate technique is hashing;
-   It requires guaranteeing non-repudiation, the appropriate technique
    is the digital signature.

</div>
