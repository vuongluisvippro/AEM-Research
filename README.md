# Install the AEM Movie Component package
> **Setup Maven in your development environment**
>> - Done with settings.xml
 
> **Create an Experience Manager archetype project**
>> - Done with pom.xml

> **Fetch component**
>> - Open the command prompt and go to your working directory (for example, /home/xxxx/Desktop/AEM-Research).
>>> - Run **mvn archetype:generate -DarchetypeRepository=https://repo.adobe.com/nexus/content/groups/public/ -DarchetypeGroupId=com.day.jcr.vault -DarchetypeArtifactId=multimodule-content-package-archetype -DarchetypeVersion=1.0.2 -DgroupId=com.moviecomponent.moviecomponent.core.service -DartifactId=movie -Dversion=1.0-SNAPSHOT -Dpackage=com.moviecomponent.moviecomponent.core.service -DappsFolderName=myproject -DartifactName="My Project" -DcqVersion="5.6.1" -DpackageGroup="My Company"**
>>> - When prompted for additional information, specify Y.
>>> - Once done, you will see a message like:
[INFO] Total time: 03:34 min
[INFO] Finished at: 2018-03-20T10:27:34+07:00
[INFO] Final Memory: 15M/210M
>>> - Open it with IJ Editor.

> **Delete all packages other than com.moviecomponent.moviecomponent.core.service. Next make sure to delete all generated JAVA files**
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_movie_component_1/cq1.png)

> **Make sure that the only Java files in this package are these ones:**
>> - Constant - defines constant variables used in this AEM service
>> - MovieInterface - defines an operation named getUpcomingMovies that returns a list of upcoming movies
>> - MovieService - defines implementation application logic
>> - MovieQuery- this class uses the AEM QueryBuilder API to query the AEM DAM

> **Constant**
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_movie_component_1/cq2.png)
>> - The Constant class defines constants used by the service. One values is the path in the AEM DAM where the digital assets are stored. The following Java code represents class.

> **MovieInterface**
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_movie_component_1/cq3.png)

> **MovieService**
>> - The MovieService extends com.adobe.cq.sightly.WCMUse and represents the entry into the service. This class exposes the activate method that performs initialization task for the movie component. In this use case, the activate method creates an instance of the Movie interface:
>> - **rvice = getSlingScriptHelper().getService(MovieInterface.class);**
>> This class also exposes a method named getFiles that returns an ArrayList instance that contains a list of path locations. Each value represents a path to a digial asset that is displayed in the Upcoming Movies tab of the HTL component. (See the illustration shown at the start of this article.)
>> - ollowing Java code represents the MovieService class. 

> **INITIALIZE AGAIN**
> **Follow this link** https://helpx.adobe.com/experience-manager/using/first-arch10.html
>> - Configure these attributes below:
>>> - groupId: aemMovie62
>>> - version: 1.0-SNAPSHOT: : 1.0
- package: : com.moviecomponent.moviecomponent.core.service
- appsFolderName: aemMovie62
- artifactName: aemMovie62
- componentGroupName: aemMovie62
- contentFolderName: aemMovie62
- cssId: aemMovie62
- packageGroup: aemMovie62
- siteName: aemMovie62
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_movie_component_2/cq4.png)

> **Open project with IJ**
>> - Using Ij to open aemMovie62 [ AEM Movie 62]
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_movie_component_2/cq5.png)
>> - Re-install again and observe movie component appear on website. (JUST ONE WAY)

> **Delete these files not involves inside package com.moviecomponent.moviecomponent.core.service.core**
>> - Delete these files
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_movie_component_2/cq6.png)
>> - Come back to this link: https://helpx.adobe.com/experience-manager/using/htl_movie62.html
>> - Write code
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_movie_component_2/cq7.png)
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_movie_component_2/cq8.png)
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_movie_component_2/cq9.png)
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_movie_component_2/cq10.png)

>> - Adjust pom.xml

          <dependency>
               <groupId>com.adobe.aem</groupId>
               <artifactId>uber-jar</artifactId>
               <version>6.2.0</version>
               <!-- for AEM6.1 use this version     : <version>6.1.0</version> -->
               <!-- for AEM6.1 SP1 use this version : <version>6.1.0-SP1-B0001</version> -->
               <!-- for AEM6.1 SP2 use this version : <version>6.1.0-SP2</version> -->
               <!-- for AEM6.2 use this version     : <version>6.2.0</version> -->
               <classifier>obfuscated-apis</classifier>
               <scope>provided</scope>
           </dependency>
             
           <dependency>
               <groupId>org.apache.geronimo.specs</groupId>
               <artifactId>geronimo-atinject_1.0_spec</artifactId>
               <version>1.0</version>
               <scope>provided</scope>
           </dependency>

