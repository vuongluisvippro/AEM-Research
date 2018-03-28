# Creating simple navigation component
Follow this link: https://helpx.adobe.com/support/experience-manager/6-3.html
> - **Website Structure**
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/htl_design_aem_2/cq1.png)
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/htl_design_aem_2/cq2.png)

> - **Using Code snippets** in **Sublime Text**
>> - Define code to create Navigation Bar

    <li class="nav navbar-nav" data-sly-repeat="${currentPage.listChildren}">
      <a href="${item.path}.html">${item.title}</a>
    </li>
    
>> - Include to header.html 

    <div data-sly-resource="${'site-topnav' @ resourceType='training/components/content/site-topnav'}"></div>
    
>> - Follow steps by step
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/htl_design_aem_2/cq3.png)
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/htl_design_aem_2/cq4.png)

    <!-- /* Basic mock up code */ -->
    <nav class="navbar navbar-inverse navbar-absolute-top">

        <ul class="nav navbar-nav navbar-center">
            <li class="nav navbar-nav navbar-left" data-sly-repeat="${currentPage.listChildren}">
                <a href="${item.path}.html">${item.title}</a>
            </li>
        </ul>

    </nav>
    
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/htl_design_aem_2/cq5.png)

    <div class="navbar navbar-inverse navbar-fixed-top hidden-xs">
        <div class="container-fluid">
            <nav style="color: white;" >Language Navigation</nav>
            <ul class="nav navbar-nav navbar-right" style="color: white;" >
                <sly>Toolbar</sly>
            </ul>
        </div>
    </div>

    <div data-sly-resource="${'site-topnav' @ resourceType='training/components/content/site-topnav'}"></div>

![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/htl_design_aem_2/cq6.png)








