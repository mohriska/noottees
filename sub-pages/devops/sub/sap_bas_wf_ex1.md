# WF on BTP

## Description


## Set Up
1. Create MTA project: ```File > New Project from Template > Basic Multitarget Application```
2. Enter name of the app (short name)
3. Create WF module: ```Right Click on mta.yaml > Create MTA Module from Template > Workflow Module```
4. Basic WF MTA module is CREATED


## Development

1. from the workflows floder, click your current workflow
2. from diagram, on left side of the BAS Diagram... select ```User Task``` and put it inside generated diagram
3. In the General Tab on the right side in Name field insert your name
4. Assign recepient for the user task in ```Detail Tab > Users > ${info.startedBy}```
5. create Form/UI5 app from USER TASK properties window on right side of editor ``` User Task Properties > User Interface > Form > Create File```
6. form is created and you can populate the form by designer
7. repeate for other task types

8. (optional) How to setup mail destination in BTP look at: [Configure the Workflow Capability Mail Destination](https://help.sap.com/docs/workflow-capability/workflow-cloud-foundry/configure-workflow-capability-mail-destination?locale=en-US)


## Build and Deploy to WF
1. Right Click on mta.yaml and choose ```Build MTA Project``` or in terminal ```mbt build```
2. Open archive folder and right-click on *.mtar file ``` Deploy MTA Archive```

### Creation of WF Instance
1. In BTP Cockpit > click on ```Instance and Subscription``` and scroll down to subscription section and click on the link next to ```Workflow management```
2. it will open Fiori Launchpad
3. from there open ```Monitor Workflow and Workflow Definition```
4. Click ```Start new instance```
5. Provide some JSON config.
```
{
    "name": "Martin",
    "order": {
        "id": "id1",
        "name": "laptop"
    }
}
```
6. Click on ```Start new instance and Close```
7. You can monitor the workflow by: ```Monitor Workflow - Workflow Instances```





## Build and Deploy to Build Process automation


