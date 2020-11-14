## Tooling
- VS 2019
- ASP.NET Core 3.1

## Past App Architecures and Security
### Windows Applications [Tick client]
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
- Finding a way to use these tokens for authentication and Authorization for different types of applications [A protocol that's safe for authentication and authorization]

