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


