# Documentation Workshop 

## Overview
The goal of this workshop session is to assist in understanding the guidelines for writing MOSIP related documentation.

## Types of documents

### Type1

New functionalities added in Admin Portal:
* Using the Admin Portal, the administrator can now retrieve a resident's lost RID or misplaced RID. 
* Using the Admin Portal, the administrator can now control the levels of location hierarchy that are required while creating the registration centres. Each level of the location hierarchy can be configured as well.
* Using the Admin Portal, the administrator can now map the user to a registration centre and to a zone.
* Using the Admin Portal, the administrator can now create and update dynamic fields like gender, blood type, residence status, marital status etc.
* Using the Admin Portal, the administrator can now configure the number of kiosks while creating a registration centre.

### Type 2 

Steps for setting up Registration Client:

* Step 1: Download TPM utility and run it the to get machine keys. Please find the instructions to check out, build and run the utility [here]().

* Step 2: Whitelist the machine keys in server db. 

    Machine name and keys output from TPM utility should be updated in server. Use the below api to create / whitelist your machine. 
   ```curl -X POST "https://<HOSTNAME>/v1/masterdata/machine ```
    
    **Points to note: 
    * Replace appropriate ```HOSTNAME``` in the above ```curl``` command
    * To whitelist non TPM machine, set ```publicKey``` and ```signPublicKey``` with same value 

* Step 3: Know your user id and required roles. 
    * Create the user in the Keycloak.     
    * Map the user to same center as that of the machine that is created/whitelisted in Step 2.
    * One of these roles must be assigned to the user in Keycloak - REGISTRATION_SUPERVISOR or REGISTRATION_OFFICER.

* Step 4: Download Rregistration Client on the regisered machine and run it. You can now use above user Id to login into it.