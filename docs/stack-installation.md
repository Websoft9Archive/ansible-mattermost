# Initial Installation

If you have completed the Mattermost deployment on Cloud Platform, the following steps is for you to start use it quikly

## Preparation

1. Get the **Internet IP** on your Cloud Platform
2. Check you **[Inbound of Security Group Rule](https://support.websoft9.com/docs/faq/tech-instance.html)** of Cloud Console to ensure the TCP:80 is allowed
3. Make a domain resolution on your DNS Console if you want to use domain for Mattermost

## Mattermost Installation Wizard

1. Using local Chrome or Firefox to visit the URL *http://domain name* or *http://Internet IP*, you will enter the register interface of Mattermost
   ![](https://libs.websoft9.com/Websoft9/DocsPicture/en/mattermost/mattermost-install-websoft9.png)
2. Set the username and password, start to create administrator account of Mattermost
   ![](https://libs.websoft9.com/Websoft9/DocsPicture/en/mattermost/mattermost-createdaccount-websoft9.png)
3. Create a new team or Go to system console
5. Open **SITE CONFIGURATION** > **Localization** to set your language
   ![](https://libs.websoft9.com/Websoft9/DocsPicture/en/mattermost/mattermost-language-websoft9.png)
5. Quit and reload Mattermost, you can see your language is in effect

> More useful Mattermost guide, please refer to [Matterbase Administrator’s Guide](https://docs.mattermost.com/guides/administrator.html)

## Q&A

#### I can't visit the start page of Mattermost?

Your TCP:80 of Security Group Rules is not allowed so there no response from Chrome or Firefox

#### Which database does this Mattermost use?

MySQL
