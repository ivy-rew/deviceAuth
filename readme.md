# AxonIvy DeviceAuth Example

An example REST client, that uses JWT-Bearer auth of microsoft-entra-id to access REST resources of the ivy engine.

This is a reference implementation targeting the refurbished AxonIvy MobileApp. 

### auth-flow

- uses the device-auth-flow: [Device Authorization Flow](https://auth0.com/docs/get-started/authentication-and-authorization-flow/device-authorization-flow)
  
  - allows your device to manage/store the token; and refresh it in case of expiration
  
  - a simple device-code must be entered on the device itself; cryptic password inputs can be avoided without compromising the security

- demonstrates using the ms-graph device-auth-flow: [OAuth 2.0 device authorization grant - Microsoft identity platform | Microsoft Learn](https://learn.microsoft.com/en-us/entra/identity-platform/v2-oauth2-device-code)

### requirements

- security-system to be of kind 'microsoft-entra-id'
  
  - can also be set in the Designer's engine-cockpit.

- requires sprint22 release of axonivy-engine-11.3

```yaml
# yaml-language-server: $schema=https://json-schema.axonivy.com/ivy/11.3.8/ivy.json
SecuritySystems:
  default:
    IdentityProvider:
      Name: microsoft-entra-id
      Config:
        TenantId: yourId
        ClientId: yourClient
        ClientSecret: yourSecret
```


