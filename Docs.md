# SHA-1 key
>To generate the **SHA-1** Key, locate to the project file and then open the terminal in the ```root location```.

```json
keytool -list -v -keystore path to\upload-keystore.jks -alias upload
```
---
# KeyStore.jks
>To generate the ```upload-keystore.jks``` file
- Run the command below to generate the java key store file.
- Make sure to verify the alias key ```upload``` for the release builds.
  

```json
keytool -genkey -v -keystore path\upload-keystore.jks -keyalg RSA -keysize 2048 -validity 10000 -alias upload
```
>[!IMPORTANT]
>After the ```KeyStore.jks``` file is created make sure to create another important file named **key.properties** to make the required `info` about key store available to the SDK.

### key.properties
```json
    storePassword=your_keystore_password
    keyPassword=your_alias_password
    storeFile=upload-keystore.jks
    keyAlias=upload
```

- [x] Paste these in that `key.properties` file and then fill it with appropriate details.

Also check if your current project needs some additional changes to perform in order to integrate the **Java Key Store**.
