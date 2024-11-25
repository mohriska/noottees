# XML Threat Protection

[<- Back to APIM Security](./apim-security-readme.md)


This is another policy that allows you to reduce the threat through content-level attacks. XML threat protection allows you to minimize any risks posed by XML content by using the following approach:

* Validation: Validate against an XML schema.
* Evaluation: Look for keywords or patterns that are considered dangerous.
* Detection: Before a message gets parsed, detect corrupt or malformed messages.

```
<XMLThreatProtection async="false" continueOnError="false" enabled="true" xmlns="http://www.sap.com/apimgmt">
   <NameLimits>
	    <Element>10</Element>
	    <Attribute>10</Attribute>
		<NamespacePrefix>10</NamespacePrefix>
		<ProcessingInstructionTarget>10</ProcessingInstructionTarget>
	</NameLimits>
	<Source>request</Source>
	<StructureLimits>
		<NodeDepth>5</NodeDepth>
		<AttributeCountPerElement>2</AttributeCountPerElement>
       <NamespaceCountPerElement>3</NamespaceCountPerElement>
       <ChildCount  includeComment="true" includeElement="true" includeProcessingInstruction="true" includeText="true">3</ChildCount>
	</StructureLimits>
	<ValueLimits>
		<Text>15</Text>
		<Attribute>10</Attribute>
		<NamespaceURI>10</NamespaceURI>
		<Comment>10</Comment>
		<ProcessingInstructionData>10</ProcessingInstructionData>
   </ValueLimits>
</XMLThreatProtection>

```