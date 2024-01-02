# SAP CDS Notes

###  Mass activation of CDS views in Q:
- report RUTDDLSACT mass activation of CDS views in your Q system

## Content

| Topic                       | Description |
|-----------------------------|-------------|
| [Annotations](#Annotations) | Annotations |
| [Assocations](#Assocations) | Assocations |
| [References](#References)   | References  |

------
## Annotations

[<- Back to Top](#Content)


## Motavition
CDS annotations enrich the plain SQL logic of CDS data models with additional metadata that is interpreted by the ABAP runtime environment and other consumers of the CDS models (developers, analytical engine for aggregation behavior of key figures).

## Annotation definition

The following properties are specified with the technical definition of a CDS annotation:
- Unique name
- Type
- List of admissible(přípustnych) values (optional)
- Default value (optional)
- Admissible(přípustné) scopes for usage


Annotation definition of domain Semantics
```
annotation Semantics
{
    ...
    @Scope:[#ELEMENT]
    unitOfMeasure: Boolean default true;
    @Scope:[#ELEMENT]
    quantity
    {
        unitOfMeasure: ElementRef;
    }
    ...
}
```

### Annotations for Associations

Associations can only be annotated within the projection list; that is, only exposed annotations can be annotated. Annotations can't be added to the association definitions.

### Annotation names

Annotation names are structured hierarchically. Starting from a domain,
for example, Semantics, which groups semantically related CDS annotations
and simultaneously defines the root name, the fully qualified annotation
name is successively composed from several potential hierarchy levels of
intermediate components ending with a leaf element.

### Annotation Domains

| Domain | Description |
| ----------- | ----------- |
| ABAPCatalog | Controls the ABAP runtime environment and the ABAP Data Dictionary (ABAP DDIC) |
| AccessControl | Documents and controls the authorization checks for CDS models |
| Aggregation | Defines elements that can be used as aggregating key figures (successor of  defaultAggregation) |
| Analytics| Defines analytical data models and applications |
| AnalyticsDetails | Defines the details of an analytical query, such as its standard layout and the exception aggregations to be applied |
| ClientHandling | Controls the client handling of CDS models |
| Consumption | Provides hints for CDS model consumers that are evaluated in particular by implementation frameworks |
| EndUserText | Defines translatable label texts |
| Environment | Controls the defaulting logic of parameters with system variables |
| Hierarchy | Defines hierarchical relationships |
| Metadata | Controls the annotation enrichments of a CDS view by enabling CDS metadata xtensions and the propagation of element annotations |
| ObjectModel | Describes the basic structural properties of the data models, including the definition of their transactional aspects|
|OData|Exposes CDS models in OData services|
|Search|Controls search functionality|
|Semantics|Describes the basic semantics of elements and parameters|
|UI|Defines a semantic user interface (UI) representation that is independent of the specific UI implementation technology|
|VDM|Classifies CDS models in the virtual data model (VDM)|


### Groupin Annotations

If 2 annotations start with the same componenets, these annotations can be grouped by curly brackets({}).

```
...
@ObjectModel.dataCategory: #TEXT
@ObjectModel.representativeKey: 'Product'
...
```

and

```
...
@ObjectModel:{
    dataCategory: #TEXT,
    representativeKey: 'Product'
}
...
```

### Type Definitions
- A CDS annotation type can be a scalar value, a structure, or an array

## Annotation usages

## Propagation logic of element annotations

## CDS metadata Extensions

- allow us to branch out annotations from your CDS model definition



## Active Annotations

- Active annotations represent the effective annotations from the consumer's point of view


[<- Back to Top](#Content)

------

## Assocations

[<- Back to Top](#Content)

Assocations představují jiný typ shromažďování dat společně z více tabulek. Říkáme jim Join-on-demand. To znamená, že data ve spojených (přidružených) tabulkách nejsou přístupná přímo za běhu, ale pouze na vyžádání. Spouští se pouze tehdy, když uživatel tato data potřebuje.



[<- Back to Top](#Content)

------

## References

[<- Back to Top](#Content)

- [How to deal with “Not released” predefined VDM in S/4HANA](https://blogs.sap.com/2019/05/23/how-to-deal-with-not-released-predefined-vdm-in-s4hana/)
- [CDS Annotations to create Fiori Application using Business Application Studio](https://www.youtube.com/watch?v=YI9hsd8Al7k)
- [Implement CDS Extensibility for S_4HANA](https://blogs.sap.com/2018/10/03/implementation-of-cds-extensibility-for-s4-hana/)
- [SAP CDS for New And Experienced professionals](https://blogs.sap.com/2022/02/24/sap-cds-for-new-and-experienced-professionals/)
- [Standard CDS View _Extension](https://answers.sap.com/questions/13462957/standard-cds-view-extension.html)
- [Implementation of CDS Extensibility for S/4 HANA](https://blogs.sap.com/2018/10/03/implementation-of-cds-extensibility-for-s4-hana/)
- [How to Extend ABAP CDS View Entity (Core Data Services)](https://blogs.sap.com/2022/09/05/how-to-extend-abap-cds-view-entity-core-data-services/)
- [Cheat Sheet CDS ABAP](https://www.brandeis.de/en/blog/cheat-sheet-cds-abap)
- [Appending MARA (adding custom fields)](https://blogs.sap.com/2016/07/08/appending-mara-adding-custom-fields/)
- [Adding Field in standard Fiori apps of S/4HANA with Custom Fields and Logic](https://blogs.sap.com/2020/02/01/adding-field-in-standard-fiori-apps-of-s-4hana-with-custom-fields-and-logic/)
- [Adding Custom database Field to standard Fiori apps in S/4HANA with Custom Fields and Logic](https://blogs.sap.com/2020/02/06/adding-the-field-already-in-the-table-to-standard-fiori-apps-with-custom-field-and-logic/)
- [A new generation of CDS views: CDS view entities](https://blogs.sap.com/2020/09/02/a-new-generation-of-cds-views-cds-view-entities/)
- [CDS view entities are feature complete. Overview of new features, improvements, and differences](https://blogs.sap.com/2022/05/06/cds-view-entities-are-feature-complete.-overview-of-new-features-improvements-and-differences/)
- [ABAP Core Data Services: New syntax for extending CDS entities](https://blogs.sap.com/2022/02/17/abap-core-data-services-new-syntax-for-extending-cds-entities/)
- [Buffering CDS View Entities](https://blogs.sap.com/2022/01/27/buffering-cds-view-entities/?source=email-global-notification-bp-new-in-tag-followed)
- [BW Query on CDS View, OData from BW and value of BW Query in S/4HANA](https://blogs.sap.com/2018/08/08/bw-query-on-cds-view-odata-from-bw-and-value-of-bw-query-in-s4hana/)
- [Simple way to Identify the ABAP CDS views for the datasource in B4HANA](https://blogs.sap.com/2021/11/29/simple-way-to-identify-the-abap-cds-views-for-the-datasource-in-b4hana/)
- [Custom CDS Views](https://help.sap.com/docs/ABAP_PLATFORM_NEW/b5670aaaa2364a29935f40b16499972d/e30de6eae4d24d70b65996ac8ff88848.html?locale=en-US)
- [SAP HANA Academy - S/4HANA RIG: Create Custom CDS Views in SAP S/4HANA Cloud [3/5]](https://www.youtube.com/watch?v=Bib5rB0je7U)


### AMDP References

- [A Glimpse on AMDP](https://github.com/SAP-samples/abap-cheat-sheets/blob/main/12_AMDP.md)
- [A to Z of AMDP - 2021 ABAP Managed Database Procedure](https://www.youtube.com/watch?v=9zYcz1cNkh0)
- [YouTube - PART 1 - CDS Annotations to create Fiori Application using Business Application Studio](https://www.youtube.com/watch?v=YI9hsd8Al7k&list=PLU0olhFj5UjWiT1qgrZqeFY0gpAJkoap9&index=2)
- [Defining the Custom CDS Entity](https://github.com/SAP-samples/abap-platform-rap-opensap/blob/main/week5/unit3.md)

[<- Back to Top](#Content)
