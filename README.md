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

