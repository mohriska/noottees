# Cache in Fiori

SAP NOTE: 2319491

## Cache

You have three places where caching happens: 
* Client ( SAPUI5 apps & SAP FLP )
* Gateway ( SAPUI5 apps & OData service )
* Backend ( OData Service )

![cache_image](./images/sapui5_sap_fiori_odata_cache.jpg)
0. ### Clear your browser cache 

First and foremost, get rid of your browser cache. You can either delete it or open your SAPUI5 app in an incognito window. The incognito window doesn’t use cache. For example, in Chrome, press CTRL + ALT + N to open an incognito window.

1. ### Clear the Gateway Cache
* Open transaction SE38. Execute the program ```/UI2/INVALIDATE_CLIENT_CACHES```
* Execute the program ```/UI5/UPDATE_CACHEBUSTER```.
  * This program lets you manually trigger the cache buster. With an active cache buster, new resources are pulled from the server rather than the browser’s cache. The SAPUI5 and SAP Fiori cache buster is enabled by the SICF service /sap/bc/ui2/flp. Open transaction SICF and navigate to sap > bc > ui2 > flp.
* Execute the program ```/UI2/INVALIDATE_GLOBAL_CACHES```.
  * Use it with caution since it recalculates the target mapping for all users and SAPUI5 apps.
* Execute the program ```/UI2/CHIP_SYNCHRONIZE_CACHE```.
  * Check that there is no error in ```/UI2/CHIP_CHDR```
* Clear your /UI2/ cache after import of a support package. Execute the program ```/UI2/DELETE_CACHE_AFTER_IMP```
* Clear your /UI5/ cache. Execute the program ```/UI5/APP_INDEX_CALCULATE```.
  * SAPUI5’s app index provides indexing and caching for data relating to SAP Fiori apps, components, and libraries.
* Clear your ICM.  Open transaction ```SMICM```. In the top menu, select ```HTTP plugin > Server Cache > Invalidate Locally```.
  * Afterward, invalidate globally too: HTTP plugin > Server Cache > Invalidate Globally. 
  * ICM caches HTTP(S) objects before sending them to the client. 
  * When an object is requested again, the application will get it from the cache.
* Clear your /IWFND/ cache (OData metadata)
  * Transaction ```/n/IWFND/CACHE_CLEANUP```
* Clear your /IWFND/ cache (OData metadata)
  * Execute the program ```/UI5/UPD_ODATA_METADATA_CACHE```.
  * Updates OData cache tokens for back-end systems.


2. ### Clear the Backend Cache
* Clean your /IWBEP/ cache (OData metadata)
  * Transaction in backend: ```/n/IWBEP/CACHE_CLEANUP```



3. ### Disable Caches for SAPUI5, SAP Fiori, and OData Service
* Deactivate your SAPUI5 and SAP Fiori cache
  * Open transaction SU01 or SU03. 
  * Set for users the parameters ```/UI2/CACHE_DISABLE``` to ```X``` and ```/UI2/PAGE_CACHE_OFF``` to ```X```.
* Deactivate your OData metadata cache
  * Open transaction ```SPRO```. Navigate to ```Gateway > OData Channel > Administration > Cache Setting > Metadata```.


4. ### Synchronize chip cache
   Run the report ```/UI2/CHIP_SYNCHRONIZE_CACHE```. Make sure there is no error in the table ```/UI2/CHIP_CHDR```.

Run the report ```/UI2/DELETE_CACHE_AFTER_IMP```. ```/UI2/DELETE_CACHE ```

5. ### Run cache buster
   Run the report /UI5/UPDATE_CACHEBUSTER.

6. ### Clear local browser cache – to avoid views and resources being displayed from local browser cache or else implement cache buster
   
7. ### UI2 Cache

   Run report ```/UI2/INVALIDATE_GLOBAL_CACHES```. 

    This cache clearing is mandatory especially to verify the translations integrated for ex tiles,groups,catalogs in Launchpad admin

8. ### Fiori client app is capable of handling local cache whenever new resources are available in the server so no need of manual cache management implementation



-----


### FrontEnd

| Transcation                                                                          | Description                        |
|--------------------------------------------------------------------------------------|------------------------------------|
| ``` SMICM ``` (Goto -> HTTP plugin -> Server cache -> Invalidate Locally and Globally) | Clear the server http cache.       |
| ``` /UI2/CACHE ```                                                                   | Register service for UI2 cache use |
| ``` /UI2/CACHE_DEL ```  ```/UI2/DELETE_CACHE```                                                             | Delete cache entries               |
| ``` /n/UI2/INVAL_CACHES ```                                                          ||
| ``` /n/IWFND/CACHE_CLEANUP ```                                                       | Clear metadata cache (OData)       |
| ``` /n/UI2/CHIP_SYNCHRONIZE_CACHE ```                                                ||
| ``` /n/UI2/DELETE_CACHE_AFTER_IMP ```                                                ||
| ``` /n/UI5/UPDATE_CACHEBUSTER ```                                                    ||
| ``` /n/UI2/INVALIDATE_GLOBAL_CACHES ```                                              ||
| ``` /UI5/APP_INDEX_CALCULATE ```                                                     |                                    |
| ``` /UI2/INVALIDATE_GLOBAL_CACHES ```                                                |                                    |
| ``` /UI2/INVALIDATE_CLIENT_CACHES ```                                                | Invalidate Cahce at Client         |
| ```/UI2/DELETE_CACHE_AFTER_IMP```                                                    | Synchronize chip cache (Report). Make sure there is no error in the table ```/UI2/CHIP_CHDR```  |


### BackEnd

| Transcation                 | Description                  |
|-----------------------------|------------------------------|
| ``` /n/IWBEP/CACHE_CLEANUP ``` | Clear metadata cache (OData) |
