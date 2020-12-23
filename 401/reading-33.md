# JSON Web Tokens
https://jwt.io/introduction/

## What is JSON Web Token?
JSON Web Token (JWT): an oepn standard that defines a compact and self-contained way for securely transmitting information between parties as a JSON object

digitally signed:

- so information can be verified and trusted 

- signed using a secret (with the HMAC algorithm) 

- a public/private key pair using RSA or ECDSA.

- can verify the integrity 

- can be encrypted to hide claims from outside parties

## When should you use JSON Web Tokens?

Authorization

- most common use of JWT

- JWT associated with user, and token used to permit resources

Information Exchange:

- JWT are a good way of securely transmitting information

- verify that the content hasn't been tampered with

- you can be sure the senders are who they say they are

## What is the JSON Web Token structure?
JSON Web Tokens consist of three parts separated by dots

(header.payload.signature)

### Header
two parts:

- the type of the token (JWT)

- the signing algorithm

### Payload
contains the claims (statements about an entity and data)

three types: 

- registered: predefined, recommended claims that are useful and interoperable claims (ex: issuer, expiration time, subjject, audience, etc.)
- public: can be defined by the JWT user, but need to be defined in the IANA JSON Web token Registry or defined as a URI with collision resistant namespace
- private: custom claims to share info between private parties 

### Signature
To create the signature part you have to take the encoded header, the encoded payload, a secret, the algorithm specified in the header, and sign that.

used to verify the message wasn't changed along the way

can also verify that the sender of the JWT is who it says it is

## How do JSON Web Tokens work?
when the user successfully logs in using their credentials, a JSON Web Token will be returned.

ou should not keep tokens longer than required

 should not store sensitive session data in browser storage due to lack of security
 
 When user requests access, user agent should send a JWT in the AUTHORIZATION header using BEARER schema
 
 it the token is valid, the user will be allowed access
 
 Cross-Origin Resource Sharing (CORS) won't be an issue as it doesn't use cookies
 
 you should not put secret information within the token
 
 ## Why should we use JSON Web Tokens?
 compared to Simple Web Tokens (SWT) and Security Assertion Markup Language Tokens (SAML)
 
 JSON is less verbose than XML means JWT is more compact than SAML
 
 JWT are a good choice in HTML/HTTP environments
 
 signing in JSON is simple and leaves less security holes than do SAML tokens signed in XML
 
 XML doesn't ahve natural document to object mapping unlike JSON
 
 JWT is commonly used at internet scale
 
 # How to Use JWT Authentication with Django REST Framework
 https://simpleisbetterthancomplex.com/tutorial/2018/12/19/how-to-use-jwt-authentication-with-django-rest-framework.html
 
 ## How JWT Works?
JWT is just an authorization token included in requests

acquired by exchanging an username + password for an ACCESS token and an REFRESH token

- access: short-lived (5 min)

- refresh: longer (24hrs)

the JWT is composed of 3 parts: header.payload.signature

the signature is the SECRET key that you use to validate the user can access the information in the payload

## Installation and Setup
Run in terminal: pip install djangorestframework_simplejwt

in settings.py: 
```REST_FRAMEWORK = {
    'DEFAULT_AUTHENTICATION_CLASSES': [
        'rest_framework_simplejwt.authentication.JWTAuthentication',
    ],
}```
in urls.py:
```
from django.urls import path
from rest_framework_simplejwt import views as jwt_views

urlpatterns = [
    # Your URLs...
    path('api/token/', jwt_views.TokenObtainPairView.as_view(), name='token_obtain_pair'),
    path('api/token/refresh/', jwt_views.TokenRefreshView.as_view(), name='token_refresh'),
]```

## Usage

### Obtain Token
authenticate and obtain the token

endpoint is /api/token/

 only accepts POST requests

in local storage: store both the access token and the refresh token on the client side

Put the access token in the header of all requests

### Refresh Token
To get a new access token

- refresh token endpoint /api/token/refresh/

- posting the refresh token

## What’s The Point of The Refresh Token?
 If your access token have a long expire time, it may take longer to update the information associated with the token
 
 the refresh token only travel in the POST data:
 
 -the access token is sent via HTTP header
 
 # Questions
 
 If someone can manipulate your access token, why can they not find the new access token when the refreshe + access token pair is reset?
 
 

