### z/OS Connect Enterprise Edition embedding feature

Configuration files to create a Liberty feature which allows z/OS Connect Enterprise Edition to be run in a standalone WebSphere Liberty server.

This requires WebSphere Liberty V8.5.5.8 or higher.

#### Create ifaedjreg Bundle

Run the command `jar -cvmf ifaedjreg/MANIFEST.MF com.ibm.zosconnect.sample.ifaedjreg-1.0.jar`

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
