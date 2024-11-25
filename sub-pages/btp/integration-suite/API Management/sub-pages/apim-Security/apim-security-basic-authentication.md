# Basic Authentication

[<- Back to APIM Security](./apim-security-readme.md)


The classic basic authentication works with username and password. More specifically, the policy allows you to store user credentials in a variable or extract it from a header. In both cases, it uses Base64 for the encoding or decoding. Basic authentication is especially important if you want to create an authorization header for access to a backend server or to a service that requires basic authentication.


Basic authentication is not implemented for the **API proxy**. It just helps you deal with scenarios in which basic authentication is required.


### Encode
```
<BasicAuthentication async='true' continueOnError='false' enabled='true' xmlns='http://www.sap.com/apimgmt'>
 	<!-- Operation can be Encode or Decode -->
	<Operation>Encode</Operation>
	<IgnoreUnresolvedVariables>true</IgnoreUnresolvedVariables>
	<User ref='private.user'></User>
 	<Password ref='private.password'></Password>
	<AssignTo createNew="false">request.header.authorization</AssignTo>
</BasicAuthentication>


```

### Decode
```
<BasicAuthentication async='true' continueOnError='false' enabled='true' xmlns='http://www.sap.com/apimgmt'>
	<Operation>Decode</Operation>
	<IgnoreUnresolvedVariables>true</IgnoreUnresolvedVariables>
	<User ref='local.username'></User>
	<Password ref='local.password'></Password>
 	<Source>request.header.authorization</Source>
</BasicAuthentication>

```