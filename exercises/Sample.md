# Documentation Workshop 

## Overview
This is a trial workshop session to assist in understanding the guidelines for writing mosip-related documents.

## Types of documents

### Type1

Through admin portal administrator can perform below functionalities:  

* Retrieve an individual's lost RID or misplaced RID.   
* Control the level of location hierarchy which can be configured through properties file, required for creating registration centres.    
* Map the users to registration centre and zone.  
* Create and update dynamic fields such as gender, blood type, residence status, marital status etc.  
* Configure number of kiosks for a particular registration centre while creating.  

### Type 2 

Setting up registration client

Step1: Download TPM utility and run to get machine keys  
Find the instructions to check out, build and run the utility.  

Step2: Allowlist machine keys in server db  
Machine name and keys output from utility should be updated in server.  

Use the below api to create/allowlist your machine  
curl -X POST "https://HOSTNAME/v1/masterdata/machine"  

NOTE : 
-> Replace appropriate HOSTNAME in the above curl command.    
-> In case trying to whitelist NON-TPM machine set publickey and signpublickey with same value.  

Step3: Know your userId and required roles  
Create the user in the keycloak.

Map the user to same center as that of the machine that is created/allowlisted in step2.

Either one of these roles must be assigned to the user in keycloak - "REGISTRATION_SUPERVISOR, "REG_OFFICER".
  
Step4:Download and start registration client  
Registration client package can be downloaded from below URL, if env is setup with mosip standard deployment.
  
