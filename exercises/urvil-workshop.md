# Documenatation Workshop 

## Overview
This is a trial workshop session to assist us in understanding the guidelines for writing mosip - related documents.

## Types of documents

### Type 1
The points below describes the Admin Portal:
    
 1. The administrator can now retrieve an individual's lost RID or misplaced RID. 
 2. The administrator can now control the levels of location hierarchy that they require while creating the registration centres. The level of the hierarchy can be configured through configuration property value.
 3. The administrator can now map the users to a registration centre and to a zone.
 4. The administrator can now create and update dynamic fields such as gender, blood Type, residence status, marital status etc. 
 5. The administrator can now configure the number of kiosks in a particular registration centre during the process of creating it.

### Type 2 
Follow below steps to set up Registration Client: 
    
 1. Download TPM utility and run the to get machine keys. Refer the instructions to check out, build, and run the utility![here]().
 2. Whitelist the machine keys in server db. Machine name and keys output from the utility should be updated on the server.

  Use the below API to create / whitelist your machine:
    
   ```
   curl -X POST "https://<HOSTNAME>/v1/masterdata/machine
   ``` 
    
  NOTE : 
     -> Replace appropriate HOSTNAME in the above curl command.
     -> In case, we are trying to whitelist NON-TPM machine, Please set publicKey and signPublicKey with same value.

 3. Follow steps to setup keycloak for user:
    1. Create the user in the keycloak.
    2. Map the user to the same center as that of the machine that was created/whitelisted in step 2.
    3. Either one of these roles must be assigned to the user in keycloak: "REGISTRATION_SUPERVISOR","REGISTRATION_OFFICER".
    
 4. Download Registration Client and begin the Registration Client package can be downloaded from the URL below if the environment is configured with mosip standard deployment.
    
