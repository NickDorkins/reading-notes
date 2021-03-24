# Class 33: Readings: Authentication & Production Server


## [JSON Web Tokens](https://jwt.io/introduction/)

### What is JSON Web Token?

JSON Web Token (JWT) is an open standard ([RFC 7519](https://tools.ietf.org/html/rfc7519)) that defines a compact and self-contained way for securely transmitting information between parties as a JSON object. This information can be verified and trusted because it is digitally signed. JWTs can be signed using a secret (with the HMAC algorithm) or a public/private key pair using RSA or ECDSA.

### When should you use JSON Web Tokens?

- **Authorization**: This is the most common scenario for using JWT. Once the user is logged in, each subsequent request will include the JWT, allowing the user to access routes, services, and resources that are permitted with that token. Single Sign On is a feature that widely uses JWT nowadays, because of its small overhead and its ability to be easily used across different domains.

- **Information Exchange**: JSON Web Tokens are a good way of securely transmitting information between parties. Because JWTs can be signed—for example, using public/private key pairs—you can be sure the senders are who they say they are. Additionally, as the signature is calculated using the header and the payload, you can also verify that the content hasn't been tampered with.

### What is the JSON Web Token structure?

In its compact form, JSON Web Tokens consist of three parts separated by dots (.), which are:

- Header
- Payload
- Signature

```
xxxxx.yyyyy.zzzzz

HEADER.PAYLOAD.SIGNATURE
```

**Header**

The header typically consists of two parts: the type of the token, which is JWT, and the signing algorithm being used, such as HMAC SHA256 or RSA.

```
{
  "alg": "HS256",
  "typ": "JWT"
}
```

**Payload**

The second part of the token is the payload, which contains the claims. Claims are statements about an entity (typically, the user) and additional data. There are three types of claims: registered, public, and private claims.

- **Registered claims**: These are a set of predefined claims which are not mandatory but recommended, to provide a set of useful, interoperable claims. Some of them are: **iss** (issuer), **exp** (expiration time), **sub** (subject), **aud** (audience), and [others](https://tools.ietf.org/html/rfc7519#section-4.1).

    > Notice that the claim names are only three characters long as JWT is meant to be compact.

- Public claims: These can be defined at will by those using JWTs. But to avoid collisions they should be defined in the IANA JSON Web Token Registry or be defined as a URI that contains a collision resistant namespace.

- Private claims: These are the custom claims created to share information between parties that agree on using them and are neither registered or public claims.

Example Payload:
```
{
  "sub": "1234567890",
  "name": "John Doe",
  "admin": true
}
```

> ### Note that for signed tokens this information, though protected against tampering, is readable by anyone. Do not put secret information in the payload or header elements of a JWT unless it is encrypted.

**Signature**

To create the signature part you have to take the encoded header, the encoded payload, a secret, the algorithm specified in the header, and sign that.

```
HMACSHA256(
  base64UrlEncode(header) + "." +
  base64UrlEncode(payload),
  secret)
  ```

## Putting all together

The output is three Base64-URL strings separated by dots that can be easily passed in HTML and HTTP environments, while being more compact when compared to XML-based standards such as SAML.

The following shows a JWT that has the previous header and payload encoded, and it is signed with a secret. Encoded JWT

![sample encoded](https://cdn.auth0.com/content/jwt/encoded-jwt3.png)

---
## [Django Rest Framework JSON Web Token Authentication](https://simpleisbetterthancomplex.com/tutorial/2018/12/19/how-to-use-jwt-authentication-with-django-rest-framework.html)

## How JWT Works?

The JWT is acquired by exchanging an username + password for an **access token** and a **refresh token**.

- **Access token** is usually short-lived (expires in 5 min or so, can be customized though).

- **Refresh token** lives a little bit longer (expires in 24 hours, also customizable). It is comparable to an authentication session. After it expires, you need a full login with username + password again.


It’s a security feature and also it’s because the JWT holds a little bit more information. If you look closely you will see the token is composed by three parts:

```
xxxxx.yyyyy.zzzzz
```

Those are three distinctive parts that compose a JWT:

```
header.payload.signature
```

So we have here:

```
header = eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9
payload = eyJ0b2tlbl90eXBlIjoiYWNjZXNzIiwiZXhwIjoxNTQzODI4NDMxLCJqdGkiOiI3ZjU5OTdiNzE1MGQ0NjU3OWRjMmI0OTE2NzA5N2U3YiIsInVzZXJfaWQiOjF9
signature = Ju70kdcaHKn1Qaz8H42zrOYk0Jx9kIckTn9Xx7vhikY
```

This information is encoded using Base64. If we decode, we will see something like this:

**header**

```
{
  "typ": "JWT",
  "alg": "HS256"
}
```

**payload**

```
{
  "token_type": "access",
  "exp": 1543828431,
  "jti": "7f5997b7150d46579dc2b49167097e7b",
  "user_id": 1
}
```

**signature**

The signature is issued by the JWT backend, using the `header base64` + `payload base64` + `SECRET_KEY`. Upon each request this signature is verified. If any information in the header or in the payload was changed by the client it will invalidate the signature. The only way of checking and validating the signature is by using your application’s `SECRET_KEY`. 
> You should always keep your `SECRET_KEY` **secret**!

## Installation & Setup

For this tutorial we are going to use the djangorestframework_simplejwt library, recommended by the DRF developers.

```
pip install djangorestframework_simplejwt
```

**settings.py**

```
REST_FRAMEWORK = {
    'DEFAULT_AUTHENTICATION_CLASSES': [
        'rest_framework_simplejwt.authentication.JWTAuthentication',
    ],
}
```

**urls.py**

```
from django.urls import path
from rest_framework_simplejwt import views as jwt_views

urlpatterns = [
    # Your URLs...
    path('api/token/', jwt_views.TokenObtainPairView.as_view(), name='token_obtain_pair'),
    path('api/token/refresh/', jwt_views.TokenRefreshView.as_view(), name='token_refresh'),
]
```

---
## Additional Resources:

## [Video: JWT with DRF](https://www.youtube.com/watch?v=Fhcn2qx-4VQ)
---
## [Skim Reading: Django Migrations Primer](https://realpython.com/django-migrations-a-primer/)
---