
[<- Beck](./../sap-btp-cap-readme.md)

### Deployment Dependencies
- install support for local role teesting on your CDS server with the npm module Passport
    - install by: ```npm i -g passport```
- Cloud MTA Build Tool
    - install by: ```npm i -g mbt```
    - verify by: ```mbt``` in terminal
- Cloud Foundry CLI
    - if it is installed already, uninstall it first and then install newer version
        - uninstall by: ```cf uninstall-plugin multiapps```
    - install by: ```cf install-plugin multiapps```
