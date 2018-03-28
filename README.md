# Define a design in AEM
Follow this link: https://helpx.adobe.com/support/experience-manager/6-3.html
> - **Steps to creating Client Library**
>> - 1. Define a design
>> - 2. Create client library 
>> - 3. Call client library
>> - 4. Assign a design to website
>> **Define a design*

>>> - Access this link: **http://localhost:4502/miscadmin**
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/htl_design_aem/cq1.png)
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/htl_design_aem/cq2.png)

>>> - Standing here: *http://localhost:4502/miscadmin#/etc/designs* and Create **New Page**
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/htl_design_aem/cq3.png)
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/htl_design_aem/cq4.png)
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/htl_design_aem/cq5.png)

>>> - Access this link: **/etc/designs/training**
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/htl_design_aem/cq6.png)

>> **Creating client library**
# WAY 1: IMPORT AVAILABLE PACKAGE
>>> - Prepare **css** and **js** outside and import CRX. For example: **we-train-design-package.zip**
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/htl_design_aem/cq7.png)
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/htl_design_aem/cq8.png)

>>> - Access this link: **apps/training**
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/htl_design_aem/cq9.png)
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/htl_design_aem/cq10.png)

>>> - Move folder **clientlib-all** to ****
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/htl_design_aem/cq11.png)
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/htl_design_aem/cq12.png)

>>> - Using **Ctrl + F** to adjust file **css** or **js**
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/htl_design_aem/cq13.png)
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/htl_design_aem/cq14.png)

# WAY 2: CREATE FOLDER 
>>> - Create structure below
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/htl_design_aem/cq15.png)
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/htl_design_aem/cq16.png)

>>> - Add attribute **categories** into **clientlib-training**
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/htl_design_aem/cq17.png)


>> **Calling client library in AEM**
>>> - Come back to **/apps/myHTL62/components/structure/modularizepage**
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/htl_design_aem/cq18.png)
>>> - Create **customheaderlibs.html.html** and **customfooterlibs.html**
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/htl_design_aem/cq19.png)
>>> - Adjust file

    <!--/* Include the site client libraries (loading only the CSS in the header, JS will be loaded in the footer) */-->
    <sly data-sly-use.clientLib="/libs/granite/sightly/templates/clientlib.html" data-sly-call="${clientLib.css @ categories='we.train.all'}" />

    <!--/* Include the site client libraries (loading only the JS in the footer, CSS was loaded in the header) */-->
    <sly data-sly-use.clientLib="/libs/granite/sightly/templates/clientlib.html" data-sly-call="${clientLib.js @  categories='we.train.all'}"/>
    
>> **Assign a design to website**
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/htl_design_aem/cq20.png)
>>> - *View Properties* of **myHTL62**
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/htl_design_aem/cq21.png)
>>> - Move to tab **Advanced** and notice item **Design** 
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/htl_design_aem/cq22.png)
>>> - Click **Save** and **Close**
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/htl_design_aem/cq23.png)







