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


