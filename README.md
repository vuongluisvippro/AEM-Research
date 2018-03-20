# Agenda:
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_movie_component_3/cq1.png)

> **Deploy the bundle to Experience Manager**
>> - Deploy the OSGi bundle to Experience Manager by performing these steps:
>>> - Login to Apache Felix Web Console at http://server:port/system/console/bundles (default admin user = admin with password= admin).
>>> - Click the Bundles tab, sort the bundle list by Id, and note the Id of the last bundle.
>>> - Click the Install/Update button.
>>> - Browse to the bundle JAR file you just built using Maven. (C:\AdobeCQ\aemMovie62\core\target).
>>> - Click Install.
>>> - Click the Refresh Packages button.
>>> - Check the bundle with the highest Id.
>>> - Click Active. Your new bundle should now be listed with the status Active.
>>> - If the status is not Active, check the CQ error.log for exceptions.
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_movie_component_3/cq2.png)

> **Movie component dialog**
