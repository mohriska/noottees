# OAuth


[<- Back to APIM Security](./apim-security-readme.md)

SAP API Management allows you to deal with OAuth 2.0. The handling of OAuth and OAuth tokens from within your API proxy is supported by three policies:

* OAuth v2.0
* OAuth v2.0 Get
* OAuth v2.0 Set

### GenerateOAuthAccessToken
```
<OAuthV2 async="false" continueOnError="false" enabled="true" xmlns="http://www.sap.com/apimgmt">
   <ExternalAuthorization>false</ExternalAuthorization>
   <Operation>GenerateAccessToken</Operation>
   <GenerateResponse enabled="true"/>
   <SupportedGrantTypes/>
   <Tokens/>
</OAuthV2>

```

### GenerateOAuthAccessToken_CustomAttributes
```
<OAuthV2 async="false" continueOnError="false" enabled="true" xmlns="http://www.sap.com/apimgmt">
    <Attributes> 
        <Attribute name="sapapim.hidden.customattribute" ref=" sapapim.customattribute" display="false"></Attribute>
    </Attributes>
    <Operation>GenerateAccessToken</Operation>
    <GenerateResponse/>
    <SupportedGrantTypes>
        <GrantType>client_credentials</GrantType>
    </SupportedGrantTypes>
</OAuthV2>

```

### VerifyAccessToken 
```
<OAuthV2 async="false" continueOnError="false" enabled="true" xmlns="http://www.sap.com/apimgmt">
   <Operation>VerifyAccessToken</Operation>
</OAuthV2>
```

