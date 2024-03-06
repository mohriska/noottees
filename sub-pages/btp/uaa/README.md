# UAA Notes


## Getting user Info in BTP Launcgpad

The application router exposes a user API that returns the details of the user who is logged in. This API supports two endpoints: /currentUser and /attributes. The /currentUser endpoint returns all details of logged in users, while the /attributes endpoint returns the main user properties.

If you build an application using Managed Approuter which is available in BTP Launchpad, all you have to do is just to add a route to xs-app.json file. 

1. Generate an UI5 project
2. Add a route to xs-app.json

```
// add the following to webapp/xs-app.json
// WARNING: Not at the end of xs-app.json... 
// definitelly before "source":"^/(*)" ... otherwise it is not gone work

{
    "source": "^/user-api/currentUser$",
    "target": "/currentUser",
    "service": "sap-approuter-userapi"
}
```

The endpoint /user-api/currentUsers returns user info in the following structure.

```
{
   "firstname": "John",
   "lastname": "Doe",
   "email": "john.doe@sap.com",
   "name": "john.doe@sap.com",
   "displayName": "John Doe (john.doe@sap.com)"
}
```

3. Write controller code to get user info

```
sap.ui.define([
    "demo/userapi/controller/BaseController",
    "sap/ui/model/json/JSONModel"
], function (Controller, JSONModel) {
    "use strict";

    return Controller.extend("demo.userapi.controller.MainView", {
        onInit: function () {
            this.getUserInfo();
        },
        getUserInfo: function () {
            const url = this.getBaseURL() + "/user-api/currentUser";
            var oModel = new JSONModel();
            var mock = {
                firstname: "Dummy",
                lastname: "User",
                email: "dummy.user@com",
                name: "dummy.user@com",
                displayName: "Dummy User (dummy.user@com)"
            }; 

            oModel.loadData(url);
            oModel.dataLoaded()
            .then(()=>{
                //check if data has been loaded
                //for local testing, set mock data
                if (!oModel.getData().email) {
                    oModel.setData(mock);
                }
                this.getView().setModel(oModel, "userInfo");
            })
            .catch(()=>{               
                oModel.setData(mock);
                this.getView().setModel(oModel, "userInfo");
            });
        },      
        
        getBaseURL: function () {
            var appId = this.getOwnerComponent().getManifestEntry("/sap.app/id");
            var appPath = appId.replaceAll(".", "/");
            var appModulePath = jQuery.sap.getModulePath(appPath);
            return appModulePath;
        },        

    });
});
```

4. Special Notes
*  In the BTP Launchpad, you need to add base URL (something like '/6933944e-429d-4c98-8fb1-24d04de767f7.userapiservice.demouserapi/~010821071004+0000~') before the URL you're actually calling. Without the base URL, the call will fail with Not Found (404) error. This is not specific to User API, but applies to any other URLs.

5. View

```
<f:content>
    <Label text="First Name" />
    <Text text="{userInfo>/firstname}" />
    <Label text="Last Name" />
    <Text text="{userInfo>/lastname}" />
    <Label text="Email" />
    <Text text="{userInfo>/email}" />
    <Label text="Display Name" />
    <Text text="{userInfo>/displayName}" />                                      
</f:content>

```

6. Deploy to CF

``` 
npm run deploy

``` 