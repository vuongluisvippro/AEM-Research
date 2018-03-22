# Agenda:
Follow this link: https://helpx.adobe.com/experience-manager/using/first_htl_WCMUsePojo.html

# Notice
> **HeroTextBean class**
>> - The HeroTextBean defines two class members and contains getter and setter methods. The following Java code represents this class. 

    public class HeroTextBean {

        /** The heading text. */
        private String headingText;

        /** The description. */
        private String description;
        /**
         * @return the headingText
         */
        public String getHeadingText() {
            return headingText;
        }
        /**
         * @param headingText the headingText to set
         */
        public void setHeadingText(String headingText) {
            this.headingText = headingText;
        }
        /**
         * @return the description
         */
        public String getDescription() {
            return description;
        }
        /**
         * @param description the description to set
         */
        public void setDescription(String description) {
            this.description = description;
        }

    }
    
>> - **HeroTextComponent class**
>>> - The HeroTextComponent is the Java server-side part of the AEM HTL component. This class extends the WCMUsePojo class. You override the activate method in this class. The following Java code represents the activate method.

    public void activate() throws Exception {
        Node currentNode = getResource().adaptTo(Node.class);
        heroTextBean = new HeroTextBean();
        if(currentNode.hasProperty("jcr:Heading")){
            heroTextBean.setHeadingText(currentNode.getProperty("./jcr:Heading").getString());
        }
        if(currentNode.hasProperty("jcr:description")){
            heroTextBean.setDescription(currentNode.getProperty("./jcr:description").getString());
        } 
    }
    
>>> - Function activate of WCusePojo
>>>> - A Node instance is created by calling the getReource().adaptTo() method. This returns the node that corresponds to component's dialog. Notice that the following methods:
>>>> - currentNode.getProperty("./jcr:Heading") ;
>>>> - currentNode.getProperty("./jcr:description");
>>>> - This code retrieves the values that the user enters into the component's dialog. The values ./jcr:Heading and ./jcr:description corresponds to the property values that you set when defining the component's dialog. (These values are defined in the classic and touch-ui dialogs.)
>>>> - The following Java code represents the HeroTextComponent Java class.

> **Adjust file pom.xml**
> **Build the OSGi bundle using Maven**
>>> - To build the OSGi bundle by using Maven, perform these steps:
>>>> - Open the command prompt and go to the C:\AdobeCQ\myHTL62.
>>>> - Run the following maven command: mvn -PautoInstallPackage install.
>>>> - The OSGi component can be found in the following folder: C:\AdobeCQ\myHTL62\core\target. The file name of the OSGi component is myHTL62.core-1.0-SNAPSHOT.jar.
>>>> - The command -PautoInstallPackage automatically deploys the OSGi bundle to AEM.
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl/cq1.png)
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl/cq2.png)

> **Create the HTL Front End Component**
>> - When you use the Maven Archetype 10 archetype to create an AEM project, a default front end project is created, as shown in the following illustration.
>> - We need to sync CRX with Intellij

> **AEM+Filevault+Intellij integration**
>> - Setup the vault tool
>>> - The next task to perform is to setup the vault tool so Intellij can use it to synchronize between AEM JCR and IntelliJ. For example, later in this development article, a template and page component is created using CRXDE lite. You can synchronize the code using the vault tool from Intellij, which is shown later.
>>> - From within IntelliJ, click File, Settings. Select External tools and click the + icon.
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_2/cq3.png)
>>> - Install package: **vault-cli-3.1.6**
>>> - Take package: **filevault.zip**
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_2/cq4.png)
>>> - Unzip file and put in this location
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_2/cq5.png)
>>> Configure code below **check out**
>>> - Name: whatever you want (For example: "check out")
>>> - Group: whatever you want (For example: "vault" )
>>> - Description: Whatever you want
>>> - Program: **/opt/vault-cli-3.1.16/bin/vlt**
>>> - Parameters: **co http://localhost:4502/crx --force --credentials admin:admin**
>>> - Working Directory: Where you put your project (For example: **/home/lorence/Desktop/AEM-Research/myHTL62**)
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_2/cq6.png)
>>> - Similarity **check in**
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_2/cq7.png)

>> **Write code**
>>> - Location: **/apps/myHTL62/components/content/helloworld/helloworld.html**

# STATUS 1:

