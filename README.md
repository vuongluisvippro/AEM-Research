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

