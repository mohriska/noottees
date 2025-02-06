# SAP BTP CAPM


What is CAPM: Lib + Language + Tools + Framework

App(s) in Cloud: 
- UI
- Service
- Backend  (CDS, Annotations)

General Rule: 
* Declarative Approach (functional side of app)
* Service Based Approach 
* Services are stateless in CAPm

// final code> GitHub> ajaytech / capmlevel1final


- CAPM is a generic runtime that hooks CDS and allow developers to extend and customize through Express or Spring
- CAPM is domain-driven design
    - some principles of domain-driven design
        - Clean modeling: Don't fill your model with technical detail
        - Concise modeling: use short names an simple , flat models
        - Comprehensible modeling
- Defining a Schema - produce entities


### Some benefits and reqs of CAPM
- The application should explicitly declare and isolate dependencies (SQLite, SAP HANA, NPM packages)
- The application should have proper logging implemented
- Should be properly modularized a microservice architecture
- The application should support a RESTful architecture and provide services in OData format
- The application should support multi-tenancy
          
# Content

| Topic                                                  | 
|--------------------------------------------------------|
| [Setup](./sub/sap-btp-cap-setup.md )  |
| [Deployment Dependencies](./sub/sap-btp-cap-deploy-depend.md)|               
| [Setup Project](./sub/sap-btp-cap-project.md)                        |
| [CDS](#CAPM_CDS)                                      | 
| [Association & composition](#Association_Composition) | 
| [Query](#Query)                                       |
| [References](#Reference)                              |


-----

## Reference:




* [Extend SAP SuccessFactors on SAP BTP with the SAP Cloud Application Programming Model (CAP)](https://developers.sap.com/mission.btp-extend-sfsf-cap.html)
* [Build a Business Application Using CAP for Node.js](https://developers.sap.com/mission.cp-starter-extensions-cap.html)
* [Build an Application End-to-End Using CAP, Node.js and VS Code](https://developers.sap.com/mission.btp-application-cap-e2e.html)
* []()





* [Build a Single Page Application Using UI5 Web Components for React](https://developers.sap.com/mission.react-spa.html)

- [cloud-cap-samples](https://github.com/SAP-samples/cloud-cap-samples/tree/main)
- [GitHUb - SAP Cloud Application Programming Model](https://github.com/cap-js)
- [Sending Notifications from SAP BTP Applications to the SAP Fiori Launchpad](https://www.youtube.com/watch?v=PZPp1gyLLQo)
- [Create Freestyle Fiori App on CAPM BTP SAP Fiori App development on Business application studio BAS](https://www.youtube.com/watch?v=vxoZlkZ-gCM)
- [Create a SAP Fiori App using OData and Deploy it to SAP BTP](https://www.youtube.com/watch?v=9kdldvuBF9k)
- [09 CAPM Create Fiori App BTP Training | Build and Deploy Your SAP Fiori App to BTP](https://www.youtube.com/watch?v=Y0Zz3girtWc)
- [10 CAPM Fiori UI Annotations | Create UI with Annotation in SAP® CAPM](https://www.youtube.com/watch?v=NMCUO19DD5I)
- [11 SAP BTP Use S4HANA Sales Service | Create a Service Instance to Consume the SAP S4HANA Cloud APIs](https://www.youtube.com/watch?v=SK5t8yyC8sA)
- [Making CAP Application Development Easier and Faster with the Help of Storyboard in SAP Business Application Studio](https://blogs.sap.com/2023/09/20/making-cap-application-development-easier-and-faster-with-the-help-of-storyboard-in-sap-business-application-studio/)

- [Working with Modeling Content in a Project](https://learning.sap.com/learning-journey/modeling-in-sap-hana-cloud/working-with-modeling-content-in-a-project)
- [SAP Business Technology Platform Showcase: Access SAP HANA Cloud Database Underneath SAP Data Warehouse Cloud](https://github.com/SAP-samples/btp-showcase-actuals-cap)
- [SAP Business Application Studio for SAP Fiori Development - Introduction and Exercise 1](https://www.youtube.com/watch?v=VFLFp_pHYJQ)
- [Start Developing in SAP BTP](https://developers.sap.com/mission.scp-1-start-developing.html)
- [Connect to Third-Party Services Using SAP Integration Suite](https://developers.sap.com/mission.apim-open-connectors.html)
- [Combine CAP with SAP HANA Cloud to Create Full-Stack Applications](https://developers.sap.com/mission.hana-cloud-cap.html)
- [SAP Business Technology Platform ABAP Environment](https://community.sap.com/topics/btp-abap-environment)
- [SAP Cloud SDK](https://sap.github.io/cloud-sdk/docs/js/features/odata/execute-odata-request)
- [SAP-samples/s4hana-btp-extension-devops](https://github.com/SAP-samples/s4hana-btp-extension-devops)
- [SAP/business-partner-sample-app-s4hana-cloud](https://github.com/SAP/business-partner-sample-app-s4hana-cloud)
- [SAP-samples/s4hana-btp-extension-devops](https://github.com/SAP-samples/s4hana-btp-extension-devops)
- [MTA CLoudTool](https://sap.github.io/cloud-mta-build-tool/)
- [Create an App Using SAP Cloud SDK for JavaScript](https://developers.sap.com/group.s4sdk-js-cloud-foundry.html)
- [Consuming REST APIs with (Cloud) ABAP](https://blogs.sap.com/2020/10/27/consuming-rest-apis-with-cloud-abap/)
- [Level Up with SAP BTP, ABAP Environment](https://developers.sap.com/mission.abap-env-level-up.html)
- [Create an XSUAA Instance](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/2ce1a962c3be48dd8035513b0a2d7397.html)
- [Create business partner in S/4HANA Cloud using ABAP Environment data](https://developers.sap.com/tutorials/abap-environment-business-partner.html)
- [Step 4 with SAP Cloud SDK: Calling an OData Service with the Virtual Data Model](https://blogs.sap.com/2017/05/21/step-4-with-sap-s4hana-cloud-sdk-calling-an-odata-service/#WriteBusinessPartnerServlet)
- [Build an SAP Fiori App that Consumes Data from an On-Premise System](https://developers.sap.com/group.appstudio-fiori.html)
- [Create OData Entities with the SAP Cloud SDK's Virtual Data Model](https://developers.sap.com/tutorials/cloudsdk-js-vdm-create.html)
- [SAP Tech Bytes: FAQ Managed Approuter vs. Standalone Approuter](https://blogs.sap.com/2021/05/17/sap-tech-bytes-faq-managed-approuter-vs.-standalone-approuter/)
- [CAP](https://cap.cloud.sap/docs/about/)
- [SAP® CAPM | SAP® Cloud Application Programming Model Tutorial | SAP® CAP Model End-to-End](https://www.youtube.com/watch?v=mA5yYLI-byc)
- [Tutorial - Create SAP Cloud Application Programming Model Project for SAP HANA Cloud](https://www.youtube.com/watch?v=ydDOGz7P--8)
- [SAP Cloud Application Programming Model: Consume External Services](https://www.youtube.com/watch?v=rWQFbXFEr1M)
- [SAP® CAPM App in SAP® BAS | SAP ®CAPM Tutorial](https://www.youtube.com/watch?v=svlVsSbxi_E)
- [CAP in a nutshell](https://cap.cloud.sap/docs/get-started/in-a-nutshell)
- [UI5CN Lab](http://www.lab.ui5cn.com/docs/deploy-app-to-scf)
- [Build a Business Application Using CAP for Node.js](https://developers.sap.com/mission.cp-starter-extensions-cap.html)
- [SAP Cloud Application Programming Model](https://community.sap.com/topics/cloud-application-programming)
- [SAP Cloud Application Programming Model (CAP) | SAP Community Call](https://www.youtube.com/watch?v=OQVUkCs7mzY)
- [SAP HANA Cloud and CAP to Build Full-Stack Applications Using VSCode](https://www.youtube.com/watch?v=yceqr9vycrs)
- [Create Calculation View and Expose via CAP (SAP HANA Cloud)](https://developers.sap.com/tutorials/hana-cloud-cap-calc-view.html)
- [Create UI & Integrate OData in UI5 Application on BAS for CAPM Full Stack UI5 Development](https://blogs.sap.com/2022/04/05/create-ui-integrate-odata-in-ui5-application-on-bas-for-capm-full-stack-ui5-development/)
- [Working with Modeling Content in a Project](https://learning.sap.com/learning-journey/modeling-in-sap-hana-cloud/working-with-modeling-content-in-a-project)
- [SAP Business Technology Platform Showcase: Access SAP HANA Cloud Database Underneath SAP Data Warehouse Cloud](https://github.com/SAP-samples/btp-showcase-actuals-cap)
- [Start Developing in SAP BTP](https://developers.sap.com/mission.scp-1-start-developing.html)
- [Connect to Third-Party Services Using SAP Integration Suite](https://developers.sap.com/mission.apim-open-connectors.html)
- [Combine CAP with SAP HANA Cloud to Create Full-Stack Applications](https://developers.sap.com/mission.hana-cloud-cap.html)
- [SAP Business Technology Platform ABAP Environment](https://community.sap.com/topics/btp-abap-environment)
- [SAP Cloud SDK](https://sap.github.io/cloud-sdk/docs/js/features/odata/execute-odata-request)
- [SAP-samples/s4hana-btp-extension-devops](https://github.com/SAP-samples/s4hana-btp-extension-devops)
- [SAP/business-partner-sample-app-s4hana-cloud](https://github.com/SAP/business-partner-sample-app-s4hana-cloud)
- [SAP-samples/s4hana-btp-extension-devops](https://github.com/SAP-samples/s4hana-btp-extension-devops)
- [MTA CLoudTool](https://sap.github.io/cloud-mta-build-tool/)
- [Create an App Using SAP Cloud SDK for JavaScript](https://developers.sap.com/group.s4sdk-js-cloud-foundry.html)
- [Consuming REST APIs with (Cloud) ABAP](https://blogs.sap.com/2020/10/27/consuming-rest-apis-with-cloud-abap/)
- [Level Up with SAP BTP, ABAP Environment](https://developers.sap.com/mission.abap-env-level-up.html)
- [Create an XSUAA Instance](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/2ce1a962c3be48dd8035513b0a2d7397.html)
- [Create business partner in S/4HANA Cloud using ABAP Environment data](https://developers.sap.com/tutorials/abap-environment-business-partner.html)
- [Step 4 with SAP Cloud SDK: Calling an OData Service with the Virtual Data Model](https://blogs.sap.com/2017/05/21/step-4-with-sap-s4hana-cloud-sdk-calling-an-odata-service/#WriteBusinessPartnerServlet)
- [Build an SAP Fiori App that Consumes Data from an On-Premise System](https://developers.sap.com/group.appstudio-fiori.html)
- [Create OData Entities with the SAP Cloud SDK's Virtual Data Model](https://developers.sap.com/tutorials/cloudsdk-js-vdm-create.html)
- [SAP Tech Bytes: FAQ Managed Approuter vs. Standalone Approuter](https://blogs.sap.com/2021/05/17/sap-tech-bytes-faq-managed-approuter-vs.-standalone-approuter/)
- [Capire repo GitHub](https://github.com/cap-js/docs)

- [Welcome to the CAP SFLIGHT App](https://github.com/SAP-samples/cap-sflight)

- [Service integration with SAP Cloud Application Programming Model](https://github.com/SAP-samples/cap-service-integration-codejam)

- [SAP Business Technology Platform Showcase: Access SAP HANA Cloud Database Underneath SAP Data Warehouse Cloud](https://github.com/SAP-samples/btp-showcase-actuals-cap)

- [cloud-sf-extension-cap-sample](https://github.com/SAP-samples/cloud-sf-extension-cap-sample)

- [Create Automated System Tests for SAP Cloud Application Programming Model Projects](https://developers.sap.com/tutorials/cicd-wdi5-cap.html)

- [teched2020-DEV164](https://github.com/SAP-archive/teched2020-DEV164)
- [Contributions to the SAPUI5 Documentation](https://github.com/SAP-docs/sapui5)

- [Automated System Tests for CAP-Based Projects](https://github.com/SAP-samples/cap-bookshop-wdi5)

- [SAP BTP Developer's Guide](https://github.com/SAP-samples/btp-developer-guide-cap)

- [btp-cap-multitenant-saas](https://github.com/SAP-samples/btp-cap-multitenant-saas)

- [sap-cap-examples](https://github.com/sebastianesch/sap-cap-examples)

- [ui5-typescript](https://github.com/SAP/ui5-typescript)

- [UI5 Language Assistant](https://github.com/SAP/ui5-language-assistant)

- [openSAP-ui5-course](https://github.com/SAP/openSAP-ui5-course)

- [sapui5bin](https://github.com/qmacro/sapui5bin)

- [SAPUI5-Fiori](https://github.com/qmacro/SAPUI5-Fiori)
- [Extending your On-Premise OData Entities in CAP](https://www.youtube.com/watch?v=suKt7xMhEY4)
- [The Art and Science of CAP](https://www.youtube.com/playlist?list=PL6RpkC85SLQAe45xlhIfhTYB9G0mdRVjI)
* [Using the SAP Approuter at dev time - a full-stack journey with UI5 and SAP CAP](https://www.youtube.com/watch?v=bJIMIE7yjIE&list=PL6RpkC85SLQAxfeffIBpvAs-02ChcuEuh)
* [Continuous Integration and Delivery](https://www.youtube.com/watch?v=gvWSHSZFPok&list=PL6RpkC85SLQAyZ8EtrK6O2idEAq4yHfDJ)

[<- Back to Content](#content)


