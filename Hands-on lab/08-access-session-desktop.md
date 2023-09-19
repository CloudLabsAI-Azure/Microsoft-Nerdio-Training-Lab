# Lab 8: Access Session desktop using Browser

## Overview

Azure Virtual Desktop (AVD) integrates virtual desktop infrastructure (VDI) and the cloud. AVD is Microsoft Azure’s platform-as-a-service (PaaS) offering from Microsoft. It enables small to large cloud consumers to provide remote applications and full desktops from Microsoft Cloud to their end-users. Azure Files is also a  platform service (PaaS) and is one of the recommended solutions for hosting FSLogix containers for AVD users. In this lab, you'll be accessing the Desktop using a browser and verifying the User profiles stored in the File Share

## Exercise 1: Access the Desktop using AVD Desktop Client

In this lab, We will use a Remote Desktop client to verify Microsoft Office 365 access and we will access file share to check the implementation of FSLogix.

1. Open the following URL in a new browser tab in the JumpVM. This URL will lead us to the Remote Desktop Web Client.

   ``` 
   aka.ms/wvdarmweb 
   ``` 
   
1. Enter your **credentials** to access the workspace.

   - Username: *Paste your NMMUser 01 username* **<inject key="Nmm User 01" />** *and then click on **Next**.*
   
   ![ws name.](media/4s9.1.png)

   - Password: Paste the password of ***nmmuser01*** which you had copied earlier in **`Lab 3 -> Exercise 1 -> Step 3`** and click on **Sign in**.*

   ![ws name.](media/410.1.png)
   
   >**Note:** If there's a popup entitled **Help us protect your account** click **Skip for now (14 days until this is required)**

   ![](media/4s11.png)
   
1. In the All Resources tab, Click on the **AVD-HP-01** icon to access the session desktop.

   ![](media/ba1.png)
   
1. In the Access local resource pop-up window, Click on **Allow**.

   ![](media/ba2.png)
   
1. In Enter your Credentials pop-up window, Provide the Username and Password of NMM User 01 and click on **Submit**.

   ![](media/ba3.png)
   
1. Once logged into the session host, Search for **Word** application using the search bar. We won't be able to find the application as NMM User 01 is not part of the AVD MS Office users group.

   ![](media/ba4.png)
   
1. Sign out from the session host by clicking on the **sign out** from the top-right corner.

   ![](media/ba9.png)
   
1. Enter your **credentials** to access the workspace.

   - Username: *Paste your NMMUser 02 username* **<inject key="Nmm User 02" />** *and then click on **Next**.*
   
   ![ws name.](media/ba5.png)

   - Password: Paste the password of ***nmmuser02*** which you had copied earlier in **`Lab 3 -> Exercise 1 -> Step 6`** and click on **Sign in**.*

   ![ws name.](media/ba6.png)
   
1. In the All Resources tab, Click on the **AVD-HP-01** icon to access the session desktop.

   ![](media/ba1.png)
   
1. In the Access local resource pop-up window, Click on **Allow**.

   ![](media/ba2.png)
   
1. In Enter your Credentials pop-up window, Provide the Username and Password of NMM User 01 and click on **Submit**.

   ![](media/ba7.png)
   
1. Once logged into the session host, Search for **Word** ***(1)*** application using the search bar. We will be able to find the **Word application** ***(2)*** as NMM User 02 is part of the AVD MS Office users group. This confirms the working of the App masking rule set.

   ![](media/ba8.png)
   
1. Sign out from the session host by clicking on the **sign out** from the top-right corner.

   ![](media/ba10.png)
   
## Exercise 2: Verifying the User profiles stored in the File Share

In this exercise, We'll be verifying the user profiles stored in a file share in the Azure portal.

1. From the Azure Portal, search for *storage accounts* in the search bar and click on **Storage Accounts** from the suggestions.

   ![ws name.](media/4s17.png)
   
1. Select the **fslogix<inject key="DeploymentID" enableCopy="false" />** storage account which was created while creating the NMM account.

   ![ws name.](media/4s18.1.png)
   
1. Select **File shares** from the left side menu.

   ![ws name.](media/4s19.1.png)
   
1. Click on the **fsprofilestore** file share.

   ![ws name.](media/4s20.png)
   
1. Click on **browse (1)**, You will see the user **folder (2)** created in the file share, click on any one of the folders.

   ![ws name.](media/L8-EX2-S5.png)
   
7. Now you will be able to see the user profile data stored in the filesharers in a ***.vhd*** format.

   ![ws name.](media/L8-EX2-S6.png)
     
14. Click on the **Next** button present in the bottom-right corner of this lab guide. 
    
