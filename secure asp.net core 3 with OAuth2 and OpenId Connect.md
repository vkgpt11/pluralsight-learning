## Tooling
- VS 2019
- ASP.NET Core 3.1

## Past App Architecures and Security
### Windows Applications [Thick client]
 - Windows Based Authentication
### Web Apps (ASP.NET)
 - Windows Forms based authentication 
### Service-based applications 
 - WS-Security (WCF)
 - IP-level configuraton (firewall)
### SAML 2.0
 - Standard for exchanging authentication and authorization data between security domains
 
## Morden App Architecures and Security
### Token based security
 - Client apps send tokens representing consent to API
### Home-grown token services emerged...
 - Application still has access to usename/password
### New Token based 
- Expiration
- Token signing and validation 
- Token format
- Seprating Authentication and Authorization
- Securely delivering tokens to different application types

### Issues with current Auth Architecture
- No longer handle user credential at user level, It should be handled by **A central identity provider**
- Finding a way to use these tokens for authentication and Authorization for different types of applications **[A protocol that's safe for authentication and authorization]**

## Identity Providers
- It's the responsibility of an identity provider (IDP) to authenticate the user and if needed, safely provide proof of identity to an application. Most often such an identity providers are also used for user account related tasks.

**Identity and access management related tasks**
- User registration and management
- locking out the users
- password policies, strength and resets 
These are tedious tasks, prone to change:- Handle them in a central location and reuse them across apps.

**Why IDP**
- User accounts are reused across applications
- Identity and access management related tasks are common concerns 
- Safely storing account related information is prone to change 
- Means of authentication are added or changed.
A cental identity provider(IDP) for identity and access management (IAM) system solves these issues

## OAuth2
- OAuth2 is an open protocol to allow secure *authorization* in a simple and standard method from web, mobile and desktop applications 
- A Client application can request an access token to gain access to an API.
- OAuth2 defines how a client app can securely achieve authorization.
IdentityServer and Azure AD implement the OAuth2 standards are example of Authorization/Token provider services, Token can only be used to acess the resources. They should not be used to sign-in to an application thats authentication not authorization.

## OpenIdConnect
- OpenId connect is a simple identity layer on top of the OAuth2 protocol
- A client application can request an identity token (next to an access token)
- That identity token is used to sign in to the client application, While the same application uses the access token to access an API
- OpenID connect is the superior protocol: it extends and supersedes OAuth2
  - Even if the client application only requires authorization to access an API, We should use OIDC instead of Plain OAuth2 

--------
Summay:-
--------
- Identity and Access Management (IAM) belongs at a central location: an Identity Provider (IDP)
- That IDP should implement protocols that safely allow authentication and authorization OpenId Connect and OAuth2

## How do you store password in your application?

## Public and Confidential Clients
|Confidential Clients|Public Clients|
|--------------------|-------------|
|Capable of maintaiing the confidentiality of their credentials (e.g. clientid & clientsecret)|Incapable of maintaiing the confidentiality of their credentials (e.g. clientid & clientsecret)|
|Live on the server|Live on the device|
|These client applications can safely authenticated|These client applications **cannot** safely authenticated|
|E.g.: server-side web apps|E.g.: javascript apps (and mobile apps)|

