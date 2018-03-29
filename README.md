# Practice Page
Follow this link: https://helpx.adobe.com/experience-manager/using/toy_login.html
> - **Setup Package**
>> - **template-htl-page**
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/htl_java_use_api/cq1.png)

    In addition to this, the Use-API has some common variables available right off the bat.
    - currentNode
    - currentPage
    - resource
    - log
    - sling
    - pageProperties
    - properties
    - pageManager
    - component
    - designer
    - currentDesign
    - currentStyle

![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/htl_java_use_api/cq2.png)
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/htl_java_use_api/cq3.png)
        
>> - **https://www.youtube.com/watch?v=sqIL3JiZeLw**
>>> - Observe useful of using Bracket before coding

    <div>
        <h1>${properties.title}</h1>
        <p>${properties.description}</p>
    </div>
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/htl_java_use_api/cq4.png)
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/htl_java_use_api/cq5.png)

>> - **Install and Configure brackets with Adobe CQ or AEM**
>>> - Follow step by step
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/htl_java_use_api/cq6.png)
>>> - Go to **AEM/Project Settings**

    Location: http://localhost:4502
    username: admin
    password: admin
    
>>> - Open folder with location address: **/home/lorence/Desktop/Lorence/AEM-Research/myHTL62/ui.apps/src/main/content**
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/htl_java_use_api/cq7.png)
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/htl_java_use_api/cq8.png)
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/htl_java_use_api/cq9.png)
>>> - Click icon AEM(Green icon) to synch between CRX and Bracket.
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/htl_java_use_api/cq10.png)
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/htl_java_use_api/cq11.png)
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/htl_java_use_api/cq12.png)

# HTL User Guide
> - **What is HTL?**
>> - Fundamental Concepts of HTL

    <h1 data-sly-test="${properties.jcr:title}">${properties.jcr:title}</h1>
    
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/htl_java_use_api/cq13.png)

>>> - HTL Block Statements
>>>> - data-sly-use analyze into three parts **data** - **sly** - **use**
>>>> - **data** + more information here https://helpx.adobe.com/experience-manager/htl/using/block-statements.html

>> - Upgrade code

        <!DOCTYPE html>
        <html>
        <head>
            <title>Getting Started with HTL</title>
        </head>
        <body>
            <div>
                <sly data-sly-test="${properties.jcr:title && properties.jcr:description}">
                    <h1>${properties.jcr:title}</h1>
                    <p>${properties.jcr:description}</p>
                </sly>
            </div>
        </body>
        </html>

        <!DOCTYPE html>
        <html>
        <head>
            <title>Getting Started with HTL</title>
        </head>
        <body>
            <!--/* An HTL Comment */-->
            <!-- /*  If there are both, a jcr:title and a jcr:decription property defined, 
        and if none of them are empty: -->
            <div data-sly-test="${properties.jcr:title || properties.jcr:description}">
                <h1>${properties.jcr:title}</h1>
                <p>${properties.jcr:description}</p>
            </div>
        </body>
        </html>
        
>> - How can we have this attribute **properties.jcr:description**
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/htl_java_use_api/cq14.png)
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/htl_java_use_api/cq15.png)

>> - **HTL Comments**
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/htl_java_use_api/cq16.png)

# Learning HTL (HTL AGAIN 1)
<> Follow this site: https://github.com/Adobe-Marketing-Cloud/aem-htl-sample-todomvc
> - **HTL intro part 1**
>> - **myHTL62/components/structure/sample1**
>> - Access link: **currentpage.name docs.adobe.com**
>>> - Google Key: "currentpage.name docs.adobe.com"
>>> - References: http://blogs.adobe.com/experiencedelivers/experience-management/htl-intro-part-1/

        <!DOCTYPE html>
        <html>
        <head>
            <title>Getting Started with HTL</title>
        </head>
        <body>
            <!--/* An HTL Comment */-->
            <div>currentPageName: ${currentPage.name}</div>
            <div>currentPagePath: ${currentPage.path}</div>
            <div>currentPageLanguage: ${currentPage.language}</div>
        </body>
        </html>

![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/htl_java_use_api/cq17.png)
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/htl_java_use_api/cq18.png)

        <!DOCTYPE html>
        <html>
        <head>
            <title>Getting Started with HTL</title>
        </head>
        <body>
            <!--/* An HTL Comment */-->
            <div data-sly-test="${wcmmode.edit}">Show this only in edit mode to the author: ${wcmmode.edit}</div>
        </body>
        </html>

![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/htl_java_use_api/cq19.png)

        <!DOCTYPE html>
        <html>
        <head>
            <title>Getting Started with HTL</title>
        </head>
        <body>
            <!--/* An HTL Comment */-->
            <div data-sly-test.author="${wcmmode.edit || wcmmode.design}">Show this to the author </div> 
            <div data-sly-test="${!author}"> Not in author mode anymore.. </div>
        </body>
        </html>

        <div data-sly-text="${currentPage.title}">Mock page title</div>
        
        <!DOCTYPE html>
        <html>
        <head>
            <title>Getting Started with HTL</title>
        </head>
        <body>
            <!--/* An HTL Comment */-->
            <ul data-sly-list.child="${currentPage.listChildren}"> <li>${child.title}</li> </ul>
        </body>
        </html>
        
## PENDING HERE

        

### Preferences 
- @link: https://helpx.adobe.com/experience-manager/htl/using/use-api-javascript.html
- @link: https://helpx.adobe.com/experience-manager/htl/user-guide.html?topic=/experience-manager/htl/morehelp/html-template-language.ug.js
- @link: https://helpx.adobe.com/experience-manager/htl/using/dev-tools.html
- @link: https://helpx.adobe.com/experience-manager/6-3/sites/developing/using/aem-brackets.html
- @link: http://brackets.io/#

### Preference Bracket
- @link: https://github.com/adobe/brackets/wiki/Brackets-Shortcuts

