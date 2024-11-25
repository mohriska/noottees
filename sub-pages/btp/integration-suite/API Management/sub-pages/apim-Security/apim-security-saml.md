# SAML


[<- Back to APIM Security](./apim-security-readme.md)

SAP API Management allows you to use Security Assertion Markup Language (SAML). The handling of SAML and SAML assertions from within your API proxy is supported by two policies:

* SAML assertion generation
* SAML assertion validation

### ValidateSAMLAssertion
```
<ValidateSAMLAssertion async="false" continueOnError="false" enabled="true" ignoreContentType = "true" xmlns="http://www.sap.com/apimgmt">
    <RemoveAssertion>true</RemoveAssertion>
	<Source name="message">
	<Namespaces>
    <Namespace prefix="prot">urn:oasis:names:tc:SAML:2.0:protocol</Namespace>
	<Namespace prefix="ns2">urn:oasis:names:tc:SAML:2.0:assertion</Namespace>
	</Namespaces>
	<XPath>/prot:Response/ns2:Assertion</XPath>
	</Source>
	<TrustStore>samlroot</TrustStore>
</ValidateSAMLAssertion>

```


### GenerateSAMLAssertion
```
<GenerateSAMLAssertion async="false" continueOnError="false" enabled="true" ignoreContentType ="true" xmlns="http://www.sap.com/apimgmt">
	<CanonicalizationAlgorithm />
   <Issuer ref="sapapim.issuer"/>
 <KeyStore>
        <Name ref="sapapim.storename"></Name>
        <Alias ref="sapapim.keyname"></Alias>
    </KeyStore>
	<OutputVariable>
   <FlowVariable name="sapapim.assertion"/>
	</OutputVariable>
	<SignatureAlgorithm />
	 <Subject ref="sapapim.username"/>
	<Template ignoreUnresolvedVariables="false">
<![CDATA[
<saml2:Assertion ID="{saml.id}" IssueInstant="{saml.issueInstant}" Version="2.0"
        xmlns:saml2="urn:oasis:names:tc:SAML:2.0:assertion"
        xmlns:xs="http://www.w3.org/2001/XMLSchema"><saml2:Issuer
        xmlns:saml2="urn:oasis:names:tc:SAML:2.0:assertion">{saml.issuer}</saml2:Issuer><saml2:Subject
        xmlns:saml2="urn:oasis:names:tc:SAML:2.0:assertion"><saml2:NameID Format="urn:oasis:names:tc:SAML:1.1:nameid-format:unspecified">{saml.subject}</saml2:NameID><saml2:SubjectConfirmation Method="urn:oasis:names:tc:SAML:2.0:cm:bearer"><saml2:SubjectConfirmationData NotOnOrAfter="{sapapim.notOnorAfter}" Recipient="{sapapim.recipient}"/></saml2:SubjectConfirmation></saml2:Subject><saml2:Conditions NotBefore="{sapapim.notBefore}" NotOnOrAfter="{sapapim.notOnorAfter}"
        xmlns:saml2="urn:oasis:names:tc:SAML:2.0:assertion"><saml2:AudienceRestriction><saml2:Audience>{sapapim.audience}</saml2:Audience></saml2:AudienceRestriction></saml2:Conditions><saml2:AuthnStatement AuthnInstant="{sapapim.timestamp}" SessionNotOnOrAfter="{sapapim.notOnorAfter}"
        xmlns:saml2="urn:oasis:names:tc:SAML:2.0:assertion"><saml2:AuthnContext><saml2:AuthnContextClassRef>urn:none</saml2:AuthnContextClassRef></saml2:AuthnContext></saml2:AuthnStatement>
</saml2:Assertion>
                ]]>
   </Template>
</GenerateSAMLAssertion>


```