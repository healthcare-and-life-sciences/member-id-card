![](/images/first_image.png)
<h1>A-HLS Member ID Card</h1>

Allows a member to generate their own Insurance Card with Policy Details

<h2>Overview</h2>

This OmniScript generates a Member ID Card that includes the member's plan details including:

* Member Name, DOB, and Member ID
* Group Number
* Plan Name
* Dependencies
* Jurisdiction, Effective and Expiration Dates
* Deductible and Out-of-Pocket Maximum
* Back of Card with with contact details

<h2>Sample Data Generated</h2>

![](/images/second_image.png)

<h2>Business Objective</h2>

Allows a member to generate their own insurance ID card with policy details.

<h3>Business Value and Benefits</h3>

* Member self-service
* Re-usable document generation Omniscript
* Leverages information from Product, Asset, Person Account, and Household Objects in Health Cloud


<h2>Industry Focus and Workflow</h2>

Primary Industry:

* Payer

Primary User Persona:

* Member

User Workflow:

* Member engages the component which presents the ID Card. 


<h2>Package Includes:</h2>

1 DataPack named MemberCardWithSampleData.json which contains the following assets:

*OmniScript (2)*

* AHLSMemberIDCard
* Re-usable Doc Gen Omniscript

*DataRaptor (6)*

* AHLSCreateAssetSample 
* AHLSCreatePersonAccount 
* AHLSGetAssetDetails 
* AHLSMakanaIDCardTransform 
* DR_ExtractDocumentTemplateByName_DCT 
* transformDocumentTemples_DCT 

Integration Procedure (1)

* AHLSLoadMemberCardSampleData

Document Template (1)

* MakanaIDCard


<h2>Configuration Requirements</h2>

<h3>Pre-Install Configuration Steps</h3>

1. Create the main font resource as described below (taken from here: https://docs.vlocity.com/en/Post-Upgrade-Steps-for-Vlocity-Lifecycle-Management-for-Insurance-Summer--22.html) 
2. ![](/images/3image.png)
3. vlocity_ins.CmPostInstallClass.preparePdfFontLibrary(false, null);

<h3>Install the Data Pack</h3>

1. The MemberCardWithSampleData.json in the following GitHub repository contains one (1) Omnistudio Data Pack. Please download the Data Pack file and save it to your desktop: https://github.com/healthcare-and-life-sciences/member-id-card
2. Then, complete the following steps to import them into your Salesforce org.
    1. To Import, in your destination Salesforce org, Click on *App Launcher* → Search for '*OmniStudio DataPacks*' and click on it.
    2. Click on '*Installed*' and on the right side click on '*Import from*'.
    3. Select '*From File*' - When the window opens, select the Data Pack file that you downloaded and stored on your machine. Click '*Install*'.
    4. After install, choose *‘Activate Now’*. This will activate all components except the Document Template. You will need to manually activate the Document Template record after this step. 
    5. The Data Pack is: MemberCardWithSampleData.json 
3. The OmniScript can now be invoked from a component of your choosing. A couple of options on how it can be invoked:
    1. Adding it to a FlexCard that is accessible to a Member (e.g., in an Experience Cloud page)
    2. Adding it to another OmniScript that a member engages with. 
    3. *NOTE:* FlexCards / LWCs that host the OmniScript are not included in this Accelerator. 

<h2>Post-Install Configuration Steps:</h2>

1. De-activate and re-activate the omniscript:
2. ![](/images/4image.png)
3. ![](/images/5image.png)


<h2>Sample Data Creation Process for Testing</h2>

The below steps outline how a user may generate sample data to preview the Member ID Card in their org. These steps are not required for the Accelerator to function.

1. Create an account to represent the insurance carrier.
    1. Go to “Accounts” and click new:
    2. ![](/images/6image.png)
    3. Choose the record type “Carrier”
    4. ![](/images/7image.png)
    5. Fill out the Account details as shown below
    6. ![](/images/8image.png)
    7. You should see this (or similar)
    8. ![](/images/9image.png)
    9. Create a basic product:
    10. Go to “Products” and click new: 
    11. ![](/images/10image.png)
    12. Perform the following steps to create a new product with this exact name: 
        HLS Medical Plan HMO 7000
    13. ![](/images/11image.png)
    14. ![](/images/12image.png)
    15. Add the “MakanaHealth” Carrier you created earlier:
    16. ![](/images/13image.png)
2. Run the integration procedure’s preview (no data is necessary, follow the steps below)
3. ![](/images/14image.png)
4. ![](/images/15image.png)
5. ![](/images/16image.png)
6. There will not be anything in the response window:
7. ![](/images/17image.png)
8. To confirm it was successful, go to Assets:
9. ![](/images/18image.png)
10. ![](/images/19image.png)
11. This confirms the objects were created:
12. ![](/images/20image.png)
13. Now click on the “J.J. Johnson” account link to get the ID
14. ![](/images/21image.png)
15. ![](/images/22image.png)
16. ![](/images/23image.png)
17. Run the omniscript with the ID from J.J. Johnson
18. ![](/images/24image.png)
19. You should see the document created like this: 
20. ![](/images/25image.png)
    1. 


<h2>Assumptions</h2>

1. The Omniscript will be invoked from another component.
2. A customer has licenses for Health Cloud and the HINS Managed Package with OmniStudio.  These solutions have all be installed and are functional.
3. A customer is assuming Salesforce Lightning Experience — not Classic.
4. Data Model elements that are part of the HINS (Vlocity) Managed package and Health Cloud are all available.
5. The Accelerator uses the Lightning Design System standards and look. Customers may want to apply their own branding which can be achieved. 


<h2>Revision History</h2>

* *Revision Short Description (Month Day, Year)*

    * Initial release

