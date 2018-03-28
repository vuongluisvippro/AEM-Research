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

    <div data-sly-resource="${'site-topnav' @ resourceType='myHTL62/components/content/site-topnav'}"></div>

![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/htl_design_aem_2/cq6.png)
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/htl_design_aem_2/cq7.png)

> - ***STOP HERE!

> - **Creating Complex navigation component using java helper in AEM**

        package apps.myHTL62.components.content.site_topnav;

        import java.util.*;
        import java.util.Iterator;
        import com.day.cq.wcm.api.Page;
        import com.day.cq.wcm.api.PageFilter;

        import com.adobe.cq.sightly.WCMUsePojo;

        public class TopNav extends WCMUsePojo{
            private List<Page> items = new ArrayList<Page>();
            private Page rootPage;

            // Initializes the navigation
            @Override
            public void activate() throws Exception {
                rootPage = getCurrentPage().getAbsoluteParent(2);

                if (rootPage == null) {
                    rootPage = getCurrentPage();
                }

                Iterator<Page> childPages = rootPage.listChildren(new PageFilter(getRequest()));
                while (childPages.hasNext()) {
                    items.add(childPages.next());
                }
            }

            // Returns the navigation items
            public List<Page> getItems() {
                return items;
            }
            // Returns the navigation root
            public Page getRoot() {
                return rootPage;
            }
        }

        <!-- /* Add the business logic*/ -->
        <div data-sly-use.topnav="TopNav" class="container we-Container--top-navbar">
            <nav class="navbar navbar-inverse navbar-absolute-top">
                <div class="navbar-header">
                    <button type="button" class="navbar-toggle collapsed" data-toggle="collapse" data-target="#we-example-navbar-collapse-inverse" aria-expanded="false">
                        <span class="sr-only">Toggle navigation</span>
                        <span class="icon-bar"></span> <span class="icon-bar"></span>
                    </button>
                    <button type="button" class="navbar-toggle navbar-toggle-close collapsed" data-toggle="collapse" data-target="#we-example-navbar-collapse-inverse" aria-expanded="false">
                        <span class="sr-only">Toggle navigation</span>
                    </button>
                    <a class="navbar-brand" href="${topnav.root.path}.html">we.<strong>train</strong></a>
                    <div class="pull-right visible-xs"></div>
                </div>

                <!-- /.navbar-header -->
                <div class="collapse navbar-collapse width" id="we-example-navbar-collapse-inverse">
                    <ul class="nav navbar-nav navbar-center">
                        <li class="visible-xs"><a href="${topnav.root.path}.html">we.<strong class="text-primary">train</strong></a></li>

                        <!-- /* Nav with business logic */ -->
                        <li class="nav navbar-nav navbar-left" data-sly-repeat="${topnav.items}">
                            <a href="${item.path}.html">${item.title}</a>
                        </li>

                        <li class="visible-xs divider" role="separator"></li>
                    </ul>
                </div>
                <span style="height: 0px;" class="navbar-shutter"></span>
            </nav>
            <!-- /.navbar -->
        </div>
        
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/htl_design_aem_2/cq8.png)

> - **Creating Complex navigation component using javascript helper in AEM**
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/htl_design_aem_2/cq9.png)