![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_2/cq8.png)
>>> - Checkout and we have result below
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_2/cq9.png)
>>> - View form reality
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_2/cq10.png)
>>> - This is reason of issue  **HelloWorldModel not to show**
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl-2/cq11.png)

# STATUS 2:

>>> - **Check in** with vault on each exactly file **helloworld.xml**
>>> - Type command line **mvn -PautoInstallPackage install**
>>> - Running website
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_2/cq12.png)

# GET STARTED WITH HTL Component
>>> - @Link: https://helpx.adobe.com/experience-manager/htl/using/getting-started.html
>>> - @link https://helpx.adobe.com/experience-manager/using/first_htl_WCMUsePojo.html

# Dowload Intellivault
> **Link** https://plugins.jetbrains.com/plugin/7328-intellivault
> **Configuration**
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_2/cq13.png)
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_2/cq14.png)
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_2/cq15.png)
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_2/cq16.png)
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_2/cq17.png)

# Add HTL code
> **Jumping into apps/.../myHTL62/components/helloworld/helloworld.html**
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_2/cq18.png)
>> - Write code

        <p>This is your AEM HTML Template Language component:</p>
        <div data-sly-use.heroTextObject="com.foo.service.core.HeroTextComponent" data-sly-test="${heroTextObject}">
               <h1>${heroTextObject.heroTextBean.headingText}</h1>
               <p>${heroTextObject.heroTextBean.description}</p>    
        </div>
        
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_2/cq19.png)
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_2/cq20.png)

>> - Distinguish between **Touch UI Dialog** and **Classic UI Dialog**
>>> - **Touch UI Dialog**
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_2/cq21.png)
>>> - **Classic UI Dialog**
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_2/cq22.png)
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_2/cq23.png)

> - **Create the helloworld dialog**
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_2/cq24.png)

## Create the Touch UI Dialog
>>> - Perform these tasks to create the AEM Touch UI dialog for the helloworld component:
- 1. Select **/apps/myHTL62/components/content/helloworld**.
- 2. Right click and select Create, Create Node.
- 3. Enter the following values:
> - Name: cq:dialog
> - Type: nt:unstructured
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_2/cq25.png)
>> - Click SaveALL
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_2/cq26.png)

>> - Continue

- 4. Add the following properties to the cq:dialog node.
> - helppath (String) - en/cq/current/wcm/default_components.html#Carousel
> - jcr:title (String) - Hero Text
> - sling:resourceType (Stgring) - cq/gui/components/authoring/dialog
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_2/cq27.png)

- 5. Click on the following node: /apps/myHTL62/components/content/helloworld/cq:dialog.
- 6. Right click and select Create, Create Node. Enter the following values:
> - Name: content
> - Type: nt:unstructured
- 7. Add the following property to the content node.
sling:resourceType (String) - **granite**/ui/components/foundation/container
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_2/cq28.png)
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_2/cq29.png)

- 9. Right click and select Create, Create Node. Enter the following values:
> - Name: layout
> - Type: nt:unstructured
- 10. Add the following properties to the layout node.
> - sling:resourceType (String) - granite/ui/components/foundation/layouts/tabs
> - type (String) -nav
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_2/cq30.png)

- 11. Click on the following node: /apps/myHTL62/components/content/helloworld/cq:dialog/content.
- 12. Right click and select Create, Create Node. Enter the following values:
> - Name: items
> - Type: nt:unstructured

- 13. Click on the following node: /apps/myHTL62/components/content/helloworld/cq:dialog/content/items.
- 14. Right click and select Create, Create Node. Enter the following values:
> - Name: herotext
> - Type: nt:unstructured
- 15. Add the following properties to the herotext node (this node represents the tab).
> - jcr:title (String) - Hero Text Properties
> - sling:resourceType (String) - granite/ui/components/foundation/section
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_2/cq31.png)

- 16. Click on the following node: /apps/myHTL62/components/content/helloworld/cq:dialog/content/items/herotext.
- 17. Right click and select Create, Create Node. Enter the following values:
> - Name: layout
> - Type: nt:unstructured
- 18. Add the following property to the layout node.
> - sling:resourceType (String) - granite/ui/components/foundation/layouts/fixedcolumns
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_2/cq32.png)

- 19. Click on the following node: /apps/myHTL62/components/content/helloworld/cq:dialog/content/items/herotext.
- 20. Right click and select Create, Create Node. Enter the following values:
> - Name: items
> - Type: nt:unstructured

