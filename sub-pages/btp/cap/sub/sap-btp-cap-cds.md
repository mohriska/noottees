# CAP CDS

### Entity:
- An entity is a distinct object containing a set number of CDS elements
- You can also refer to an entity as a table or a design-time file
- represent data with primary keys

### Element
- An element is a property, specifically a property in relation to an entity
- And element can be a simple key and type, or you can apply element modifiers to specify that it is a key or default value

### Type
- A descriptor of the CDS element describing the primitive type (e.g.: string or integer)

The following code defines an example entity:

```
entity Car : {
    brand : String;
    model : String;
    buildDate : Date;
    color : String;
    weight : Integer; 
}

```

* create ```cds``` file in ```srv``` folder, e.g.:
```
service say {
    function hello (to: String) returns String;
    
}
```


### Custom types & Enums
```
namespace db.example;

type Rating: Integer enum {
    Best = 5;
    Good = 4;
    Average = 3;
    Poor = 2;
    Worst = 1;
}

type Amount {
    value: Decimal(10,3);
    currency: Currency; 
}

// usage of a type & enum


entity Products {
    key ID: Integer;
    title : String;
    rating: Rating; 
    price : Amount;
}

```


### Aspects

* Aspects in CDS helps enhance modularity by allowing you to group behaviors into manageable parts that can be used by multiple entities.
* In example, ```managedBy``` is an aspect further used in the <b>Products</b> entity
* DB for <b>Products</b> would be 4 columns

```
aspect managedBy{
    createdAt: Timestamp;
    createdBy: String;
}

entity Products: managedBy{
    key ID : Integer;
    title: String;
}
```

### Views
* Entities can be further exposed as other entities using
    * ```as select from``` OR
    * ```as projection on```
* These new entities are mapped to an SQL view in the database
* The difference is
    * ```as select from ``` can be used with joins, SQL clauses, unions.
    * ```as projection on ``` can not be used with SQL

```
entity Products as select from Products;
entity Products as select from Products where ID = 1;
entity Products as projection on Products;
```

### Service Definitions

* You can define a service in CDS by exposing entities enclosed in a service block

```
service ProductService{
    entity Products as projection on Products;
    entity Product_1 as select from Products where ID = 1;
}
```





### Implement Services (in Node.js)
- it is possible to use ```Express.js``` or ```JS ES6 classes```
- ```Express.js``` is recommended way
- with ```JS ES6 classes``` there are some restriction, like only registering only one handler per event event
- to implement the service, you must create a JS file to match your service definition
- create same file as cds but with ```.js``` extension in the same folder

```
module.exports = (say) => {
    say.on("hello", req => `Hello ${req.data.to}!`);
}
``` 

### Consuming Services
```
http://localhost:4004/say/hello(to='readers')

```


## Association_Composition

[<- Back to Content](#content)

You'll use it to maintain relationships between entities


## Associations
* In an association, all objects have their own lifecycles, and there is no ownership.
* e.g.: A book can be associated with one or more authors.

### Unmanaged Associations
* In unmanaged Association, you'll specify the join clause using a foreign key.

```
entity Books {
    key ID: Integer; 
    title: String;
    author_ID: Integer;  // foreign key to Authors
    author : Association to Authors on author.ID = author_ID;
}

entity Authors {
    key ID: Integer;
    name : String;
}
```

In OData it looks like this:

![unmanaged](./images/1.jpg)


----

### Managed-to-One Associations

* In a managed-to-one association, you aren't specifying a join clause
* CDS automatically resolves and adds the required foreign key elements from the target entity's primary key
* This example is equivalent to the unmanaged association example shown earlier except that foreign key Author_ID is automatically added to the Books entity when CDS model is deployed to the DB

```
// Managed-to-one Associations
entity Books {
    key ID: Integer;
    title: String;
    author: Association to Authors;
}

entity Authors {
    key ID: Integer;
    name: String;
}

```

###  Managed-to-Many Associations
* one book is associated with one or more authors
* Authors entity contains a backlink (e.g. book), which is specified in the Books entity by using the ```on``` operator

```
entity Books {
    key ID : Integer;
    title: String;
    author: Association to many Authors on author.book = $self;
}

entity Authors {
    key ID: Integer;
    name: String;
    book: Association to Books; // backlink
}
```
![managed-to-many](./images/2.jpg)

-----

### Compositions

* A composition is a special type of association between two entities when one entity owns other entity
* A child entity cannot exist if its parent entity dies. (death relationship)
* e.g.: book and the cover of the book

```
entity Books {
    key ID: Integer;
    title: String;
    bookCovers: Composition of many BookCovers on bookCovers.book = $self; 
}

entity BookCovers {
    key ID: Integer;
    imageName: String;
    book: Association to Books;  // backlink
}
```

* Generated OData is also similar to the managed to-many association
* except: OnDeleteAction="Cascade"

## Query

[<- Back to Content](#content)


CDS Query Language (CQL or CDS QL) is an extension of SQL and upgrades SQL with some really handy features:
- postfix projections
- path expressions
- CDL-Style Casts

### Postfix Projections
CQL allows you to put a SELECT clause behind a FROM clause, enclosed in curly braces.

```
// this has same effect
    Select ID, title from Products;
    Select from Products {ID, title};
```



### CDL-Style Casts

CDS does not support SQL-style type cast. Instead, you can use CDL-style casts.

```
Select from Products {price+100 as NewPrice : Decimal};
```

### Path Expressions

You can use path expressions to navigate along associations and structured elements

```
SELECT from SalesInvoice[ID=1].Products;
```



### Some CDS Commands
* cds help
* cds init
* cds deploy
    * cds deploy --to hana
    * cds deploy --to sqlite
    * cds deploy --to sqlite:db/book-service.db
* cds serve
* cds compile
    * cds compile products.cds --to json
    * cds compile products.cds --to sql
    * cds compile products.cds --to hana
    * cds compile products.cds --to yaml
* cds watch
