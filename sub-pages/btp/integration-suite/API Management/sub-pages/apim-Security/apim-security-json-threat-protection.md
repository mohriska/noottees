# JSON Threat Protection

[<- Back to APIM Security](./apim-security-readme.md)

Sometimes, the security risk lies within the content itself. JSON threat protection helps you reduce the risk of such content-level attacks for JSON by defining specific limitations to JSON structures.


```
<JSONThreatProtection async="false" continueOnError="false" enabled="true" xmlns="http://www.sap.com/apimgmt">
	<ArrayElementCount>20</ArrayElementCount>
	<ContainerDepth>10</ContainerDepth>
	<ObjectEntryCount>15</ObjectEntryCount>
	<ObjectEntryNameLength>50</ObjectEntryNameLength>
	<Source>request</Source>
	<StringValueLength>500</StringValueLength>
</JSONThreatProtection>

```