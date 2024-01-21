# SQLite3 as DB for CAP

## DB in SQLite 3 for development
- install dependecies for development only by: ```npm i sqlite3 -D```
- deploy to sqlite3 DB by: ```cds deploy --to sqlite:bookshop.db```

## Access SQLite3 DB
- open terminal and : ```sqlite3```
- open db: ```.open bookshop.db```
- open tables: ```.tabbles```
- use SQL to query SQLite3:

```
SELECT * FROM CatalogService_Authors;
SELECT COUNT(*) FROM CatalogService_Authors;
```

- close ```.exit```


## Create connection in SAP BAS
- Icon of a storage bin on the left toolbar
- in terminal ```ls -l``` and  ```pwd```
- add necessary info and **Test It**  & **Save it**


## Deploy to DB
* Root project folder: ```cds deploy``` to deploy to SQLite3 DB



## To Query DB from SAP BAS
* create a ```queries.http``` file and add e.g.:
```
GET http://localhost:4004/odata/v4/catalog/Books
```
* for info, which port is expost go to> ```Command Pallet: Ports: Preview```