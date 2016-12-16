### z/OS Connect Enterprise Edition embedding instructions

Configuration files to create a Liberty feature which allows z/OS Connect Enterprise Edition open beta to be run in a standalone WebSphere Liberty server.

This requires WebSphere Liberty V16.0.0.3 or higher with the [Java EE Web Profile 7.0](https://developer.ibm.com/wasdev/downloads/#asset/features-com.ibm.websphere.appserver.webProfile-7.0) feature installed.

Please note this is an experimental feature for use only with the z/OS Connect EE open beta. The are no guarantees that this will become a supported option in a production environment.

#### Configure the Liberty installation

Copy the `zosconnect.properties` file to `wlp/etc/extensions/`. If you modified the location of the z/OS Connect EE install from the default then you will need to update this file to include that modification.

By default `$WLP_USER_DIR` is the `usr` directory under the WebSphere Liberty install directory.

*Note:* If transferring this file via ftp to the mainframe it should be transferred as binary.

#### Configure the Liberty server

Add the feature

```
<feature>zosconnect:zosconnect-2.0</feature>
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
