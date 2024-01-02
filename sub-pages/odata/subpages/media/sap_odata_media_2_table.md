# SAP OData for Media Links (File Upload/Download)

**Media entities and streams are the go-to-way of handling files in an OData Service**

*Thus handling is either available for OData v2/V4 services and can be added to the main frameworks for building OData services for SAP-related services*

-----

SAPUI5 provides designated controls for handling file upload and download. These files are transported as data streams with the help of OData media entities. 

Transaction: **SEGW** or **ABAP RAP**

## Media Entities

An OData media entity is a special entity in the data model of an OData service that offers stream methods that must either be implemented manually (**SEGW**) or that are generically provided by a framework (**ABAP RAP**). 

Such entity is flagged in the metadata document of an OData service as streamable (**attribute hasStream is set**) and **must** offer at least the following properties:

* **Content** - the content of the file gets sent, often stored as raw string on a db level
* **MimeType** - using the MIME type, the content type of the file will be persisted
* **FileName** - file name also must be persisted

----
*NOTES: MIME types - internet media type, identifies the content type of data in the internet. When using media entities, this information is sent with all requests and must be persistent on a DB level. A MIME type consists of type and subtype. A type can be an application (for binary data), text (for texts), or image (for pictures). Each type adds subtypes to provide more information, such as application/pdf or text/xml.*


----





[<- Back to Main](../../README.md)