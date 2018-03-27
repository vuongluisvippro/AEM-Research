# Agenda:
Follow this link: https://www.youtube.com/channel/UC5LctNk2GMEknreC-ZJO7vQ
> - **Analyze Structure**    
>> - We have two components for creating page **homepage** ang **page**
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_4/cq1.png)
>> - **homepage** component. We define hard code (HTML or JS not need to using HTL)

    <!DOCTYPE html>
      <html>
      <body>
        <h1>My First Heading</h1>
        <p>My first paragraph.</p>
      </body>
    </html>

![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_4/cq2.png)
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_4/cq3.png)
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_4/cq5.png)

>> **page** component. We use HTL and allow user drag and configure widget
  
  <!--/*
    Copyright 2015 Adobe Systems Incorporated
  
    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at
  
        http://www.apache.org/licenses/LICENSE-2.0
  
    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
    */-->
    <div class="page__main" data-sly-use.main="main.js">
        <header class="page__header">
            <div class="page__logo" data-sly-resource="logo"></div>
            <nav class="page__topnav" data-sly-resource="topnav"></nav>
        </header>

        <div class="page__title" data-sly-resource="${'title' @ decorationTagName='div'}"></div>
        <div class="page__par" data-sly-resource="par"></div>
      <div>This is my template for HOMEPAGE</div>

        <footer class="page__footer">
            <p class="page__copyright">${"&copy; {0} myHTL62 Site. All rights reserved." @ i18n, format=main.year, context='html'}</p>
        </footer>
    </div>

![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_4/cq4.png)
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_4/cq5.png)

> **allowedPaths**
>> - For example: myHTL62 just only have one template: **template-home-page**
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_4/cq6.png)
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_4/cq7.png)

>> - We create a new Template for **myHTL62**
>>> - Case 1: **http://localhost:4502/sites.html/content** + **/content(/.*)?**
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_4/cq8.png)

>>> - Case 2: **http://localhost:4502/sites.html/content/aemMovie62** + **/content(/.*)?**
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_4/cq9.png)

>>> - Case 3 **http://localhost:4502/mnt/overlay/wcm/core/content/sites/createpagewizard.html/content/myHTL62** + **/content/myHTL62(/.*)?**
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_4/cq10.png)

>>> - Case 4 **http://localhost:4502/mnt/overlay/wcm/core/content/sites/createpagewizard.html/content** + **/content/myHTL62(/.*)?**
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_4/cq11.png)

> **allowedTemplates**
>> - We want to take **Template Child Page** from **myHTL62** to **aemMovie62** by allowedTemplates
>> - Go to **/content/aemMovie62**
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_4/cq12.png)
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_4/cq13.png)

> **ADDING THUMBNAIL TO PAGE IN AEM**
>> - View propertiese of page
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_4/cq14.png)
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_4/cq15.png)
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_4/cq16.png)
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_4/cq17.png)

> **CREATE WEBSITE STRUCTURE IN AEM**
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_4/cq18.png)

> **Sightly / HTL language**
>> - **HTL** stands for **HTML template language** 
>>> - **Templating Language**
>>> - **HTL is HTML5**
>>> - **Alternate of JSP**
>>> - **Simplied Development**
>>> - **Security**
>>> - **Separation of concern**

       e.g: <p data-sly-use.obj="script.js">${obj.text}
       
> **Sightly Syntax with examples**
