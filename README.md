### z/OS Connect Enterprise Edition embedding feature

Configuration files to create a Liberty feature which allows z/OS Connect Enterprise Edition open beta to be run in a standalone WebSphere Liberty server.

This requires WebSphere Liberty V8.5.5.8 or higher with the [Java EE Web Profile 7.0](https://developer.ibm.com/wasdev/downloads/#asset/features-com.ibm.websphere.appserver.webProfile-7.0) feature installed.

Please note this is an experimental feature for use only with the z/OS Connect EE open beta. The are no guarantees that this will become a supported option in a production environment.

#### Create ifaedjreg Bundle

Run the command `jar -cvmf ifaedjreg/MANIFEST.MF com.ibm.zosconnect.sample.ifaedjreg-1.0.jar`

#### Add the necessary files to the Liberty server

1. Copy the file `zosconnect.properties` to `wlp/etc/extensions/`. If you modified the location of the z/OS Connect EE install from the default then you will need to update this file to include that modificiation.
2. Copy the file `com.ibm.zosconnect.sample.ifaedjreg-1.0.jar` to `$WLP_USER_DIR/extension/lib`
3. Copy the file `zosConnectEmbed.mf` to `$WLP_USER_DIR/extension/lib/features`

By default `$WLP_USER_DIR` is the `usr` directory under the WebSphere Liberty install directory.

*Note:* If transferring these files via ftp to the mainframe, all of them should be transferred as binary.

#### Configure the Liberty server

Add the feature

```
<feature>usr:zosconnectembed-1.0</feature>
```
to `server.xml` and configure z/OS Connect EE as per the product documentation.

Copy the `bootstrap.properties` file to server directory or add the contents to your existing `bootstrap.properties` file.

*Note:* If transferring this file via ftp to the mainframe it should be transferred as binary.

#### License

```
Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
```
