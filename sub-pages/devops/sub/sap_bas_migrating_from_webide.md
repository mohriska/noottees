[<-- Back](./../README.md)

# SAP BAS Migrating from SAP Web IDE

## Migrating SAP Fiori app from SAPWebIDE to BAS
1. Open SAPWebIDE and project in it
2. Right-click on it and select <b>Export</b>
3. Open SAP BAS and import it to some workspace
4. Click on the <b>Import</b> option and ```Start Migration```
5. If migration is done sucesfully, create new file under ```webapp``` folder called ```xs-app.json```
6. Add content to xs-app.json
```
{
    "authenticationMethod" : "none",
    "routes" : [
        {
            "source" : "^(.*)$",
            "target" : "$1",
            "service"  : "html5-apps-repo-rt"
        }
    ]
}
```
7. Delete : 
```
    neo-app.json
    package-lock.json
```
8. After deletion, right click on app folder and click ```Preview Application```
9. select option: ```start noflp fiori run --open "index.html"```
10. Should work - DONE

***

## Migrating SAP CAP from SAPWebIDE to BAS
1. Open SAPWebIDE and project in it
2. Right-click on it and select <b>Export</b>
3. Create Full-Stack Cloud Application space in SAP BAS
4. Import it to SAP BAS
5. Remove ```.che``` folder
6. check ```srv``` and ```db``` modules
7. Click on ```Run Configuration``` add ```db``` configurations and bind the bindings
8. Check your ```db``` bindings and deploy ```cds```  to the <b>SAP HANA</b> instance
9. Go to ```package.json``` and recheck the dependencies and versions
10. From ```RUN CONFIGURATIONS``` panel, click on the ```Run Application``` button
11. DONE