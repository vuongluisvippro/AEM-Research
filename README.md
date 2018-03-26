# Agenda:
Follow this link: https://www.youtube.com/channel/UC5LctNk2GMEknreC-ZJO7vQ
> - **Install Package**
>> - Where can I get package from AEM
  
    mvn clean install
    
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_3/cq1.png)
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_3/cq2.png)
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_3/cq3.png)

> - **Folder description**
>> - **/app**: custom templates, components, run modes.
>> - **/conf**: All configurations of site
>> - **/libs**: out of the box components
>> - **/content**: All content of your website
>> - **/etc**: client library, design dialog info
>> - **/tmp**: temporary working area here
>> - **/var**: contains files that change or updated by the system
>> - **/home**: information about the users and group

> - **Create a Project structure in AEM**
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_3/cq4.png)

> - **Create Page rendering component in AEM**
>> - Collection of scripts
>> - Modular, reusable unit.
>> - What does reusable unit contain?
>>> - Text
>>> - image
>>> - header
>>> - breadcrump
>>> - video
>> - You can use Adobe Experience XD to simulator about structure of website.
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_3/cq5.png)
>> - Follow step by step to creat 'component'
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_3/cq6.png)
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_3/cq7.png)
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_3/cq8.png)
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_3/cq9.png)


> - **Observe URL path**
>> - **/apps/training/components/structure/contentpage**
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_3/cq10.png)
>> - Navigate **/apps/training/components/structure/contentpage/contentpage.html**
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_3/cq11.png)
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_3/cq12.png)

# Notice
- If you want to create struture and put it in your aemHTL62 and sycn with IJ Editor.

> - **Create a template in AEM**
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_3/cq13.png)
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_3/cq14.png)
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_3/cq15.png)
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_3/cq16.png)
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_3/cq17.png)

> - Observe **We.Train Content page**
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_3/cq18.png)
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_3/cq19.png)
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_3/cq20.png)
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_3/cq21.png)
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_3/cq22.png)

> - **Decomposing a URL in AEM**
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_3/cq23.png)

> - **Apache Sling resource resolution with example**
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_3/cq24.png)
>> - Create file blue.html
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_3/cq25.png)
>> - Double click we-train
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_3/cq26.png)
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_3/cq27.png)
> - **CREATE PAGE REDERING COMPONENT IN AEM**
>> - Let's synchronize between CRX and AEM
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_3/cq28.png)
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_3/cq29.png)
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_3/cq30.png)
>> - Notice here: When you create component. Normally, we use libs are supported in AEM
   
    **wcm/foundation/components/page**
    
>> - How to access libs follow this path:
>>> - Just access this path **/libs/wcm/foundation/components/page**

>> - Go to detail **contentpage[structure]**
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_3/cq31.png)
>>> - Change contentpage.jsp into contentpage.html
>>> - Save All please
>>> - Push CRX
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_3/cq32.png)

>>> - Adjust content in contentpage.html
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_3/cq33.png)
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_3/cq34.png)
>>> - **mvn clean install**

> - **CREATE A TEMPLATE IN AEM**
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_3/cq35.png)
>> - **mvn clean install**
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_3/cq36.png)






