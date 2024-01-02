As an alternative, if you want to access using OAuth 2.0 Password Credentials instead of Authorization Code Grant (login popup):

Approach only works when SAP ID Service is used, or when the IAS is connect via OpenID Connect
IAS Proxy mode not supported
Additional Steps with IAS (Identity Authentication Service):

Check that subaccount trusts IAS using OpenID Connect: Origin Key must be sap.custom & Trust Configuration must be active
Check that IAS application is configured for OpenID Connect
Get User ID from IAS
Steps in ABAP Service Instance:

Create a service key
Copy credentials from services key
Request Access Token in Postman:

Grant type: Password Credentials
Access Token URL:
IAS: <service_key-url>/oauth/token?login_hint=%7B%22origin%22%3A%22sap.custom%22%7D
or SAP ID Service: <service_key-url>/oauth/token
Client ID: <service_key-clientID>
Client Secret: <service_key-clientid>
Username: <user ID from IAS or SAP ID Service>
Password: <password of IAS user or SAP ID Service>


------
