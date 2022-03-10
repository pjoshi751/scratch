# Documentation Workshop 

## Overview
This is a trial workshop session to assist us in understanding the guidelines for writing MOSIP related document.

## Types of documents

### Type 1

_the paragraph below describes Admin portal_

1. Using the Admin portal, the administrator can now retrieve an individual's lost rid or misplaced rid. Using the Admin portal, the **Admin** can now control the levels of location hierarchy they required while creating the registration centres. The level of the hierarchy can be configured through configuration property value. 
2. Using the Admin portal, the administrator can now map the users to a registration centre and to a zone.
3. Using the Admin portal, the administrator can now create and update dynamic fields such as gender, blood type, residence status, marital status, etc. 
4. Using the admin portal, the administrator can now configure the number of kiosks in a particular reg-centre during the process of creating the registration centre.

### Type 2 

Setting up Registration client

Step 1: Download TPM utility and run the to get machine keys
Please find the instructions to check out, build and run the utility here

Step 2: Whitelist the machine keys in server db
Machine name and keys output from utility should be updated in server.

use the below api to create / whitelist your machine
curl -X POST "https://<HOSTNAME>/v1/masterdata/machine

NOTE : 
-> Replace appropriate HOSTNAME in the above curl command
-> In case, we are trying to whitelist NON-TPM machine, Please set publicKey and signPublicKey with same value 

step 3: Know your userId and required roles
  Create the user in the keycloak.

Map the user to same center as that of the machine that is created/whitelisted in Step-2.

Either one of these roles must be assigned to the user in keycloak - "REGISTRATION_Supervisor, "Reg_OFFICER"
  
Step 4: Download registration client and start reg-client.
Registration client package can be downloaded from below URL, if env is setup with mosip standard deployment.
  
