# Lab 4: How to create custom domains for your websites

## Overview

A custom domain is a unique branded label that's connected to the IP address of a website. To visit a particular site, you can type its custom domain name into the address bar of your browser. In this lab, you'll be creating a custom domain of an App Service through the Azure portal.

## Exercise 1: Create Custom Domain **(Read Only)**

>**NOTE**: This is a **Read-Only** exercise, do not perform these steps. Please go through the lab guide to understand the implementation of adding custom domains.

1. On the **Azure portal** search for **Resource groups** in the search bar ***(1)*** and select **Resource groups** ***(2)*** from the suggestions.

   ![](media/c5.png)
   
1. Select **NMM-RESOURCES-RG** from the list of resource groups which is a dynamic RG created during the creation of NMM.

   ![](media/ss1.png)
   
1. Select the App service from the name, **web-admin-portal-[unique ID]** from the list of resources.

   ![](media/ss2.png)
   
1. From the left-hand side blade under **Settings** ***(1)***, Click on **Custom domains** ***(2)***. 

   ![](media/6s1.png)
   
1. Copy the app service's default domain.

   ![](media/6s3.png)

1. Create a new *CNAME* record in your domain's public DNS zone for the custom domain you want to add. (For example, nmm.mydomain.com). This CNAME record should point to the existing app's URL with the following configurations:

   - Record Type: **CNAME**
   - Name: **nmm.mydomain.com**
   - Value: the app service default URL
   - TTL: **1800** (or your preferred default)
   

1. Click on **Add custom domains** ***(1)***. Under **Add custom domains**, Provide **nmm-amol-demo.nerdio.net** ***(2)*** for custom domain option and click on **Validate** ***(3)***.
   
   ![](media/6s2.png)
   
1. After validation succeeds, click the **Add custom domain** button to finish adding the domain.
   
   ![](media/6s4.png)
   
1. To ensure traffic to the new domain is secure, click **Add binding** under SSL binding.
   
   ![](media/c34.png)
   
1. Click **Upload PFX Certificate** to provide the export of your certificate file.

   ![](media/6s6.png)
   
1. You may also purchase an SSL certificate through Azure, by navigating to the App Service's TLS/SSL Settings.

   ![](media/6s7.png)
   
1. Once the certificate is uploaded, associate the new domain to the certificate and click the **Add Binding** button.

   ![](media/6s8.png)
   
1. Now navigate to Azure Active Directory, Select **App Registrations**, and find the web admin portal application.  If your Web Admin Portal application is not shown, ensure "All Applications" is clicked.  This screen may default to **Owned Applications**.

1. In the menu on the left, select the **Authentication** tab. Under Redirect URIs, do not remove the original URL but do add URIs for your custom domain. Click the "Save" option.

   >**NOTE**: if you do not see the Redirect URIs section, click "Add a platform" and select "Web." Then add the necessary Redirect URIs.

1. Click on Configuration, then Application Settings.

   ![](media/6s10.png)
   
1. Find the setting for Deployment: WebAppUrl and change it to your custom domain (without the trailing slash). Click on **OK**.

   ![](media/6s11.png)
   
1. Verify that your custom domain for NMM works by navigating to `https://nmm.mydomain.com`.

1. Click on the **Next** button present in the bottom-right corner of this lab guide.




