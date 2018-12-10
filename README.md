## eSDK\_FC\_SDK\_Java
FusionCompute is a cloud operating system software that is responsible for the virtualization of hardware resources and centralized management of virtual resources, service resources, and user resources.
It uses virtual computing, virtual storage, virtual network and other technologies to complete the virtualization of computing resources, storage resources, and network resources. At the same time, the virtual resources are centrally scheduled and managed through a unified interface, thereby reducing the running cost of the service, ensuring the security and reliability of the system, and assisting operators and enterprises to build a secure, green, and energy-efficient cloud data center capability.

**FusionCompute Java SDK** provides FusionCompute's standardized interface based on JAVA language. It provides you with hardware resource virtualization and business integration capabilities for virtual resources, business resources, and centralized management of user resources.

## Version
FusionCompute Java SDK latest version: v2.1.0

## Development environment / compatibility
- Source code: Java 1.6
- Java Development Kit: 7u10,recommended version 1.7 and above
- Tomcat: Tomcat 7.0 and above

## Directory structure
- Source code: `src/`
- Sample code: `sample/`
- Interface reference: `doc/`

## Getting started
- You can generate a `*.jar` file by downloading the source code and running `mvn package`. The file will be generated in the `target/` directory.
- Otherwise, if you use Maven to manage the dependencies in your Java project, add the following code to the `<dependencies>` section in your `pom.xml`.

```xml
<dependency>
    <groupId>com.huawei</groupId>
    <artifactId>esdk-fusioncompute</artifactId>
    <version>2.1.0</version>
</dependency>
```

### User login
The following code demonstrates how to log in to the FusionCompute system to help you quickly understand the capabilities of the FusionCompute Java SDK.

```java
public static void main(String[] args) {
    ClientProviderBean clientProvider = new ClientProviderBean(); 
    clientProvider.setServerIp("172.22.39.9");
    clientProvider.setProtocol(useHttps ? "https" : "http");
    clientProvider.setServerPort(useHttps ? "7443" : "7070");

    clientProvider.setVersion(6.1f);
    clientProvider.setUserName(username);

    AuthenticateResource auth = ServiceFactory.getService(AuthenticateResource.class, clientProvider);
    FCSDKResponse<LoginResp> resp = auth.login(username, hashedPassword); // SHA-256
}
```

## Get help
During the development process, you can go to the [DevCenter](https://devcenter.huawei.com) and browse the docs. You can also find or ask questions in the [Huawei Developer Community](https://developer.huawei.com/ict/en/site-cloud/product/fusioncompute). In addition, there is the Huawei technical support hotline: 400-8828-000. Huawei technical support email: esdk@huawei.com
