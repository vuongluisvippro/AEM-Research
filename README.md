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
>> - Navigate **/apps/moviecomponent/components/content/tab-component/dialog** with CRX mode
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_movie_component_3/cq3.png)

> **PathField**
>> - For example: /apps/moviecomponent/components/content/tab-component/dialog/items/movie-details/items/video
>> - This node contain a child node named video of type granite/ui/components/foundation/form/pathbrowser. This node is a pathbrowser that lets an author select the JCR path to where the video for the movie trailor is located. This pathbrowser is shown in the following illustration.  
>> - Open **/apps/moviecomponent/components/content/tab-component/tab-component.html
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_movie_component_3/cq4.png)
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_movie_component_3/cq5.png)

>> - The name property of this node is ./video.  Once this value is set, it is used in the HTL  component to render the video. The following code represents the section of the HTL component that uses the value of the video node. 

        <div id="mvideo">

         <video id="my-video" class="video-js" controls preload="auto" width="640" height="264" poster="${properties.fileReference}" data-setup="{}">
         <source src="${properties.video}" type='video/mp4'>
         <p class="vjs-no-js">
            To view this video please enable JavaScript, and consider upgrading to a web browser that
         <a href="http://videojs.com/html5-video-support/" target="_blank">supports HTML5 video</a>
        </p>
        </video>

>> - Notice how the value of the video nodes name property is used: 
>> - **<source src="${properties.video}"**
>> - This is used in a video html element to render the video (the asset in the AEM DAM).  

> **Interacting with the MovieService**
>> - Notice the node located at: 
>> - Location: **/apps/moviecomponent/components/content/tab-component/cq:dialog/content/items/random-movie/items**
>> - This node has two child nodes: 
>>> - movies-path - specifies the path where the digital assets are located for the Upcoming Movies tab. This node is a granite/ui/components/foundation/form/pathbrowser. 
>>> - number - specifies the number of assets to display. ThIs node is a granite/ui/components/foundation/form/textfield. 

> **Analysis Node**
>> - **/apps/moviecomponent/components/content/tab-component/cq:dialog/content/items/random-movie/items**
>> - This node has two child nodes: 
>>> - movies-path - specifies the path where the digital assets are located for the Upcoming Movies tab. This node is a granite/ui/components/foundation/form/pathbrowser. 
>>> - number - specifies the number of assets to display. ThIs node is a granite/ui/components/foundation/form/textfield. 

### For more information: https://helpx.adobe.com/experience-manager/using/htl_movie62.html
