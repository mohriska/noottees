# Manifest YAML


### Cloud Foundry - Creating YAML Manifests

Manifest tells the CF PUSH what to do with app. 
* Describes push activities
* Looks locally for manifest.yaml
* Required and optional parameters
* Multi-app support 

```
--- # 3 dashes are required
# comment in a manifest
Applications: 
    -   name: <name of the website> #
        buildpack:                  # 
        stack:                      #
        domain:                     # 
        host: manage                #
        command: node app.js        #
        instances: 3                #
        memory: 512M                #
        path: ./web/                #
        timeout: 60                 #
        no-route: true              #
Services: 
    -   wzdemo
    -   rabbitqueue
```


```
---
# multiple applications in one yaml
Applications: 
    -   name: donationswebsite
        instances: 2
        path: ./web/
    -   name: donationpoller
        instances: 1
        path: ./worker/
```

or

```
---
# multiple applications in one yaml
instances: 2
Applications: 
    -   name: donationswebsite
        path: ./web/
    -   name: donationpoller
        path: ./worker/
```

Manifest can have parent - child relationships
```
---
# child manifest
inherit: base_manifest.yml
Applications: 
    -   name: donationwebsite
        path: ./web/
        instances: 3
        memory: 1GB
```


### Example of manifest

```
---
applications: 
- name: pscloudfoundryservice
  memory: 128MB
  instances: 1
  command: node ./bin/www
services: 
- mymongo
```

then: 

```
cf push <appname>
cf push -help
```