>> - Follow step:
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_movie_component_2/cq11.png)
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_movie_component_2/cq12.png)

>> - Adjust file pom.xml in core folder: 

      <dependencies>
        <!-- OSGi Dependencies -->
             
        <dependency>
            <groupId>com.adobe.aem</groupId>
            <artifactId>uber-jar</artifactId>
            <classifier>obfuscated-apis</classifier>
        </dependency>
  
        <dependency>
            <groupId>org.apache.geronimo.specs</groupId>
            <artifactId>geronimo-atinject_1.0_spec</artifactId>
        </dependency>
        <dependency>
            <groupId>org.apache.jackrabbit</groupId>
            <artifactId>jackrabbit-api</artifactId>
            <version>2.10.0</version>
            <scope>provided</scope>
         </dependency>
         <dependency>
             <groupId>com.day.commons.osgi.wrapper</groupId>
             <artifactId>com.day.commons.osgi.wrapper.commons-lang2</artifactId>
             <version>2.5-0001</version>
             <scope>provided</scope>
         </dependency>
         <dependency>
            <groupId>org.apache.felix</groupId>
            <artifactId>org.apache.felix.scr</artifactId>
        </dependency>
        <dependency>
            <groupId>org.apache.felix</groupId>
            <artifactId>org.apache.felix.scr.annotations</artifactId>
        </dependency>
        <dependency>
            <groupId>biz.aQute</groupId>
            <artifactId>bndlib</artifactId>
        </dependency>
        <dependency>
            <groupId>org.osgi</groupId>
            <artifactId>org.osgi.core</artifactId>
        </dependency>
        <dependency>
            <groupId>org.osgi</groupId>
            <artifactId>org.osgi.compendium</artifactId>
        </dependency>
        <!-- Other Dependencies -->
        <dependency>
            <groupId>org.slf4j</groupId>
            <artifactId>slf4j-api</artifactId>
        </dependency>
        <dependency>
            <groupId>javax.jcr</groupId>
            <artifactId>jcr</artifactId>
        </dependency>
        <dependency>
            <groupId>javax.servlet</groupId>
            <artifactId>servlet-api</artifactId>
        </dependency>
        <dependency>
            <groupId>com.adobe.aem</groupId>
            <artifactId>aem-api</artifactId>
        </dependency>
        <dependency>
            <groupId>org.apache.sling</groupId>
            <artifactId>org.apache.sling.models.api</artifactId>
        </dependency>
        <dependency>
            <groupId>junit</groupId>
            <artifactId>junit</artifactId>
        </dependency>
        <dependency>
            <groupId>org.mockito</groupId>
            <artifactId>mockito-all</artifactId>
        </dependency>
        <dependency>
            <groupId>junit-addons</groupId>
            <artifactId>junit-addons</artifactId>
        </dependency>
    </dependencies>
    
>> - Follow step: Override these old files.
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_movie_component_2/cq13.png)


>> - Remove Ui.test, Ui.lanncher and somethings here
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_movie_component_2/cq14.png)
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_movie_component_2/cq15.png)

>> - Result achieve
>>> - Run **mvn clean install** or **mvn -PautoInstallPackage install**
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_movie_component_2/cq16.png)
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_movie_component_2/cq17.png)

>>> - Go to this link: http://localhost:4502/system/console/bundles
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_movie_component_2/cq18.png)

>>> - Click install/update
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_movie_component_2/cq19.png)
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_movie_component_2/cq20.png)
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_movie_component_2/cq21.png)

>>> - Click Acitivate 
# Fix error
> **Go to this website: https://mvnrepository.com/**
>> - Search keyword: For example  **org.apache.felix:org.apache.felix.scr:jar**
>> - Go to detail services: https://mvnrepository.com/artifact/org.apache.felix/org.apache.felix.scr
>> - Go to detail each version(pick newest version) https://mvnrepository.com/artifact/org.apache.felix/org.apache.felix.scr/2.0.14
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_movie_component_2/cq22.png)

> **Track error from command line**
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_movie_component_2/cq23.png)
>> - We have 13 errors
>> - Fix with 

    <!-- https://mvnrepository.com/artifact/org.apache.felix/org.apache.felix.scr -->
    <dependency>
        <groupId>org.apache.felix</groupId>
        <artifactId>org.apache.felix.scr</artifactId>
        <version>2.0.14</version>
    </dependency>
    
>> - Fix bugs ==> Backup file pom.xml

