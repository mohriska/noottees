# sap_odata

## Content

* **Media**
    * [media](./subpages/media/sap_odata_media_2_table.md)
* **Postman**
    * [sap-client option](./subpages/Postman/sap_btp_postman-sap-client.md)
    * [cookie option](./subpages/Postman/sap_btp_postman-cookie.md)


- [AttachmentCommentSAPUI5](https://github.com/aditheos/AttachmentCommentSAPUI5)

https://blogs.sap.com/2022/01/22/howto-odata-high-level-overview/

- [SAP Developer Challenge – SAP Cloud Application Programming Model](https://blogs.sap.com/2023/07/05/sap-developer-challenge-sap-cloud-application-programming-model/)

- [Explaining SAP Business Technology Platform (SAP BTP) to a Beginner](https://blogs.sap.com/2023/07/11/explaining-sap-business-technology-platform-sap-btp-to-a-beginner/)

- [How to create a destination for a deployed CAP App in cloud foundry using oauth2-configuration](https://answers.sap.com/questions/13941468/how-to-create-a-destination-for-a-deployed-cap-app.html)

- [All Blog Posts](https://blogs.sap.com)

- [All Questions](https://answers.sap.com/index.html)

- [SAP Business Technology Platform](https://community.sap.com/topics/business-technology-platform#tutorials)

- [SAP Business Technology Platform](https://help.sap.com/docs/btp/sap-business-technology-platform/btp-development?locale=en-US)

- [Extend SAP S/4HANA with a Custom UI on SAP Cloud Platform | SAP TechEd for SAP Community](https://www.youtube.com/watch?v=OdH9L-RzuIw)

- [MTA on Cloud Foundry: using (none odata) web service via basic authentication](https://answers.sap.com/questions/13421409/mta-on-cloud-foundry-using-none-odata-web-service.html)

- [Deep Dive 11 – Calling an OData Service from a Web IDE Project using the SAP S/4HANA Cloud SDK](https://blogs.sap.com/2018/05/27/step-4a-calling-an-odata-service-from-a-web-ide-project-using-the-sap-s4hana-cloud-sdk/)

- [SAP Developer Challenge - SAP Cloud Application Programming Model (Week 4)](https://groups.community.sap.com/t5/application-development/sap-developer-challenge-sap-cloud-application-programming-model/td-p/274851)

- [File Upload/Download through NetWeaver Gateway](https://blogs.sap.com/2014/09/23/file-uploaddownload-through-netweaver-gateway/)

- [File Attachment using gateway](https://answers.sap.com/questions/9644736/file-attachment-using-gateway.html)


## How to create deep entity with oModel.createEntry

Yes you can execute deep entity creation with oData V2. In order to do so you need to build your request body according to your metadata structure. Let's assume that your metadata model is User and each user have multiple Communication. So we have a user entity and communication entity. We also have association of fromUserToCommunications and navigation property let's call it Communications


In order to execute a call to deep create a User entity you will need to do the following: 

```
// Create the oData Model
var oModel = new sap.ui.model.odata.ODataModel("{YOUR_SERVICE_DOCUMENT_URL}");


// Create the user request body, please make sure that 
// all required fields are filled in and are according to the 
// user entity metadata
var userRequestBody = {
    id: "123",
    firstName: "Your First Name",
    lastName: "Your Last Name",
    address: "Your Address",
    communications: []  // contain multiple communications 
};

var comm1 = {
    id : "1",
    userId : "123", // foregin key to the user entity
    homePhone: "+134342445435" 
};

var comm2 = {
    id : "2",
    userId : "123", // foregin key to the user entity
    homePhone: "+134342445436" 
};    

// add the communications to the user entity 
userRequestBody.communications.push(comm1);
userRequestBody.communications.push(comm2);

oModel.create("/UserCollection",userRequestBody,{
    success: function(result){
        // everything is OK 
    },
    error: function(err){
        // some error occuerd 
    },
    async: true,  // execute async request to not stuck the main thread
    urlParameters: {}  // send URL parameters if required 
}); 
```