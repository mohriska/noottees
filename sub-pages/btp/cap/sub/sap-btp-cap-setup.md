## Setup

[<- Back to Content](./../sap-btp-cap-readme.md)


- Windows requires you to install SQLite
    - Create a folder called ```C:\sqlite``` and unzipe the contents of the download to this folder
    - Run sqlite3.exe within this folder
    - Add SQLite to your PATh Environment Variable (see http://s-prs.co/v560611)
    - then it is possible to run SQLite anywhere with command: sqlite3
- MACOSX
    - XCode installed & XCode CLI
        - in terminal run ```xcode-select --install```
    - Cloud Foundry cli
        - installer is in GitHub repository
        - if you have brew: ```brew install cloudfoundry/tap/cf-cli```
        - validate by: cf --version
    - @ui5/cli
        - install @ui5/cli by: ```npm install --global @ui5/cli```
        - verify: ```ui5 --version```
    - UI5 tooling
        - install by: ```npm install --global @sap/ux-ui5-tooling```
    - Yeoman
        - install Yeoman by: ```npm i --global yo```
        - verify by: ```yo --version```
    - CDS Dev Kit
        - if you already have it installed, remove it first
        - install by: ```npm install --global @sap/cds-dk```
        - verify by: ```cds --version```
    - VSCode + Extensions
        - install extension: SAP CDS Language Support


## Setup CAP

```
// check cds-dk in USER
npm ls -g --depth=0

// check if you have access sap npm libraries/packages
npm config list 

// if not, then:
npm set @sap:registry=https://npm.sap.com
npm search --registry https://npm.sap.com sap

// install sap cds packages
npm i -g @sap/cds-dk
cds help


// sqlite3
npm i sqlite3

```



## Run
```
cds run --in-memory // in the package.json 
```