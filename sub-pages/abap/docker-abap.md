* [sapse/abap-cloud-developer-trial](https://hub.docker.com/r/sapse/abap-cloud-developer-trial)
* [Install ABAP Platform Trial 2022 on Google Cloud Platform and Install ABAP SDK](https://codelabs.developers.google.com/abap-sdk/install-abap-on-gcp#2)

Run from folder where a4h.txt is located... license

```
docker run --stop-timeout 3600 -i --name a4h -h vhcala4hci -p 3200:3200 -p 3300:3300 -p 8443:8443 -p 30213:30213 -p 50000:50000 -p 50001:50001 sapse/abap-cloud-developer-trial:ABAPTRIAL_2022_SP01 -skip-limits-check -agree-to-sap-license
```

Hardware Key . . : T0194705127

J0103265132
docker cp <local file path> <container name>:/opt/sap/ASABAP_license

HDB Hardware Key   : L2183778543
```
docker rm -f a4h
```

```
docker stop -t 7200 a4h
```

```
docker start -ai a4h
```

### License
You can check the expiry date of your ABAP license in the transaction **SLICENSE** in SAPGUI

---

1. Logon to your ABAP system with the user SAP*, client 000, same password as for DEVELOPER (DEVELOPER , client 001, is locked).

2. Start transaction SLICENSE; copy the hardware key.
3. Get the license from the following site, choosing the system A4H: SAP Licenses for Preview, Evaluation, and Demo Systems - "minisap"⁠
4. Back in your ABAP System, start SLICENSE again, then choose Install.
5. Log off, then log on with the user DEVELOPER, client 001.
6. Start SLICENSE again; remove the old invalid licenses. (sap* is not allowed to delete licenses).



### Cloud Connector

```
docker exec -it a4h bash
```

```
/usr/local/sbin/rcscc_daemon start
```

```
https://localhost:8443
```

```
/usr/local/sbin/rcscc_daemon stop
```

```
exit
```
