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

> **STOP HERE**
For more information here: https://helpx.adobe.com/experience-manager/using/movie.html
