# Cloud foundry CLI


* **cf api**
```
API endpoint:   https://api.cf.us10-001.hana.ondemand.com
API version:    3.158.0
```

* **cf target**
```
API endpoint:   https://api.cf.us10-001.hana.ondemand.com
API version:    3.158.0
user:           mohriska@aledaproduction.cz
org:            de3434f6trial
space:          dev
```

* **cf login**

* **cf spaces**
```
Getting spaces in org de3434f6trial as mohriska@aledaproduction.cz...

name
dev
```

* **cf create-space testing**
* **cf space dev**
```
Getting info for space dev in org de3434f6trial as mohriska@aledaproduction.cz...

name:                      dev
org:                       de3434f6trial
apps:                      
services:                  connectivity-lite, default_abap-trial, dest-trial, xsuaa-trial
isolation segment:         trial (org default)
quota:                     
running security groups:   public_networks, dns, aws_ext, connectivity_service_security_group_for_space_03b39faf-5b26-4a74-b4ce-a7d558dd66fc
staging security groups:   public_networks, dns, aws_ext
```

* **cf quotas**
```
```

* **cf target -s testing** ... switch spaces
* **cf services** .. get all active services