# Practice Page
Follow this link: https://helpx.adobe.com/experience-manager/using/toy_login.html
> - **Setup Package**
>> - We access this folder **package** to get file **AEM_ToySite-1.0**
>> - Install package on **CRX**
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/practice_page_login/cq1.png)

>> - Observe structure of page
>>> - **templates/homepage**
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/practice_page_login/cq2.png)
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/practice_page_login/cq3.png)

>>>>> - **summit_toys/components/structure/homepage** => **/apps/summit_toys/components/structure/homepage/content.html**
#### Static code HOMEPAGE
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/practice_page_login/cq4.png)

>>>> - **templates/apps/summit_toys/templates/contentpage*** => **/apps/summit_toys/components/structure/contentpage** + **/libs/wcm/foundation/components/page/page.html**
#### Include component such as header, footer, ... CONTENTPAGE
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/practice_page_login/cq5.png)

>>>> - **templates//apps/summit_toys/templates/contact-us** => ***/apps/summit_toys/components/content/contact-us/content.html*
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/practice_page_login/cq6.png)

# LET'S GET STARTED
> - **Download Bootstrap Library files**
>> - @Link: http://getbootstrap.com/getting-started/#download
>> - Access this folder **package** to get it.

> - **Create an Experience Manager client library folder**
1. Right-click /etc/clientlibs then select New, Node.
2. Make sure that the node type is cq:ClientLibraryFolder and the name of the node is boot-foundation.
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/practice_page_login/cq7.png)
3. Right click on clientlibs and select Properties. Add the two properties specified here:  **/etc/clientlibs/boot-foundation**
- dependencies (String[]) - cq.jquery
- categories (String[]) - summit.boot.foundation

4. On your file system, navigate to the folder where the Bootstrap JS files are located. Upload the bootstrap.min.js file to the clientlib. Also upload the CSS files. (Place the JS file in the JS folder and CSS files in the CS folder). We copy **Bracket** and using **Move** tool.
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/practice_page_login/cq8.png)
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/practice_page_login/cq9.png)
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/practice_page_login/cq10.png)

5. Add a TXT file to the clientlibs folder named js.txt. Add this content to the file.
![alt text](https://github.com/vuongluisvippro/AEM-Research/blob/practice_page_login/cq11.png)

# Create Login component using HTL

        
### Preferences 
- @link: https://helpx.adobe.com/experience-manager/htl/using/use-api-javascript.html
- @link: https://helpx.adobe.com/experience-manager/htl/user-guide.html?topic=/experience-manager/htl/morehelp/html-template-language.ug.js
- @link: https://helpx.adobe.com/experience-manager/htl/using/dev-tools.html
- @link: https://helpx.adobe.com/experience-manager/6-3/sites/developing/using/aem-brackets.html
- @link: http://brackets.io/#

### Preference Bracket
- @link: https://github.com/adobe/brackets/wiki/Brackets-Shortcuts

### Continue with link: https://helpx.adobe.com/experience-manager/using/toy_login.html
### Refer video youtube: 