- 21. Click on the following node: /apps/myHTL62/components/content/helloworld/cq:dialog/content/items/herotext/items.
- 22. Right click and select Create, Create Node. Enter the following values:
> - Name: columns
> - Type: nt:unstructured

- 23. Click on the following node: /apps/myHTL62/components/content/helloworld/cq:dialog/content/items/herotext/items/column.
- 24. Add the following property to the columns node.
> -  sling:resourceType (String) - granite/ui/components/foundation/container
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_2/cq33.png)

- 25. Click on the following node: /apps/myHTL62/components/content/helloworld/cq:dialog/content/items/herotext/items/column.
- 26. Right click and select Create, Create Node. Enter the following values:
> - Name: items
> - Type: nt:unstructured

- 27. Click on the following node: /apps/myHTL62/components/content/helloworld/cq:dialog/content/items/herotext/items/column/items.
- 28. Right click and select Create, Create Node. Enter the following values:
> - Name: headingText
> - Type: nt:unstructured
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_2/cq34.png)

- 29. Click on the following node: /apps/myHTL62/components/content/helloworld/cq:dialog/content/items/herotext/items/column/items/headingText.
- 30. Add the following properties to the headingText node (this node represents the Heading Text input control on the dialog. See the illustration at the start of this article.)
> - fieldLabel (String) - Heading Text
> - name (String) - ./jcr:Heading
> - sling:resourceType (String) - granite/ui/components/foundation/form/textfield
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_2/cq35.png)

- 31. Click on the following node: /apps/myHTL62/components/content/helloworld/cq:dialog/content/items/herotext/items/column/items.
- 32. Right click and select Create, Create Node. Enter the following values:
> - Name: description
> - Type: nt:unstructured

- 33. Click on the following node: /apps/myHTL62/components/content/helloworld/cq:dialog/content/items/herotext/
items/column/items/description.
- 34. Add the following property to the description node (this node represents the Description input control on the dialog. See the illustration at the start of this article.)
> - fieldLabel (String) - Description
> - name (String) - ./jcr:description
> - sling:resourceType (String) - granite/ui/components/foundation/form/textarea
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_2/cq36.png)

## Create the Classic Dialog
### Perform these tasks to create the AEM Classic UI dialog for the helloworld component:
- 1. Select /apps/myHTL/components/content/helloworld, right click and select Create, Create Dialog.
- 2 . In the Title field, enter herohtl.
- 3. Click Ok.
- 4. Delete all nodes under /apps/myHTL62/components/content/helloworld/dialog/.
- 5. Click on the following node: /apps/myHTL62/components/content/helloworld/dialog.
- 6. Right click and select Create, Create Node. Enter the following values:
> - Name: items
> - Type: cq:WidgetCollection
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_2/cq37.png)
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_2/cq38.png)

- 7. Select the /apps/myHTL62/components/content/helloworld/dialog/items node.
- 8. Right click and select Create, Create Node. Enter the following values:
> - Name: tab3
> - Type: cq:Widget
- 9. Click on the following node: apps/myHTL62/components/content/helloworld/dialog/items/tab3.
- 10. Add the following properties to the tab3 node.
> - title (String) - Text Details
> - xtype (String) -  panel

- 11. Click on the following node: apps/myHTL62/components/content/helloworld/dialog/items/tab3.
- 12. Right click and select Create, Create Node. Enter the following values:
> - Name: items
> - Type: cq:WidgetCollections.
- 13. Click on the following node:  apps/myHTL62/components/content/helloworld/dialog/items/tab3/items.
- 14. Right click and select Create, Create Node. Enter the following values:
> - Name: headingText
> - Type: cq:Widget
- 15. Add the following properties to the headingText node.
> - fieldLabel (String) -  Heading Text
> - hideLabel (Boolean) - true
> - name (String) - ./jcr:Heading
> - xtype (String) - textfield

- 16. Click on the following node: apps/myHTL62/components/content/helloworld/dialog/items/tab3/items.
- 17. Right click and select Create, Create Node. Enter the following values:
> - Name: description
> - Type: cq:Widget
- 18. Add the following properties to the description node.
> - fieldLabel (String) - Description
> - name (String) - ./jcr:description
> - xtype (String) - textarea
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_2/cq39.png)
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/tab_component_htl_2/cq40.png)

