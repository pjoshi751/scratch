# Documenatation Workshop
## Overview

This is a trial workshop session to assist us in understanding the guidelines for writing MOSIP-related document.

## Types of documents.

### Type 1 
*The paragraph below in describes Admin portal.*

Using the Admin portal, the administrator can now retrieve an individual's lost RID or misplaced RID. Using the Admin portal, the admin can now controll the levels of location hierarchy they required while creating the registration centres. The level of the hierarchy can be configured through configuration property value. Using the admin portal, the administrator can now map the users to a registration centre and to a zone Using the Admin portal, the administrator can now create and update dynamic fields such as Gender, Blood Type, Residence Status, Marital Status etc.Using the Admin portal, the administrator can now configure the number of kiosks in a particular reg centre during the process of creating the registration centre.

### Type 2
Setting up Registration client

**Step 1 :** Download TPM utility and run the to get machine keys Please find the instructions to check out, build and run the utility here.

**Step 2 :** Whitelist the machine keys in server DB machine name and keys output from utility should be updated in server.

Use the below api to create/whitelist your machine curl -X POST "https:///v1/masterdata/machine

**NOTE** : -> Replace appropriate HOSTNAME in the above curl command -> In case,we are trying to whitelist NON-TPM machine, 
Please set publicKey and signpublickey with same value.

**Step 3 :** Know your userId and required roles Create the user in the keycloak.

Map the user to same center as that of the machine that is created/whitelisted in Step-2.

Either one of these roles must be assigned to the user in keycloak - "Registration_Supervisor, "Reg_Officer".

**Step 4 :** Download Registration client and start Registration client and Registration client package can be downloaded from below URL, 
if env is setup with mosip standard deployment.
