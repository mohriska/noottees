# Cloud Foundry Instances Services


### Services and Instances
- On demand resources = service instances
- two types
    - Managed Service Instances
    - Userr Provided Service Instances
- Multiple deployment options
- Choose plan based on projected growth

**Create a Service Instance**

```
cf marketpalce
cf marketplace -e SERVICE_OFFERING
cf create-service 
cf create-service build-workzone-standard standard wzdemo
cf services
```
