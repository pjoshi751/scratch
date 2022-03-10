# Documentation workshop 

### Overview
This is a trial workshop session to assist in understanding the guidelines for writting mosip-related documents.

## Types of documents

### Type1

The paragraph below describes admin portal

Using the admin portal, the administrator can 
-> retrieve an individual's lost rid or misplaced rid.   
-> control the level of location hierarchy which can be configured through properties file, required for creating registration centres.    
-> map the users to registration centre and zone.  
-> create and update dynamic fields such as gender, blood type, residence status, marital status etc.  
-> configure number of kiosks for a particular registration centre while creating.  

### Type 2 

Setting up registration client

Step:1 Download TPM utility and run to get machine keys
Find the instructions to check out, build and run the utility.

Step:2 Whitelist the machine keys in server db
Machine names and keys output from utility should be updated in server.

use the below api to create/whitelist your machine
curl -X POST "https://<HOSTNAME>/v1/masterdata/machine

NOTE : 
-> Replace appropriate HOSTNAME in the above curl command
-> In case trying to whitelist NON-TPM machine set publickey and signpublickey with same value.

step3: Know your userId and required roles
Create the user in the keycloak.

Map the user to same center as that of the machine that is created/whitelisted in Step2.

Either one of these roles must be assigned to the user in keycloak - "REGISTRATION_SUPERVISOR, "REG_OFFICER".
  
Step-4. Download registration client and start reg-client
Registration client package can be downloaded from below URL, if env is setup with mosip standard deployment.
  
