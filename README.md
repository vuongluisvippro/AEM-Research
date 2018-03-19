# What is AEM?
> **Level 1**: AEM stands for Adode Experience Manager
>> CMS : Content Management System is a computer application that supports the creation and modification of digital content. **Digital content** is any content that exists in the form of digital data. Also known as digital media, digital content is stored on digital or analog storage in specific formats. Forms of digital content include information that is digitally broadcast, streamed, or contained in computer files.

**OSGI Framework**: 
- is a set of specifications that define a dynamic component system for Java. These specifications enable a development model where applications are (dynamically) composed of many different (reusable) components. 
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/master/1.png)

- **Modules** The fundamental concept that enables such a system is modularity.
- **Services** 

**How To Get Started With OSGi?**

# Let's get started with new project

> **Install Maven 3.2.1 on Ubuntu by command line:**
>> - sudo apt-get remove maven2
>> - sudo add-apt-repository "deb http://ppa.launchpad.net/natecarlson/maven3/ubuntu precise main"
>> - sudo apt-get update
>> - sudo apt-get install maven3
>> - sudo ln -s /usr/share/maven3/bin/mvn /usr/bin/mvn
>> - sudo apt-get update

> **Copy the Maven configuration file named settings.xml from [install location]\apache-maven-3.0.4\conf\ to your user profile**
>> - Take file settings.xml
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/master/cq1.png)
>> - Find hidden folder (.m2) from local computer and paster file settings.xml [DONE]
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/master/cq2.png)
>> - Configure settings.xml like this: 
https://github.com/vuongluisvippro/AEM-Research/blob/master/settings.xml

> **Running it:** 
>> - mvn archetype:generate -DarchetypeGroupId=com.adobe.granite.archetypes -DarchetypeArtifactId=aem-project-archetype -DarchetypeVersion=10 -DarchetypeRepository=https://repo.adobe.com/nexus/content/groups/public/
>> - Fill in 
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/master/cq3.png)
>> - You can get more information below
When prompted, specify the following information:  
- groupId - AEM62App 
- artifactId - echo62
- version - 1.0-SNAPSHOT
- package - com.aem.community
- appsFolderName - AEM62App  
- artifactName - AEM62App 
- componentGroupName - AEM62
- contentFolderName - AEM62App 
- cssId - AEM62CSS
- packageGroup -AEM62App 
- siteName - AEM62App 
> **Open folder project "echo2" by Eclipse or IJ**
 ![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/master/cq4.png)
 
> **Notice about structure of modules in website**
>> - After you import the project into Eclipse, notice each module is a separate Eclipse project: 
>>> - core - where Java files that are used in OSGi services and sling servlets are located
>>> - launcher - where additional Java files are located
>>> - tests - Java files for tests like JUNIT tests
>>> - apps - content under /apps
>>> - content - content under /content

> **Notice attach JDK 1.8 to fix error "Setup SDK"

> **Explore some avaiblible files in folder including**
>> - TestHelloWorldModel.java
>>> - is used to perform JUNIT tests

>> - LoggingFilter.java
>>> - performs a simple servlet filter operation that logs incoming requests.
>>> - using the @SlingFilter annotation that supports filter processing by applying filter chains requests before dispatching to the servlet for processing. For more information: https://sling.apache.org/documentation/the-sling-engine/filters.html

>> - SimpleResourceListener.java
>>> - Is a service to demonstrate how changes in the resource tree can be listened for
>>> - It registers an event handler service and uses these annotations
>>>> - @Component – defines the class as a component
>>>> - @Service - defines the service interface that is provided by the component
>>>> - For more information: http://felix.apache.org/documentation/subprojects/apache-felix-maven-scr-plugin/scr-annotations.html

>> - HelloWorldModel.java
>>> - Using Sling Model annotations such as @Model. For more information: https://sling.apache.org/documentation/bundles/models.html

>> - SimpleScheduledTask.java
>>> - get executed regularly
>>> - It also demonstrates how property values can be set. For more information: https://sling.apache.org/documentation/bundles/scheduler-service-commons-scheduler.html

>> - SimpleServlet
>>> - Represents a simple AEM servlet created using Apache Sling APIs.
>>> - Using resoure type binding to invoke the servlet

> **Modify the Maven POM file**
>> - Open file porn.xml in folder project.
>> - Adjust some information about project

> **Build the OSGi bundle using Maven**
>> - To build the OSGi bundle by using Maven, perform these steps:
>>> - Open the command prompt and go to the C:\AdobeCQ\echo62 folder.
>>> - Run the following maven command: mvn -PautoInstallPackage install.
>>> - The OSGi component can be found in the following folder: C:\AdobeCQ\echo62\core\target. The file name of the OSGi component is echo62.core-1.0-SNAPSHOT.jar.

> **Viewing the running OSGi bundle**
>> - Using this website to display: http://localhost:4502/system/console/bundles
>> - Notice: View your OSGi bundle by performing these steps:
>>> - Login to Adobe CQ’s Apache Felix Web Console at http://server:port/system/console/bundles (default admin user = admin with password= admin).
>>> - Click the Bundles tab, sort the bundle list by Id, and note the Id of the last bundle.
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/master/cq5.png)
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/master/cq6.png)
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/master/cq7.png)
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/master/cq8.png)
