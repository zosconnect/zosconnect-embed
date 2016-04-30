### z/OS Connect Enterprise Edition embedding feature

#### Create ifaedjreg Bundle

Run the command `java -jar cvmf ifaedjreg/MANIFEST.MF com.ibm.zosconnect.sample.ifaedjreg-1.0.jar`

#### Add the necessary files to the Liberty server

1. Copy the file `zosconnect.properties` to `wlp/etc/extensions/`. If you modified the location of the z/OS Connect EE install from the default then you will need to update this file to include that modificiation.
2. Copy the file `com.ibm.zosconnect.sample.ifaedjreg-1.0.jar` to `wlp/usr/extensions`
3. Copy the file `zosConnectEmbed.mf` to `wlp/usr/extensions/features`

#### Configure the Liberty server

Add the feature

```
<feature>usr:zosConnectEmbed-1.0</feature>
```
to `server.xml` and configure z/OS Connect EE as per the product documentation.
