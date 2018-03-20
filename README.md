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
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_movie_component_1/cq2.png)

> **Make sure that the only Java files in this package are these ones:**
>> - Constant - defines constant variables used in this AEM service
>> - MovieInterface - defines an operation named getUpcomingMovies that returns a list of upcoming movies
>> - MovieService - defines implementation application logic
>> - MovieQuery- this class uses the AEM QueryBuilder API to query the AEM DAM
