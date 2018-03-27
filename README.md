# Agenda:
Follow this link: https://helpx.adobe.com/support/experience-manager/6-3.html
> - **Sightly Syntax with examples**    
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_5/cq1.png)
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_5/cq2.png)
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_5/cq3.png)
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_5/cq4.png)
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_5/cq5.png)
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_5/cq6.png)

> - **There are two directions here**
>> - **Direction 1: HTL Java Use-API**
>>> - Google search: HTL Java Use-API
>>> - @link https://helpx.adobe.com/experience-manager/htl/using/use-api-java.html
>>> - @link https://helpx.adobe.com/experience-manager/6-3/sites/developing/using/we-retail.html

>> - **Direction 2:**
>>> - @link https://helpx.adobe.com/experience-manager/6-3/sites/developing/using/page-templates-editable.html

>> - **Direction 3:**
>>> - @link: http://blogs.adobe.com/experiencedelivers/experience-management/htl-intro-part-3/

> - **currentPage, properties and currentNode object in AEM**
>> - **currentPage**

      **currentPage** Instance of the page (AEM api) class.
      Eg: ${currentPage.Title}
      
      properties object: Instance of the ValuleMap(Sling api) class.
      Eg : Title : ${properties.jcr:title}
      
      currentNode object : Instance of the Node(JCR api) class.
      Eg: ${currentNode.Name}
      
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_5/cq7.png)
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_5/cq8.png)
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_5/cq9.png)

> - **Render basic page content in AEM**
>> - Refer example code here: https://github.com/pankajchhatri/AEM
>> - Remove **blue.html** and chage **homepage.html** into **another content**

      <!doctype html>
      <html>
      <head>
          <meta charset="utf-8"/>
          </head>
          <body>
              <h1>Hello World!!</h1>
                  <h3>Sling PropertiesObject</h3>
                  <p>Page Title : ${properties.jcr:title}</p>

                  <h3>Page Details</h3>
                  <p>currentPage Title: ${currentPage.Title}</p>
                  <p>currentPage Name: ${currentPage.Name}</p>
                  <p>currentPage Path: ${currentPage.Path}</p>
                  <p>currentPage Depth: ${currentPage.Depth}</p>

                          <h3> Node Details </h3>
                  <p>currentNode Name: ${currentNode.Name}</p>
                  <p>currentNode Path: ${currentNode.Path}</p>
                  <p>currentNode Depth: ${currentNode.Depth}</p>
          </body>
      </html>
      
>> - Demonstration
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_5/cq10.png)
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_5/cq11.png)

> - **Modularize the Page rendering(contentpage) component**
>> - Understand of structure of website
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_5/cq12.png)

>> - It's very important for all of pages. **Here we go. Let's get started**
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_5/cq13.png)
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_5/cq14.png)

> - **Inheritance in AEM**
>> - Move to this page: **/apps/myHTL62/components/structure/modularizepage**
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_5/cq15.png)
>> - Notice

     wcm/foundation/components/page
     
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_5/cq16.png)

>> - We you remove **wcm/foundation/components/page** and we didn't open **Open Properties**
>> - We delete **modularizepage.html** in **/apps/myHTL62/components/structure/modularizepage** and lauch website
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_5/cq17.png)

>> - *EXPLAIN THIS MATTER* **wcm/foundation/components/page** + **/libs/wcm/foundation/components/page/page.html**

     <!--/*~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
       ~ Copyright 2016 Adobe Systems Incorporated
       ~
       ~ Licensed under the Apache License, Version 2.0 (the "License");
       ~ you may not use this file except in compliance with the License.
       ~ You may obtain a copy of the License at
       ~
       ~     http://www.apache.org/licenses/LICENSE-2.0
       ~
       ~ Unless required by applicable law or agreed to in writing, software
       ~ distributed under the License is distributed on an "AS IS" BASIS,
       ~ WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
       ~ See the License for the specific language governing permissions and
       ~ limitations under the License.
       ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~*/-->
     <!DOCTYPE HTML>
     <html>
         <head data-sly-include="head.html"></head>
         <body data-sly-use.body="body.js" class="${body.cssClasses}"
                 data-sly-include="body.html"></body>
     </html>

![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_5/cq18.png)

> - **client library in AEM**









